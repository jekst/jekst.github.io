+++
title = "自定义Docker镜像"
description = ""
date = 2021-09-02
draft = false
toc = true
categories = [
  "编程开发"
]
tags = [
  "Docker"
]
images = []
+++


以制作redis镜像为例，讲一下docker镜像制作及push到仓库流程

#### 1.编写Dockerfile

```dockerfile
FROM alpine:latest
# install redis
RUN apk add redis 
# expose port
EXPOSE 6379
# start redis server
CMD ["redis-server "]
```

#### 2.创建镜像

```powershell
docker build -t redis:0.0.1 .
```
#### 3.登陆仓库

```powershell
docker login --username=username registry.cn-hangzhou.aliyuncs.com
```
#### 4.镜像打标签

```powershell

docker tag redis:0.0.1 registry.cn-hangzhou.aliyuncs.com/jekst/redis:0.0.1
```

#### 5.上传镜像

```powershell
docker push registry.cn-hangzhou.aliyuncs.com/jekst/redis:0.0.1
```