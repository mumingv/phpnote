# 工厂模式

## 基本概念

工厂设计模式（Factory Design Pattern）用于提供获取某个类的新实例的一个接口。


## 使用场景

有多个基类，这些基类对外具有相同的接口方法；如果在具体要使用哪个基类实例化对象时，需要进行类型的判断才能确定，这时就可以考虑使用工厂模式来替代这些判断。简要示例如下；

1. 不使用工厂模式实例化对象
```php
if ($type = 'A') {
        $obj = new ClassA();
} else if ($type = 'B') {
        $obj = new ClassB();
} else if ($type = 'C') {
        $obj = new ClassC();
} else {
        $obj = new ClassOther();
}
```

2. 使用工厂模式实例化对象
```php
$obj = FactoryClass::getInstance($type);
```


## 代码示例

代码示例: [创建不同CD类的对象](https://github.com/mumingv/php/tree/master/books/my_php_design_patterns/chapter_9)。

