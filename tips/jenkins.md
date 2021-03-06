# JENKINS

## Amazon Linux

### Install

```
$ sudo wget -O /etc/yum.repos.d/jenkins.repo http://pkg.jenkins-ci.org/redhat/jenkins.repo
$ sudo rpm --import http://pkg.jenkins-ci.org/redhat/jenkins-ci.org.key
$ sudo yum install jenkins
```

### Configuration 
```
$ sudo vi /etc/sysconfig/jenkins
---
JENKINS_HOME="/home/jenkins"
...
JENKINS_PORT="13000"
---
```

### Start & Stop

```
$ sudo chkconfig --add jenkins
$ sudo chkconfig --list

$ sudo service jenkins start
Starting Jenkins                                       [  OK  ]

$ sudo service jenkins stop
Shutting down Jenkins                                  [  OK  ]
```

## Mac OS

### Install

```
$ brew install jenkins
```

### Start
```
$ jenkins
```

### Start as Service
```
$ brew services start jenkins
````

## Docker

```
$ docker run -p 8080:8080 -p 50000:50000 jenkins/jenkins:lts
```
or
```
$ docker run -d -v jenkins_home:/var/jenkins_home -p 8080:8080 -p 50000:50000 --name jenkins jenkins/jenkins:lts
```

Go to http://localhost:8080/

To get admin password:
```
$ docker exec -it jenkins cat /var/jenkins_home/secrets/initialAdminPassword
```
