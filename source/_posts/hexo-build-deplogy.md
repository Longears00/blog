---
title: 'hexo:build & deplogy'
date: 2018-09-07 13:54:59
tags: hexo
category: other
---
### 简介

什么是 Hexo？
Hexo 是一个快速、简洁且高效的博客框架。
>hexo官网链接 [hexo](https://hexo.io/zh-cn/)
>

#### 从安装到本地浏览
1. npm install hexo-cli -g
1. hexo init blog
1. cd blog
1. npm install
1. hexo server

安装官网上的初始化命令就可以简单的快速搭建一个hexo blog.运行 hexo server 可以在本地 localhost:4000 上进行预览

ps：将运行命令加入package.json
```
 "scripts": {
    "dev": "hexo server"
  },
```
<!--more-->

#### 发布hexo项目到git
1. 在git上创建新的 repository 命名格式：{your-git-name}.github.io
ex: git 登录名称为 Longears00 那么创建的respository就应该为：Longears00.github.io  注意的是：名称一定要一模一样。大小写也要一样

2.更改hexo项目中的项目_config.yml url
```
# URL
## If your site is put in a subdirectory, set url as 'http://yoursite.com/child' and root as '/child/'
url: https://Longears00.github.io
root: /
permalink: :year/:month/:day/:title/
permalink_defaults:

```
这里的url一定要和发布的repository 一致。是访问hexo 博客的地址 


3.更改hexo项目中的项目_config.yml deploy 
```
# Deployment
## Docs: https://hexo.io/docs/deployment.html
deploy:
  type: git
  repo: https://github.com/Longears00/Longears00.github.io
  branch: master
```
这里的repo是远程发布的推送地址

4.运行hexo命令进行发布
```
hexo generate
hexo deploy
```
将命令配置到package.json
```
"scripts": {
    "dev": "hexo server",
    "deploy": "hexo clean && hexo generate && hexo deploy"
  }
```
最后输入https://Longears00.github.io [Longears00-hexo-blog](https://Longears00.github.io) 就可以看到博客的地址

 
