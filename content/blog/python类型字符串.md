---
title: 「python」- 字符串
date: 2019-06-12 10:21:34
description: python中没有所谓的字符类型，一个字符也是字符串，没有字符也是字符串（空字符串）
categories: 
- python
tags:
- 字符串
- python基础
top_img: https://pic.downk.cc/item/5f02986f14195aa594ca4810.jpg
cover: https://pic.downk.cc/item/5f030a1c14195aa594ff2d57.jpg
highlight_shrink: false
---



# python类型 - 字符串
1. python中的字符串就是一串字符
2. python中没有单独的字符类型(c和java有),<u>一个字符也是字符串、没有字符也是字符串</u>
3. 字符串很多操作和`list`、`tuple`是通用的，Python称之为`sequence（序列)`


## 创建字符串
1. python中<u>单引号和双引号没有区别</u>。

+ 例子：

```python
    a = 'abc'
    b = "abc"

    print(a == b)

    #输出： True
```
---

2. 字符串是大小写敏感的，也就是<u>`'Abc'`和`'abc'`是不同的</u>
3. 可以用str构造函数来创建字符串。
+ 例子：

```python
user1 = str() 
#等价于user = '',等价于user = ""。
```
---

值得注意的是：python多次创建一个字符串，并不会创建多个副本（相对于Java、c++、js而言）。

## Python字符串都是静态字符串

无论用任何方式“创建”字符串，其实得到的是<u>同一个对象</u>

+ 例子：

```python
#id(..)函数，可以获取对象在内存中的地址（也叫指针）
a = '123'
b = "123"
c = str('123')
d = '1'+'23'
e = str('1'+'23')

print(id(a))
print(id(b))
print(id(c))
print(id(d))
print(id(e))

#  1291309978928
#  1291309978928
#  1291309978928
#  1291309978928
#  1291309978928
```
---

只要字符串是相同的，无论用任何方法创造，创造出来都是一样的，不会创造副本。

## 字符串运算符
1. 索引的作用：找字符串中某一位东西。  
>注：计算机中的序号，都是从0开始。

+ 例子：

```python

    s1 = 'abc'
    print(s1[0])

    #输出 ：a
```
---

2. 连接   
只有字符串可以连接。

+ 例子：

```python
    a = 'abc'
    b = 'ddd'

    print(a+b)
   # 输出： abcddd

   #!只需记住不能和不同类型一起加。
   #print(12+'abc')会报错。
```
---

3. 重复
除了`+`和`*`，其他数学运算符对字符串不适用。

+ 例子：

```python
print('abc'*5)
#abcabcabcabcabc
```
---




## 字符串截取
可以截取字符串中的一部分。

**语法：str1[start:end]**  
+ 用法1：**起点、终点**  

+ 例子：

```python
    s1 = 'abcdefg'
    print(s1[0:3])----取索引0-3的内容

    #输出:abc------顾头不顾尾，不包含索引3的对象
```
---

+ 用法2：**起点**  
+ 例子：

```python
    s1 = 'abcdefg'
    print(s1[3:]) 
    #取索引3到结尾的内容
    #输出：defg
```
---

+ 用法3：**终点**  
+ 例子：

```python
s1 = 'abcdefg'
print(s1[:5])
#取索引0-5的内容，顾头不顾尾

#输出：abcde
```
---

+ 用法4： **神经病版**  
+ 例子：

```python
s1 = 'abcdefg'
print(s1[:])
#取字符串所有内容

#输出：abcdefg

#字符串是静态的，所以用法4毫无意义，但对其他数据结构，却很有用。
```
---


## 字符编码
任何字符在计算机中，都会表示为一个数字，这就是字符编码。由于历史原因，其实有很多种编码  。
<u>ACSII编码  
gb2312:简体中文  
GBK:简体中文+繁体中文  
shift_jis:日文</u>
但是**Unicode**（统一编码)比较特殊，<u>囊括了人类所有语言、符号</u>，而且为未来的语言预留空间。
>注：**utf-8是Unicode的一种实现**



## 操作编码
+ **字符->编码--`ord()`**
```python
ord('a')  #97
ord('智')  #26234
```
---

+ **编码->字符--`chr()`**
```python
chr(97)  #'a'
chr(26234)  #'智'
```
---

+ **`in` 和 `not in`**
>判断字符串有没有/是否存在某个东西
```python

    s1 = 'hello world'
    print('h'in s1)
    print('word'in s1)

#输出：
#True
#False
```
---

## 字符串比较
1. 这种比较本质上是比较其字符编码。
2. 先比较第0个字符编码，如果相同就比较第二个，直到不同为止。
```python
print('app'<'bear')
#输出 ：True
print('apple'>'apply')
#输出：False
print('Apple' > 'apple')
#输出：False
print('abc' >'')
#输出：True
```
---

空字符串本质上第一位字符编码是0。


## 字符串循环
```python
str1 = 'Hello'
for s in str1:
#s称之为循环变量，简单来说就是把字符串里面的每个字符以s来丢给你。
	print(s)

#输出：
#H
#e
#l
#1
#o
#当然也说过python字符串里面没有真正意义上的字符，所以上面打印出来：

print(type(s))
#输出：<class'str'>还是个字符串
```
---


## 字符串检测

|检测方法|说明|
|:----:|:----:|
|isalnum() |  是否为字母或数字|
|isalpha()|   是否为字母|
|isdigit() |  是否为数字|
|isidentifier()|  是否是合法标识符|
|islower() |   是否为全小写|
|isupper()  |     是否为全大写|
|isspace() |      是否为全标识符|

+ 用法举例：

```python
    'aaa'.isdigit()    #False
    'aaa'.isappha()    #True
```
---

## 字符串搜索

|方法|说明|
|:----:|:----:|
|find()    | 从左边找，找到返回下标，没找到返回-1|
|rfind()   |       从右边找，找到返回下标，没找到返回-1|
|count(str)    |   计数|
|startswith(str) | 是否以str开头|
|endswtih(str) |   是否以str结尾|

+ 用法举例：
```python

    s1 = 'abcddef'
    print(s1.find('d'))
    print(s1.find('w'))
    #输出：3，只会查找从左开始找的第一个。
    #输出：-1

    print(s1.count('dd'))
    #输出：1，出现了一次。

    url = 'http://www.baidu.com'
    print(url.startswith('http://'))
    #判断url是否为一个网址，实际用途可以为判断用户输入是否正确。
```
---



#字符串转换
|方法|说明|
|:----:|:----:|
|upper() | 转为大写|
|lower()|  转为小写|
|swapcase() | 反转大小写|
|capitalize()|  首字母大写|
|title()|  每个单词首字母大写|
|replace(old,new) | 替换|


+ 用法举例:
```python
    'aBeDf'.lower()    #abedf 
    #!!最常用replace(old,new)，抓取数据有用
    'hello world,i am came'.replace('a','A')
    #'hello world,i Am cAme'
```
---






 

