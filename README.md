# deploy-kafka-with-docker

Sample repository to deploy kafka with Confluent Platform using docker-compose

## Deploy with docker-compose

```bash
$ docker-compose \
  --file cp-all-in-one/cp-all-in-one/docker-compose.yml \
  --file docker-compose.override.yml \
  up -d
```

Confirm target services are start up.

```bash
$ docker-compose \
  --file cp-all-in-one/cp-all-in-one/docker-compose.yml \
  --file docker-compose.override.yml \
  ps
```

Stop kafka services.

```bash
$ docker container stop $(docker container ls -a -q -f "label=io.confluent.docker")
```

Then, deletes containers, networks, volumes, and images if needed.

```bash
$ docker system prune -a -f --volumes
```

## Reference

* https://docs.confluent.io/current/quickstart/ce-docker-quickstart.html
