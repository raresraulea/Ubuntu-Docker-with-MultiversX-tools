CONTAINER_NAME=ubuntu-container
IMAGE_NAME=ubuntu-image

.PHONY: clean
clean:
	docker rmi $(IMAGE_NAME) --force || true
	docker stop ${CONTAINER_NAME} || true
	docker rm ${CONTAINER_NAME} || true

.PHONY: prune
prune:
	docker system prune --all --force --volumes

.PHONY: build-image
build-image:
	docker build -t $(IMAGE_NAME) .

.PHONY: run-container
run-container:
	docker run -d -v /var/run/docker.sock:/var/run/docker.sock --name $(CONTAINER_NAME) $(IMAGE_NAME) 
	

.PHONY: enter-ubuntu
enter-ubuntu:
	docker exec -it $(CONTAINER_NAME) /bin/sh
	
.PHONY: setup-ubuntu
setup-ubuntu:
	make build-image
	make run-container	

PHONY: mxpy-ubuntu
mxpy-ubuntu:
	make clean
	make setup-ubuntu
	make enter-ubuntu
