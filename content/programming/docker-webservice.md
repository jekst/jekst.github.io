+++
title = "Docker Webservice"
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

**Mysql**

```powershell
docker run -d -v /Users/User/data/dbdata:/var/lib/mysql --name mysql -p 3306:3306 -e MYSQL_ROOT_PASSWORD=llqwe mysql:latest
```

**Redis**
```powershell
docker run -d --name=redis -p 6379:6379 redis:alpine
```


