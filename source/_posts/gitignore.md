---
title: git如何忽略文件
date: 2017-05-02 15:33:52
tags: git
---

前言
我们在使用git管理我们的代码和资源时候，经常会碰到一些文件或者目录不能提交到版本库，
但是项目里又不的没有这些文件或目录（待续...）



## 环境

linux elementary OS 0.4 Loki
git version 2.7.4


## 忽略文件的几种方法

[方法一] 配置.gitignore

在仓库目录下新建.gitignore文件
```bash
$ touch .gitignore
```
编辑 .gitignore 文件增加忽略项
```bash
$ vim .gitignore
```

.gitignore文件对其所在的目录及所在目录的全部子目录均有效。通过将.gitignore文件添加到仓库，
其他开发者更新该文件到本地仓库，以共享同一套忽略规则
