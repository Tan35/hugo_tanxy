---
date: 2020-11-30
linktitle: How to draw a diamond
menu:
  main:
    parent: tutorials
title: Linear planning for drawing rhombuses
weight: 10
---

## 前言

最近在学习写shell脚本的时候，遇到了一道题，是关于写菱形的。与刚学C语言for循环输出菱形的思路不一样，这个shell脚本用了高中数学线性规划的原理，突然就觉得这种思路还挺有意思的，那么就记录下来吧。

## 回顾

太久没有使用C语言了，于是就试着用以前的思路先输出菱形试试。代码如下，有部分注解

```c
#include<stdio.h>
#include<stdlib.h>

int main()
{
	int a, b, c, d, e, f;//对角线长度，上行数，空白数，星号数，中线
	printf("请不要输入非数字\n");
	A:printf("请输入菱形对角线长度（必须是奇数），离开请输入0：");
	scanf("%d", &a);
	if (a == 0)//输入0即结束程序
	{
		return 0;
	}
	if (a % 2 == 0)//确认是奇数才继续执行
	{
		goto A;
	}
	f = (a + 1) / 2;//中线值等于对角线长度+1除以2
	for (b = 1;b <= f;b++)// 画出菱形上半部（含最中间那一行）
	{
		for (d = f - b;d > 0;d--)//画空白
		{
			printf(" ");
		}
		for (e = 1;e <= 2 * b - 1;e++)//画星号
		{
			printf("*");
		}
		printf("\n");//换行
	}
	for (b = f - 1;b > 0;b--)
	{
		for (d = f - b;d > 0;d--)//画空白
		{
			printf(" ");
		}
		for (e = 1;e <= 2 * b - 1;e++)//画星号
		{
			printf("*");
		}
		printf("\n");//换行
	}
	goto A;//继续画下一个菱形
}
```

当然这也是最基本的思路，还有更加简单的思路。

## 线性规划？
没有接触这个词大概有两三年了吧，突然听到还蛮惊喜的。说回正题，其实思路也非常明确。确定图形，建立直角坐标系，求出图形的边的函数表达式。这里就可能意识到，只要在稍微改一下代码，就可以在空心菱形
和实心菱形中切换了，来看看代码吧。

```shell
#!/bin/bash
read -p "请输入对角线*号个数：" number
r=(number-1)/2
for ((y=0; y<=2*r; y++))
do
    for ((x=0; x<=2*r; x++))
    do
            if((y>=-x+r && y<=-x+3*r && y<=x+r && y>=x-r))
        then
            echo -n "*"
        else
            echo -n " "
        fi
    done
    echo " " 
done
```

## 写在最后
线性规划的思想看上去 虽然思路不错，但是仔细一想好像也没简单了多少，只是单纯的换了一种思路。但是这种思想却又能画出其他花里胡哨的图形，比如说椭圆、心形等等。这是最初的思路解决不了的。