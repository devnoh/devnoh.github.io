# DOCKER

## CLI

```
$ docker images
$ docker ps
$ docker search ${image}
$ docker run —name ${container} -P -d ${image}
```

```
$ docker start ${container}
$ docker stop ${container}
```

```
$ docker rm ${container}
$ docker rm $(docker ps -aq)
$ docker rmi ${image}

### Remove all stopped containers
```
$ docker rm $(docker ps -a -q)
```

### Remove all untagged images
```
$ docker rmi $(docker images | grep "^<none>" | awk "{print $3}")
```

## Docker Run
$ docker run [OPTIONS] IMAGE[:TAG|@DIGEST] [COMMAND] [ARG...]

### nginx
```
$ docker run --name mynginx1 -P -d nginx
```

### jenkins
```
$ docker run --name myjenkins -p 8080:8080 -v /var/jenkins_home jenkins
```

### mongo
```
$ docker run -p 27017:27017 -v /data/db:/data/db mongo
$ docker run -d -p 27017:27017 -v /data/db:/data/db —name mymongo mongo
$ docker run -it -p 27017:27017 -v /data/db:/data/db --name mymongo mongo
```

### tomcat
```
$ docker run -it --rm -p 8888:8080 --name mytomcat tomcat
```

### redis
```
$ docker run -it redis
$ docker run -d --name myredis redis
$ docker run -it -p 6379:6379 --name myredis redis
```

### ActiveMQ
```
$ docker run -t -p 61616:61616 -p 8161:8161 webcenter/activemq
```

### MySQL
```
$ docker run -p 3306:3306 -e MYSQL_ROOT_PASSWORD=secret -d mysql:5.6
```

## Docker Compose

```
$ docker-compose up --build
$ docker-compose down (or docker-compose stop)
```
## Docker Machine

### Create
```
$ docker-machine create --driver virtualbox --virtualbox-memory 4000 default
```

### List
```
$ docker-machine ls
```

### Get the environment
```
$ docker-machine env default
```

### Connect the shell(terminal) to the new machine
```
$ eval "$(docker-machine env default)"
```

### Start / Stop
```
$ docker-machine stop default
$ docker-machine start default
```

### Remove
```
$ docker-machine rm default
```
