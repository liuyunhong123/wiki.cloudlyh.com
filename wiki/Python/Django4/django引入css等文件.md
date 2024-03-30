---
title: 10.django引入css等文件
description: django引入css等文件
published: true
date: 2024-03-30T11:21:59.974Z
tags: django
editor: markdown
dateCreated: 2024-03-30T11:19:14.072Z
---

![django导入css文件.png](/wiki/python/django/django导入css文件.png)
## 1.在html文件开始加入
```
{% load static %}
```
## 2.导入antapp目录下的bootstrap.min.css文件
```
<link rel="stylesheet" href="{% static 'antapp/bootstrap.min.css' %}">
```
## 3.导入antapp目录下的jquery.min.js和bootstrap.bundle.min.js
```
<script src="{% static 'antapp/jquery.min.js' %}"></script>
<script src="{% static 'antapp/bootstrap.bundle.min.js' %}"></script>
```
## 4.总结格式
```
开始导入{% load static %}
```
然后路径使用以下方式代替：
```
{% static '需要导入的文件路径' %}
```
