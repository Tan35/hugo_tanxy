---
author: "Tanxy"
date: 2020-12-16
linktitle: Matrix Series
menu:
  main:
    parent: tutorials
title: 抽象矩阵求逆矩阵
weight: 10
---

> <font size="3" color="#888888">线性代数基础，<b>抽象矩阵求逆矩阵</b></font>

### 解法

1. 常规解法：「**凑**」,<mark>从高次幂到低次幂依次凑</mark>，但不是强硬的凑。下面来看两个例题体验一下「凑」。当涉及到两个矩阵的时候，要学会用<u>左乘或者右乘某个矩阵的逆</u>（=E）来达到凑的效果。
2. **先斩后奏法**：先凑出结果，再装模作样写过程。这个方法在B站上看到的，觉得比较适合用于选择题或者填空题，或者遇到一些你想不出来怎么凑的题目的时候，下面会细说。

### **常规解法**

### 例题1

已知n阶矩阵 A 满足 A²(A - 2E) = 3A + E,证明 A+E 可逆，并求 (A+E)<sup>-1</sup>。

<pre><code>
解：由已知得  
	A²(A-2E)-3A-E=0  
	-> A³-2A²-3A-E=0  
	-> (A³+A²)-3A³-3A-E=0  
	-> A²(A+E)-3(A²+A)=E  
	-> A²(A+E)-3A(A+E)=E  
	-> (A²-3A)(A+E)=E  

<strong>所以 A+E 可逆，且(A+E)<sup>-1</sup> = A²-3A。</strong>
</code>
</pre>

---

### 例题2

若矩阵A满足等式  A² + 5A = 3E ,则 A<sup>-1</sup> = ? , (A - 3E)<sup>-1</sup> = ?


<pre><code>
(1)解：由已知得  
	A²+5A=3E
	-> A(A+5E) = 3E
	-> A(A+5E)/3 = E

<strong>所以 A 可逆，且A<sup>-1</sup> = (A+5E)/3。</strong>

</code>
</pre>


<pre><code>
(2)解：由已知得  
	A²+5A=3E
	-> A²+5A-3E = 0
	-> A(A-3E) + 8A -3E = 0
	-> A(A-3E) + 8(A-3E) + 21E = 0
	-> (A-3E)[-(A+8E)]/21 = E

<strong>所以 A-3E 可逆，且 (A-3E)<sup>-1</sup> = -(A+8E)/21 </strong>
</code>
</pre>

---

### 例题3

