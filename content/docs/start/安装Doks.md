---
title: "安装Doks"
description: ""
summary: ""
date: 2023-12-27T15:06:33+08:00
lastmod: 2023-12-27T15:06:33+08:00
draft: false
menu:
  docs:
    parent: ""
    identifier: "安装Doks-4f458a67b9c2e2db8815f01a6757fdd4"
weight: 210
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

```bash{title="Installing dependencies…"}
pnpm create hyas@latest
```

### 修改主页
layout/index.html

### 修改侧边栏
调整权重，不要从0开始。。。

### 新建一个docs风格的
npm run create-- --kind docs name
