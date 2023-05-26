# MxPy-Ubuntu-Docker-Scripts

🐳 A Docker Image based on Ubuntu@22.04 with python3, mxpy, and optionally Docker Engine installed. 🚀

📜 Scripts for making container interaction as user-friendly as possible. ✨

## Overview

🔍 The repository can be helpful for testing and local development in an Ubuntu Container with the MultiversX tools.

👉 It provides a starting point for developing a stable production-ready Docker image with the MultiversX tools installed. It aims to mimic a web server's production environment and includes essential packages and scripts to facilitate container management.

## Purpose

The primary purposes of this repository are:

1. Mimic a web server's production environment (a Linux web server with Python and MxPy installed - and Docker Engine optionally).
2. Provide a starting point for developing a stable production-ready image with the MultiversX tools installed for Docker production environments.

## Contents

The repository consists of the following directories:

- `ubuntu-mxpy`: Contains the Dockerfile for building an Ubuntu image with Python and MxPy installed.
- `ubuntu-mxpy-docker-in-docker`: Contains everything from `ubuntu-mxpy` and additionally installs Docker inside Docker.

Each of the mentioned directories contains the following files:

- `Makefile`: Contains basic scripts for interacting with the Docker image and container (same one for both directories).
- `Dockerfile`: Describes a Docker image based on the Linux Ubuntu@22.04 distribution with its necessary dependencies.

## Getting Started

To set up the MultiversX Docker-Ubuntu-MxPy Environment, follow these steps:

1. Clone the repository:

   ```shell
   git clone https://github.com/raresraulea/MxPy-Ubuntu-Docker-Scripts.git
   ```

2. Navigate to the cloned repository:

   ```shell
   cd <repository_directory>/<version_you_need>
   ```

3. Build and run the Docker container:

   ```shell
   make mxpy-ubuntu
   ```

   This command will execute a series of scripts defined in the Makefile to clean any existing containers or images, build the Docker image, run the Docker container, and enter the Ubuntu environment within the container.

🎉 Congratulations! You now have the MultiversX Docker Production Environment set up on your system. You can start working with the environment and utilize the MultiversX tools for web development and blockchain-based platform development.

Enjoy coding and building amazing applications with MultiversX! 🚀




# More Details

## Included Packages

The Docker image built from this repository includes the following packages:

- Python3
- Python3 Venv
- MxPy (MultiversX's Python CLI)
- cron
- vim
- libncurses5
- apt
- software-properties-common
- wget

These packages are pre-installed in the Docker image to provide a comprehensive environment for web server development and production setups.

## Scripts

### mxpy-ubuntu

For a complete setup of the Ubuntu environment, including cleaning up previous resources, setting up the environment, and entering the Ubuntu container, execute the following command:

```bash
make mxpy-ubuntu
```

This command will perform the necessary steps sequentially to prepare and enter the Ubuntu container.

### Setting up the Ubuntu Environment

To set up the Ubuntu environment, including building the image and running the container, run the following command:

```bash
make setup-ubuntu
```

This command will build the Docker image and start the Docker container.

### Building the Image

To build the Docker image, run the following command:

```bash
make build-image
```

This command will build the Docker image based on the provided Dockerfile.

### Running the Container

To run the Docker container, execute the following command:

```

bash
make run-container
```

This command will start the Docker container.

### Entering the Ubuntu Container

To enter the running Ubuntu container, run the following command:

```bash
make enter-ubuntu
```

This command will open an interactive shell session within the running container.

### Cleaning

To clean up the Docker environment and remove the container and image, run the following command:

```bash
make clean
```

This command will force-remove the Docker image and container.

### Pruning

To perform a Docker system prune and remove all unused images, containers, networks, and volumes, run the following command:

```bash
make prune
```

This command will clean up and free up disk space by removing unused Docker resources.

Note: Make sure you have fulfilled the prerequisites mentioned in the [Prerequisites](#prerequisites) section before proceeding with the setup.

## Contributing

Contributions to this repository are welcome. To contribute, please follow the guidelines outlined in the CONTRIBUTING.md file.

## License

This repository is licensed under the MIT License. See the LICENSE file for more information.
