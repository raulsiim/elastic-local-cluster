![alt text](https://media-exp1.licdn.com/dms/image/C5112AQGjI7yIwlNiTQ/article-cover_image-shrink_423_752/0/1551025352498?e=1675900800&v=beta&t=4POcQ-bEO60Wuo76MMfA_YRb3pbd5dQGsZGbD5Vd9Mo)


# Fun fact
The predecessor of ElasticSearch was called Compass. It was first released on 2004 and replaced by ElasticSearch on 2010.


# Using this repository
The intention behind this repository was to be able to spawn ELK local testing environment fast and without any extra hassle.
This repository contains configuration to test ELK clusters on __Docker__

To start using `docker-compose` configuration provided by this repository, it is recommended to clone (`git clone https://github.com/raulsiim/elastic-local-cluster.git`) the repository to a local computer or download the contents of this repo by other means.
Docker compose configuration is using `logstash` sub-folders, thus the folder (including sub-folders) must be present in the root folder where docker-compose files are copied.

## Installing prerequsites
Local computer must have Docker and Docker Compose installed.

### Verifying Docker installation
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

### Windows installation instructions
Official documentation on how to install Docker on Windows OS can be found [here](https://docs.docker.com/desktop/install/windows-install/).
An excellent and easy to follow guide can also be found [here](https://www.simplilearn.com/tutorials/docker-tutorial/install-docker-on-windows).

__Important!!!__ It is necessary to set `vm.max_map_count=262144` value before running docker-compose. Otherwise ElasticSearch won't start! More information can be found [here](https://www.elastic.co/guide/en/elasticsearch/reference/current/docker.html#_windows_with_docker_desktop_wsl_2_backend).

### MacOS installation guide
Official documentation how to install Docker in MacOS can be found [here](https://docs.docker.com/desktop/install/mac-install/).
An excellent and easy to follow guide can be found also [here](https://runnable.com/docker/install-docker-on-macos).

__Important!!!__ It is necessary to set `vm.max_map_count=262144` value before running docker-compose. Otherwise ElasticSearch won't start! More information can be found [here](https://www.elastic.co/guide/en/elasticsearch/reference/current/docker.html#_macos_with_docker_for_mac).

### Linux
You are an advanced user, a king, a queen of computers, if you will. Surely you don't need a step-by-step guide to tell you how to install stuff :smirk:

__An important hint!!!__: It is necessary to set `vm.max_map_count=262144` value. Otherwise ElasticSearch won't start! The issue is described in more details [here](https://www.elastic.co/guide/en/elasticsearch/reference/current/docker.html#_linux).

# Managing the services
For things to run smoodly it is required to start `cluster01` first. `cluster01.yml` has configuration to start the network named `cluster01_default` and other containers connect to that network.

## Starting the services
```
$ docker-compose -f cluster01.yml -p cluster01 up -d
$ docker-compose -f cluster02.yml -p cluster02 up -d
$ docker-compose -f logstash.yml -p logstash up -d
```

## Stopping the services
Depending on what was started, to stop services:
```
$ docker-compose -f cluster02.yml -p cluster02 down
$ docker-compose -f logstash.yml -p logstash down
$ docker-compose -f cluster01.yml -p cluster01 down
```
# Accessing Kibana
Hopefully everything started up and Kibana is responding on the address: `localhost:5601`. 

__Username is: elastic__
__Password is: elastic__

Username and password can be changed in the `.env` file