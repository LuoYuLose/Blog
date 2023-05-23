---
title: Git搭建服务器托管平台常见问题
date: 2023-05-08 08:47:00
tags:
categories:
    - 教程
summary: 提出一些解决Git搭建服务器托管平台的方案
---

###  长期更新
#### 本博客旨在记录本人搭建服务器用Git托管平台时遇见的常见问题

Q:为什么我在`git init`后无法`git branch`更换分支？
>需要进行`git add`并进行一次`git commit`后才能进行分支修改操作。
此时master分支默认未建立（当然，也不允许`git branch master`这种愚蠢的行为），固然也无法进行分支操作

Q:用云服务器+Git方案托管博客的最佳方案是`git init`还是`git init --bare`？   
>个人评价为裸库最好位于第三方，比如在云服务器建立个git用户或者利用github之类的托管平台中继  
>
>>`git init`有工作区（人话就是Markdown文件能正常读取），但是`git push`时会crash（总之多人冲突）。   
解决方案......就是`git branch`换分支然后`git push`，但很蠢不是吗？
>
>>`git init --bare`创建裸库不会冲突，但也不会把工作区表现出来（你写的Markdown全是SHA1散列.jpg），博客读取文件会受阻     
>
>借助托管平台可以实现上述功能，但感觉还是有点把简单问题复杂化了，总之有更好解决方案会回来第一时间记录于此（
