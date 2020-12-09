---
title: 「python」- 数字
date: 2019-06-06 14:24:25
description: 三种类型：整数、浮点数、复数
categories: 
- python
tags:
- 数字
- python基础
top_img: https://pic.downk.cc/item/5f02984e14195aa594ca3624.jpg
cover: https://pic.downk.cc/item/5f030a1614195aa594ff2a71.jpg
highlight_shrink: false
---



# python中的数字

+ int 整数：23  
+ float 浮点数、小数：15.8   
+ complex 复数，：-1根号  


## 三种类型：
1. 整数：所有的整数都属于int类
```python
a=12
print(type(a))

#输出 <class 'int'>
```
---


### python3里面没有long，也用不着long

```c
//c语言中
int a //32位整数
long b //64位整数
long long c 128位整数
```
---

```python
#python的整数可以非常大
a = 999999999999999999999999999999
print(a)
输出：999999999999999999999999999999
```
---


2. 浮点数：所有浮点数都属于float类

```python
a = 12.5
print(type(a))
#输出<class'float'>
#python中没有double，也用不着double。
```
---


3. 复数：复数都是complex类
```python
a = 15+3j
b = 8-2j

print(a+b)
```
---


## 类型检测
```python
#type(x)可以用来检测类型
type(120)  #int
type(5.0)  #float
type(12+0j) #complex
```
---

## Python运算符

基本运算符（+-*/）和其他语言都一样，但也有些不一样的。

```python
#正常除法
16/5   #3.2
16%5   #1--余数

#整除
16//5  #3
```
---

## 幂操作
```python
print(3**100)  #两个*代表多少次方
#转个思路
print(9**0.5)   #9的二分之一次方就是开根号
```
---


## 扩展赋值
```python
a = 15
a = a + 5 #等价于 a += 5
print(a)
#输出： 20
```
---

## python没有`++` `--` 操作

`i++`  ==>  `i+=1
`i--`  ==>  `i-=1`

python没有自增、自减操作，也不需要


## 运算符优先级
```python
12+6/2  #15
(12+6)/2  #9
```
---

## 优先级表：
<u>括号 > 函数 > 列表/属性 > 数值运算 > 逻辑运算 > 赋值</u>


 

