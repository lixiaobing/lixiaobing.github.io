---
---
title: git如何忽略文件
date: 2017-05-02 15:33:52
tags: git
---

我们在使用git管理我们的代码工程，有时有的文件是不希望上传到版本库的，如项目编译生成的临时文件或调试时的配置等等，每次commit 的时候都需要把这些文件排除在外，非常麻烦。其实我们可以吧这写文件忽略掉，本文介绍几种忽略文件的方法



## 环境

linux elementary OS 0.4 Loki
git version 2.7.4


* [方法一] 配置.gitignore

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

* [方式二] 配置.git/info/exclude文件

```bash
$ vim .git/info/exclude
``` 

```bash
git ls-files --others --exclude-from=.git/info/exclude
Lines that start with '#' are comments.
For a project mostly in C, the following would be a good set of
exclude patterns (uncomment them if you want to use them):
*.[oa]
*~
```




这种方式对仓库全局有效，只能对自己本地仓库有作用，其他人没办法通过这种方式来共享忽略规则，除非他人也修改其本地仓库的该文件。

## [方式三]
       通过.git/config配置文件的core. Excludesfile选项，指定一个忽略规则文件（完整路径），如下图所示。忽略规则在文件e:/gitignore.txt中（当然该文件名可以任意取）。
       该方式的作用域是也全局的。


* 配置说明
\# 忽略*.o和*.a文件
 *.[oa]
\# 忽略*.b和*.B文件，my.b除外
*.[bB]
!my.b
\# 忽略dbg文件和dbg目录
dbg
\# 只忽略dbg目录，不忽略dbg文件
dbg/
\# 只忽略dbg文件，不忽略dbg目录
dbg
!dbg/
\# 只忽略当前目录下的dbg文件和目录，子目录的dbg不在忽略范围内
/dbg


