# Django 下载


## 下载Django
`pip3 install django`
## 查看版本
`python3 -m django --version`

## 创建项目
`django-admin startproject <first是项目名称>`

此时项目的结构为
```shell
first #根目录
├── first #是python包的存放处,名称不能随便改
│   ├── asgi.py
│   ├── __init__.py #一个空文件，告诉 Python 这个目录应该被认为是一个 Python 包
│   ├── settings.py #项目配置文件
│   ├── urls.py #URL调度器
│   └── wsgi.py #web 服务网关接口 （Web Server Gateway Interface）
|               #wsgi web server 和 wsgi web application
|               #它们通常是运行在一个python进程中的两个模块，或者说两个子系统。
|               #wsgi web server 接受到前端的http请求后，会调用 wsgi web application 的接口（ 比如函数或者类方法）方法，由wsgi web 
|               #application 具体处理该请求。然后再把处理结果返回给 wsgi web server， wsgi web server再返回给前端。
|               #为什么要搞出两个子系统，这么麻烦呢？
|               #因为这两个子系统有各自负责的重点。
|               #wsgi web server 负责 提供高效的http请求处理环境，可以使用多线程、多进程或者协程的机制。
|               #http 请求发送到 wsgi web server ， wsgi web server 分配线程或者进程或者轻量级线程(协程)，然后在这些线程、进程、或者协程
|               #里面，去调用执行 wsgi web application 的入口代码。
|               #wsgi web application 被调用后，负责处理业务逻辑。业务逻辑的处理可能非常复杂， wsgi web application 需要精心的设计来正确理。
|               #django是 wsgi web application 的框架，它只有一个简单的单线程 wsgi web server。 供调试时使用。
|               #产品正式上线运行的时候，通常我们需要高效的 wsgi web server 产品，比如 gunicorn，uwsgi，cherrypy等，结合Django ，组成一个高效
|               #的 后端服务。
|               #所以这个 wsgi.py 就是 提供给wsgi web server调用 的接口文件
|               #里面的变量application对应对象实现了 wsgi入口，供wsgi web server调用 。
└── manage.py #管理项目的工具
```
## 运行web服务器项目
进入到所谓的项目根目录，运行
```shell
nohup python3 manage.py runserver &
```
访问本机端口8000 `curl 127.0.0.1:8000`，会看到Django官方给的一个小例子。
同时也可以通过 `nohup python3 manage.py runserver 9090 &` 使得web服务器再次开通一个端口，但这些端口都是本地127的。
如果你想全局访问这些端口，首先需要将setting.py里面的 ALLOWED_HOSTS = [] 添加主机 ALLOWED_HOSTS = ['*']。
其次在运行时加入 0.0.0.0:8080即可。例子`nohup python3 manage.py runserver 0.0.0.0:8080`。
## 创建应用
web服务器项目开始运行后，我们可以着手创建应用，应用是类似于博客系统、商城网站等的实体web服务系统。
```shell
 python3 manage.py startapp testcompany
```
你会发现在first根目录下又生成了一系列文件
```shell
└── testcompany
    ├── admin.py
    ├── apps.py
    ├── __init__.py
    ├── migrations
    │   └── __init__.py
    ├── models.py
    ├── tests.py
    └── views.py #视图
```
