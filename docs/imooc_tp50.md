# TP5.0 仿百度糯米开发多商家电商平台

## 需求分析

系统三大模块：
- 商家平台
- 主平台
- 前台模块

E-R图也称实体-联系图(Entity Relationship Diagram)，提供了表示实体类型、属性和联系的方法，用来描述现实世界的概念模型。


## 数据库表设计

根据需求分析产出的E-R图设计数据库表结构。

### 分类表

```php
CREATE TABLE `o2o_category`(
    `id` int(11) unsigned not null auto_increment,
    `name` varchar(50) not null default '',
    `parent_id` int(10) unsigned not null default 0,
    `listorder` int(8) unsigned not null default 0,
    `status` tinyint(1) not null default 0,
    `create_time` int(11) unsigned not null default 0,
    `update_time` int(11) unsigned not null default 0,
    PRIMARY KEY(`id`),
    KEY parent_id(`parent_id`)
)ENGINE=InnoDB AUTO_INCREMENT=1 DEFAULT CHARSET=utf8;
```


### 城市表

```php
CREATE TABLE `o2o_city`(
    `id` int(11) unsigned not null auto_increment,
    `name` varchar(50) not null default '',
    `uname` varchar(50) not null default '',
    `parent_id` int(10) unsigned not null default 0,
    `listorder` int(8) unsigned not null default 0,
    `status` tinyint(1) not null default 0,
    `create_time` int(11) unsigned not null default 0,
    `update_time` int(11) unsigned not null default 0,
    PRIMARY KEY(`id`),
    KEY parent_id(`parent_id`),
    UNIQUE KEY uname(`uname`)
)ENGINE=InnoDB AUTO_INCREMENT=1 DEFAULT CHARSET=utf8;
```


### 商圈表

```php
CREATE TABLE `o2o_area`(
    `id` int(11) unsigned not null auto_increment,
    `name` varchar(50) not null default '',
    `city_id` int(11) unsigned not null default 0,
    `parent_id` int(10) unsigned not null default 0,
    `listorder` int(8) unsigned not null default 0,
    `status` tinyint(1) not null default 0,
    `create_time` int(11) unsigned not null default 0,
    `update_time` int(11) unsigned not null default 0,
    PRIMARY KEY(`id`),
    KEY parent_id(`parent_id`),
    KEY city_id(`city_id`)
)ENGINE=InnoDB AUTO_INCREMENT=1 DEFAULT CHARSET=utf8;
```


### 商户表

```php
CREATE TABLE `o2o_bis`(
    `id` int(11) unsigned not null auto_increment,
    `name` varchar(50) not null default '',
    `email` varchar(50) not null default '',
    `logo` varchar(255) not null default '',
    `licence_logo` varchar(255) not null default '',
    `description` text not null,
    `city_id` int(11) unsigned not null default 0,
    `city_path` varchar(50) not null default '',
    `bank_info` varchar(50) not null default '',
    `money` decimal(20, 2) not null default '0.00',
    `bank_name` varchar(50) not null default '',
    `bank_user` varchar(50) not null default '',
    `faren` varchar(50) not null default '',
    `faren_tel` varchar(50) not null default '',
    `listorder` int(8) unsigned not null default 0,
    `status` tinyint(1) not null default 0,
    `create_time` int(11) unsigned not null default 0,
    `update_time` int(11) unsigned not null default 0,
    PRIMARY KEY(`id`),
    KEY name(`name`),
    KEY city_id(`city_id`)
)ENGINE=InnoDB AUTO_INCREMENT=1 DEFAULT CHARSET=utf8;
```


### 商户账号表

```php
CREATE TABLE `o2o_bis_account`(
    `id` int(11) unsigned not null auto_increment,
    `username` varchar(50) not null default '',
    `password` char(32) not null default '',
    `code` varchar(10) not null default '',
    `bis_id` int(11) unsigned not null default 0,
    `last_login_ip` varchar(20) not null default '',
    `last_login_time` int(11) unsigned not null default 0,
    `is_main` tinyint(1) not null default 0,
    `listorder` int(8) unsigned not null default 0,
    `status` tinyint(1) not null default 0,
    `create_time` int(11) unsigned not null default 0,
    `update_time` int(11) unsigned not null default 0,
    PRIMARY KEY(`id`),
    KEY bis_id(`bis_id`),
    KEY username(`username`)
)ENGINE=InnoDB AUTO_INCREMENT=1 DEFAULT CHARSET=utf8;
```


### 商户门店表