设矩阵A = 
<svg xmlns="http://www.w3.org/2000/svg" width="12.101ex" height="8.597ex" viewBox="0 -2150 6028 3800" xmlns:xlink="http://www.w3.org/1999/xlink" aria-hidden="true" style=""><defs><path id="MJX-48-TEX-S4-239B" d="M837 1154Q843 1148 843 1145Q843 1141 818 1106T753 1002T667 841T574 604T494 299Q417 -84 417 -609Q417 -641 416 -647T411 -654Q409 -655 366 -655Q299 -655 297 -654Q292 -652 292 -643T291 -583Q293 -400 304 -242T347 110T432 470T574 813T785 1136Q787 1139 790 1142T794 1147T796 1150T799 1152T802 1153T807 1154T813 1154H819H837Z"></path><path id="MJX-48-TEX-S4-239D" d="M843 -635Q843 -638 837 -644H820Q801 -644 800 -643Q792 -635 785 -626Q684 -503 605 -363T473 -75T385 216T330 518T302 809T291 1093Q291 1144 291 1153T296 1164Q298 1165 366 1165Q409 1165 411 1164Q415 1163 416 1157T417 1119Q417 529 517 109T833 -617Q843 -631 843 -635Z"></path><path id="MJX-48-TEX-S4-239C" d="M413 -9Q412 -9 407 -9T388 -10T354 -10Q300 -10 297 -9Q294 -8 293 -5Q291 5 291 127V300Q291 602 292 605L296 609Q298 610 366 610Q382 610 392 610T407 610T412 609Q416 609 416 592T417 473V127Q417 -9 413 -9Z"></path><path id="MJX-48-TEX-N-31" d="M213 578L200 573Q186 568 160 563T102 556H83V602H102Q149 604 189 617T245 641T273 663Q275 666 285 666Q294 666 302 660V361L303 61Q310 54 315 52T339 48T401 46H427V0H416Q395 3 257 3Q121 3 100 0H88V46H114Q136 46 152 46T177 47T193 50T201 52T207 57T213 61V578Z"></path><path id="MJX-48-TEX-N-2212" d="M84 237T84 250T98 270H679Q694 262 694 250T679 230H98Q84 237 84 250Z"></path><path id="MJX-48-TEX-N-32" d="M109 429Q82 429 66 447T50 491Q50 562 103 614T235 666Q326 666 387 610T449 465Q449 422 429 383T381 315T301 241Q265 210 201 149L142 93L218 92Q375 92 385 97Q392 99 409 186V189H449V186Q448 183 436 95T421 3V0H50V19V31Q50 38 56 46T86 81Q115 113 136 137Q145 147 170 174T204 211T233 244T261 278T284 308T305 340T320 369T333 401T340 431T343 464Q343 527 309 573T212 619Q179 619 154 602T119 569T109 550Q109 549 114 549Q132 549 151 535T170 489Q170 464 154 447T109 429Z"></path><path id="MJX-48-TEX-N-30" d="M96 585Q152 666 249 666Q297 666 345 640T423 548Q460 465 460 320Q460 165 417 83Q397 41 362 16T301 -15T250 -22Q224 -22 198 -16T137 16T82 83Q39 165 39 320Q39 494 96 585ZM321 597Q291 629 250 629Q208 629 178 597Q153 571 145 525T137 333Q137 175 145 125T181 46Q209 16 250 16Q290 16 318 46Q347 76 354 130T362 333Q362 478 354 524T321 597Z"></path><path id="MJX-48-TEX-S4-239E" d="M31 1143Q31 1154 49 1154H59Q72 1154 75 1152T89 1136Q190 1013 269 873T401 585T489 294T544 -8T572 -299T583 -583Q583 -634 583 -643T577 -654Q575 -655 508 -655Q465 -655 463 -654Q459 -653 458 -647T457 -609Q457 -58 371 340T100 1037Q87 1059 61 1098T31 1143Z"></path><path id="MJX-48-TEX-S4-23A0" d="M56 -644H50Q31 -644 31 -635Q31 -632 37 -622Q69 -579 100 -527Q286 -228 371 170T457 1119Q457 1161 462 1164Q464 1165 520 1165Q575 1165 577 1164Q582 1162 582 1153T583 1093Q581 910 570 752T527 400T442 40T300 -303T89 -626Q78 -640 75 -642T61 -644H56Z"></path><path id="MJX-48-TEX-S4-239F" d="M579 -9Q578 -9 573 -9T554 -10T520 -10Q466 -10 463 -9Q460 -8 459 -5Q457 5 457 127V300Q457 602 458 605L462 609Q464 610 532 610Q548 610 558 610T573 610T578 609Q582 609 582 592T583 473V127Q583 -9 579 -9Z"></path></defs><g stroke="currentColor" fill="currentColor" stroke-width="0" transform="matrix(1 0 0 -1 0 0)"><g data-mml-node="math"><g data-mml-node="mrow"><g data-mml-node="mo"><use xlink:href="#MJX-48-TEX-S4-239B" transform="translate(0, 996)"></use><use xlink:href="#MJX-48-TEX-S4-239D" transform="translate(0, -1006)"></use><svg width="875" height="382" y="59" x="0" viewBox="0 86.3 875 382"><use xlink:href="#MJX-48-TEX-S4-239C" transform="scale(1, 0.924)"></use></svg></g><g data-mml-node="mtable" transform="translate(875, 0)"><g data-mml-node="mtr" transform="translate(0, 1400)"><g data-mml-node="mtd"><g data-mml-node="mn"><use xlink:href="#MJX-48-TEX-N-31"></use></g></g><g data-mml-node="mtd" transform="translate(1500, 0)"><g data-mml-node="mo"><use xlink:href="#MJX-48-TEX-N-2212"></use></g><g data-mml-node="mn" transform="translate(778, 0)"><use xlink:href="#MJX-48-TEX-N-32"></use></g></g><g data-mml-node="mtd" transform="translate(3778, 0)"><g data-mml-node="mn"><use xlink:href="#MJX-48-TEX-N-30"></use></g></g></g><g data-mml-node="mtr"><g data-mml-node="mtd"><g data-mml-node="mn"><use xlink:href="#MJX-48-TEX-N-31"></use></g></g><g data-mml-node="mtd" transform="translate(1889, 0)"><g data-mml-node="mn"><use xlink:href="#MJX-48-TEX-N-32"></use></g></g><g data-mml-node="mtd" transform="translate(3778, 0)"><g data-mml-node="mn"><use xlink:href="#MJX-48-TEX-N-30"></use></g></g></g><g data-mml-node="mtr" transform="translate(0, -1400)"><g data-mml-node="mtd"><g data-mml-node="mn"><use xlink:href="#MJX-48-TEX-N-30"></use></g></g><g data-mml-node="mtd" transform="translate(1889, 0)"><g data-mml-node="mn"><use xlink:href="#MJX-48-TEX-N-30"></use></g></g><g data-mml-node="mtd" transform="translate(3778, 0)"><g data-mml-node="mn"><use xlink:href="#MJX-48-TEX-N-32"></use></g></g></g></g><g data-mml-node="mo" transform="translate(5153, 0)"><use xlink:href="#MJX-48-TEX-S4-239E" transform="translate(0, 996)"></use><use xlink:href="#MJX-48-TEX-S4-23A0" transform="translate(0, -1006)"></use><svg width="875" height="382" y="59" x="0" viewBox="0 86.3 875 382"><use xlink:href="#MJX-48-TEX-S4-239F" transform="scale(1, 0.924)"></use></svg></g></g></g></g></svg>,
B为3阶矩阵，且满足 2B<sup>-1</sup>A + 4E = A, 证明： B - 2E 可逆，并求 (B-2E)<sup>-1</sup> 。

