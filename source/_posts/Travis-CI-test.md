---
title: Travis-CI
date: 2018-04-22
tags: CI
---

### Travis-CI

最终效果：
> 只需提交md文件到Git项目的hexo分支，由Travis自动部署到master，达到动态更新blog的效果

1. Github.io项目准备两个分支
* master分支存放静态文件
* hexo分支存放hexo环境文件

2. 生成一个access_token，提供给Travis push静态文件到master

3. hexo分支搭建，添加.travis.yml文件
