---
title: 使用django-crispy-forms组件
description: 使用django-crispy-forms时，跳转到signup页面出错
published: true
date: 2024-04-24T05:27:24.890Z
tags: django, django-crispy-forms
editor: markdown
dateCreated: 2024-04-24T05:26:45.542Z
---

# 使用django-crispy-forms组件
在使用django-crispy-forms时，页面出错

## 解决方法：

使用bootstrap5

### 1. 安装crispy-bootstrap5

Install this plugin using pip:
```
pip install crispy-bootstrap5
```
### 2. 在setting.py文件中添加代码
```
INSTALLED_APPS = (

    ...

    "crispy_forms",

    "crispy_bootstrap5",

    ...

)
```
```
CRISPY_ALLOWED_TEMPLATE_PACKS = "bootstrap5"

CRISPY_TEMPLATE_PACK = "bootstrap5"
```

来源：https://www.cnblogs.com/chrisxyz/p/17145751.html