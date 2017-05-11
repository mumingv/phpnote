# [类/对象函数](https://github.com/mumingv/php/tree/master/func/classobject)

## 总结

### 类/对象存在判定(2)

###### 

|函数名称           |含义                                   |
|-------------------|---------------------------------------|
|class_exists       |检查类是否已定义                       |
|method_exists      |检查类的方法是否存在                   |


## method_exists 检查类的方法是否存在

函数原型：

```php
bool method_exists ( mixed $object , string $method_name )
```

### 示例：检查类的方法是否在指定的类当中

```php
var_dump(method_exists('Directory','read')); //bool(true)
```

### 示例：检查对象的方法是否在指定的类当中

```php
$directory = new Directory('.');
var_dump(method_exists($directory,'read')); //bool(true)
```

