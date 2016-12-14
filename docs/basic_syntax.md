# 基本语法

## 注释

支持C、C++以及Shell三种风格的注释。

```
/* ... */
```

```
// ...
```

```
# ...
```

## 类型

### 数组

详细内容，请参考官方文档：[php.net](http://php.net/manual/zh/language.types.array.php)。

示例：创建一个数组

```php
$arr = ['Apple', 'Oragnge'];
print_r($arr);
```
```php
Array
(
    [0] => Apple
    [1] => Oragnge
)
```

## 变量


##  函数


## 字符串

字符串定义使用单引号或者双引号都可以。

```php
$str = "Hello World!";
```

```php
$str = 'Hello World!';
```

单引号字符串不能扩展变量和转义字符，双引号字符串可以扩展变量和转义字符。

```php
$name = 'Jay';
echo('My name is $name!\n');  # 输出：My name is $name!\n
echo("My name is $name!\n");  # 输出：My name is Jay!
```

一般情况下，要扩展变量的话，将其直接放进双引号中就可以了。但是对于数组或复杂对象中的变量的话，就需要使用大括号（PHP解释器进行处理）或者使用字符串连接符（点号）。

```php
$user = array(
    "name" => "Jay",
    "gender" => "male",
);
echo "My name is {$user['name']}, gender is {$user['gender']}.\n";
echo "My name is ".$user['name'].", gender is ".$user['gender'].".\n";
```
这两种方法都会有相同的输出。
```php
My name is Jay, gender is male.
```

字符串一般情况下作为标量值，但也可以当作一个数组进行处理。

```php
$str = "Hello World!";
$length = strlen($str);
for ($i = 0; $i < $length; $i++) {
    echo "{$str[$i]}\n";
}
```
```php
H
e
l
l
o
 
W
o
r
l
d
!
```

<font color="red">说明：字符串作为数组的能力仅限于此，不能将字符串作为参数传递给处理数组的函数。</font>



## 分支语句


## 循环语句


## 关键字


## 其他


