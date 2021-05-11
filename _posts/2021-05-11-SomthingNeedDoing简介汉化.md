---
layout:     post
title:      SomthingNeedDoing简介汉化
subtitle:   卫月插件SomthingNeedDoing的简介汉化
date:       2021-05-11
author:     LittleNightmare
header-img: img/post-bg-map.jpg
catalog: true
tags:
    - FF14
    - 卫月
    - SomthingNeedDoing
    - Dalamud
---
# SomethingNeedDoing

## 介绍

这个插件让你控制一个“小兽人劳工”帮你干活。特别是制作方面。给你带来更好的使用与储存多种宏的体验

![](https://github.com/daemitus/SomethingNeedDoing/raw/master/res/game.png)

## 功能
- 可以创建文件夹，并可以用推拽的方式重新排序宏，支持重命名。
- `<wait.#>` 默认的等待指令简写，如`<wait.5>`
- `<wait.#-#>` - 在你规定的范围，运行一个随机的等待时间，如`<wait.2-5>`
- `/wait #` - 默认的等待指令命令格式
- `/wait #-#` - 在你规定的范围，运行一个随机的等待时间，如`/wait 2-3`
- `/loop` - 再运行这行命令之上的宏一次
- `/loop #` - 再运行这行命令之上的宏#次，具体来说，`/loop 3`会让这行命令上面的宏，再运行3次，总共4次
- `/require "<name>"` - 要求当前处于 特定状态，如`强化药` 或 `进食`。默认等待1秒。如`/require 进食`
- `/waitaddon "<name>"` - 等待直到指定UI窗口弹出再运行接下来的宏。默认等待5秒，如果没有出现则结束运行
> - 译者注：UI的名字可以用卫月的窗口调试找到，如制作笔记界面的等待是`/waitaddon RecipeNote`
- `<maxwait.#>` - 覆盖`/require` 和 `/waitaddon` 的默认等待时间
- 精准等待 - 任何等待选项的时间都可以设置成`#.#` 这样的小数
  - 如 `<wait.1.5>` 或 `/wait 1.5-4.0`
- `/runmacro "<name>"` - 在宏里运行名字是`name`的宏
- 智能技能队列 - 除非收到游戏服务器的响应，否则不会运行下一个制作技能。可以在高延迟的情况下使用，但仍然需要 `<wait.#>` 来调整时间。 因为通常情况，服务器响应时间比动画快。
- `/ac "skill-name" <unsafe>` - 不管出于什么原因，绕过智能技能队列 。
  - 备注: 除非其他插件或游戏提供，智能技能队列不会在制作之外的情况下运行

## 使用
* 在聊天栏输入 `/pcraft` 

## 译者注
本文原作者是daemitus，翻译自daemitus的SomethingNeedDoing的[README](https://github.com/daemitus/SomethingNeedDoing/blob/master/README.md )。这些就是基础的功能介绍了。根据个人经历，写完宏建议多测试几遍，特别是工匠宏，曾经有出现过问题，如果还存在可以跟Macrology组合起来用，记得写`wait`。是的，如果有对应的卫月指令可以直接输入在聊天栏里启动的，在这个插件里写效果也是一样