---
layout:     post
title:      "高精度除法"
date:       2015-04-24 22:02:57
author:     "Aspe"
header-img: "img/fangao.jpg"
mathjax:    false
catalog:    true
tags:
    - 数论
    - 算法&数据结构
---

``` c++
#include<iostream>
#include<cstring>
using namespace std;

int ans[100000];

void add4(int x);
void _out();

int main()
{
    int x,i,f;
    char st[10000];
    cin>>st;
    cin>>x;
    ans[0]=strlen(st);
    for (i=ans[0];i>0;i--) ans[i]=st[ans[0]-i]-48;
    add4(x);
    _out();
}

void _out()
{
    for (int i=ans[0];i>0;i--) cout<<ans[i];
}

void add4(int x)
{
    int i;
    for(i=ans[0];i>1;i--)
    {
        ans[i-1]+=ans[i]%x*10;
        ans[i]=ans[i]/x;
    }
    ans[i]=ans[i]/x;
    for(i=ans[0];(ans[i]==0)&&(i>1);i--,ans[0]--);
}
```
