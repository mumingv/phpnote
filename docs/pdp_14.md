# 原型模式

## 基本概念

原型设计模式（Proto Design Pattern）创建对象的方式是复制和克隆初始对象或模型，这种方式比创建新实例更有效。


## 使用场景

使用`clone`关键字直接从初始对象进行克隆，而不是使用`new`关键字创建新实例的方式进行创建对象。好处是可以省掉直接`new`一个对象产生的开销，如：构造函数`__construct()`中有很多创建对象的默认操作。


## 代码示例

代码示例：[让用户自定义CD专辑](https://github.com/mumingv/php/tree/master/books/my_php_design_patterns/chapter_14)。

### 关键点说明

1. 使用`clone`关键字克隆对象。

