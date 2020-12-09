---
title: 「python」- 数据类型和变量
date: 2019-06-04 13:45:21
description: python入门必了解的数据类型与变量
categories: 
- python
tags:
- 数据类型
- 变量
- python基础
top_img: https://pic.downk.cc/item/5f0298c414195aa594ca8c83.jpg
cover: https://pic.downk.cc/item/5f030a0e14195aa594ff267d.jpg
highlight_shrink: false
---



# Python入门 - 数据类型和变量
变量是用来存东西的。就像一个杯子用来装水,但是Python里面存的不是水，而存的是在哪能找到这个水，存的是引用，即变量用于引用内存中存储的对象。

## python中的一切都是“对象”（Object）
基本类型也是对象。

## Python是动态类型的

一个变量的类型可以变，可以存数字，过一会可以存字符串。

```python
a = 12
print(a)
	
a = 'abc'
print(a)
	
#输出：
#12
#abc
```
---
		  
## Python的变量无需声明

在第一次赋值的时候产生。

```java
//java中：
int a;
a = 12;
```
---

```python
#python中：
a = 12   # 即可
```
---

### python是强类型的
不能随便把一个数字和字符串放到一块去。

```python	
#连等
a = b = c = 12
#等价于
a = 12
b = 12
c = 12
	 
#再次说明：在python中，a并不保存值本身，而是引用这个值
```
---

其他语言比如c语言，你让他保存12到一个变量a里面，这个变量里面是真的存了这个12的值。


	
## 解构赋值（联合赋值）
```python
a,b,c = 12,5,8
```
---


说白了，就是可以同时给很多个变量赋值。可以做一些好玩的事情：

```python
a = 12
b = 5
print(a,b)

b,a = a,b
print(a,b)

#输出：
#12 5
#5 12
```
---	   

## Python基本数据类型

|数据类型|表示|
|:----:|:----:|
|数字|int，float|
|字符串|str|
|列表|list|
|元组|tuple|
|字典|dict|
|布尔值|bool|



```python
#接收用户输入
（python是强类型的）

name = input('请输入你的名字：')
print('你好'，+name)

输出：请输入你的名字：张三（这个张三是用户输入进去的）
      你好，张三
	  
#注：
age = input('你今年几岁')
year = 2018-int(age)   
#加int转换类型是因为input所输入进来的一切都是字符串，所以要转换为int

print('你是'+str(year)+'出生的')
#加str是因为year被上面转换成数字，这里'你是'是字符串，所以需要再转换
```
---
