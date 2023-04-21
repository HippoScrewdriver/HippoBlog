---
title: shell scripts的基本用法
date: 2023-04-10 15:02:07
tags:
    - shell
    - 学习
categories:
    - tech
---

# 这里是我的cse374笔记

> 4.10的时候写完了作业，这几天有空的时候可以整理一下具体的内容做个复习。


# Linux File System

这是我觉得很好的一张图

![](images/post_img/file_system_structure.jpg)

> 这里主要是一些零碎整理的常用功能和方法，结构并不完善也不够全面，仅做学习用。

## I/O 输入输出

- 标准输入输出：  
        stdin=0  
        stdout=1  
        stderr=2

1. `process < usrfile` 用于控制输入

2. `process > or >> outputfile` 用于控制输出，单个代表新文件，两个代表追加。换成`2>`代表输出error。
        
    - 1 >& 2 为把标准输出转化成error
    以及 2 >& 1 都可以把标准输出转化为标准错误输出，或者标准错误输出转化为标准输出。

在这里要提及一点，就是

## pipe






