# GO

### Inatall Go with Brew

$ brew install go

### Setup Path for Go

$ vi ~/.profile
~~~
export GOROOT=/usr/local/opt/go/libexec
export GOPATH=$HOME/.go
export PATH=$PATH:$GOROOT/bin:$GOPATH/bin
~~~

### Dependency Management Tool for Go
~~~
$ brew install dep
$ brew upgrade dep
~~~


### Go Get

```
 go get -u all
 go get -u github.vianttech.com/adelphic/adelphic-go/models
 ```