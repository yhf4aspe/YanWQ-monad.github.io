---
layout:     post
title:      "高精度加法"
date:       2015-04-24 22:03:51
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

using namespace std;

struct Tlong
{
    int a[10100];
    int len;
    Tlong()
    {
        len=0;
        memset(a,0,sizeof a);
    }
};

Tlong a,b,z;

void add(Tlong a,Tlong b,Tlong &z);
void _out(Tlong a);
void _in(Tlong &a,string st);

int main()
{
    string s1,s2;
    int i;
    
    cin>>s1;
    cin>>s2;
    
    _in(a,s1);
    _in(b,s2);
    
    add(a,b,z);
    
    _out(z);
}

void _out(Tlong a)
{
    for (int i=a.len-1; i>=0; i--)
      cout<<a.a[i];
    cout<<endl;
}

void _in(Tlong &a,string st)
{
    for (int i=st.size()-1; i>=0; i--,a.len++)
      a.a[a.len]=st[i]-'0';
}

void add(Tlong a,Tlong b,Tlong &z)
{
    int i,c=0;
    z.len=b.len;
    if (a.len>b.len) z.len=a.len;
    for (i=0; i<z.len; i++)
    {
        z.a[i]=a.a[i]+b.a[i]+c;
        c=z.a[i]/10;
        z.a[i]%=10;
    }
    for (i=z.len-1; c>0; i++)
    {
        z.a[i+1]+=c;
        c=z.a[i+1]/10;
        z.a[i+1]%=10;
    }
    z.len=i+1;
}
```
