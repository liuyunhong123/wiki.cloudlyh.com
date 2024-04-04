---
title: 17.django过滤器
description: django过滤器
published: true
date: 2024-04-04T15:12:29.595Z
tags: django
editor: markdown
dateCreated: 2024-04-04T14:52:36.880Z
---

# django过滤器
## 通过使用 过滤器 修改显示的变量
```django
# 字符串长度
{{ value|length }}

# 转换成小写
{{ value|lower }}

# 日期格式化
{{ value|date:"Y-M-d" }}
```
例子：
## 模版
![过滤器01.png](/wiki/python/django/过滤器01.png)
## 视图
![过滤器02.png](/wiki/python/django/过滤器02.png)
## 效果
![过滤器效果.png](/wiki/python/django/过滤器效果.png)
