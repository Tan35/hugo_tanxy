---
author: "Tanxy"
date: 2021-04-14
linktitle: Stack
menu:
  main:
    parent: tutorials1
title: stack
weight: 10
---

## 栈与队列（四）-用栈实现表达式转换

### 中缀表达式转后缀表达式

1. 从左到右进行扫描，遇到操作数写出来，遇到运算符就把他入栈。
2. <u>入栈之前!</u>将扫描到的运算符和栈顶运算符比较，如果扫描到的运算符**小于或等于**栈顶运算符优先级，就把栈顶运算符出栈并写入当前结果表达式中。
3. 这个过程是一直循环的。即如果<u>~小于等于</u>，就出栈，写入结果表达式中，然后继续和新的栈顶运算符作比较，如果还是小于等于就继续出栈写入，这样一直进行下去，直到<u>~大于</u>，再将扫描到的运算符入栈。（栈空的时候也是直接入栈）
4. 对于表达式里含有括号的情况，遇到左括号直接入栈。当栈顶元素是左括号的时候，所有扫描到的运算符都入栈，当扫描到右括号的时候，执行一系列出栈操作即：把当前栈中从栈顶到左括号鹅元素全部出栈，并将其写入结果表达式中，括号不写，出栈的括号直接扔掉。
5. 最后当扫描完中缀表达式中的所有运算符的时候，若栈中还有剩余的运算符，则将其全部出栈，并写入结果表达式中。

![](https://cdn.jsdelivr.net/gh/Tan35/ImgHosting/Tan35-PIC/testzzh.gif)

```c
void infixToPostFix(char infix[], cahr s2[], int &top2)
{
    char s1[maxsize]; int top = -1;
    int i = 0;
    while(infix[i] != '\0')
    {
        if('0' <= infix[i] && infix[i] <= '9')
        {
            s2[++top2] = infix[i];
            ++i;
        }
        else if( infix[i] == '(')
        {
            s1[++top] = '(';
            ++i;
        }
        else if( infix[i] == '+' || infix[i] == '-' || infix[i] == '*' || infix[i] == '/')
        {
            if(top1 == -1 || s1[top1] == '(' || getPriority(infix[i]) > getPriority(s1[top1]))
            {
                s1[++top1] = infix[i];
                ++i;
            }
            else
                s2[++top2] = s1[top--];
        }
        else if( infix[i] = ')')
        {
            while (s1[top1] != '(')
                s2[++top2] = s1[top--];
            --top1;
            ++i;
        }
    }
    while ( top1 != -1)
        s2[++top2] = s1[top--];
}
```

### 中缀表达式转前缀表达式
>不同上面的是，是从右往左扫描，遇到右括号入栈，遇到左括号全部出栈（这里所说的全部是指把栈顶到右括号之间的元素全部出栈。

![](https://cdn.jsdelivr.net/gh/Tan35/ImgHosting/Tan35-PIC/testzzq.gif)

```c
void infixToPostFix(char infix[], cahr s2[], int &top2)
{
    char s1[maxsize]; int top = -1;
    int i = 0;
    while(infix[i] != '\0')
    {
        if('0' <= infix[i] && infix[i] [i] <= '9')
        {
            s2[++top2] = infix[i];
            --i;
        }
        else if( infix[i] == ')')
        {
            s1[++top] = ')';
            --i;
        }
        else if( infix[i] == '+' || infix[i] == '-' || infix[i] == '*' || infix[i] == '/')
        {
            if(top1 == -1 || s1[top1] == ')' || getPriority(infix[i]) >= getPriority(s1[top1]))
            {
                s1[++top1] = infix[i];
                --i;
            }
            else
                s2[++top2] = s1[top--];
        }
        else if( infix[i] = '(')
        {
            while (s1[top1] != ')')
                s2[++top2] = s1[top--];
            --top1;
            --i;
        }
    }
    while ( top1 != -1)
        s2[++top2] = s1[top--];
}
```

### 重要比较

|中缀转前缀|中缀转后缀|
|----|----|
|当前读取运算符优先级<mark>小于</mark>栈顶运算符优先级别出栈|当前读取运算符优先级<mark>小于或等于</mark>栈顶运算符优先级别出栈|


### 后缀表达式转前缀表达式
>每次扫描到一个运算符的时候，就把这个运算符所对应的两个子表达式移到运算符的右边即可。

![](https://cdn.jsdelivr.net/gh/Tan35/ImgHosting/Tan35-PIC/hzq0413.gif)