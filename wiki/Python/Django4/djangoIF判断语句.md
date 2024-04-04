---
title: 18.if判断语句
description: if判断语句
published: true
date: 2024-04-04T15:08:51.924Z
tags: django
editor: markdown
dateCreated: 2024-04-04T14:54:11.449Z
---

# djangoIF判断语句
```django
{% if user.is_authenticated %}
Hello, {{ user.username }}.
{% endif %}
{% if athlete_list %}
Number of athletes: {{ athlete_list|length }}
{% elif athlete_in_locker_room_list %}
Athletes should be out of the locker room soon!
{% else %}
No athletes.
{% endif %}
```

例子：
## 模版
![if判断01.png](/wiki/python/django/if判断01.png)
## 视图
![if判断02.png](/wiki/python/django/if判断02.png)
## 效果
![if判断03.png](/wiki/python/django/if判断03.png)