---
title: "本地创建博客项目"
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

## 使用nodesource安装Node.js
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

运行完后新开一个终端(刷新一下，不然可能找不到npm)，运行以下代码以检查安装成功

```bash{title="输出版本号即成功"}
node -v
npm -v
```

## 初试Doks
### 创建一个新项目
根据[官方文档](https://getdoks.org/docs/start-here/getting-started/),使用以下命令，建立一个Hyas + Doks 项目：

```bash
npm create hyas@latest -- --template doks
```

按提示输入你想要的项目名称，即可完成创建。
然后按提示运行`npm install`安装依赖。
{{< callout context="note" title="Note" icon="info-circle" >}}
这里安装依赖的时间较长，请耐心等待，并保证网络通畅。

{{< /callout >}}
最后，运行以下命令运行示例：

```bash
npm run dev
```

提示在浏览器打开，会提供两个url，打开后如果不对，尝试下另外一个url。
如果没有问题，恭喜本地博客已经初始化好了。

### 添加一个新页面
内容放在content文件夹下，使用子文件夹的形式组织文件。
例如以下命令创建的`.md`文件会在`example.com/docs/guides/faq`生成一个页面：

```bash
npm run create docs/guides/faq.md
```

然后就可以在faq.md文件中开始写博客了。

### 本地渲染
如果想在本地查看页面渲染，使用以下命令：

```bash
npm run build
npm run preview
```

不过有时需要build两次，可能是因为缓存的导致的报错。
