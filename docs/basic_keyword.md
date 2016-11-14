# 关键字

## const

`const`用于声明类常量，可以通过类名或者对象名的域操作符`::`进行访问。

```php
echo ClassName::CONSTANT;
```

```php
$obj = new ClassName();
echo $obj::CONSTANT;
```

具体示例，请参考：[PHP手册](http://php.net/manual/zh/language.oop5.constants.php)。


## static


## abstract


## clone

`clone`用于拷贝/复制一个对象，如果对象中有`__clone()`方法，则新对象会在拷贝/复制完成后进行调用。

```php
$copy_of_object = clone $object;
```

具体示例，请参考：[PHP手册](http://www.php.net/manual/zh/language.oop5.cloning.php)。

