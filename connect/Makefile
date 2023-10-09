SHELL := /bin/bash
.PHONY: build-apk

IMAGE="debezium-with-confluent"
RAND := $(shell /bin/bash -c "echo $$RANDOM")
TAG="2.4.0-${RAND}"

build-docker-web-dev:
	docker build -t ${IMAGE} . --progress=plain

build-and-push-docker-image:
	docker build -t jojoooo1/${IMAGE}:${TAG} . --progress=plain
	docker push jojoooo1/${IMAGE}:${TAG}