# [PHP扩展安装指南](http://www.imooc.com/learn/757)

## PHP扩展简介

### PHP扩展简介

PHP扩展为PHP提供一些扩展的功能。

使用扩展方式的优点：
- 快速扩展功能；
- 按需加载，节省资源；

常见PHP扩展：
- myslq: PHP操作mysql数据库
- gd2: 动态创建图像(如：生成验证码)
- xdebug: 跟踪、调试和分析PHP程序的运行状况


### PHP扩展运行原理

#### PHP运行原理

Zend引擎 -> Extensions -> Sapi -> 上层应用。

注：Sapi(服务应用程序接口)。


#### PHP扩展运行原理

Extensions -> 初始化 -> Sapi请求初始化 -> 执行。

初始化的内容包含：
- 内部变量；
- 分配资源；
- 注册资源句柄；
- 注册Zend函数；


### 查看管理PHP扩展

#### 查看PHP扩展

方法1：使用phpinfo探针函数。

示例：[链接](http://123.56.21.232:8254/)。

方法2：使用get_loaded_extensions函数。

示例：[链接](http://123.56.21.232:8254/videos/imooc/ext_install/get_loaded_extensions.php)。

方法3：使用extension_loaded查看某个扩展是否开启。

示例：[链接](http://123.56.21.232:8254/videos/imooc/ext_install/extension_loaded.php)。 


#### 管理PHP扩展

扩展目录，对应php.ini中的extension_dir。

1.对于bdp，配置文件为/home/work/bdp/php/etc/php.ini。

存放扩展的目录为：

```
extension_dir="/home/work/bdp/php/ext"
```

2.对于yum安装的php，配置文件为/etc/php.ini，和/etc/php.d/.ini。

存放扩展的目录为：

```
/usr/lib64/php/modules
```


## Windows下安装PHP扩展

### Windows下PHP扩展安装流程

PECL：The PHP Extension Community Library。打包安装的PHP扩展库仓库。

官网：pecl.php.net(http://pecl.php.net)。


### 实战-Windows下安装redis扩展

略。


## Linux下安装PHP扩展

### Linux下安装PHP扩展流程

Linux下的扩展就是一个.so文件。

安装流程：
- 下载 http://pecl.php.net/
- 选择版本
- 解压下载文件

判断安装类型：
- 直装：直接复制文件到扩展目录，开启相应扩展
- 编译安装：进行编译

编译安装：
1. 在解压扩展目录下执行phpize；
2. 配置编译参数，主要是配置php配置文件参数。如：
```
./configure --with-php-config=/usr/local/php/bin/php-config
```
3. 编译和安装。
```
make && make install
```
4. 复制扩展文件到对应目录。
5. 开启扩展，配置相应扩展参数。
6. 重启php-fpm。

注：
1. phpize是用来扩展php扩展模块的，通过phpize可以建立php的外挂模块。
2. 出现配置信息错误，需要安装autoconf。如下：
```
yum install audoconf
```
3. audoconf可以生成自动地配置软件源代码。


### 实战-Linux下直接装ZendGuardLoader扩展

1.下载安装.so文件

```
$ wget http://downloads.zend.com/guard/7.0.0/zend-loader-php5.6-linux-x86_64.tar.gz
$ tar xvzf zend-loader-php5.6-linux-x86_64.tar.gz
$ cd zend-loader-php5.6-linux-x86_64/
$ cp ZendGuardLoader.so /home/work/mdp/output/php/lib/php/extensions/no-debug-non-zts-20131226/
```

注：[zend-loader各版本下载地址](http://www.newsmth.net/nForum/#!article/PHP/96548?p=1)。当然也可以从[Zend官方网站](http://www.zend.com/)下载，不做需要先注册。

2.修改配置

```
$ vim /home/work/mdp/output/php/etc/php.ini
zend_extension=/home/work/mdp/output/php/lib/php/extensions/no-debug-non-zts-20131226/ZendGuardLoader.so
zend_loader.enable=1
```

3.重启php-fpm

```
$ service php-fpm restart
```


### 实战-Linux下编译安装redis扩展

1.下载redis扩展源码并解压

```
$ wget http://pecl.php.net/get/redis-3.1.0.tgz
$ tar xvzf redis-3.1.0.tgz 
```

注：redis扩展源码下载地址 http://pecl.php.net。

2.预编译和编译安装

```
$ cd redis-3.1.0/
$ /home/work/mdp/output/php/bin/phpize 
Configuring for:
PHP Api Version:         20131106
Zend Module Api No:      20131226
Zend Extension Api No:   220131226
$ ./configure --with-php-config=/home/work/mdp/output/php/bin/php-config
$ make
$ make install
Installing shared extensions:     /home/work/mdp/output/php/lib/php/extensions/no-debug-non-zts-20131226/
```

3.修改配置

```
$ vim /home/work/mdp/output/php/etc/php.ini
extension=/home/work/mdp/output/php/lib/php/extensions/no-debug-non-zts-20131226/redis.so
```

4.重启php-fpm

```
$ service php-fpm restart
```


## 课程回顾

### 课程回顾


