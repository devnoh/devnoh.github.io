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

# Spark
export SPARK_HOME="/usr/local/spark"

# Go
export GOROOT=/usr/local/opt/go/libexec
export GOPATH=$HOME/.go
export PATH=$PATH:$GOROOT/bin:$GOPATH/bin

# Alias
alias ll='ls -al'
alias git-devnoh='git config user.name "Sehwan Noh";git config user.email "devnoh@gmail.com"'
alias git-mirror='git fetch -p origin; git push --mirror'
```

### Install Homebrew

```
$ ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
