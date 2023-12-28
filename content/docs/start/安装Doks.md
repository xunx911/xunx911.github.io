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

# 使用nodesource安装Node.js
Hyas要求Node.js版本{{< math >}}$\geq 16.12.0${{< /math >}}，因此需要先安装Node.js。
{{< callout context="caution" title="注意" icon="alert-triangle" >}}
不要直接使用`sudo apt-get install nodejs -y`进行安装，Ubuntu22.04官方支持的版本只到12.x。
{{< /callout >}}

通过[nodesource](https://github.com/nodesource/distributions)安装，依次执行下列命令即可：

```bash{title="Download and import the Nodesource GPG key"}
sudo apt-get update
sudo apt-get install -y ca-certificates curl gnupg
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://deb.nodesource.com/gpgkey/nodesource-repo.gpg.key | sudo gpg --dearmor -o /etc/apt/keyrings/nodesource.gpg
```

```bash{title="Create deb repository"}
NODE_MAJOR=20
echo "deb [signed-by=/etc/apt/keyrings/nodesource.gpg] https://deb.nodesource.com/node_$NODE_MAJOR.x nodistro main" | sudo tee /etc/apt/sources.list.d/nodesource.list
```

{{< details "Details" >}}

```bash{title="改变NODE_MAJOR以指定版本"}
NODE_MAJOR=16
NODE_MAJOR=18
NODE_MAJOR=20
NODE_MAJOR=21

```

{{< /details >}}

```bash{title="Run Update and Install"}
sudo apt-get update
sudo apt-get install nodejs -y
```
