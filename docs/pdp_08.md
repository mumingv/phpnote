# 外观模式

## 基本概念

外观设计模式（Facade Design Pattern）通过在必需的逻辑和方法的集合前创建简单的外观接口，其隐藏了来自调用对象的复杂性。


## 使用场景

1. 将一系列的处理逻辑封装起来，使用外观类对外提供统一的接口，方便外部调用。


## 代码示例

代码示例: [更改CD属性值为大写并生成XML文档](https://github.com/mumingv/php/tree/master/books/my_php_design_patterns/chapter_08)。

```php
$ php index.php 
<?xml version="1.0"?>
<CD><TITLE>LOVE YOU</TITLE><BAND>BEYOND</BAND><TRACKS><TRACK>FIRST SONG</TRACK><TRACK>SECOND SONG</TRACK><TRACK>THIRD SONG</TRACK></TRACKS></CD>
```

