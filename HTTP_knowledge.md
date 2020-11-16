#### HTTP请求响应消息

1. 请求头
    - GET
    ```shell
    请求类型 请求资源地址 http协议版本 #这是请求行 request line
    下面是请求头 是  【名称：值】 这个格式 request headers

    #下面是例子
    GET /mgr/login.html HTTP/1.1  #这是请求行
    Host: www.baiyueheiyu.com  #请求头 访问的主机
    User-Agent: Mozilla/6.0 (compatible; MSIE5.01; Windows NT) #请求头 客户端类型
    Accept-Language: zh-cn
    Accept-Encoding: gzip, deflate
    ```
    - POST
    ```shell
    请求类型 请求资源地址 http协议版本 #这是请求行
    请求头 是  【名称：值】 这个格式

    请求消息  request headers

    #下面是例子
    POST /api/medicine HTTP/1.1 #这是请求行
    Host: www.baiyueheiyu.com #请求头 访问主机
    User-Agent: Mozilla/6.0 (compatible; MSIE5.01; Windows NT)  #请求头 客户端类型
    Content-Type: application/x-www-form-urlencoded
    Content-Length: 51
    Accept-Language: zh-cn
    Accept-Encoding: gzip, deflate

    name=qingmeisu&sn=099877883837&desc=qingmeisuyaopin #请求消息体 要与上面有空行
    ```

- 请求方法
    - GET 获取资源请求
    - POST 添加资源消息到服务器处理
    - PUT 更新信息
    - DELETE 删除资源信息
    标准消息头：[官方信息说明](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers)

2. 响应消息
    ```shell
    协议版本 状态码  描述状态的语句 #响应状态行 status line
    响应头 response headers

    消息体 message body
    #下面是例子
    HTTP/1.1 200 OK #注意了解常见的响应行和响应头
    Date: Thu, 19 Sep 2019 08:08:27 GMT
    Server: WSGIServer/0.2 CPython/3.7.3
    Content-Type: application/json
    Content-Length: 37
    X-Frame-Options: SAMEORIGIN
    Vary: Cookie

    {"ret": 0, "retlist": [], "total": 0}
    ```