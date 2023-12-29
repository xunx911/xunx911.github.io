---
title: "Netlify部署"
description: ""
summary: ""
date: 2023-12-28T19:06:26+08:00
lastmod: 2023-12-28T19:06:26+08:00
draft: false
menu:
  docs:
    parent: ""
    identifier: "Netlify部署-1313f0bb6633b34bbfba91590fe2bf15"
weight: 230
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---

参见[官方文档](https://docs.gethyas.com/guides/deploy/netlify/)，简而言之：

1. 注册一个Netlify账号
2. 在仪表盘中点击`Add a new site`，选择`Import an existing project`
3. 点击`Deploy with Github`,授权后选择博客的仓库，然后配置上应该会自动填写，`Build Command`手动填一下`hyas build`或者`npm run build`就可以了。

部署成功，之后只需要`git push`之后，这边就会自动更新网站了(需要一点时间)。
