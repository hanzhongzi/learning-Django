# Django 下载


## 下载Django
`pip3 install django`
## 查看版本
`python3 -m django --version`

## 创建项目
`django-admin startproject first`

此时项目的结构为
```shell
first #根目录
├── first
│   ├── asgi.py
│   ├── __init__.py
│   ├── settings.py 
│   ├── urls.py 路由表
│   └── wsgi.py 网管接口
└── manage.py #管理项目的工具
```