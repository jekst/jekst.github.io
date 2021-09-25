+++
title = "Zsh配置"
description = ""
date = 2021-09-02
draft = false
toc = true
categories = [
  "软件配置"
]
tags = [
  "Zsh"
]
images = []
+++

zsh自定义配置
```dotnetcli
#Tell ls to be colourful 
export CLICOLOR=1
export LSCOLORS="Gxfxcxdxbxegedabagacad"
#Tell grep to highlight matches
export GREP_OPTIONS='--color=auto'
# Enabling completion
autoload -U compinit && compinit
# Enabling color prompt
autoload -U colors && colors
# Enabling and setting git info var to be used in prompt config.
autoload -Uz vcs_info
zstyle ':vcs_info:*' enable git svn
# This line obtains information from the vcs.
zstyle ':vcs_info:git*' formats " - (%b)"
precmd() {
    vcs_info
}

# Enable substitution in the prompt.
setopt prompt_subst

# Config for the prompt. PS1 synonym.
PROMPT='[%{$fg_bold[green]%}%c%{$fg_bold[blue]%}${vcs_info_msg_0_}%{$reset_color%}]$ '

export HOMEBREW_BOTTLE_DOMAIN=https://mirrors.aliyun.com/homebrew/homebrew-bottles


egrep='egrep --color=auto --exclude-dir={.bzr,CVS,.git,.hg,.svn,.idea,.tox}'
fgrep='fgrep --color=auto --exclude-dir={.bzr,CVS,.git,.hg,.svn,.idea,.tox}'


alias l="ls -lah"
alias la="ls -lAh"
alias ll="ls -lh"
```