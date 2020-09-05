---
title: CI_Travis
date: 2018-04-22
tags: CI
---

### Travis-CI

最终效果：
> 只需提交md文件到Git项目的hexo分支，由Travis自动部署到master，达到动态更新blog的效果

 <!-- more -->

1. Github.io项目准备两个分支
* master分支存放静态文件
* hexo分支存放hexo环境文件

2. 生成access_token以供Travis部署到Github
* 在Github生成一个access_token
* 在Travis里面设置变量GH_TOKEN（然后在下面会用到）

3. hexo分支搭建，添加.travis.yml文件
```
language: node_js  #设置语言

node_js: stable  #设置相应的版本

cache:
    apt: true
    directories:
        - node_modules # 缓存不经常更改的内容

before_install:
    - export TZ='Asia/Shanghai' # 更改时区

install:
  - npm install  #安装hexo及插件

script:
  - hexo clean  #清除
  - hexo g  #生成

after_script:
  - git clone https://${GH_REF} .deploy_git  # GH_REF是最下面配置的仓库地址
  - cd .deploy_git
  - git checkout master
  - cd ../
  - mv .deploy_git/.git/ ./public/   # 这一步之前的操作是为了保留master分支的提交记录，不然每次git init的话只有1条commit
  - cd ./public
  - git config user.name "lov3bugs"  #修改name
  - git config user.email "ggdebug@gmail.com"  #修改email
  - git add .
  - git commit -m "Travis CI Auto Builder at `date +"%Y-%m-%d %H:%M"`"  # 提交记录包含时间 跟上面更改时区配合
  - git push --force --quiet "https://${GH_TOKEN}@${GH_REF}" master:master  #GH_Token是在Travis中配置环境变量的名称

branches:
  only:
    - hexo  #只监测hexo分支，根据自己情况设置
env:
 global:
   - GH_REF: github.com/lov3bugs/lov3bugs.github.io.git  #设置GH_REF，注意更改yourname

# configure notifications (email, IRC, campfire etc)
# please update this section to your needs!
# https://docs.travis-ci.com/user/notifications/
notifications:
  email:
    - ggdebug@gmail.com
  on_success: change
  on_failure: always
```
4. 本地clone hexo分支，在_posts下面编辑md文档，然后push到hexo分支即可