<pre><code>
解:由已知得  
	2B<sup>-1</sup>A + 4E = A  
	-> (两边同时左乘B)   
	-> 2BB<sup>-1</sup>A + 4B = AB  
	-> 2A + 4B - AB = 0  
	-> 2A - AB + 4B = 0  
	-> A(2E-B) + 4B = 0  
	-> A(2E-B) + 4(B-2E) + 8E = 0  
	-> -A(B-2E) + 4(B-2E) = -8E  
	-> A(B-2E) - 4(B-2E) = 8E  
	-> (A-4)(B-2E) = 8E  
	-> (A-4)/8 * (B-2E) = E  

<strong>所以 (B-2E)<sup>-1</sup> 可逆，且 (B-2E)<sup>-1</sup> = (A-4)/8</strong>   
又因为A矩阵已知，代入即可得出结果。

</code>
</pre>



### **先斩后奏法**

#### 例题1

> <font size="3" color="#888888">还是拿上面的第三题来讲 </font>  


设矩阵A = 
<svg xmlns="http://www.w3.org/2000/svg" width="12.101ex" height="8.597ex" viewBox="0 -2150 6028 3800" xmlns:xlink="http://www.w3.org/1999/xlink" aria-hidden="true" style=""><defs><path id="MJX-48-TEX-S4-239B" d="M837 1154Q843 1148 843 1145Q843 1141 818 1106T753 1002T667 841T574 604T494 299Q417 -84 417 -609Q417 -641 416 -647T411 -654Q409 -655 366 -655Q299 -655 297 -654Q292 -652 292 -643T291 -583Q293 -400 304 -242T347 110T432 470T574 813T785 1136Q787 1139 790 1142T794 1147T796 1150T799 1152T802 1153T807 1154T813 1154H819H837Z"></path><path id="MJX-48-TEX-S4-239D" d="M843 -635Q843 -638 837 -644H820Q801 -644 800 -643Q792 -635 785 -626Q684 -503 605 -363T473 -75T385 216T330 518T302 809T291 1093Q291 1144 291 1153T296 1164Q298 1165 366 1165Q409 1165 411 1164Q415 1163 416 1157T417 1119Q417 529 517 109T833 -617Q843 -631 843 -635Z"></path><path id="MJX-48-TEX-S4-239C" d="M413 -9Q412 -9 407 -9T388 -10T354 -10Q300 -10 297 -9Q294 -8 293 -5Q291 5 291 127V300Q291 602 292 605L296 609Q298 610 366 610Q382 610 392 610T407 610T412 609Q416 609 416 592T417 473V127Q417 -9 413 -9Z"></path><path id="MJX-48-TEX-N-31" d="M213 578L200 573Q186 568 160 563T102 556H83V602H102Q149 604 189 617T245 641T273 663Q275 666 285 666Q294 666 302 660V361L303 61Q310 54 315 52T339 48T401 46H427V0H416Q395 3 257 3Q121 3 100 0H88V46H114Q136 46 152 46T177 47T193 50T201 52T207 57T213 61V578Z"></path><path id="MJX-48-TEX-N-2212" d="M84 237T84 250T98 270H679Q694 262 694 250T679 230H98Q84 237 84 250Z"></path><path id="MJX-48-TEX-N-32" d="M109 429Q82 429 66 447T50 491Q50 562 103 614T235 666Q326 666 387 610T449 465Q449 422 429 383T381 315T301 241Q265 210 201 149L142 93L218 92Q375 92 385 97Q392 99 409 186V189H449V186Q448 183 436 95T421 3V0H50V19V31Q50 38 56 46T86 81Q115 113 136 137Q145 147 170 174T204 211T233 244T261 278T284 308T305 340T320 369T333 401T340 431T343 464Q343 527 309 573T212 619Q179 619 154 602T119 569T109 550Q109 549 114 549Q132 549 151 535T170 489Q170 464 154 447T109 429Z"></path><path id="MJX-48-TEX-N-30" d="M96 585Q152 666 249 666Q297 666 345 640T423 548Q460 465 460 320Q460 165 417 83Q397 41 362 16T301 -15T250 -22Q224 -22 198 -16T137 16T82 83Q39 165 39 320Q39 494 96 585ZM321 597Q291 629 250 629Q208 629 178 597Q153 571 145 525T137 333Q137 175 145 125T181 46Q209 16 250 16Q290 16 318 46Q347 76 354 130T362 333Q362 478 354 524T321 597Z"></path><path id="MJX-48-TEX-S4-239E" d="M31 1143Q31 1154 49 1154H59Q72 1154 75 1152T89 1136Q190 1013 269 873T401 585T489 294T544 -8T572 -299T583 -583Q583 -634 583 -643T577 -654Q575 -655 508 -655Q465 -655 463 -654Q459 -653 458 -647T457 -609Q457 -58 371 340T100 1037Q87 1059 61 1098T31 1143Z"></path><path id="MJX-48-TEX-S4-23A0" d="M56 -644H50Q31 -644 31 -635Q31 -632 37 -622Q69 -579 100 -527Q286 -228 371 170T457 1119Q457 1161 462 1164Q464 1165 520 1165Q575 1165 577 1164Q582 1162 582 1153T583 1093Q581 910 570 752T527 400T442 40T300 -303T89 -626Q78 -640 75 -642T61 -644H56Z"></path><path id="MJX-48-TEX-S4-239F" d="M579 -9Q578 -9 573 -9T554 -10T520 -10Q466 -10 463 -9Q460 -8 459 -5Q457 5 457 127V300Q457 602 458 605L462 609Q464 610 532 610Q548 610 558 610T573 610T578 609Q582 609 582 592T583 473V127Q583 -9 579 -9Z"></path></defs><g stroke="currentColor" fill="currentColor" stroke-width="0" transform="matrix(1 0 0 -1 0 0)"><g data-mml-node="math"><g data-mml-node="mrow"><g data-mml-node="mo"><use xlink:href="#MJX-48-TEX-S4-239B" transform="translate(0, 996)"></use><use xlink:href="#MJX-48-TEX-S4-239D" transform="translate(0, -1006)"></use><svg width="875" height="382" y="59" x="0" viewBox="0 86.3 875 382"><use xlink:href="#MJX-48-TEX-S4-239C" transform="scale(1, 0.924)"></use></svg></g><g data-mml-node="mtable" transform="translate(875, 0)"><g data-mml-node="mtr" transform="translate(0, 1400)"><g data-mml-node="mtd"><g data-mml-node="mn"><use xlink:href="#MJX-48-TEX-N-31"></use></g></g><g data-mml-node="mtd" transform="translate(1500, 0)"><g data-mml-node="mo"><use xlink:href="#MJX-48-TEX-N-2212"></use></g><g data-mml-node="mn" transform="translate(778, 0)"><use xlink:href="#MJX-48-TEX-N-32"></use></g></g><g data-mml-node="mtd" transform="translate(3778, 0)"><g data-mml-node="mn"><use xlink:href="#MJX-48-TEX-N-30"></use></g></g></g><g data-mml-node="mtr"><g data-mml-node="mtd"><g data-mml-node="mn"><use xlink:href="#MJX-48-TEX-N-31"></use></g></g><g data-mml-node="mtd" transform="translate(1889, 0)"><g data-mml-node="mn"><use xlink:href="#MJX-48-TEX-N-32"></use></g></g><g data-mml-node="mtd" transform="translate(3778, 0)"><g data-mml-node="mn"><use xlink:href="#MJX-48-TEX-N-30"></use></g></g></g><g data-mml-node="mtr" transform="translate(0, -1400)"><g data-mml-node="mtd"><g data-mml-node="mn"><use xlink:href="#MJX-48-TEX-N-30"></use></g></g><g data-mml-node="mtd" transform="translate(1889, 0)"><g data-mml-node="mn"><use xlink:href="#MJX-48-TEX-N-30"></use></g></g><g data-mml-node="mtd" transform="translate(3778, 0)"><g data-mml-node="mn"><use xlink:href="#MJX-48-TEX-N-32"></use></g></g></g></g><g data-mml-node="mo" transform="translate(5153, 0)"><use xlink:href="#MJX-48-TEX-S4-239E" transform="translate(0, 996)"></use><use xlink:href="#MJX-48-TEX-S4-23A0" transform="translate(0, -1006)"></use><svg width="875" height="382" y="59" x="0" viewBox="0 86.3 875 382"><use xlink:href="#MJX-48-TEX-S4-239F" transform="scale(1, 0.924)"></use></svg></g></g></g></g></svg>,
B为3阶矩阵，且满足 2B<sup>-1</sup>A + 4E = A, 证明： B - 2E 可逆，并求 (B-2E)<sup>-1</sup> 。

