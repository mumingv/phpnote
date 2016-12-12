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


## use

`use`用于导入/使用别名。类似于类Unix系统中创建其它文件或目录的符号链接。

导入命名空间：

```php
use My\Full\NSname;  // 等价于：use My\Full\NSname as NSname;
```

导入类：

```php
use My\Full\Classname as Another;
```

导入全局类：

```php
use Classname;
```

导入函数：

```php
use function My\Full\functionName;
```

```php
use function My\Full\functionName as func;  // 设置别名
```

导入常量：

```php
use const My\Full\CONSTANT;
```

具体示例，请参考：[PHP手册](http://php.net/manual/zh/language.namespaces.importing.php)。



