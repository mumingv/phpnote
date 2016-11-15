# 策略模式

## 基本概念

策略设计模式（Strategy Design Pattern）帮助构建的对象不必自身包含逻辑，而是能够根据需要利用其他对象中的算法。


## 使用场景

由于策略的多样性，将策略的接口开放出去，基类仅仅提供数据和接口。


## 代码示例

代码示例：[基于基类对象同时提供XML和JSON接口](https://github.com/mumingv/php/tree/master/books/my_php_design_patterns/chapter_17)。

```bash
$ php index.php 
<?xml version="1.0"?>
<CD><TITLE>&#x5149;&#x8F89;&#x5C81;&#x6708;</TITLE><BAND>beyond</BAND></CD>
{"CD":{"band":"beyond","title":"\u5149\u8f89\u5c81\u6708"}}
```

XML文档用浏览器打开的效果为：
```
  <?xml version="1.0"?>
- <CD>
    <TITLE>光辉岁月</TITLE>
    <BAND>beyond</BAND>
  </CD>
```


## FAQ

**问题描述：执行脚本时，php5.4提示如下错误。**

```bash
$ php index.php 
PHP Fatal error:  Class 'DomDocument' not found in ...
```

**问题原因**：php5.4版本默认安装是不带xml插件的，需要自行安装。

**解决方法**：安装php-xml即可。

```bash
$ sudo yum install php-xml
```

