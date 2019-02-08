---
title: Build My Site
date: 2019-01-29 12:13:43
categories:
- blog
tags:
- learn
- blog
---
本文件用于测试博客的各项功能，并收录简要的建站相关笔记。
<!--more-->

### 博客编写原则

本博客使用[Hexo](https://hexo.io/)博客框架、[maupassant-hexo](https://www.haomwei.com/technology/maupassant-hexo.html)主题进行搭建，用于记录、总结学习过程中的各种零碎知识。主要编写原则是

- 简明、朴素。
- 仅包含学习相关内容。

### 编写、发布

在本地编写时，主要会用到以下命令。

```bash
$ hexo n <file-name>         # 创建文件
$ hexo g -w                  # 监听Markdown文件变化并实时产生对应html文件
$ hexo s                     # 创建本地服务器
$ hexo d                     # 发布到Github服务器
```

可以[用Livereload或BrowserSync自动刷新](https://jerry011235.github.io/2015/05/07/Hexo%E4%B8%8D%E9%87%8D%E6%96%B0%E7%94%9F%E6%88%90%E4%B9%9F%E5%8F%AF%E9%A2%84%E8%A7%88/)。目前使用BrowserSync，直接执行命令`hexo s`便可预览博客并实时刷新。

### 其他

- about的信息存放在[source/about/index.md](../about/index.md)中。

