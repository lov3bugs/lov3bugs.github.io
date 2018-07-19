---
title: Git常用操作
date: 2018-07-19
tags: 工作
---


<!-- more -->

# 基本操作

## git clone

git clone 拷贝一个 Git 仓库到本地，让自己能够查看该项目，或者进行修改。
```
git clone [url]
```

## git status

查看git状态, 当前所在分支和本地是否有文件修改
```
git status
```

## git add

git add 命令可将修改文件添加到缓存区
```
git add . // . 表示添加所有修改文件到缓存
```

## git commit 

将缓存区的修改提交到版本库
```
git commit -m "create readme.txt" // -m 是对本次提交的描述，最好是有意义的
```

## git push

```
git push // 提交所有修改到远程仓库
```

## git merge

合并分支到当前分支

## git pull

拉取远程仓库最新提交，并合并到指定的本地分支上。
```
git pull 
```

# 使用场景

## 提交修改到某个分支

比如修改并提交到jiangpan分支
```
git pull // 拉取远程仓库
git checkout jiangpan // 首先切换到jiangpan分支
git status // 查看本地工作区的状态, 当前分支和是否有修改
git add . // 添加本地所有修改到缓存区, 每次修改完都要重新add
git commit -m "修改备注信息" // 提交缓存的修改到版本库
git push // 提交到远程仓库
```

## 合并master到某个分支

比如合并master到分支jiangpan
```
git checkout jiangpan // 首先切换到jiangpan分支
git merge master // 切换到jiangpan之后, 合并master分支到当前分支
```

## 合并某个分支到master

比如合并分支jiangpan到master
```
git checkout master // 首先切换到master分支
git merge jiangpan // 切换到master之后, 合并jiangpan分支到当前分支,即master
```
