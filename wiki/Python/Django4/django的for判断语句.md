---
title: 19.django的for判断语句
description: django的for判断语句
published: true
date: 2024-04-04T15:23:27.944Z
tags: django
editor: markdown
dateCreated: 2024-04-04T14:55:46.375Z
---

# django的for循环语句
```django
{% for story in story_list %}
<h2>
<a href="{{ story.get_absolute_url }}">
{{ story.headline }}
</a>
</h2>
<p>{{ story.tease|truncatewords:"100" }}</p>
{% endfor %}
```
## 案例1：
### 模版
![for循环输出列表.png](/wiki/python/django/for循环输出列表.png)
### 视图
![for循环输出列表02.png](/wiki/python/django/for循环输出列表02.png)
### 效果：
![for案例.png](/wiki/python/django/for案例.png)

## 案例2：
### 模版
![for循环01.png](/wiki/python/django/for循环01.png)
### 视图
![for循环02.png](/wiki/python/django/for循环02.png)
### 效果
![for循环03.png](/wiki/python/django/for循环03.png)
