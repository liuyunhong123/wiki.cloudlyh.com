---
title: django模板语法详细
description: django模板语法详细
published: true
date: 2024-04-04T13:49:48.650Z
tags: django
editor: markdown
dateCreated: 2024-04-04T13:46:22.208Z
---

## 1.模板继承：
### 继承父模板文件
```
{% extends "base.html" %}
```
### 定义和覆盖区块
```
{% block mainbody %} {% endblock %}
```
## 2.使用静态文件：
### 加载 static 标签
```
{% load static %}
```
### 引入css文件
```
<link rel="stylesheet" href="{% static 'appname/style.css' %}">
```
### 引入javascript文件
```
<script src="{% static 'antapp/jquery.min.js' %}"></script>
```
## 3.安全标签：
```
{% csrf_token %}
```









