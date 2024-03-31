---
title: 12.django与Bootstrap生成网页
description: django与Bootstrap生成网页
published: true
date: 2024-03-31T14:34:42.060Z
tags: django, bootstrap
editor: markdown
dateCreated: 2024-03-31T10:56:57.812Z
---

## 1.html代码
![html代码.png](/wiki/python/django/html代码.png)

## 2.添加路由
```
path("show_excel2/", views.show_excel2),
```
![路由.png](/wiki/python/django/路由.png)

## 3.视图方法
```
def show_excel2(request):
    df = pd.read_excel(BASE_DIR / "datas/数据-学生成绩表.xlsx")
    return render(request, "show_excel2.html", {"df": df})
```
![视图方法.png](/wiki/python/django/视图方法.png)

## 4.运行结果
![运行结果.png](/wiki/python/django/运行结果.png)
