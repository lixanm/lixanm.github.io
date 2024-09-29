---
title: python学习
date: 2024-09-28 10:34:00 +0800
categories: [随笔]
tags: [生活]
pin: true
author: 理性暗面

toc: true
comments: true
typora-root-url: ../../lixanm.github.io
math: false
mermaid: true

image:
  src:
  alt: 

---

# python学习

# 字符串

## 1.字符串三种定义方式

```python
a='1'
b="1"
c='''1'''
print(c)
#输出：1
```

## 2.字符串拼接

字符串+字符串

## 3.字符串格式化

````python
a=1
b="123%s"%a
print(b)
#输出：1231

'''
%s   占位字符串
%d   占位整数
%f   占位浮点数
'''

name='理性暗面'
year=2024
price=19.99
c="我是%s,今年是%d,%f" % (name,year,price)
print(c)
#输出:我是理性暗面,今年是2024,19.990000
````

## 4.字符串格式化的精度控制

```python
'''
%m.n
m:控制宽度，要求是数字
n:控制精度，会  四舍五入
'''
a=12345
b=12.1234567
print("%10d"%a)
print("%.3f"%b)
#输出:     12345
#输出:12.123
```

## 5.字符串格式化--快速写法

```python
name= "理性暗面"
year=2004
price=19.99
print(f"我是{name}，今年{year},{price}")
#输出:我是理性暗面，今年2004,19.99
```

```python
name= "理性暗面"
year=2004
price=19.99
print(f"我是{name}，今年{year},{price:.1f}")
#输出:我是理性暗面，今年2004,20.0
```

## 6.对表达式进行格式化

```python
#表达式：一条具有明确执行结果的代码语句
print("%d" % (1*1))
print(f"{1*1}")
print("%s" % type('字符串'))
'''
输出:1
1
<class 'str'>
'''
```

# 数据输入

```python
#input()函数的使用
name=int(input("请输入你的年龄："))
```

# python判断类型

## 1.布尔类型和比较运算符

```python
a=true
```

## 2.if语句的基本格式

````python
age=30
if age>=18:
    print("age>=18")
b=2
````

## 3.if else

```python
a=8
if a!=0:
	a=1
else:
	a=0
```

## 4.if elif else

```python
```

# python循环语句

## 1.while

```python
i=0
while i<100:
    print("小美，我喜欢你")
    i+=1
```

## 2.for

```python
'''
while循环的循环条件是自定义的，自行控制循环条件
for循环是对一批内容进行逐个处理
'''
name="itheima"
for x in name:
    print(x)
```

## 3.for循环的range语句

```python
#range(5)=[0,1,2,3,4]
'''
range(num1,num2,num3)
起始，结尾，步长
range(5,10,2)=[5,7,9]
'''

#range语法1
for x in range(10):
    print(x)
```

## 4.for循环临时变量作用域

```python
i=0
for i in range(5):
    print(i)
print(i)
```

## 5.for循环打印99乘法表

```python
for i in range(1,10):
    for j in range(1,i+1):
        print(f"{i}*{j}={i*j}\t",end="")
    print()
```

## 6.continue和break

```python
#暂时跳过某次循环，直接进行下一次--continue
#提前退出循环，不再继续--break
```

# 函数

## 1.介绍

```python
def my_len(data):
    count=0
    for i in data:
        count+=1
    print(f"{data}的长度为{count}")

a="1234567"
b="12345"
c='123'
my_len(a)
my_len(b)
my_len(c)
```











































