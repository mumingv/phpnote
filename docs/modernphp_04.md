# 组件

## 为什么使用组件


## 组件是什么？


## 组件和框架对比


## 查找组件


## 使用PHP组件

### 如何安装Composer

参考：[getcomposer.org](https://getcomposer.org/doc/00-intro.md#installation-linux-unix-osx)。

具体安装步骤如下：

Step1. 下载安装脚本并执行

```
$ curl -sS https://getcomposer.org/installer | php
```
```
$ ll
total 1776
-rwxr-xr-x 1 work work 1815925 Jan 13 12:15 composer.phar
```

Step2. [可选]安装composer命令

```
$ sudo mv composer.phar /usr/local/bin/composer
$ sudo chown root /usr/local/bin/composer
```

Step3. 查看composer版本

方式1：使用脚本

```
$ php composer.phar -V
Composer version 1.3.1 2017-01-07 18:08:51
```

方式2：使用命令

```
$ composer -V
Composer version 1.3.1 2017-01-07 18:08:51
```


### 如何使用Composer

#### 组件的名称

组件的名称由厂商名和包名组成。如：league/flysystem，league为厂商名，flysystem为包名。


#### 安装组件





## 参考资料

- [Packagist官网](http://packagist.org/)
- [Packagist镜像](http://pkg.phpcomposer.com/)


