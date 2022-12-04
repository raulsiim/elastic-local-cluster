# Fun fact


# Overview
Predominantly the intention behind this repository was hassle free and fast spawning of ELK stack in local environment.

# Managing the service
## Starting the services
```bash
$ docker-compose -f cluster01.yml -p cluster01 up -d
$ docker-compose -f cluster02.yml -p cluster02 up -d
$ docker-compose -f logstash.yml -p logstash up -d
```

## Stopping the services
Depending on what was started, to stop services:
```bash
$ docker-compose -f cluster02.yml -p cluster02 down
$ docker-compose -f logstash.yml -p logstash down
$ docker-compose -f cluster01.yml -p cluster01 down
```