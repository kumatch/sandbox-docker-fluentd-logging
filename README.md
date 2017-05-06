sandbox-docker-fluentd-logging
======

(Sandbox)


## Usage

### Creates Fluentd logging server container

```
$ docker build -t sandbox-fluentd ./fluentd
$ docker run --name logger -d sandbox-fluentd
```

### Creates log send container (ex. Nginx)

```
$ docker build -t sandbox-nginx ./nginx
$ docker run -d --name web1 -p 80:80 --log-driver=fluentd --log-opt fluentd-address=localhost:24224 --log-opt fluentd-tag=docker.{{.FullID}} sandbox-nginx
```

### See logs

displays nginx access logs.

```
$ docker logs -f logger
```
