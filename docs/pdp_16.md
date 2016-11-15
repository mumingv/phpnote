# 单元素模式

## 基本概念

单元素设计模式（Single Element Design Pattern）通过提供对自身共享实例的访问，用于限制特定对象只能被创建一次。


## 使用场景

当需要重复利用某个资源（如：数据库连接）时，可以使用单元素模式。


## 代码示例

代码示例：[数据库操作对象使用单元素模式](https://github.com/mumingv/php/tree/master/books/my_php_design_patterns/chapter_16)。

### 关键点说明

1. 将构造函数声明为`protected`就可以使得该类无法直接被实例化，如下所示
```php
protected function __construct() {
    ...
}
```
这样一来，就只能在类的内部使用`new self`来进行实例化操作。

