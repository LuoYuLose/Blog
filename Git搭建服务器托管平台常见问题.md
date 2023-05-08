---
title: Git搭建服务器托管平台常见问题
date: 2023-05-08 08:47:00
tags:
---

# 长期更新
本片博客旨在记录本人搭建服务器用Git托管平台时遇见的常见问题

<!--more-->

Q:为什么我在`git init`后无法`git branch`更换分支？
>需要进行`git add`并进行一次`git commit`后才能进行分支修改操作。
此时master分支默认未建立（当然，也不允许`git branch master`这种愚蠢的行为），固然也无法进行分支操作
