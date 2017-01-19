# [PHP中的HTTP协议](http://www.imooc.com/learn/758)

## HTTP协议基础详解

### HTTP协议概述

HTTP协议之模拟表单提交。

#### HTTP协议的由来

使用计算机发送报价单的需求，诞生了HTTP。


#### HTTP协议的应用场景

- Web Service
- WSDL
- SOAP
- 小偷程序
- 采集程序
- 爬虫程序
- 图片防盗链


#### HTTP协议特点&基本组成部分

HTTP协议特点：http协议是无状态协议(每次http请求都是独立的，每次都需要重新建立和断开连接)；

HTTP协议基本组成：
- 报文首部
- 空行(CR+LF)
- 报文主体

请求报文首部包含：
- 请求行
- 请求首部字段
- 通用首部字段
- 实体首部字段
- 其他

响应报文首部包含：
- 状态行
- 响应首部字段
- 通用首部字段
- 实体首部字段
- 其他


### telnet模拟get和post方法

telnet模拟http请求：
1. 使用cmd：telnet <host-ip> 80；
2. 按 'Ctrl + ]' 并回车打开回显功能；
3. 发送请求报文；

说明：如果是Windows系统，需要启动Telnet服务，步骤如下。
1. 控制面板 -> 程序 -> 打开或关闭Windows功能 -> 勾选Telnet服务器和Telnet客户端。
2. 计算机(右键) -> 管理 -> 服务和应用程序 -> 服务 -> 双击Telnet -> 启动类型选择自动。

以Linux系统为例，使用telnet发送HTTP GET请求的示例：

```
$ telnet 127.0.0.1 8254
Trying 127.0.0.1...
Connected to 127.0.0.1.
Escape character is '^]'.
^]
telnet> 
GET /videos/imooc/php_http/test_get.php HTTP/1.1    
Host: localhost

HTTP/1.1 200 OK
Server: nginx/1.8.0
Date: Wed, 18 Jan 2017 17:36:11 GMT
Content-Type: text/html; charset=UTF-8
Transfer-Encoding: chunked
Connection: close
Vary: Accept-Encoding
X-Powered-By: PHP/5.6.29
Set-Cookie: BAIDUID=87D4A794B01A3BD0B98E2DC8D7B6FA02:FG=1; expires=Thu, 18-Jan-18 17:36:11 GMT; max-age=31536000; path=/; domain=.baidu.com; version=1
P3P: CP=" OTI DSP COR IVA OUR IND COM "

9
http demo
0

Connection closed by foreign host.
```

以Linux系统为例，使用telnet发送HTTP POST请求的示例：

```
$ telnet 127.0.0.1 8254
Trying 127.0.0.1...
Connected to 127.0.0.1.
Escape character is '^]'.
^]
telnet> 
POST /videos/imooc/php_http/test_post.php HTTP/1.1
Host: localhost
Content-type: application/x-www-form-urlencoded
Content-length: 20

act=query&name=henry
HTTP/1.1 200 OK
Server: nginx/1.8.0
Date: Wed, 18 Jan 2017 17:44:02 GMT
Content-Type: text/html; charset=UTF-8
Transfer-Encoding: chunked
Connection: close
Vary: Accept-Encoding
X-Powered-By: PHP/5.6.29
Set-Cookie: BAIDUID=028E30B330F76C7C0C636B2760E06638:FG=1; expires=Thu, 18-Jan-18 17:44:02 GMT; max-age=31536000; path=/; domain=.baidu.com; version=1
P3P: CP=" OTI DSP COR IVA OUR IND COM "

b
query
henry
0

Connection closed by foreign host.
```


## HTTP协议综合运用

三种方式模拟表单发布留言：
1. 利用file_get_contents的第三个参数；
2. socket方式；
3. curl扩展；

### 利用file_get_contents的第三个参数；







## 反向Ajax实现即时聊天程序


