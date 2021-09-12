+++
title = "brew阿里源配置"
description = ""
date = 2021-09-04
draft = false
toc = true
categories = [
  "编程开发"
]
tags = [
  "Brew"
]
images = []
+++

#### Bash 终端配置

```bash
    # 替换brew.git:
    cd "$(brew --repo)"
    git remote set-url origin https://mirrors.aliyun.com/homebrew/brew.git
    # 替换homebrew-core.git:
    cd "$(brew --repo)/Library/Taps/homebrew/homebrew-core"
    git remote set-url origin https://mirrors.aliyun.com/homebrew/homebrew-core.git
    # 应用生效
    brew update
    # 替换homebrew-bottles:
    echo 'export HOMEBREW_BOTTLE_DOMAIN=https://mirrors.aliyun.com/homebrew/homebrew-bottles' >> ~/.bashrc
    source ~/.bashrc
```

#### Zsh 终端配置

```bash
    # 替换brew.git:
    cd "$(brew --repo)"
    git remote set-url origin https://mirrors.aliyun.com/homebrew/brew.git
    # 替换homebrew-core.git:
    cd "$(brew --repo)/Library/Taps/homebrew/homebrew-core"
    git remote set-url origin https://mirrors.aliyun.com/homebrew/homebrew-core.git
    # 应用生效
    brew update
    # 替换homebrew-bottles:
    echo 'export HOMEBREW_BOTTLE_DOMAIN=https://mirrors.aliyun.com/homebrew/homebrew-bottles' >> ~/.zshrc
    source ~/.zshrc

```

#### 恢复默认配置

执行以下命令
```bash
    # 重置brew.git:
	$ cd "$(brew --repo)"
	$ git remote set-url origin https://github.com/Homebrew/brew.git
	# 重置homebrew-core.git:
	$ cd "$(brew --repo)/Library/Taps/homebrew/homebrew-core"
	$ git remote set-url origin https://github.com/Homebrew/homebrew-core.git

```
然后删掉`HOMEBREW_BOTTLE_DOMAIN`环境变量。

将你终端文件`~/.bashrc` 或者`~/.zshrc`中的`HOMEBREW_BOTTLE_DOMAIN`行删掉。

最后执行`source ~/.bashrc`或者`source ~/.zshrc`。