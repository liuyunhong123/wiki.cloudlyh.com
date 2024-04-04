---
title: 16.django变量输出
description: django变量输出
published: true
date: 2024-04-04T14:50:28.118Z
tags: django
editor: markdown
dateCreated: 2024-04-04T14:48:52.389Z
---

# 变量输出
## 如果是单个值：
```
My first name is {{ first_name }}. My last name is {{ last_name }}.
```
## 字典查找，属性查找和列表索引查找均以点符号实现：
```
{{ my_dict.key }}
{{ my_object.attribute }}
{{ my_list.0 }}
```

