# 《ThinkPHP5快速入门》

官方文档：[《ThinkPHP5快速入门》（https://www.kancloud.cn/）（已购买，GitHub账号登录）](https://www.kancloud.cn/thinkphp/thinkphp5_quickstart/147278)

基础运行环境：

```
cd tp5/
sh run.sh
```
```
http://localhost:8888/index.php/index/index/index
```

数据库：

```
mysql -uroot -p
mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| demo               |
+--------------------+
```
```
http://localhost:8888/index.php/index/IndexViewDb/index
```


## 基础

### 简介

略。


### 安装

```
composer create-project topthink/think=5.0.* tp5 --prefer-dist
```


### 目录结构

略。


### 运行环境

#### 使用PHP自带的WebServer

```
cd tp5/public
php -S localhost:8888 router.php
```
```
http://localhost:8888/
```


### 入口文件

入口文件为`public/inex.php`，示例：

```
cd thinkphp5_quickstart
php -S localhost:8888
```
```
http://localhost:8888/tp5/public
```


### 资源访问

略。


### 调试模式

略。


### 控制器

#### 默认控制器（Index）

```
http://localhost:8888/
```
等价于：
```
http://localhost:8888/index.php/index/index
```
其中，`index.php`是入口文件，其后的两个`index`分别表示应用名称和控制器名称。


#### 驼峰控制器（HelloWorld）


```
# cat application/index/controller/HelloWorld.php

<?php
namespace app\index\controller;

class HelloWorld
{
    public function index()
    {
        return 'Hello, world!';
    }
}
```

和文档描述的不一致，默认情况下，如下这三种写法都能正常工作。

```
http://localhost:8888/index.php/index/HelloWorld
http://localhost:8888/index.php/index/helloworld
http://localhost:8888/index.php/index/hello_world
```


### 视图

代码：[GitHub](https://github.com/mumingv/php/commit/eafd0f56da7b4bffa962b2c750fc649d0c23dde6)

```
http://localhost:8888/index.php/index/IndexView/hello
```


### 读取数据

代码：[GitHub](https://github.com/mumingv/php/commit/fb933ccf25a3b84f8b744c211ade0514c91fe5fb)

```
http://localhost:8888/index.php/index/IndexViewDb/index
```


### 总结

略。


## URL和路由

### URL访问

代码：[GitHub](https://github.com/mumingv/php/commit/4a06436af92e728262ac5113330aa4c6db2a5c59)


###### 
|index.php|index|index|hello     |name|thinkphp|
|---------|-----|-----|----------|----|--------|
|入口文件  |模块  |控制器|操作（函数）|参数名称|参数值|

```
http://localhost:8888/index.php/index/index/hello/name/thinkphp
```


### 参数传入

代码：[GitHub](https://github.com/mumingv/php/commit/b74e29063b4cccd14d1c1676658a0f86e2875b6e)

如下四种方法等价：

```
http://localhost:8888/index.php/index/index/hello2/name/thinkphp/city/shanghai
http://localhost:8888/index.php/index/index/hello2/city/shanghai/name/thinkphp
```
```
http://localhost:8888/index.php/index/index/hello2?name=thinkphp&city=shanghai
http://localhost:8888/index.php/index/index/hello2?city=shanghai&name=thinkphp
```


### 隐藏入口

需要通过Nginx配置来实现。

```
location / { // …..省略部分代码
    if (!-e $request_filename) {
        rewrite  ^(.*)$  /index.php?s=/$1  last;
        break;
    }
}
```


### 定义路由

略。


### URL生成

略。


### 总结

略。


## 请求和响应

### 请求对象

代码：[GitHub](https://github.com/mumingv/php/commit/46913bdd2956a3b331c4df662cbf8988889081fa)

```
http://localhost:8888/index.php/index/IndexRequest/hello
```
```
http://localhost:8888/index/indexrequest/hello?name=thinkphp
```


### 请求信息

代码：[GitHub](https://github.com/mumingv/php/commit/dcb637a062721b91599986e6b8f7ef33342efb03)

```
http://localhost:8888/index/indexrequest/hello2?test=ddd&name=thinkphp
```


### 响应对象

代码：[GitHub](https://github.com/mumingv/php/commit/70c02feedcf7ca3e3317c414c7e9e00fb5030747)

```
http://localhost:8888/index/IndexResponse/hello
```


### 总结

略。


## 数据库

### 原生查询

代码：[GitHub](https://github.com/mumingv/php/commit/4e67dd675f2a9208531c2b2d5565f73cb5b34d62)

```
http://localhost:8888/index.php/index/IndexViewDb/create
http://localhost:8888/index.php/index/IndexViewDb/update
http://localhost:8888/index.php/index/IndexViewDb/read
http://localhost:8888/index.php/index/IndexViewDb/delete
```


## 查询语言

待学习。


## 模型和关联

待学习。


## 视图和模板

待学习。


## 调试和日志

待学习。


## API开发

### API版本

待学习。


## 命令行工具

待学习。


## 扩展

待学习。


## 杂项

待学习。



