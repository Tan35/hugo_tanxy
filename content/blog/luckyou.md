---
title: “幸运之子会是谁呢”
date: 2020-08-15 20:48:22
description: 一款有趣的“抽奖”工具
categories: 
- 一些软件
tags:
- VUE
- 抽奖
- LuckyYou
- 软件
top_img: https://i.loli.net/2020/07/05/IQsCpRNel7VMTBf.jpg
cover: https://pic.downk.cc/item/5f39f36014195aa594859305.png
thumbnail: https://pic.downk.cc/item/5f39f36014195aa594859305.png
highlight_shrink: false
photos:
 - https://pic.downk.cc/item/5f39f36014195aa594859305.png
---

一款有趣的“抽奖”工具
<!--more-->

## 前言 
今日分享的是一个偶然在少数派上面看到的一个软件：LuckyYou，这款软件的作者是 [jwenjian](https://github.com/jwenjian),我是被作者对这款软件的描述吸引的：

![](https://cdn.jsdelivr.net/gh/Tan35/ImgHosting/Tan35-PIC/Snipaste_2020-11-22_17-08-14.jpg)

而对于这款软件的实际意义来说简单四个字：随机抽取（~~废话~~）
+ 班级上的点名，无论是随机点到还是随机"抽奖"
+ 幸运观众的抽取

## 优势   
在这个花名册逐渐电子化的时代，“抽奖工具”的出现似乎是必不可少了，那么这款软件最大的优势是什么呢？  **强（hao）大（kan）**  。

## 下载安装
代码是开源的。链接🔗： [Download](https://github.com/jwenjian/lucky-you/releases)
![](https://cdn.jsdelivr.net/gh/Tan35/ImgHosting/Tan35-PIC/3.jpg)
不同系统选择不同的安装包下载即可  
>**注**：

|系统说明|安装包后缀名|
|:----:|:----:|
|Windows|.msi|
|Ubuntu|.deb|
|Macos|.dmg|

---

## 使用步骤
![主界面](https://pic.downk.cc/item/5f37b0fe14195aa594fe21cd.jpg)

---  
### 事前准备
你要准备好抽取对象的照片和名字，照片最后会被软件裁切为正方形，毕竟本意也是个“电子花名册”，下面以抽取三个人（张三，李四，欧阳六）为例子进行展示
### 开始！
按下软件主界面中间的`Select images(选择图片)`即可进行抽取对象的选择，然后按开始便可以享受抽取的快乐 
![](https://pic.downk.cc/item/5f37bb7114195aa594013581.gif)
### 软件小tips
+ 软件设计默认为英文，右上角**第二个**按钮可进行语言的切换，可切换到简体中文
+ 软件支持深色模式，右上角**第五个**按钮可实现浅色模式与深色模式的切换
+ 声音是老虎机的声音，比较有趣，右上角**第一个**按钮可进行声音开关操作
+ 选取的图片格式可以是：.jpg,.jpeg,.png,.gif（.ico也可以!）
+ 选取的图片不宜过大，并不是不能过大，测试过7M的照片还是可以的，至于作者所说的不宜过大应该是在抽取过程中，如果图片过大会使得图片动画过渡不自然，最终抽取效果不佳
+ 选取的照片张数作者并没有说，不过测试过50张也是没有问题的
+ 当然你也可以请作者喝杯咖啡，选择右上角**第四个**按钮  

### 第三个按钮呢？
软件**第三个**按钮为设置抽取的规则  

![](https://cdn.jsdelivr.net/gh/Tan35/ImgHosting/Tan35-PIC/Snipaste_2020-11-22_17-12-45.jpg) 

这个规则直白点说就是：**上面的例子中，张三/李四/欧阳六是否可以被重复抽中多次**。然而更让我意想不到的是（~~愚钝的我~~）,在选择否之后，软件在抽取一个对象之后，会将此抽中对象从抽取列表中删除，然后进行列表中剩余对象的抽取。（我本以为这个规则的意思是在多次抽取的过程中，同一个对象是否能被多此抽中）如图，我在选择否之后再次进行抽奖。  

![](https://pic.downk.cc/item/5f37c01914195aa594028f43.gif)  

可看到被抽中的对象一个个从抽奖列表中删除，直到最后剩下张三不再进行抽奖。  
其实不难理解，我觉得这也应该是定下这个规则之后的抽奖逻辑，当然选择否之后不从列表删除抽中对象这个逻辑也是没有问题的。

## 最后
在写下这篇博客的时候，作者对于此应用在Windows下的适配还没有完全解决好，Windows系统安装完之后还是不能正常使用，只能通过作者提供的方法使用[PWA应用](https://luckyyou.netlify.app/)。我也算是和这位作者有点缘份，作者在少数派发表文章之后我就发现了问题并求教作者，给作者提供Windows下LuckyYou不能运行的具体问题，在交流之中可以看出是一位比较负责的作者了。最后希望Windows系统下的LuckyYou可以尽快修复bug，毕竟这软件真不错，无论是界面、UI还是主要功能，当然也希望作者可以加入更多额外功能，比如某网友说的从 Excel 导入学号姓名作为“抽奖”的另一种方法，也可以制定更多抽奖的规则。

![](https://pic.downk.cc/item/5fba2cfcb18d6271139caaaf.jpg)
![](https://pic.downk.cc/item/5fba2cfcb18d6271139caab6.jpg)
