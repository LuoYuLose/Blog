---
title: Hyprland配置记录
date: 2023-05-18 17:59:01
tags:
categories: 教程
summary: 作为个人入门完全自定义Wayland的首次尝试，这篇博客记录下安装过程中踩过的坑
---

### 只是作为对自己尝试Wayland时各种踩坑的记录，实际上我对Wayland不如X.Org熟悉，因此给出的方案也不一定能100%解决问题

Q: Wayland下的Electron应用配置  
>作为Wayland下比较出名的劝退因素，ArchWiki下给出了算是比较详细的解决方案（但使用过程中还是或多或少存在问题，而且不同的Electron版本需要不同的解决方案
只能期待Electron官方给修复（记得Chromium已经有了解决方案了  
以下摘录一些ArchWiki给出的的解决方案    
>>

Q: Hyprland（Wayland下一款wm）经常遇到卡死问题
>我这里查Crash报告一般都是内存炸了然后卡死，而这些情况一般发生在听音乐时（没错，Linux下好用的音乐播放器有不少Electron框架   
所以解决方案也很简单——按照上面改下配置文件就可以有效避免，但其他爆内存或是Crash也存在，等到自己遇到后在做记录吧

Q: Wayland下的游戏问题
>如果你有游戏需求（尤其是大型游戏），那我极不建议你迁移到Wayland（或者说为什么不保留一个X.Org或者Windows引导呢  
目前Linux下Wayland游戏实现大部分还是依赖XWayland实现，XWayland...   
>
>>1. XWayland本质还是X服务  
>>2. XWayland的性能和X11相当，因此对于N卡可能有性能下降 
>>3. XWayland不完全向后兼容X11，因此对于某些应用可能出现不完全兼容现象
>
>总结来讲就是上不去下不来，卡在那了，但Wayand下XWayland算不错的方案了，总之期待后续优化吧
（顺带一提，Steam客户端也是仅支持X11的

Q: Wayland下的应用管理（应用启动方式
>之前一直用Wofi，但现在听说Rofi也支持Wayland了，挺好的  
这两个启动方式我更推荐Rofi，单纯用习惯了

Q: Wayland下的dm选择
>ArchWiki下说的很详细了，这里只是讨论几个常用dm对Wayland支持
>
>>1. Sddm。个人在使用Sddm启动Wayland（Hypr）时曾出现卡死现象（排除了Electron的因素），因此建议Sddm用户使用Sddm-git启用Wayland   
>>2. Gdm。作为Gnome亲儿子，Gdm对于Wayland支持大可放心，不过不用Gnome一般也没人去碰Gdm（实际上我用Gnome也会选择Sddm
>>3. Lightdm。怎么说呢，虽然没使用过Ldm，但个人不推荐Ldm启动Wayland（完全是因为听说过Ldm算X11亲儿子），ArchWiki也不建议Ldm启动Wayland，但如果想尝试可以用用看？

Q: Wayland下的Termial选择
>Wayland下的Termial...其实网络上都在推荐alacritty和kitty（st：那我呢    
这两个终端我都推荐，看个人喜好吧（不过kitty那一大串配置文档让人看了想死     
>
>>alacritty基于Rust编写，而且据说解决issue也很勤快  
>>kitty用C和Python编写，之前对于中文支持很拉胯，但现在好多了，而且kitty有连字支持和窗口多开，习惯了很舒服

Q: 我是否需要XWayland兼容？
>省流：有游戏需求（尤其是大型游戏）还是X11或是Windows吧，Wayland在这方面是硬伤。    
对于Electron兼容还是有点问题，但日用没问题，总之日常用用还是可以的  
而且Wayland是真的漂亮，相比于X.Org下一群组件的相互配合，Wayland更加自然
