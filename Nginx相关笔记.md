---
title: Nginx相关笔记
date: 2023-05-08 08:02:36
tags:
categories:
    - 教程
summary: 本篇用来记录使用nginx的各种思考感受，比如网站好好的怎么给我重定向到我的404界面了（
---

# 长期更新
本博客旨在记录本人学习Nginx相关体会，请酌情参考

## Nginx控制是使用nginx还是systemctl？

我个人倾向于使用sudo + nginx (+s stop/reload)来进行Nginx控制，主要原因为本人在使用systemctl时systemctl总会无端报错。
相对于寻找解决方案，我更倾向于使用自身提供的方案解决问题
