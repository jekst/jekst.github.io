+++
title = "Golang配置"
description = ""
date = 2021-09-02
draft = false
toc = true
categories = [
  ""
]
tags = [
  "Golang"
]
images = []
+++

```bash
go env -w GO111MODULE=auto
go env -w GOPROXY=https://goproxy.cn,direct
go env -w GOPRIVATE=*.example.com
```