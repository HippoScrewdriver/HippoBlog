---
title: 从零开始用Hexo建站的历程
date: 2023-03-22 01:27:29
tags: 
   - 建站
   - 学习
categories:
- tech
top: true
---

## 我是如何开始的❗️❓

关于个人博客，不同于其他社交媒体，我一直很想创建一个既能让我尝试摸索前端开发，又可以浓缩生活的个人空间。于是在winter quarter结束后，我开始慢慢试图寻找资料，当然我目前的水平还不足以直接用前端框架直接搭建，因此所有内容都很基础。

于是我从一篇知乎文章["如何自己搭建一个个人网站"](https://www.zhihu.com/question/22197688)开始入手。本文采用**Hexo**博客框架（当然也是一个捷径啦，在基本熟悉网站结构后我会继续研究Hexo的具体原理），部署在**github**上，~~采用**MiHoYo**的主题框架（有点二次元但很简洁！），并且使用无后端的**Valine**（在考虑换成包含后端的Waline）作为评论系统。~~  
现在改成了nexT主题，因为这个主题更加成熟也有更多拓展空间。

这篇文章的内容大部分来源于大佬的介绍，我只是根据自己的建站历程进行整理。中间有些部分和原文章不完全一样，是因为我在过程中遇到了更多问题   ，这些解决办法将包含在文章中。

---

## 创建git仓库，配置，和安装：

1. 首先！创建你的github仓库，这个仓库就是储存你网站信息的。仓库名称需为固定写法：**username.github.io**

2. 在git安装运行正常的基础上进行配置，我使用的是mac，因此在terminal设置git的配置信息

   ```bash
   git config --global user.name "github的username"
   git config --global user.email "github的注册邮箱"
   ```

3. 配置成功后，我们需要通过以下命令生成ssh key文件
   ```bash
   1ssh-keygen -t rsa -C "github的注册邮箱"
   ```
   在这里可以先不设置密码，直接回车。  
   完成后我们会在隐藏文件夹`.ssh`中找到两个文件：`id_rsa`和`id_rsa.pub`，复制`id_rsa.pub`文件里的所有内容，然后将你复制的key粘贴到github中。
   
   在我正在使用的github页面中，ssh key粘贴的位置如下：

   * 选择Settings
   * 左侧边栏SSH and GPG keys
   * 然后添加你的SSH keys，命名并且记得增加权限。


4. 
等我在另一台设备上重新设置再继续写，现在因为已经设置过了，操作的结果和最初不一样。




