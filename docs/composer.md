# Composer

## [Mac]安装composer并使用国内镜像

### 安装composer

安装方法，参考：[安装](http://pkg.phpcomposer.com/#how-to-install-composer)。

这里采用了全局安装的方式，命令如下：

```
$ mv composer.phar /usr/local/bin/composer
```

安装完成之后就可以直接使用`composer`命令了，否则只能使用`php composer.phar`的方式使用composer。


### 配置国内镜像

```
composer config -g repo.packagist composer https://packagist.phpcomposer.com
```


## [Linux]安装composer并使用国内镜像

### 安装composer

安装方法，参考：[安装](http://pkg.phpcomposer.com/#how-to-install-composer)。

这里采用了全局安装的方式，命令如下：

```
$ mv composer.phar /usr/local/bin/composer
```

安装完成之后就可以直接使用`composer`命令了，否则只能使用`php composer.phar`的方式使用composer。


### 配置国内镜像：

```
composer config -g repo.packagist composer https://packagist.phpcomposer.com
```

示例：

```
$ cat composer.json 
{
    "require": {
        "league/flysystem": "^1.0"
    }
}
```
```
$ composer install
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


## composer 查看命令列表

示例：查看composer命令列表

```
$ composer
   ______
  / ____/___  ____ ___  ____  ____  ________  _____
 / /   / __ \/ __ `__ \/ __ \/ __ \/ ___/ _ \/ ___/
/ /___/ /_/ / / / / / / /_/ / /_/ (__  )  __/ /
\____/\____/_/ /_/ /_/ .___/\____/____/\___/_/
                    /_/
Composer version 1.3.1 2017-01-07 18:08:51
...
Available commands:
  about           Short information about Composer
  archive         Create an archive of this composer package
  browse          Opens the package's repository URL or homepage in your browser.
...
  update          Updates your dependencies to the latest version according to composer.json, and updates the composer.lock file.
  validate        Validates a composer.json and composer.lock
  why             Shows which packages cause the given package to be installed
  why-not         Shows which packages prevent the given package from being installed
```

## composer help 查看命令帮助

示例：查看config命令的帮助

```
$ composer help config
Usage:
  config [options] [--] [<setting-key>] [<setting-value>]...
...
```


## composer config 设置/查看配置信息

示例：查看全局配置信息

```
$ composer config -l -g
[repositories.packagist.org.type] composer
[repositories.packagist.org.url] https?://packagist.org
...
[home] /home/yinjie/.composer
```


## composer install 安装软件

前提：必须存在composer.lock或composer.json文件。如果同时存在，则使用composer.lock文件。

示例：

```
$ composer install
```


## composer require 增加composer.json配置并安装包

示例：安装flysystem包

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


## composer selfupdate 安全更新composer

示例：安全更新

```
$ composer selfupdate
You are already using composer version 1.3.1 (stable channel).
```


## composer create-project 创建一个新项目

示例：创建一个TP5框架项目

```
$ composer create-project topthink/think TP5
Installing topthink/think (v5.0.7)
  - Installing topthink/think (v5.0.7) Loading from cache
Created project in TP5
Loading composer repositories with package information
Updating dependencies (including require-dev)
Package operations: 2 installs, 0 updates, 0 removals
  - Installing topthink/think-installer (v1.0.11) Loading from cache
  - Installing topthink/framework (v5.0.7) Loading from cache
Writing lock file
Generating autoload files
```

<font color="red">
说明：topthink是组织名称，think是项目名称，TP5是项目的存放目录。
</font>


## [FAQ]如何在composer.json中指定packagist？

```
{
    "require": {
        "vega/curl": "1.0.0",
        "justinrainbow/json-schema": "^5.2"
    },
    "config": {
        "secure-http": false,
        "vendor-dir": "../php/vendor"
    },
    "repositories": [
        {
            "type": "composer",
            "url": "https://packagist.org/"
        },
        {
            "packagist": false
        }
    ]
}
```


## 参考资料

- [中文-composer官网](https://www.phpcomposer.com/)
- [英文-composer官网](https://getcomposer.org/)
- [中文-Packagist镜像（带中文composer安装及镜像配置指导）](http://pkg.phpcomposer.com/)
- [英文-Packagist官网](http://packagist.org/)
- [中文-composer文档](http://docs.phpcomposer.com/)
- [英文-composer文档](https://getcomposer.org/doc/)






