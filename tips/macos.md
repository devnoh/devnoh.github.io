# MACOS

### ~/.profile

```
# PATH
PATH=$PATH:/usr/local/ant/bin
PATH=$PATH:/usr/local/maven/bin
PATH=$PATH:/usr/local/gradle/bin
PATH=$PATH:/usr/local/mysql/bin
PATH=$PATH:/usr/local/mongodb/bin
PATH=$PATH:/usr/local/activemq/bin
PATH=$PATH:/usr/local/kafka/bin
PATH=$PATH:/usr/local/hadoop/bin:/usr/local/hadoop/sbin:/usr/local/hadoop/lib/native
PATH=$PATH:/usr/local/spark/bin::/usr/local/spark/sbin
PATH=$PATH:/usr/local/elasticsearch/bin
PATH=$PATH:/usr/local/kibana/bin
PATH=$PATH:/usr/local/logstash/bin
export PATH

# Go
export GOROOT=/usr/local/opt/go/libexec
export GOPATH=$HOME/.go
export PATH=$PATH:$GOROOT/bin:$GOPATH/bin

# Spark
export SPARK_HOME="/usr/local/spark"

# Kafka
export KAFKA_HOME="/usr/local/kafka"
alias zkstart='$KAFKA_HOME/bin/zookeeper-server-start.sh $KAFKA_HOME/config/zookeeper.properties'
alias kfstart='$KAFKA_HOME/bin/kafka-server-start.sh $KAFKA_HOME/config/server.properties'

# Alias
alias ll='ls -al'
alias git-devnoh='git config user.name "Sehwan Noh";git config user.email "devnoh@gmail.com"'
alias git-mirror='git fetch -p origin; git push --mirror'
#ij /path/to/project/pom.xml
alias "ij=open -b com.jetbrains.intellij"
```

### Install Homebrew

```
$ ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

### Common Dev Tools

```
$ brew install maven
$ brew install gradle
$ brew install kotlin
$ brew install scala
$ brew install python
$ brew install go
$ brew install node
    $ brew install node@8
    $ brew link node@8
$ brew install httpie
$ brew install mongodb
$ brew install mysql
$ brew install apache-activemq
$ brew install rabbitmq
$ brew install redis
$ brew install elasticsearch
