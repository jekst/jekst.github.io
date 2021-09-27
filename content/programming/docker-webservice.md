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

```dockerfile
version: '3.9'
services:
  #Redis Service
  redis:
    image: redis:alpine
    container_name: redis
    restart: on-failure
    ports:
      - "6379:6379"

  #Nginx Service
  nginx:
    image: nginx:alpine
    container_name: nginx
    restart: on-failure
    ports:
      - "80:80"
      - "443:443"
    volumes:
      - "/Users/xxx/code/www:/usr/share/nginx/html"
      - "/etc/nginx/nginx.conf:/etc/nginx/nginx.conf:ro"

  #MySQL Service
  mysql:
    image: mysql:latest
    command: --default-authentication-plugin=mysql_native_password --character-set-server=utf8mb4 --collation-server=utf8mb4_unicode_ci
    container_name: mysql
    restart: on-failure
    tty: true
    ports:
      - "3306:3306"
    environment:
      MYSQL_ROOT_PASSWORD: xian
    volumes:
      - "/Users/xxx/data/dbdata:/var/lib/mysql"
```


