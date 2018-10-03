# RANCHER

https://gist.github.com/lmmendes/fbed32a452cf02d2a1095658795cb3d2

## Launching Management Server

$ sudo docker run -d --restart=unless-stopped -p 9090:8080 rancher/server
c9e09a7a9d4d9e6bb07349f0a273dc5b0a2dfaa7a125907ecb652bee535409ae

### Start monitoring the Rancher Server logs

$ docker logs c9e09a7a9d4d9e6bb07349f0a273dc5b0a2dfaa7a125907ecb652bee535409ae

### Connection to the Rancher Server

Connect to http://localhost:8080

## Adding hosts

### Get local machine IP

$ sudo ipconfig getifaddr en0
10.100.100.85

### Launching the hosts

$ docker-machine create -d virtualbox --virtualbox-boot2docker-url https://releases.rancher.com/os/latest/rancheros.iso rancher01
$ docker-machine create -d virtualbox --virtualbox-boot2docker-url https://releases.rancher.com/os/latest/rancheros.iso rancher02

or

$ docker-machine create -d virtualbox rancher01
$ docker-machine create -d virtualbox rancher02

### Rancher web interface: Add Host

* Management Web Console: Infrastructure -> Hosts -> Add Host

* Copy the agent code snippet (modified IP) and run the command on each host

```
$ sudo docker run --rm --privileged -v /var/run/docker.sock:/var/run/docker.sock -v /var/lib/rancher:/var/lib/rancher rancher/agent:v1.2.11 http://10.100.100.85:8080/v1/scripts/F1B33E88D4EAE2FAD67A:1514678400000:zFiNSEUJVre5jJyR6dP97Tblt5M
```

### Running Rancher Agent in the new Hosts

$ docker-machine ssh rancher01

docker@rancher01:~$ sudo docker run --rm --privileged -v /var/run/docker.sock:/var/run/docker.sock -v /var/lib/rancher:/var/lib/rancher rancher/agent:v1.2.11 http://10.100.100.85:8080/v1/scripts/F1B33E88D4EAE2FAD67A:1514678400000:zFiNSEUJVre5jJyR6dP97Tblt5M
Unable to find image 'rancher/agent:v1.2.11' locally
v1.2.11: Pulling from rancher/agent
b3e1c725a85f: Pull complete 
6a710864a9fc: Pull complete 
d0ac3b234321: Pull complete 
87f567b5cf58: Pull complete 
063e24b217c4: Pull complete 
d0a3f58caef0: Pull complete 
16914729cfd3: Pull complete 
bbad862633b9: Pull complete 
3cf9849d7f3c: Pull complete 
Digest: sha256:0fba3fb10108f7821596dc5ad4bfa30e93426d034cd3471f6ccd3afb5f87a963
Status: Downloaded newer image for rancher/agent:v1.2.11

INFO: Running Agent Registration Process, CATTLE_URL=http://10.100.100.85:8080/v1
INFO: Attempting to connect to: http://10.100.100.85:8080/v1
INFO: http://10.100.100.85:8080/v1 is accessible
INFO: Configured Host Registration URL info: CATTLE_URL=http://10.100.100.85:8080/v1 ENV_URL=http://10.100.100.85:8080/v1
INFO: Inspecting host capabilities
INFO: Boot2Docker: true
INFO: Host writable: false
INFO: Token: xxxxxxxx
INFO: Running registration
INFO: Printing Environment
INFO: ENV: CATTLE_ACCESS_KEY=08193E5C6CA0B862677C
INFO: ENV: CATTLE_HOME=/var/lib/cattle
INFO: ENV: CATTLE_REGISTRATION_ACCESS_KEY=registrationToken
INFO: ENV: CATTLE_REGISTRATION_SECRET_KEY=xxxxxxx
INFO: ENV: CATTLE_SECRET_KEY=xxxxxxx
INFO: ENV: CATTLE_URL=http://10.100.100.85:8080/v1
INFO: ENV: DETECTED_CATTLE_AGENT_IP=172.17.0.1
INFO: ENV: RANCHER_AGENT_IMAGE=rancher/agent:v1.2.11
INFO: Launched Rancher Agent: 547f5987466c81204dac6fc6a38ad462c3e4c72625a1ba6860aaf8fde1efec50

$ docker-machine ssh rancher02

docker@rancher02:~$ sudo docker run --rm --privileged -v /var/run/docker.sock:/var/run/docker.sock -v /var/lib/rancher:/var/lib/rancher rancher/agent:v1.2.11 http://10.100.100.85:8080/v1/scripts/F1B33E88D4EAE2FAD67A:1514678400000:zFiNSEUJVre5jJyR6dP97Tblt5M
(...)
