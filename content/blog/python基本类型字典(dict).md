---
title: 「python」- 字典
date: 2019-08-13 10:28:25
description: 字典本质上是一个键值对，比如用户名->用户资料
categories: 
- python
tags:
- 字典
- python基础
top_img: https://pic.downk.cc/item/5f0298a814195aa594ca7360.jpg
cover: https://pic.downk.cc/item/5f030a2b14195aa594ff34f5.jpg
highlight_shrink: false
---

# python学习笔记之字典
+ 要唯一，最好是数字。
+ 字典的作用：找东西。`key`很关键，要定好。
+ 字典用于存储“键值对”，用于快速获取、添加、删除、修改某个值，类似于PHP的联合数组、Java的`HashMap`、JS的`json`，用户名->用户资料等等。
+ 所有语言中的字典，都是基于Hash、二叉树或其他类似结构的一类无序数据结构，目的就是为了<u>增加数据访问的速度</u>。

## 创建字典
在Python中，有两种方式创建字典。

1. 方法1：直接写。
```python
    d = {
        "name": "张三",
        "age" : 35,
        "gender": "男"
    }

    print(d['gender'])  #男
    print(d['age'])  #35
```
---

2. 方法2：构造器
```python
   d2 = dict([
        ['name','张三'],
        ['age',35],
        ['gender','男']
    ])
```
---

## 字典的增删改查

+ 例子：
```python
d = {
        "name": "张三",
        "age" : 35,
         "gender": "男"
    }

d['height'] = 185 #增加身高为185
del d['gender'] #删除性别
d['age'] -= 5# 修改岁数减少5

#循环
for item in d:
    print(item)
    
#输出：
#name 
#age
#gender
            
print(key + ":" + str(d[key]))
```
---


1. 要全部输出（key和value），可以进行序列的拼接。
2. 因为35是数字（整型），所以要转换为字符串。

### 长度：
```python
d = {
        "name": "张三",
        "age" : 35,
        "gender": "男"
    }
print(len(d))
#输出：3
```
---

可以理解为3个东西，3个键值对。


### 是否相等
+ 顺序对字典毫无意义  
+ 比较的是`key`，以及`key`后面的`value`是否相同。


### in操作
dict 的`in`操作,<u>检测的是key不是value</u>。

## 字典的方法

|方法|说明|
|:----:|:----:|
|clear() |   清空字典|
|keys()  |   返回所有key |    
|values() |  返回所有value|    
|get(key) |  索引，类似于[]|
|pop(key) |  删除，类似于上面的del|




    





