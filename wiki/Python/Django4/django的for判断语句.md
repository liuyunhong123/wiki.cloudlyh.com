---
title: 19.django的for判断语句
description: django的for判断语句
published: true
date: 2024-04-04T15:01:52.652Z
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



