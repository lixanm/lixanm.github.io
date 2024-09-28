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
name=input()
```

# python判断类型

## 1.布尔类型和比较运算符

```python
```











































