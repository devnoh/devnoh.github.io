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