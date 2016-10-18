# 使用数组

如未特别指明，本章对应的代码可参考[示例](https://github.com/mumingv/php/blob/master/books/my_php_and_mysql_web_develop/chapter_03/array.php)。

数组可以具有多个元素，每个元素有一个值，这个值可以是数字、字符串或者是另一个数组。一个包含其他数组的数组称为多维数组。


## 什么是数组

标量变量就是一个用来存储数值的命名区域；相应地，数组就是一个用来存储一系列变量值的命名区域。可以使用数组组织标量变量。

存储在素组中的值称为数组元素，每个数组元素都有一个相关的索引（也称为关键字），可以使用它来访问数组元素。

PHP支持混合索引，即：在一个数组中可以同时使用数字和字符串作为索引，甚至其它类型也是可以的。

PHP数组主要分为两大类：数字索引数组和关联数组。关联数组类似于其他编程语言的映射表。


## 数字索引数组

### 数字索引数组的初始化

创建数字索引数组的几种方式：

1. 自动创建方式

```clike
$products[0] = 'Tires';
$products[1] = 'Oil';
$products[2] = 'Spark Plugs';
```
```clike
Array
(
    [0] => Tires
    [1] => Oil
    [2] => Spark Plugs
)
```

PHP数组和其他类型一样，数组并不需要预先初始化或创建；在第一次使用数组的时候，会自动创建。数组的大小将根据所增加元素的多少动态地变化，很多其他编程语言都并不支持这种特性。

当然，也可以先显示指明`$products`是一个数组（空数组），然后再向其中添加元素。
```clike
$products = [];
$products[0] = 'Tires';
$products[1] = 'Oil';
$products[2] = 'Spark Plugs';
```

2. 使用`array()`

```clike
$products = array('Tires', 'Oil', 'Spark Plugs');
```
```clike
Array
(
    [0] => Tires
    [1] => Oil
    [2] => Spark Plugs
)
```

3. 使用`range()`函数

`range()`函数创建数字数组，示例如下：

创建一个连续的数字数组：
```clike
$numbers = range(1, 10);
```
```clike
Array
(
    [0] => 1
    [1] => 2
    [2] => 3
    [3] => 4
    [4] => 5
    [5] => 6
    [6] => 7
    [7] => 8
    [8] => 9
    [9] => 10
)
```

创建一个奇数数组：
```clike
$numbers = range(1, 10, 2);
```
```clike
Array
(
    [0] => 1
    [1] => 3
    [2] => 5
    [3] => 7
    [4] => 9
)
```

4. 从文件载入数组

`file()`函数读取文件，并返回一个数组，将文件中的每一行作为数组的一个元素。

```clike
$products = file("file.txt");
```
```clike
Array
(
    [0] => Tires

    [1] => Oil

    [2] => 

    [3] => Spark Plugs

)
```

出现上面打印不紧凑的情况，是因为每行末尾的换行符也被读取到数组元素当中了，另外空行也被当作一个单独的元素了。要解决这个问题，使用参数`(FILE_IGNORE_NEW_LINES | FILE_SKIP_EMPTY_LINES)`即可。

```clike
$products = file("file.txt", (FILE_IGNORE_NEW_LINES | FILE_SKIP_EMPTY_LINES));
```
```clike
Array
(
    [0] => Tires
    [1] => Oil
    [2] => Spark Plugs
)
```

5. 从数据库载入数组

待后续补充。


### 访问数组的内容

和C、C++、Java等其他大部分编程语言一样，数组的下标是从0开始的。

访问方式如下
```clike
echo $products[1];
```
```clike
Oil
```


### 使用循环访问数组

1. `while`循环

略。

2. `do...while`循环

略。

3. `for`循环

```clike
for ($i = 0; $i < 3; $i++) {
    echo $products[$i] . PHP_EOL;
}
```
```clike
Tires
Oil
Spark Plugs
```

4. `foreach`循环

```clike
foreach ($products as $product) {
    echo $product . PHP_EOL;
}
```
```clike
Tires
Oil
Spark Plugs
```

也可以同时使用key

```clike
foreach ($products as $key => $product) {
    echo $key.' => '.$product.PHP_EOL;
}
```
```clike
0 => Tires
1 => Oil
2 => Spark Plugs
```


## 使用不同索引的数组

## 数组操作符

## 多维数组

## 数组排序

## 多维数组的排序

## 对数组进行重新排序

## 从文件载入数组

## 执行其他数组操作

## 进一步学习


