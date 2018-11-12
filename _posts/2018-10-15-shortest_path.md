---
layout:     post
title:      "最短路的各种奇技*巧"
subtitle:   "转换转换转换"
date:       2018-10-15 12:00:00
author:     "Aspe"
header-img: "img/post-bg-2015.jpg"
mathjax:    false
catalog:    true
tags:
    - 算法
    - AC自动机
---

## 大体

   最短路学会后，我们可以说我会 SPFA 啦，我会 dijkstra 啦。但能说，我会做最短路的题了吗？  
   
   嘿嘿……  
   
   但其实，最短路的题目，究其代码，终究逃不过 SPFA,dijkstra 的模板，只是在其基础上改改。  
   
   所以比较硬的就是，想到如下几点：  
   
   *1，这题是最短路*  
   *2，如何表示状态*  
   *3，如何互相转移*  

---

## 实例

### 优化转移

   1 点连多边
