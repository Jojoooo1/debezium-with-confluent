# Debezium

[Debezium](https://debezium.io/) stopped to include confluent [schema-registry](https://docs.confluent.io/platform/7.0/schema-registry/) dependencies since version 2.X.
This is why we need to inject it inside the [connect-base](https://hub.docker.com/r/debezium/connect-base) image. This image is only compatible with the confluent schema registry version 7.0.4.

## Debezium connect-base

To upgrade the [connect-base](https://hub.docker.com/r/debezium/connect-base) image, update the `FROM` condition with the latest release, update the `TAG=` var inside the Makefile accordingly and run:

```bash
make build-and-push-docker-image
```

## Debezium connect

To upgrade the [connect](https://hub.docker.com/r/debezium/connect) image, update the `FROM` condition with the latest debezium connect-base image you just created, update the `Dockerfile` with the latest value from [connect](https://github.com/Intelipoint/debezium-connect/blob/main/base/Dockerfile) Dockerfile, update the `TAG=` var inside the Makefile accordingly and run:

```bash
make build-and-push-docker-image
```
