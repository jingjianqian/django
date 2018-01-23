# Django
001-创建项目
1,下载Django框架，或者pip install Django
2,创建项目，选择目录，执行
[code]
    django-admin.py startproject dj1
[/code]
002--创建自己的模块
1,进入项目根目录，执行 python manage.py startapp my1
2,编辑项目根目录下的 my1/views.py
[code]
from django.urls import path
from . import views

urlpatterns = [
    path('', views.index, name='index'),
]
[/code]
3,my1目录下新增url.py,编辑内容为
[code]
from django.http import HttpResponse

def index(request):
    return HttpResponse("Hello,world.You are at my1 app index.")

[/code]
4,编辑项目根目录下的dj1/urls.py 改为
[code]
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('my1/', include('my1.url')),
]
[/code]