---
title: 评论系统上线
date: 2024-04-19 16:11:00 +0800
categories: [随笔]  #[A, B]
tags: [] #[TAG]     # TAG names should always be lowercase
author: [1]
---



#### 前言

心血来潮，想给博客添加一个评论系统。

采用免费、开源、无广告等特点的giscus，可以较容易地安装在利用github部署的网站上。

[giscus](giscus.app)的官方网站上有比较详细的介绍，而且上面有一个简易的html脚本生成器，可以根据你的需求，生成特定的脚本。

缺点就是不能在jekyll上直接使用。

#### 配置过程

##### 安装giscus

https://github.com/apps/giscus

##### 检查仓库状态

需要满足下面的要求：

1. 该仓库是公开的，否则访客将无法查看 discussion。 
2. Discussions 功能已在你的仓库中启用。

##### 修改文件

只需要修改`_config.yml`文件：

```yaml
comments:
  active: giscus #空白代表不使用评论系统
  giscus:
    repo: "QyDing02/qyding02.github.io" 
    repo_id: "R_kgDOJgDQQQ"
    category: "General"
    category_id: "DIC_kwDOJgDQQc4Ceyht" #前四项从giscus.app生成的脚本复制过来
    mapping: "pathname" # optional, default to 'pathname'
    input_position: "top" # optional, default to 'bottom'
    lang: "zh-CN" # optional, default to the value of `site.lang`
    reactions_enabled: "1" # optional, default to the value of `1`

```

评论是以github仓库中的discussion的方式存储的，不依赖额外的数据库。可以在discussion专区进行管理。


#### 参考链接

1. https://giscus.app/zh-CN

2. https://lazyren.github.io/devlog/use-utterances-for-jekyll-comments.html

3. https://blog.jakelee.co.uk/migrating-from-utterances-to-giscus-comments/
