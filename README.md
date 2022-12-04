![alt text](https://media-exp1.licdn.com/dms/image/C5112AQGjI7yIwlNiTQ/article-cover_image-shrink_423_752/0/1551025352498?e=1675900800&v=beta&t=4POcQ-bEO60Wuo76MMfA_YRb3pbd5dQGsZGbD5Vd9Mo)


# Fun fact
The predecessor of ElasticSearch was called Compass. It was first released on 2004 and replaced with ElasticSearch on 2010.

# Overview
The intention behind this repository was to be able to spawn ELK local testing environment fast and without any extra hassle.

# Prerequsites
Local computer must have Docker and Docker Compose installed.

## Verify Docker installation
Open a terminal and run commands:
```
$ docker --version
$ docker-compose --version
```

The output should look similar to this:
```
$ docker --version
Docker version 20.10.21, build baeda1f

$ docker-compose --version
docker-compose version 1.29.2, build unknown
```

## Windows installation instructions
Official documentation on how to install Docker on Windows OS can be found [here](https://docs.docker.com/desktop/install/windows-install/)
An excellent and easy to follow guide can be found also [here](https://www.simplilearn.com/tutorials/docker-tutorial/install-docker-on-windows)

## MacOS installation guide
Official documentation how to install Docker in MacOS can be found [here](https://docs.docker.com/desktop/install/mac-install/).
An excellent and easy to follow guide can be found also [here](https://runnable.com/docker/install-docker-on-macos)

## Linux
You are an advanced user, a king, a queen of computers, if you will. Surely you don't need a step-by-step guide to tell you how to install stuff :) 

# Managing the service
## Starting the services
```sh
$ docker-compose -f cluster01.yml -p cluster01 up -d
$ docker-compose -f cluster02.yml -p cluster02 up -d
$ docker-compose -f logstash.yml -p logstash up -d
```

## Stopping the services
Depending on what was started, to stop services:
```sh
$ docker-compose -f cluster02.yml -p cluster02 down
$ docker-compose -f logstash.yml -p logstash down
$ docker-compose -f cluster01.yml -p cluster01 down
```