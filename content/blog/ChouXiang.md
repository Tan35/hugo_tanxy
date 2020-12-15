---
author: "Tanxy"
date: 2020-12-15
linktitle: Matrix Series
menu:
  main:
    parent: tutorials
title: 抽象矩阵求逆矩阵
weight: 10
---

> <font size="4" color="#888888">线性代数基础，抽象矩阵求逆矩阵</font>

### 解法
「**凑**」,<mark>从高次幂到低次幂依次凑</mark>，但不是强硬的凑。

### 例题

已知n阶矩阵 A 满足 A²(A-2E)=3A+E,证明 A+E 可逆，并求 (A+E)<sup>-1</sup>。

```
解：由已知得  
	A²(A-2E)-3A-E=0  
	-> A²-2A²-3A-E=0  
	-> (A³+A²)-3A³-3A-E=0  
	-> A²(A+E)-3(A²+A)=E  
	-> A²(A+E)-3A(A+E)=E  
	-> (A²-3A)(A+E)=E  

```
所以 A+E 可逆，且(A+E)<sup>-1</sup> = A²-3A。  
上面这道题告诉我们，有括号就乘进去，然后从高次方开始凑。


---

	
	