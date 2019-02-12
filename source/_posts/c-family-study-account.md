---
title: C/C++ Study Notes
date: 2019-02-08 20:05:21
toc: true
tags:
- c
- c++
- learn
categories:
- c/c++
---
本文用于记录C/C++~~补习~~学习过程中遇到的各种Bug以及相应的解决方案。所有相应的代码存放在[learn-c-family](https://github.com/bigface008/learn-c-family)仓库中。
<!--more-->

# C

## [barchart.c](https://github.com/bigface008/learn-c-family/blob/master/barchart.c)

根据输入文本中字母出现次数输出直方图（实际上输出的是线图）。

### 忘记C风格字符串最后一位必须是0

我求你记住。

## [align.c](https://github.com/bigface008/learn-c-family/blob/master/align.c)

根据输入参数对齐输入文本。

```bash
$ gcc -g align.c
$ ./a.out 80 < input.log
```

### 算法设计到一半就动手

在搞清楚自己想用的算法之前，不要动手写程序。

### 以为argc是第一个参数

argc是命令中所有参数的个数（包括./a.out）。也就是说，对于`./a.out 80`这条命令，argc的值为2。

### 没有输出最后一个单词

读取单词的主循环结束后还会剩一个单词没有输出。

### 输入文本中使用了非ascii字符

从别处复制过来的文本里包括了非ascii字符，这使得某一行计算字符数的时候总会多加一些。把那个字符换成对应的ascii字符就好了。（字符编码方式真是血的教训）

