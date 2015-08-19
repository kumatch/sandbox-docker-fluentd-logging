sandbox-docker-fluentd-logging
======

## Fluentd logging server container

```
$ docker build -t sandbox-fluentd ./fluentd
$ docker run --name logger -d sandbox-fluentd
```

## log container (nginx)

```
$ docker build -t sandbox-nginx ./nginx
$ docker run --name web1 -p 80:80 -d sandbox-nginx
```

## and logging

```
$ docker logs -f logger
```