<pre>
<code>

解题思路：
	不妨设 B<sup>-1</sup> = 1/b , A = a , E = 1。 
	那么原等式可写成
	2a/b + 4 = a -- ①,
	最后是求 
	1/b-2 --- ②
	
	
	所以就是怎么由 ①得到②
	变成了传统数学代数化的求解
	
	-> 两边同时乘 b
	-> 2a + 4b - ab = 0
	-> 2a + (4-a)b = 0
	-> (4-a)b = -2a
	-> b = 2a/a-4
	
	所以 1/b-2 = 1/8 * (a-4)
	即还原为 
	<strong>(B-2E)<sup>-1</sup> = 1/8 * (A - 4E)</strong>
	<HR>
	那我们就巧妙的得到了结果，
	很显然选择题和填空题可以到这里就结束了
	但是 如果是大题怎么办？
	
	我们可以<strong>逆推</strong>回去。
	<HR>
	我们得出的结果
	(B-2E)<sup>-1</sup> = 1/8 * (A - 4E)
	其实可以表达为
	(B-2E) * 1/8 * (A - 4E) = E
	展开得
	BA - 2A - 4B + 8E = 8E
	两边消掉 8E
	BA - 2A - 4B = 0 -- ③
	B
	那么这时候与原来的等式对比
	BA - 2A - 4B = 0 -- ③
	2B<sup>-1</sup>A + 4E = A -- ④
	就差了一个 B<sup>-1</sup>
	所以 ③ 左乘 B<sup>-1</sup>
	得到 A - 2B<sup>-1</sup>A - 4E = 0 -- ⑤
	那么其实 ⑤ 就是 ④ 移项过来的
	
	那么整个逆推思路已经完成了
	所以大题目的正推思路就很明显了
	就是类似于上面的常规解法。
	
