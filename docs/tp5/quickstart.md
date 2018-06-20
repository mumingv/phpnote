# 《ThinkPHP5快速入门》

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


### 总结



## 参考资料

- [《ThinkPHP5快速入门》（https://www.kancloud.cn/）](https://www.kancloud.cn/thinkphp/thinkphp5_quickstart/147278)


