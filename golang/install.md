# GoLang安装

创建go安装目录
```bash
  mkdir /usr/local/go
  cd /usr/local/go
```

下载安装包
```bash
  wget https://dl.google.com/go/go1.13.12.linux-amd64.tar.gz
  # 其他版本: https://golang.org/dl/
```

解压
```bash
  tar -zxvf go1.13.12.linux-amd64.tar.gz
  mv go go1.13.12
```

创建软链
```bash
  ln -s /usr/local/go/go1.13.12/bin/go /usr/local/bin/go
  ln -s /usr/local/go/go1.13.12/bin/gofmt /usr/local/bin/gofmt
```

检查是否安装成功
```bash
  go version
```

查看go运行环境常量
```bash
  go env
```

常用环境常量默认值
```bash
  GOPATH="/root/go"
  GOROOT="/usr/local/go/go1.13.12"
```

设置GOPROXY（go get加速，被墙的包也畅通无阻）
```bash
  # 如果使用gomod，可以启用 Go Modules 功能
  go env -w GO111MODULE=auto
  # 配置 GOPROXY 环境变量（七牛云）
  go env -w GOPROXY=https://goproxy.cn,direct
  
  # 说明：GO111MODULE有三个可选值：off、on、auto
  # off: 无模块支持，go 会从 GOPATH 和 vendor 文件夹寻找包。
  # on: 模块支持，go 会忽略 GOPATH 和 vendor 文件夹，只根据 go.mod 下载依赖。
  # auto: 在 $GOPATH/src 外面且根目录有 go.mod 文件时，开启模块支持。
```
