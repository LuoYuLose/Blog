---
title: Sourcemod插件编写教程
date: 2023-05-08 08:02:13
tags:
categories:
    - 教程
summary: 本篇长期更新，用来记录一些编写sp文件的方法与感受（实际上能坚持搞懂大部分sp语法就算胜利
---

SourceMod，也就是起源平台的插件平台，是众多起源1游戏实现其他玩法的重要载体。
而SourcePawn则是作为该平台的脚本语言实现了大部分额外功能，包括L4D2的RPG、药抗药役；CSGO的ZE、躲猫猫等。

不过需要注意的是，sp语言只是源代码，需要编译为smx文件才能被插件正常识别并运行。
不过此教程只提供sp的编写教程，其他调试报错等不再考虑范围内。

本教程目的在于记录本人学习Sourcemod编写教程（.sp）文件，包括指令记录与用法总结。

以下为一些参考文档，如果有兴趣我更建议跟着文档去学习。

> [SourcePawn官方文档](https://sm.alliedmods.net/new-api/)
>
> [SourcePawn教程](https://blog.csdn.net/jamenu/article/details/134716521)

## 实例1：HelloWorld

正所谓每一个语言的开始都是习以为常的HelloWorld程序，而本教程也不例外。
首先编写的插件就是在聊天窗口打印“HelloWorld”。

示例代码如下：

```SourcePawn
// 引入插件所需代码，类似于C语言的#include <iostream>
#include <sourcemod>

// 声明初始化函数，该函数在插件加载时调用。类似于C语言的main()
public Plugin Start()
{
    // 将“Hello World!”打印到控制台
    PrintToChat(All, "Hello World!");

    // 返回值
    return Plugin_Continue;
}
```

可以看出SourcePawn脚本和C语言很类似。其实V社游戏中的插件代码都能看到C、Java、CSS、JSON等早期语言的身影。
把握这一规则后入门起源插件开发会更加轻松。

> C系语言风格能从SourcePawn中看出
>
> Java语言风格能从.qc这类模型定义文件中看出
>
> CSS则是起源游戏中控制HUD的语言
>
> JSON出现在地图定义文件.vmx中

## 实例2：实现定时广播信息

相比于实例1，这一实例主要增加了一项功能——固定时间后执行特定代码。
特定代码为上一实例中修改“Hello World!”为广播信息后的代码，因此我们关心SourcePawn中的时间相关函数就可以啦。
ヾ(≧▽≦*)o

To Be Continued...
