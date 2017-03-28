# REDIS

### Install:

$ brew install redis

### Start Redis as a Service

$ brew services restart redis

### Start Server:

$ redis-server

### Client:

$ redis-cli
$ redis-cli ping
$ redis-cli -h {hostname}

### Docker:

$ docker run -d --name myredis redis

$ docker run -it --name myredis redis

$ docker run -it --link myredis:redis --rm redis redis-cli -h redis -p 6379
