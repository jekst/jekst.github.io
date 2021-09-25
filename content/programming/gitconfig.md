+++
title = "Git常用配置"
description = ""
date = 2021-09-02
draft = false
toc = true
categories = [
  "软件配置"
]
tags = [
  "Git"
]
images = []
+++

```terraform
[user]
	name = 用户名
	email = 邮箱
[credential]
	helper = manager

[alias]
	st = status
	co = checkout
	ci = commit
	br = branch
	di = diff
[url "ssh://git@github.com/"]
	insteadOf = https://github.com/

```