FROM ubuntu:22.04

# Install packages
RUN apt-get update && apt-get install -y \
    cron \
    vim \
    libncurses5 \
    apt \
    software-properties-common \
    wget \
    python3.10-venv \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg \
    lsb-release \
    sudo

# Download docker installation script
RUN curl -fsSL https://get.docker.com -o get-docker.sh 

# Run docker installation script
RUN sh get-docker.sh 

# Get the mxpy-up script as recommended in the docs
RUN wget -O mxpy-up.py https://raw.githubusercontent.com/multiversx/mx-sdk-py-cli/main/mxpy-up.py 

# Add users as imposed by the installation script to not run as root
RUN useradd -m -s /bin/bash ubuntu 

# Switch user
USER ubuntu 

# Run script with yes response
RUN yes | python3 mxpy-up.py

WORKDIR /home/ubuntu

# Modify .profile and .bashrc to include ~/multiversx-sdk in $PATH
RUN echo 'export PATH="$HOME/multiversx-sdk:$PATH"' >> ~/.profile
RUN echo 'export PATH="$HOME/multiversx-sdk:$PATH"' >> ~/.bashrc

# Add the mvx-sdk to $PATH
ENV PATH="/home/ubuntu/multiversx-sdk:$PATH"

# Switch back to root
USER root

# Set the default command to keep the container running
CMD ["tail", "-f", "/dev/null"]
