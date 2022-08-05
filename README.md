# lede-builder
lede docker build 

> 此编译需要依赖外网, 如无法连接外网, 可使用已经编译好的版本


## 第一步
下载Dockerfile文件, 在Dockerfile同级文件下执行
```sh
docker build -t ancientxu/lede-builder .
```

或者直接使用已经编译好的版本
```sh
docker pull ancientxu/lede-builder:latest
```

## 第二步

1. 启动并进入docker容器
docker run -it -v /opt/docker/lede/output:/lede/bin ancientxu/lede-builder:latest

2. 在容器中执行
```sh
make menuconfig

make download -j8
make V=s -j1
```
