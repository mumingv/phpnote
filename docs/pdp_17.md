# 策略模式

## 基本概念

策略设计模式（Strategy Design Pattern）帮助构建的对象不必自身包含逻辑，而是能够根据需要利用其他对象中的算法。


## 使用场景

由于策略的多样性，将策略的接口开放出去，基类仅仅提供数据和接口。


## 代码示例

代码示例：[基于基类对象同时提供XML和JSON接口](https://github.com/mumingv/php/tree/master/books/my_php_design_patterns/chapter_17)。

```bash
$ php index.php 
CDXMLStrategy
{"CD":{"band":"beyond","title":"\u5149\u8f89\u5c81\u6708"}}
```

