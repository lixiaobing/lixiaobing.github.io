---
title: git如何忽略文件
date: 2017-05-02 15:33:52
tags: git
---


## 环境

系统	elementary OS 0.4 Loki
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