</code></pre>




#### 例题2 
> <font size="3" color="#888888">李永乐线代辅导讲义 P45，例题2.14</font>

若A是n阶矩阵，满足 A² + 3A - 2E = 0, 则 (A+E)<sup>-1</sup> = ?

<pre><code>
按照刚才介绍的思路：
	不妨设：
	A = a, E = 1,
	则求 1/(a+1) = ?
	
	原式: a² + 3a - 2  = 0
	开始凑 a+1
	-> (a+1)² + a - 3 =0
	-> (a+1)² + (a+1) = 4
	-> (a+1)(a+2) = 4
	-> 1/a+1 = 1/4 * (a+2)
	即  (A+E)<sup>-1</sup> = 1/4 * (A+2E)
	这道题是填空题，所以到这里就结束了
	如果是大题，按照上面的思路逆推即可
</code></pre>


<div style="position:relative; padding-bottom:75%; width:100%; height:0">
    <iframe src="//player.bilibili.com/player.html?bvid=BV1dE411k7Pg&page=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true" style="position:absolute; height: 100%; width: 100%;"></iframe>
</div>

<div align=center>
<font size="2" color="#888888">先斩后奏法视频</font>
</div>

### 总结

从上面两题例题都可以感受到凑的魅力。

1. **做多了就明白什么是「不是强硬的凑」**。如第一题中拆开括号后 `A³-2A²-3A-E=0`, 肯定不能强硬的去直接凑`(A+E)³`, 在我理解就是降阶凑，把 `A³` 变为 `A²` 凑`(A+E)`, 即`A³->A²(A+E)`,这样做的好处是因为等式左边还有一个二阶的，可以进行加减凑。
然后二阶又继续降阶凑。
2. **从高次幂到低次幂依次凑**。这个在第二题展现的很好，`A²->A(A-3E)`, `8A -3E -> 8(A-3E) + 21E`, 虽然我表达的不是很好，但我自己懂了，毕竟是写给自己看的。就这样吧，再遇到比较好的题会继续补充。
3. 当涉及到两个矩阵的时候，要**学会右乘或者左乘某个矩阵的逆矩阵达到凑的效果**。第三题就能表现出来，从<code>2B<sup>-1</sup>A + 4E = A</code> 左乘 B 矩阵得到 <code> 2A + 4B = AB  </code>。
4. 选择填空题的时候可以优先选择**先斩后奏法**，强烈推荐！
<br>
<br>

	


<font size="3" color="#888888">持续更新中...♥</font> 

