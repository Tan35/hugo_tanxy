---
title: 「python」- 数据类型转换
date: 2020-02-21 18:24:34
description: 各种数据类型之间都可以转换的
categories: 
- python
tags:
- 数据类型
- python基础
top_img: https://pic.downk.cc/item/5f0298dc14195aa594ca9af5.jpg
cover: https://pic.downk.cc/item/5f030a3914195aa594ff3c91.jpg
highlight_shrink: false
---


# python之数据类型转换
>直接用代码来说明

``` python
s = '5.8'                 #定义一个字符串
a = 5                     #定义一个变量=5
b = 5.8
print(float(s)+1.6)       #7.4   把字符串转换为浮点型之后与1.6相加得到 7.4
print(float(a))          #5.0   把整型变量转换为浮点型
print(int(b))            #5     把float类型转换为int类型--这里只是截取整数部分，并非四舍五入
print(str(a)+s)          #55.8  注意这里并非数值55.8，只是将5转换为字符串类型然后和5.8拼接

print(round(3.5))         #4   这才是四舍五入
print(round(3.2))         #3    四舍五入
```
---








