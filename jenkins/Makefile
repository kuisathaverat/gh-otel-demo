PROJECT_NAME := jenkins
VERSION := lts-otel
DOCKER_IMAGE ?= https://ghcr.io/kuisathaverat/gh-otel-demo/$(PROJECT_NAME):$(VERSION)
DOCKER_OPTS ?=

## @help:docker-build:build Build docker image
.PHONY: docker-build
docker-build:
	@echo "Building docker image $(DOCKER_IMAGE)"
	@docker build -t $(DOCKER_IMAGE) $(DOCKER_OPTS) .

## @help:docker-push:push Push docker image
.PHONY: docker-push
docker-push:
	@echo "Pushing docker image $(DOCKER_IMAGE)"
	@docker push $(DOCKER_IMAGE)

## @help:docker-clean:clean Clean docker image
.PHONY: docker-clean
docker-clean:
	@echo "Cleaning docker image $(DOCKER_IMAGE)"
	@docker rmi $(DOCKER_IMAGE)

## @help:docker-run:run Run docker image
.PHONY: docker-run
docker-run:
	@echo "Running docker image $(DOCKER_IMAGE)"
	@docker run --rm -it $(DOCKER_IMAGE)
