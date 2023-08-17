SHELL := /bin/bash
.PHONY: build-apk

IMAGE="debezium-base-with-confluent"
RAND := $(shell /bin/bash -c "echo $$RANDOM")
TAG="2.3.2-${RAND}"

build-and-push-docker-image:
	docker build -t jojoooo1/${IMAGE}:${TAG} . --progress=plain
	docker push jojoooo1/${IMAGE}:${TAG}