---
title: 「python」- 流程控制语句
date: 2020-02-22 15:12:25
description: 任何一个程序之所以称为程序，他总有一个逻辑在里面，流程控制语句就是来控制程序的流程
categories: 
- python
tags:
- 流程控制语句
- if语句
- python基础
top_img: https://pic.downk.cc/item/5f0298e714195aa594caa140.jpg
cover: https://pic.downk.cc/item/5f030a3e14195aa594ff3f57.jpg
highlight_shrink: false
---


# python流程控制语句
>根据条件不同执行不同的代码是程序非常常见的也是非常重要的行为

## 布尔值
### 回顾 - 关系运算符
| 符号 |说明|
|:----:|:----:|
|>   |大于|
|<   |小于|
|>=  |大于等于|
|<=  |小于等于|
|==  |相等|
|！= |不等|

关系运算符最终得出的结果返回的就是布尔值(boolean)，而所谓的布尔值也就是`False`和`True`两个,比如说  `print(12>5)# True`，`print(5>12)# False`，`True` 和 `False` 是python里面的关键字（要么是真的要么是假的）。

if 语句就是依靠布尔值来工作的

```python
if 布尔值:
    为True时执行的语句
else 布尔值:
    为False时执行的语句
```
---


来看一下关于if的所有内容举例代码：

```python
hungry = True              #当我规定hungry为真的时候
money = 5                  #定义我现在只有五块钱

if hungry:                #当hungry为真的时候，这里开始运行
    if money < 5:         #if之后再if，if是可以嵌套的，当hungry为真，且money<5的时候运行
        print('别吃了饿着吧')
    elif money < 10:      #当hungry为真，且money>5 同时小于10的时候运行
        print('吃馒头')
    elif money < 20:      #当hungry为真，且money>10 同时小于20的时候运行
        print('吃面')
    elif money < 30:      #当hungry为真，且money>20 同时小于30的时候运行
        print('吃饭')
else：                    #这个else 是对齐上面的大的if的，所以这里是hungry为假的时候运行
    print('接着工作')
```
---

## 总结
1. if语句是可以嵌套的，python中没有`switch`
2. 如果hungry为`False`就会执行下下面的"接着工作"。
3. 为什么hungry为`False`就会执行下面的"接着工作"?if 和 else，所以再次强调python的<u>缩进很重要</u>，如果上面的`else` 和最上面的`if`缩进格数不一样(通俗来讲就是不对齐的话就会报错),而对于缩进的格数没有严格的规定，只要在你相同逻辑下的语句缩进相同格数就行。
4. python中`if`是必须的但是`else`不是必须的比如说

```python
if hungry == True:
    print('快去吃饭')
```
---





