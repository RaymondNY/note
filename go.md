#### go安装

`rm -rf /usr/local/go && tar -C /usr/local -xzf go1.17.linux-amd64.tar.gz`

`vim /etc/profile`

`export GOROOT=/home/zqx/languages/go
export GOPATH=/home/zqx/languages/gopath
export PATH=$PATH:$GOROOT/bin:$GOPATH/bin
export GOPROXY=https://goproxy.io,direct
export GO111MODULE="on"`

`source /etc/profile`

#### 初始化项目

`go mod init zqx.com/goutil `

#### 异常处理

https://learnku.com/articles/52781

