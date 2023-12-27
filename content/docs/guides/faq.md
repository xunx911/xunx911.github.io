---
title: "Hugo(Hyas Doks)+Github+Netlify搭建博客(WSL)"
description: "本人搭建环境为Win10, WSL(Ubuntu22.04)，Hyas是以Hugo为引擎，Node.js作框架的网站构建工具，Doks是Hyas的官方主题，本文使用它来搭建博客。"
summary: ""
date: 2023-12-24T21:54:09+08:00
lastmod: 2023-12-24T21:54:09+08:00
draft: false
menu:
  docs:
    parent: ""
    identifier: "faq-d752adf1f3c5ec51562e973673d2fd42"
weight: 999
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---

# 本地创建博客项目
## 安装
## 踩到的坑
### apt直接安装版本不对
https://github.com/nodesource/distributions
https://getdoks.org/docs/start-here/getting-started/
### 先git clone下来再 hyas create导致设置base dictionary
### SSH
#### 之前的密钥莫名失效，新添加之后需要把之前的删除掉否则新的未应用
#### 每次重启终端都需要重新添加密钥
https://stackoverflow.com/questions/64865626/can-i-permanently-add-ssh-private-key-to-my-user-agent
### 网页没有CSS

https://github.com/gethyas/doks/issues/1041

```bash
conda install 
```

test
