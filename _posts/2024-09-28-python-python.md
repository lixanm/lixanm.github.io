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

# 2.字符串

## 2.1.字符串三种定义方式

```python
a='1'
b="1"
c='''1'''
print(c)
#输出：1
```

## 2.2.字符串拼接

字符串+字符串

## 2.3.字符串格式化

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

## 2.4.字符串格式化的精度控制

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

## 2.5.字符串格式化--快速写法

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

## 2.6.对表达式进行格式化

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

# 3.数据输入

```python
#input()函数的使用
name=int(input("请输入你的年龄："))
```

# 4.python判断类型

## 4.1.布尔类型和比较运算符

```python
a=true
```

## 4.2.if语句的基本格式

````python
age=30
if age>=18:
    print("age>=18")
b=2
````

## 4.3.if else

```python
a=8
if a!=0:
	a=1
else:
	a=0
```

## 4.4.if elif else

```python
```

# 5.python循环语句

## 5.1.while

```python
i=0
while i<100:
    print("小美，我喜欢你")
    i+=1
```

## 5.2.for

```python
'''
while循环的循环条件是自定义的，自行控制循环条件
for循环是对一批内容进行逐个处理
'''
name="itheima"
for x in name:
    print(x)
```

## 5.3.for循环的range语句

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

## 5.4.for循环临时变量作用域

```python
i=0
for i in range(5):
    print(i)
print(i)
```

## 5.5.for循环打印99乘法表

```python
for i in range(1,10):
    for j in range(1,i+1):
        print(f"{i}*{j}={i*j}\t",end="")
    print()
```

## 5.6.continue和break

```python
#暂时跳过某次循环，直接进行下一次--continue
#提前退出循环，不再继续--break
```

# 7.函数

## 7.1.介绍

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

## 7.2.变量在函数中的作用域

```python
num=100
def testA():
    print(num)

def testB():
    global num
    #global   关键字声明a是全局变量
    num=200
    print(num)

testA()
testB()
```

## 7.3.ATM案例

```python
money=5000000
name=input("请输入姓名:")
def chaxun():
    print(f"当前余额{money}")
    a=int(input("按1返回主菜单"))
    if a==1:
        zhucaidan()
def chunkuan(ck):
    global money
    money+=ck
    chaxun()
    fanhui()
def qukuan(qk):
    global money
    money-=qk
    chaxun()
    fanhui()
def zhucaidan():
    print("请选择您要办理的业务：")
    print("1.查询余额")
    print("2.存款")
    print("3.取款")
    a=int(input("请输入序号:"))
    if a==1:
        chaxun()
    elif a==2:
        ck=int(input("请输入存款数量："))
        chunkuan(ck)
    elif a==3:
        qk=int(input("请输入取款数量："))
        qukuan(qk)
    else:
        print("报错")
        fanhui()
def fanhui():
    a=int(input("按1返回主菜单:"))
    if a==1:
        zhucaidan()
zhucaidan()
```

# 8.python数据容器

## 8.1.入门

```python
name_list = ['1','2','3','4']
'''
1.是否支持重复元素
2.是否可以修改
3.是否有序
等等
。。。
列表，元组，字符串，集合，字典
'''
```

## 8.2.列表list

```python
name_list=['1','2']

name_list1=[]
name_list2=list()

#嵌套列表
a=[[1,2,3],[4,5,6]]
#a[0][0]=1
#a[-1][-1]=6
```

## 8.3.列表的常用操作

```python
#1.列表的查询功能
'''
1.1.查找某元素的下标
语法：列表.index（元素）
'''
mylist=[1,2,3]
index=mylist.index(1)
print(f"1在mylist的下标索引值为：{index}")

#2.列表的修改功能
''
mylist[1]="lio"
'''
#3.列表的插入
'''
列表.insert(下标，元素)  #插入
'''
#4.尾部追加‘一个’元素
'''
mylist.append(4)
mylist.append([5,6,7])
'''
#5.尾部追加‘一批’元素
'''
mylist2=[1,2,3]
mylist.extend(mylist)
'''
#6.删除元素
'''
1.del 列表[下标]
2.列表.pop(下标)

#删除某元素在列表中的第一个适配项
列表.remove(元素)
my_list=[1,2,3,2,3]
my_list.remove(2)#第一个2被删
'''
#7.清空列表
'''
my_list.clear()
'''
#8.统计次数
'''
my_list.count("1")#"1"出现过几次
```

## 8.4.元组tuple

不被篡改

相当于只读的list

```python
a=(1,2,3,4,5)

a=()
a=tuple()#定义空元组

a[0]=1#元组下标


#index()	查某个数据，返回对应下标

#count()	t统计某个数据出现次数

#len(元组)	统计元组内的元素个数
```

## 8.5.字符串str

字符串是字符的容器

不可修改

```python
#1.字符串.index(字符串)	查找特定字符串的下标索引值
my_str="0123456789"
print(my_str.index("567"))

#2.字符串的替换	字符串.replace(字符串1,字符串2)  得到一个新的字符串，将字符串1替换成字符串2
new_my_str=my_str.replace("qq","67")

#3.字符串的分割	字符串.split(分隔符字符串)
'''
字符串本身不变，而是得到一个列表对象
'''

#4.字符串的规整操作(去前后空格)	字符串.strip()
'''
字符串.strip("12")#去前后指定字符串，‘1’和‘2’都会被移除
'''

#5.统计字符串中某字符的出现次数	字符串.count()

#6.统计字符串的长度		字符串.len()
```

## 8.6.序列

内容连续，有序，可使用下标索引

列表，元组，字符串，均可以视为序列

序列[起始下标：结束下标：步长]

## 8.7.集合set

列表可修改，支持重复元素且有序

元组，字符串不可修改，支持重复元素且有序

***集合可修改，不支持元素的重复，且内容无序

列表：[  ]

元组：(  )

字符串："  "

集合：{  }

```python
#1.定义集合
a={"1"，"2"}

#2.添加新元素	集合.add(元素) 将指定元素添加到集合内
a.add("3")

#3.移除元素		集合.remove(元素)

#4.随机取出一个元素,同时元素被移除		集合.pop()
b=a.pop()#b为被移除的元素

#5.清空集合		集合.clear()

#6.取两个集合的差集	（集合1有而集合2没有）	集合1.difference(集合2)

#7.消除两个集合的差集		集合1.difference_updata(集合2)

#8.两个集合合并		集合1.union(集合2)

#9.统计集合元素数量		集合.len()

#10.集合的遍历
#集合不支持下标，无法用while循环遍历
#但是可以用for循环
```

## 8.8.字典dict(映射)

```python
#1.字典的定义
a={}
```









































