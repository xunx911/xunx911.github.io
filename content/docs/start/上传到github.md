---
title: "上传到Github"
description: ""
summary: ""
date: 2023-12-27T21:47:57+08:00
lastmod: 2023-12-27T21:47:57+08:00
draft: false
menu:
  docs:
    parent: ""
    identifier: "上传到github-4fa100c2932bba112496c207a54943fa"
weight: 220
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---

配置Github的部分这里不再赘述，配置好之后，这一步只需要Github上创建一个新的空仓库，仓库名是用户名.github.io，然后把本地项目push上去即可。
{{< callout context="caution" title="注意" icon="alert-triangle" >}}
务必 `cd`进项目中操作，不要上传的是一个大文件夹，不然可能会因为根目录与相对路径的问题带来不必要的麻烦。
{{< /callout >}}

## 初始化

```bash
git init
```

## 添加要上传至Github的文件

不是所有文件都需要上传上去，有的文件远程安装依赖以及构建时也会生成，并不需要本地的资源。创建一个`.gitignore`文件来排除这些文件：

```bash{title=".gitignore"}
node_modules/
resources/_gen/
public/
.DS_Store
Thumbs.db
*.log
*.tmp
.vscode/
.idea/
```

然后添加其他的所有文件：

```bash
git add .
```

## 添加远程仓库并上传
接下来要提交当前所作的操作：

```bash
git commit -m "Init"
```

将以下命令中<仓库地址>换成自己的并运行

```bash
git remote add origin <仓库地址>
git push -u origin main
```

至此，本地博客项目已被上传至Github仓库，下一步就是使用Netlify部署。

## 后续
之后有改动只需要:

```bash
git add . # (例如新建的页面是未追踪的要添加一下),
git commit -a -m "your record" # -a自动提交所有已追踪的文件的改动
git push
```

新的改动就被上传上去了。
