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

示例：安装组件league/flysystem

```
$ composer require league/flysystem
Using version ^1.0 for league/flysystem
./composer.json has been created
Loading composer repositories with package information
Updating dependencies (including require-dev)
Package operations: 1 install, 0 updates, 0 removals
  - Installing league/flysystem (1.0.32) Downloading: 100%         
league/flysystem suggests installing league/flysystem-aws-s3-v2 (Allows you to use S3 storage with AWS SDK v2)
league/flysystem suggests installing league/flysystem-aws-s3-v3 (Allows you to use S3 storage with AWS SDK v3)
league/flysystem suggests installing league/flysystem-azure (Allows you to use Windows Azure Blob storage)
league/flysystem suggests installing league/flysystem-cached-adapter (Flysystem adapter decorator for metadata caching)
league/flysystem suggests installing league/flysystem-copy (Allows you to use Copy.com storage)
league/flysystem suggests installing league/flysystem-dropbox (Allows you to use Dropbox storage)
league/flysystem suggests installing league/flysystem-eventable-filesystem (Allows you to use EventableFilesystem)
league/flysystem suggests installing league/flysystem-rackspace (Allows you to use Rackspace Cloud Files)
league/flysystem suggests installing league/flysystem-sftp (Allows you to use SFTP server storage via phpseclib)
league/flysystem suggests installing league/flysystem-webdav (Allows you to use WebDAV storage)
league/flysystem suggests installing league/flysystem-ziparchive (Allows you to use ZipArchive adapter)
Writing lock file
Generating autoload files
```


### 示例项目

代码：[Github](https://github.com/mumingv/php/tree/master/books/modernphp/modern-php-master/04-components/url-scanner-app)。


## 参考资料

- [Packagist官网](http://packagist.org/)
- [Packagist镜像](http://pkg.phpcomposer.com/)


