---
title: 23.使用django的中间件
description: 使用django的中间件，中间件的路径写法
published: true
date: 2024-04-26T17:49:43.095Z
tags: 
editor: markdown
dateCreated: 2024-04-26T17:49:43.095Z
---

# 使用django4中间件

## 1.失败路径
开始根据课程写中间件，结果无论怎么写都无法运行，配置如下：
```
MIDDLEWARE = [
    "django.middleware.security.SecurityMiddleware",
    "django.contrib.sessions.middleware.SessionMiddleware",
    "django.middleware.common.CommonMiddleware",
    "django.middleware.csrf.CsrfViewMiddleware",
    "django.contrib.auth.middleware.AuthenticationMiddleware",
    "django.contrib.messages.middleware.MessageMiddleware",
    "django.middleware.clickjacking.XFrameOptionsMiddleware",
    "antapp.middleware.login_check_middleware", #这里是我自定义的中间件，这个路径是错的
]
```

正确写法如下：
```
MIDDLEWARE = [
    "django.middleware.security.SecurityMiddleware",
    "django.contrib.sessions.middleware.SessionMiddleware",
    "django.middleware.common.CommonMiddleware",
    "django.middleware.csrf.CsrfViewMiddleware",
    "django.contrib.auth.middleware.AuthenticationMiddleware",
    "django.contrib.messages.middleware.MessageMiddleware",
    "django.middleware.clickjacking.XFrameOptionsMiddleware",
    "templates.middleware.login_check_middleware", #
]
```

原因：middleware.py这个是中间件的根路径：templates/middleware.py
"antapp.middleware.login_check_middleware"这个路径不应该写antapp因为这个路径下不存在middleware.py文件

结构及正确配置：
![中间件正确配置.png](/wiki/python/django/中间件正确配置.png)