```php
CREATE TABLE `o2o_bis_location`(
  `id` int(11) unsigned NOT NULL auto_increment,
  `name` VARCHAR(50) NOT NULL DEFAULT '' ,
  `logo` VARCHAR(255) NOT NULL DEFAULT '' ,
  `address` VARCHAR(255) NOT NULL DEFAULT '' ,
  `tel` VARCHAR(20) NOT NULL DEFAULT '' ,
  `contact` VARCHAR(20) NOT NULL DEFAULT '' ,
  `xpoint` VARCHAR(20) NOT NULL DEFAULT '',
  `ypoint` VARCHAR(20) NOT NULL DEFAULT '',
  `bis_id` int(11) unsigned NOT NULL DEFAULT 0,
  `open_time` int(11) unsigned NOT NULL DEFAULT 0,
  `content` text NOT NULL ,
  `is_main` tinyint(1)  unsigned NOT NULL default 0,
  `api_address` VARCHAR(255) NOT NULL DEFAULT '' ,
  `city_id` int(11) unsigned NOT NULL DEFAULT 0,
  `city_path` varchar(50) NOT NULL DEFAULT '' ,
  `category_id` int(11 ) unsigned NOT NULL DEFAULT 0,
  `category_path` VARCHAR(50) NOT NULL DEFAULT '',
  `bank_info` varchar(50) NOT NULL DEFAULT '' ,
  `listorder` int(8) unsigned NOT NULL default 0,
  `status` tinyint(1) NOT NULL DEFAULT 0,
  `create_time` int(11) unsigned NOT NULL default 0,
  `update_time` int(11) unsigned NOT NULL default 0,
  PRIMARY KEY (`id`),
  KEY city_id(`city_id`),
  KEY bis_id(`bis_id`),
  KEY category_id(`category_id`),
  KEY name(`name`)
)ENGINE=InnoDB AUTO_INCREMENT=1 DEFAULT  CHARSET=utf8;
```


### 团购商品表

```php
CREATE TABLE `o2o_deal`(
    `id` int(11) unsigned not null auto_increment,
    `name` varchar(100) not null default '',
    `category_id` int(11)not null default 0,
    `se_category_id` int(11)not null default 0,
    `bis_id` int(11)not null default 0,
    `location_ids` varchar(100) not null default '',
    `image` varchar(200) not null default '',
    `description` text not null,
    `start_time` int(11)not null default 0,
    `end_time` int(11)not null default 0,
    `origin_price` decimal(20, 2) not null default '0.00',
    `current_price` decimal(20, 2) not null default '0.00',
    `city_id` int(11)not null default 0,
    `buy_count` int(11)not null default 0,
    `total_count` int(11)not null default 0,
    `coupons_begin_time` int(11) not null default 0,
    `coupons_end_time` int(11) not null default 0,
    `xpoint` varchar(20) not null default '',
    `ypoint` varchar(20) not null default '',
    `bis_account_id` int(11) not null default 0,
    `balance_price` decimal(20, 2) not null default '0.00',
    `notes` text not null,
    `listorder` int(8) unsigned not null default 0,
    `status` tinyint(1) not null default 0,
    `create_time` int(11) unsigned not null default 0,
    `update_time` int(11) unsigned not null default 0,
    PRIMARY KEY(`id`),
    KEY category_id(`category_id`),
    KEY se_category_id(`se_category_id`),
    KEY city_id(`city_id`),
    KEY start_time(`start_time`),
    KEY end_time(`end_time`)
)ENGINE=InnoDB AUTO_INCREMENT=1 DEFAULT CHARSET=utf8;
```


### 用户表

```php
CREATE TABLE `o2o_user`(
    `id` int(11) unsigned not null auto_increment,
    `username` varchar(50) not null default '',
    `password` char(32) not null default '',
    `code` varchar(10) not null default '',
    `last_login_ip` varchar(20) not null default '',
    `last_login_time` int(11) unsigned not null default 0,
    `email` varchar(30) not null default '',
    `mobile` varchar(20) not null default '',
    `listorder` int(8) unsigned not null default 0,
    `status` tinyint(1) not null default 0,
    `create_time` int(11) unsigned not null default 0,
    `update_time` int(11) unsigned not null default 0,
    PRIMARY KEY(`id`),
    UNIQUE KEY username(`username`),
    UNIQUE KEY email(`email`)
)ENGINE=InnoDB AUTO_INCREMENT=1 DEFAULT CHARSET=utf8;
```


### 推荐位表

```php
CREATE TABLE `o2o_featured`(
  `id` int(11) unsigned NOT NULL auto_increment,
  `type` tinyint(1) NOT NULL DEFAULT 0,
  `title` VARCHAR(30) NOT NULL DEFAULT '',
  `image` VARCHAR(255) NOT NULL DEFAULT '',
  `url` VARCHAR(255) NOT NULL DEFAULT '',
  `description` VARCHAR(255) NOT NULL DEFAULT '',
  `listorder` int(8) unsigned NOT NULL default 0,
  `status` tinyint(1) NOT NULL DEFAULT 0,
  `create_time` int(11) unsigned NOT NULL default 0,
  `update_time` int(11) unsigned NOT NULL default 0,
  PRIMARY KEY (`id`)
)ENGINE=InnoDB AUTO_INCREMENT=1 DEFAULT  CHARSET=utf8;
```


## 数据库创建

```
$ mysql -uroot -p
mysql> create database imooc_o2o default charset utf8;
mysql> use imooc_o2o;
mysql> source o2o_sql.sql;
```


## TP5框架安装

### 方式一：官网下载

下载地址：http://www.thinkphp.cn/down/927.html


### 方式二：composer下载

```
$ composer create-project topthink/think TP5
```

<font color="red">
说明：topthink是组织名称，think是项目名称，TP5是项目的存放目录。
</font>







