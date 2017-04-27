---
title: about
date: 2017-04-27 17:09:05
tags:
---

vim模式：

1.编辑模式（命令模式）
2.输入模式
3.末行模式


编辑模式：
i 在当前光标所在的字符前面，转换为输入模式

a 在当前光标所在字符的后面，转换为输入模式

o 在当前光标所在行的下方，新建一行，并转换为输入模式

I 在当前光标所在的行首，转换为输入模式

A 在当前光标所在的行的行尾，转换为输入模式

O 在当前光标所在行的上方，新建一行，并转换为输入模式

：有编辑模式转换为末行模式


输入模式：

ESC 由输入模式转换为编辑模式


末行模式：

ESC , ESC  由末行模式转换为编辑模式

----------------------------------------

打开文件

vim +#  打开文件并定位于第#行

vim +   打开文件并定位于最后一行

vim +/pattern 打开文件并定位至第一次被pattern匹配到的行的首行

注：默认处于编辑模式


关闭文件

1.行末模式关闭文件

:q   退出

:wq  保存并退出

:q!  不保存退出

:w   保存

:w!  强行保存

:x   同wq 

2.编辑模式下退出

ZZ 保存并退出


移动光标（编辑模式）
1.琢字符移动

h 左 

l 右

j 下

k 上

#h 移动#个字符

2.以单词为单位移动

w 移至下一个单词的词首

e 跳至当前或下一个单词的词尾

b 跳至当前或钱一个单词的词首

#w 移动#个单词

3.行内跳转

0  绝对行首

^  行首的第一个非空白字符

$  绝对行末

4.行间跳转

#  跳转至第#行

gg 第一行

G  最有一行

5.末行模式

. 表示当前行

$ 最后一行

# 第#行

+# 向下的#行



翻屏

ctrl + f   向下翻一屏

ctrl + b   向上翻一屏 

ctrl + d   像下翻半屏

ctrl + u   向上翻半屏

删除单个字符

x  删除光标所在的字符

#x 删除光标所在处像后的共#个字符


删除命令 d

d命令和跳转命令组合使用
#dw #de #db

dd  删除当前光标所在的行 

#dd 删除包括当前光标所在行在内的#行 

粘贴命令 p

p 如果删除或复制为整行内容，则粘贴至光标所在行的下方，如果复制或删除的内容为非整行，则粘贴至光标所在的字符的后面

P 如果删除或复制为整行内容，则粘贴至光标所在行的下方，如果复制或删除的内容>为非整行，则粘贴至光标所在的字符的后面

复制命令y

用法同d命令

修改：先删除内容，再转换为输入模式

c  用法同d

替换

r 单字符替换

#r 光标后#个字符全部替换

R  替换模式

撤销编辑操作 u

u 撤销前一次的编辑操作

#u 直接撤销最近#次编辑的操作

连续u命令可撤销此前的n次编辑操作


ctrl + r 撤销最近一次撤销的操作


重复前一次编辑操作

. 编辑模式里重复前一次编辑操作


可视化编辑模式

v 按字符选取

V 按矩形选取

查找

/PATTERN

?PATTERN

n 下一个

N 上一个




查找并替换

在末行模式下使用s命令

headline,footlines#PATTERN#string#g

1,$   表示全文

%     表示全文


使用vim编辑多个文件

vim FILE1 FILE2 FILE3

:next  切换至下一个文件

:prev  切换至前一个文件

:last  切换至最后一个文件

:first 切换至第一个文件

:q     退出当前文件编辑

:qa    全部退出


分屏显示一个文件

ctrl + w , s  水平拆分窗口

ctrl + w , v  垂直拆分窗口

在窗口间切换光标

ctrl + w ,ARROW(h,j,k,l或方向建)

:qa 关闭所有窗口


十八、分窗口编辑多个文件

    vim -o : 水平分割显示

    vim -O : 垂直分割显示
十九、将当前文件中部分内容另存为另外一个文件

末行模式下使用w命令

    :ADDR1,ADDR2w /path/to/somewhere
二十、将另外一个文件的内容填充在当前文件中

    :r /path/to/somefile

    附加到当前文件光标后
二十一、跟shell交互

    :! COMMAND
二十二、高级话题

1、显示或取消显示行号

    :set nu

    :set nonu

    mu = number
2、显示忽略或区分字符大小写

    :set ic

    :set noic

    ic = ignorecase
3、设定自动缩进

    :set ai

    :set noai

    ai = autoindent
4、查找到的文本高亮显示或取消

    :set hlsearch

    :set nohlsearch
5、语法高亮

    :syntax on

    :syntax off
注:特性当前有效，如果想要永久有效需修改配置文件
二十三、配置文件

    /etc/vimrc    针对所有用户

    ~/.vimrc    针对当前用户 