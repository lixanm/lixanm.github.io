---
title: c++ primer阅读笔记
date: 2024-09-19 21:29:00 +0800
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

# 第一章

## 1.4	控制流

### 	1.4.1	whlie语句

### 	1.4.2	for语句

### 	1.4.3	读取数量不定的输入数据

````cpp
#include<iostream>
int main()
{
    int sum=0,value=0;
    while(std::cin>>value)	//按ctrl+r表示输入结束
        sum+=value;
    std::cout<<"sum is :"<<sum<<std::endl;
}
````

````c++
#include<iostream>
int main()
{
    int sum = 0, value = 0;
    while (std::cin >> value)
    {
        sum += value;
        if(getchar()=='\n')
            std::cout << "sum is :" << sum << std::endl;
    }
}
````

### 	1.4.4	if语句

````c++
#include<iostream>
int main()
{
    int currVal = 0, val = 0;
    if (std::cin >> currVal)
    {
        int cnt = 1;
        while (std::cin >> val)
        {
            if (val == currVal)
                ++cnt;
            else
            {
                std::cout << currVal << " occurs " << cnt << " times " << std::endl;
                currVal = val;
                cnt = 1;
            }
            if (getchar() == '\n')
            {
                break;
            }
        }
        std::cout << currVal << " occurs " << cnt << " times " << std::endl;
    }
}
````



## 1.5	类简介



## 







