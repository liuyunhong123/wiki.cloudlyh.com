---
title: 使用django-crispy-forms组件
description: 使用django-crispy-forms时，跳转到signup页面出错
published: true
date: 2024-04-24T12:29:01.818Z
tags: django, django-crispy-forms
editor: markdown
dateCreated: 2024-04-24T05:26:45.542Z
---

# 使用django-crispy-forms组件
在使用crispy-bootstrap4的django-crispy-forms时，页面出错

## 解决方法：

crispy-bootstrap4

Bootstrap4 template pack for django-crispy-forms. This template pack was included with the core django-crispy-forms package until version 2.0.

Bootstrap 4模板包，用于django-crispy-forms。这个模板包是 包含在django-crispy-forms核心包中，直到2.0版。
Installation
安装：

Install this plugin using pip:
## 使用pip安装此插件：
```
pip install crispy-bootstrap4
```

Usage
使用

You will need to update your project's settings file to add crispy_forms and crispy_bootstrap4 to your projects INSTALLED_APPS. Also set bootstrap4 as and allowed template pack and as the default template pack for your project:

您需要更新项目的设置文件以添加crispy_forms crispy_bootstrap4#也创下 INSTALLED_APPS作为和允许的模板包和作为默认模板包 对于您的项目：
```
INSTALLED_APPS = [
    ...
    "crispy_forms",
    "crispy_bootstrap4",
    ...
]

CRISPY_ALLOWED_TEMPLATE_PACKS = "bootstrap4"

CRISPY_TEMPLATE_PACK = "bootstrap4"
```

来源：https://pypi.org/project/crispy-bootstrap4/
