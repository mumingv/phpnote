# 观察者模式

## 基本概念

观察者设计模式（Observer Design Pattern）能够更便利地创建查看目标对象状态的对象，并且提供与核心对象非耦合的指定性功能。


## 使用场景

一个类的对象修改了某些属性或者时，通知观察者类的对象哪些数据被修改了。


## 代码示例

代码示例：[购买CD事件调用观察者接口](https://github.com/mumingv/php/tree/master/books/my_php_design_patterns/chapter_13)。

### 关键点说明

1. 观察者对象需要注册到基类对象中；
2. 基类对象的某个行为触发调用相关观察者的接口函数；

