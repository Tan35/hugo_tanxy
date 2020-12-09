---
title: 「python」- 列表
date: 2019-06-22 09:32:25
description: 列表（list）可以存任何东西，包括另一个list
categories: 
- python
tags:
- 列表
- list
- python基础
top_img: https://pic.downk.cc/item/5f02989214195aa594ca636e.jpg
cover: https://pic.downk.cc/item/5f030a2614195aa594ff31b7.jpg
highlight_shrink: false
---


# python 学习笔记之列表
列表跟字符串很像，只不过存的不是字符，可以是任何东西（甚至是另一个list）。


## 创建列表
+ 方法1:直接写。
```python
    l = [1,2,3,4]
```
---

+ 方法2：构造器。
```python
	l = list([1,2,3,4])
```
---

+ 也可以通过其他序列构造列表
```python
    l = list('abcd')  #l = ['a','b','c','d'] #把字符串转成列表
```
---


## 访问列表元素
(和访问字符串元素一样)。
```python
    l = [1,2,3,4,5,6]
    print(l[0])   #1
    print(l[3:5])  #3456
```
---


## 序列通用操作
字符串和`list`都是序列，所以会有很多操作可以通用（当然，也有不可通用的部分）。
+ 例子
```python
3 in [1,2,3]  #判断是否存在
3 not in [5,6,7]
[1,2,3]+[4,5,6] #连接
[1,2,3]*3       #重复
l[0]            #索引
len(l)          #长度
l(start:end)    #截取
for             #循环
max和min        #最大和最小值
sum(l)          #求和，str不可用
```
---

+ 例子：
```python
    s = 'asdfasdf'
    l = [1,2,3,4]

    print(len(s))  #8
    print(len(l))  #4
```
---

+ 例子：
```python
l = [12,5,8,99]
for item in l:
	print(item)
# 12
# 5
# 8
# 99
```
---

+ 例子：
```python
    l = [12,8,99,27]
    print(min(l))

    #输出：8

    l = [12,8,99,27,17]
    print(sum[l])

    #输出：163

    s = 'jlkjdkl'
    print(sum(s))

    #出错,字符串虽然是一个序列。因为每一元素是一个字，也是一个字符串，相加是不行的，本质上相加是数字去相加。
```
---

## 比较运算
```python
    l1 = [12,5,9]
    l2 = [8,99,99]

    print(l1>l2)
    #True
```
---

## list 专有操作
```python
   append(x)  #末尾添加
        l = [1,2,3]
        l.append(5) #l = [1,2,3,5]

   insert(index,x) #插入
        l = insert(0,5)  #l = [5,1,2,3]----在第0位插入5

   pop(i) #删除，默认不带参数是删除最后一个
        l.pop()     #l = [1,2]
        l.pop(0)    #l = [2,3]----带参数用，pop第几个-->删除第几个
   
   remove(x)   #删除，与pop的区别是，remove要你删除的是什么，不是第几个
        l.remove(1)  #l = [2,3]----我要删除1，不是位置就是删除里面的内容
   
   count(x)   #计数
        l = [12,5,8,8,8,12,5]
        print(l.count(12)) ----#2   有多少个2
        print(l.count(8))------#3   有多少个8
   
   index(x)  #查找
        l = [12,5,8,8,8,12,5]
        print(l.index(8)) --#2  ----8第一次出现是在第2位
        print(l.index(99))--#出错---99没有出现在列表里面      
   
   reverse()  #反转
        l = [1,2,3,4]
        l.reverse()
        print(l)  #----l = [4,3,2,1]

        ps:不能直接print(l.reverse())---这样会返回none，因为reverse()不是直接返回值，是修改了值，所以要再次打印
 
   sort()   #排序
        l = [12,88,9,27,6]
        l.sort()
        print(l) ---# l = [6,9,12,27,88]--默认从小到达排序
        #同理不能直接print(l.sort())
```
---


## 推倒式
推倒式是python非常有特色的一个表达式，其他语言几乎没有。(本质上)从一个序列生成另一个序列。跟循环很像。

+ 语法：[结果 for x in 序列if 条件]
+ 例子：
```python
        l = [1,2,3,4]
       #目标变成---> l2 = [6,7,8,9]
        
        l2 = [item+5 for item in l]
        print(l)
        print(l2)
        输出；[1,2,3,4]
              [6,7,8,9]
            ps:l2 = [1 for item in  l]
                输出：[1,1,1,1]----没有强制规定item一定要用
            甚至全部变成'abc' l2 = ['abc' for item in l]
        
        l1 = [1,2,3,4,5,6,7,8,9]
        l2 = [item*2 for item in l1 if item%3==0]
        print(l2)
        #输出:[6,12,18]
        #将原本数列*2 之后得到的数列 能被3整除的
```
---

推倒式非常适合用来“导出”某个数据，比如：从一组xpath中导出标题。




