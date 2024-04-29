---
title: 26.普通form实现上传功能
description: 普通form实现上传功能
published: true
date: 2024-04-29T18:13:29.158Z
tags: django
editor: markdown
dateCreated: 2024-04-29T18:13:29.158Z
---

# 普通form实现上传功能
## 1、定义form
```python
class OrderUploadForm(forms.Form):
    title = forms.CharField(label="标题", max_length=50)
    file = forms.FileField(label="上传文件")
```
## 2、前端网页
如果需要上传文件，需要加`enctype="multipart/form-data"`
```python
<form method="post" class="form-inline" novalidate enctype="multipart/form-data">
    {% csrf_token %}
    {{ form|crispy }}
    <button type="submit" class="btn btn-primary">提 交</button>
</form>
```

## 3、后端获取数据
在project的settings.py中定义MEDIA_ROOT作为上传文件的目录
```
MEDIA_ROOT = BASE_DIR / "media"
```

## view函数：
```python
def order_manage(request):
    if request.method == 'GET':
        form = OrderUploadForm()
    else:
        form = OrderUploadForm(request.POST, request.FILES)
        if form.is_valid():
            order_file = request.FILES.get('order_file')
            df = pd.read_excel(order_file)
            save_to_data_table(df)
            print(df.head())
            print(df.columns)
            fpath = settings.MEDIA_ROOT / order_file.name
            with open(fpath, "wb") as f:
                for chunk in order_file.chunks():
                    f.write(chunk)
            return HttpResponse("上传成功")
    return render(request, "order_manage.html", {"form": form})
```
其中 `request.FILES["stock_file"]` 返回django文件对象，有如下属性或者方法：
file.name：获取文件名
file.file：从django文件对象获取普通的python文件对象
file.size：返回文件的大小，单位为字节
file.chunks：返回分片的文件对象迭代器，分片访问可以节省内存

## 中文乱码问题解决方案
### 1、在数据库配置中增加编码
```
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'antProject',
        'USER': 'root',
        'PASSWORD': '12345678',
        'HOST': 'localhost',
        'PORT': '3306',
        'OPTIONS': {
            'charset': 'utf8mb4' # This is the relevant line
        }
    }
}
```
### 2、需要将数据表转换成编码UTF8
在数据库执行SQL语句：
```SQL
ALTER TABLE
antproject.antapp_orderdata
CONVERT TO CHARACTER SET utf8mb4;
```



