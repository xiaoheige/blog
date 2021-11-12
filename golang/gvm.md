# 版本管理工具GVM


Github: https://github.com/moovweb/gvm

### 安装

_安装GVM前，系统里必须已经安装了Golang_

_在Linux下安装GVM，需要安装相关依赖，详情见官网说明: https://github.com/moovweb/gvm_

```bash
  bash < <(curl -s -S -L https://raw.githubusercontent.com/moovweb/gvm/master/binscripts/gvm-installer)
```
  
重新登录shell或手动`source .bashrc`，以设置gvm环境变量


### 常用命令
```bash
  # 查看已经安装的版本，和当前使用的版本
  gvm list
  
  # 查看已经发布的所有Golang版本
  gvm listall
  
  # 安装指定的Golang版本
  gvm install go<version>
  
  # 使指定Golang版本生效
  gvm use go<version> [--default]
  # 使用"--default"参数，下次登录shell默认使用该版本
  # 安装完成后`go version`查看版本
  
  # 删除指定的Golang版本
  gvm uninstall go<version>
  
  # 完全卸载掉GVM和所有安装的Golang版本（谨慎使用）
  gvm implode
```

### 管理GOPATH

_`gvm use`切换Golang版本的时候，GOPATH会被切换到对应Golang版本的默认GOPATH下。`gvm pkgset`可以让不同Golang版本的项目，共用同一个GOPATH_
```bash
  gvm pkgset create <packagename>
  gvm pkgset list <packagename>
  gvm pkgset delete <packagename>
  gvm pkgset use <packagename>
  gvm pkgset empty <packagename>
```
