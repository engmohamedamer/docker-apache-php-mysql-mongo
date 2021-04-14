#  Apps Web server (docker-apache-php-mysql-mongo) built with Docker Compose

This is a basic Web server environment for running multiple projects built using Docker Compose. It consists following:

* PHP 7.3
* Apache 2.4
* MySQL 5.7
* MongoDB

## Installation

Clone this repository on your local computer then Run the `docker-compose up --build` for the first time to build the docker machine.

```shell
git clone https://github.com/engmohamedamer/docker-apache-php-mysql-mongo.git
cd docker-apache-php-mysql-mongo/
docker-compose up --build
```

Your Web server is now ready!! You can access start developing your projects
 `http://localhost`.
 `http://project1.localhost`.
 `http://project2.localhost`.

## Web Server

Apache is configured to run on port 80. So, you can access it via `http://project1.localhost`.

#### Apache Modules

By default necessary modules are enabled.

> If you want to enable more modules, just update `./bin/webserver/Dockerfile`. your Pull Request is Welcome.
> You have to rebuild the docker image by running `docker-compose --build` and restart the docker containers.

#### Connect via SSH

You can connect to web server using `docker exec` command to perform various operation on it. Use below command to login to container via ssh.

```shelli
docker exec -it apps-webserver  /bin/bash
```


## PHP

The installed version of PHP is 7.3

#### Extensions

By default following extensions are installed.

* mysqli
* mbstring
* zip
* intl
* mcrypt
* curl
* json
* iconv
* xml
* xmlrpc
* gd
* sass

> If you want to install more extension, just update `./bin/webserver/Dockerfile`.
> You have to rebuild the docker image by running `docker-compose --build` and restart the docker containers.

# Manage Containers 
```shelli
docker ps -a                      # List all containers
docker stop $( docker ps -a -q)   #stop all conainers
docker rm $( docker ps -a -q)     #delete all containers

sudo docker-compose start       # start container
sudo docker-compose stop        # stop container   
```
