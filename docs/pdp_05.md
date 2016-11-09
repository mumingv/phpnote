# 数据访问对象模式

## 基本概念

数据访问对象模式（Data Access Object Design Pattern）描述了如何创建提供透明访问任何数据源的对象。

注：DAO = Data Access Object

## 使用场景

1. 基类封装了访问数据库的SQL语句，同时提供了操作数据的方法（如：CRUD操作）；子类提供必要的信息，如：连接数据库的参数，以及表名、主键名等；子类也可以提供自己的接口，如：查询信息等。


## 代码示例

代码示例：[数据库访问](https://github.com/mumingv/php/tree/master/books/my_php_design_patterns/chapter_05)。


## FAQ

**问题描述：执行脚本时，php5.4提示如下错误。**

```bash
$ php index.php 
PHP Fatal error:  Call to undefined function mysql_connect() in ...
```

**问题原因**：php5.4版本默认安装是不带mysql插件的，需要自行安装。

**解决方法**：安装php-mysql或者php-mysqlnd均可。

```bash
$ yum install php-mysqlnd
```
```bash
$ yum install php-mysql
```

注：在php5.4版本安装php-mysql的话，会提示一个版本不匹配的一个警告。

```bash
$ yum install php-mysql
$ php index.php 
PHP Warning:  mysql_connect(): Headers and client library minor version mismatch. Headers:50547 Library:50625 in ...
```

