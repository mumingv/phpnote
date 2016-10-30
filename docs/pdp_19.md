# 访问者模式

## 基本概念

访问者设计模式（Vistor Design Pattern）构造了包含某个算法的截然不同的对象，在父对象以标准方式使用这些对象时就会将该算法应用于父对象。


## 使用场景

基类对象调用以访问者类对象为参数的方法，在该方法中调用由基类声明、由访问者类实现的方法。不同的访问者类提供不同的方法，且供基类对象调用。

![UML](images/book_pdp/pdp_19.jpg)

## 代码示例

代码示例：[记录CD购买日志](https://github.com/mumingv/php/tree/master/books/my_php_design_patterns/chapter_19)。

