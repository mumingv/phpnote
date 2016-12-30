# [数组函数](https://github.com/mumingv/php/tree/master/func/array)

## array_change_key_case 返回字符串键名全为小写或大写的数组

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-change-key-case.php)。

```php
array array_change_key_case ( array $input [, int $case = CASE_LOWER ] )
```

### 示例：将数组的键名改为小写

```php
$input_array = array("FirSt" => 1, "SecOnd" => 4); 
print_r(array_change_key_case($input_array));
```
```php
Array
(
    [first] => 1
    [second] => 4
)
```


### 示例：将数组的键名改为大写

```php
$input_array = array("FirSt" => 1, "SecOnd" => 4); 
print_r(array_change_key_case($input_array, CASE_UPPER));
```
```php
Array
(
    [FIRST] => 1
    [SECOND] => 4
)
```


## array_chunk 将一个数组分割成多个

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-chunk.php)。

```php
array array_chunk ( array $input , int $size [, bool $preserve_keys = false ] )
```

### 示例：将数组分隔成子数组，每个子数组的大小为2

```php
$input_array = array('a', 'b', 'c', 'd', 'e');
print_r(array_chunk($input_array, 2));
```
```php
Array
(
    [0] => Array
    (
        [0] => a
        [1] => b
    )

    [1] => Array
    (
        [0] => c
        [1] => d
    )

    [2] => Array
    (
        [0] => e
    )
)
```


### 示例：将数组分隔成子数组，每个子数组的大小为2，并且保留原数组的key

```php
$input_array = array('a', 'b', 'c', 'd', 'e');
print_r(array_chunk($input_array, 2, true));
```
```php
Array
(
    [0] => Array
    (
        [0] => a
        [1] => b
    )

    [1] => Array
    (
        [2] => c  # 这里的key没有变化
        [3] => d  # 这里的key没有变化
    )

    [2] => Array
    (
        [4] => e  # 这里的key没有变化
    )
)
```


## array_column (PHP5.5) 返回数组中指定的一列

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-column.php)。

```php
array array_column ( array $input , mixed $column_key [, mixed $index_key ] )
```

<font color="red">注：版本要求 >= PHP5.5</font>

### 示例：从二维数组中提取名为`first_name`的列，将其作为一维数组返回

```php
$records = array(
    array(
        'id' => 2135,
        'first_name' => 'John',
        'last_name' => 'Doe',
    ),
    array(
        'id' => 3245,          
        'first_name' => 'Sally',        
        'last_name' => 'Smith',
    ),
    array(
        'id' => 5342,
        'first_name' => 'Jane',
        'last_name' => 'Jones',
    ),
    array(
        'id' => 5623,          
        'first_name' => 'Peter',        
        'last_name' => 'Doe',  
    )
);
$first_names = array_column($records, 'first_name');
print_r($first_names);
```


## array_combine 创建一个数组，用一个数组的值作为其键名，另一个数组的值作为其值

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-combine.php)。

```php
array array_combine ( array $keys , array $values )
```

### 示例：根据两个一维数组构造一个二维数组

```php
$a = array('green', 'red', 'yellow');
$b = array('avocado', 'apple', 'banana');
$c = array_combine($a, $b);
print_r($c);
```
```php
Array
(       
    [green] => avocado
    [red] => apple
    [yellow] => banana
)
```


## array_count_values 统计数组中所有的值出现的次数

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-count-values.php)。

```php
array array_count_values ( array $input )
```

### 示例：统计数组中各value出现的次数

```php
$array = array(1, "hello", 1, "world", "hello");
print_r(array_count_values($array));
```
```php
Array   
(
    [1] => 2
    [hello] => 2
    [world] => 1
)
```


## array_diff_assoc 带索引检查计算数组的差集

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-diff-assoc.php)。

```php
array array_diff_assoc ( array $array1 , array $array2 [, array $... ] )
```

<font color="red">
说明：</br>
1. 和array_diff相比，不仅会比较值是否相同，也会比较键是否相同; </br>
2. 可以多个数组一起求差集，不仅仅限于两个; </br>
3. 键或值比较的时候，都是统一转换成字符串进行比较; </br>
</font>

### 示例：两个数组的差集，即：$array1 - $array2

```php
$array1 = array("a" => "green", "b" => "brown", "c" => "blue", "red"); 
$array2 = array("a" => "green", "yellow", "red");
$result = array_diff_assoc($array1, $array2);
print_r($result);              
```
```php
Array
( 
    [b] => brown
    [c] => blue
    [0] => red
)
```


### 示例：两个数组的差集，数字默认会转换成字符串进行比较

```php
$array1 = array(0, 1, 2);      
$array2 = array("00", "01", "2");
$result = array_diff_assoc($array1, $array2);
print_r($result);              
```
```php
Array
( 
    [0] => 0
    [1] => 1
)
```


### 多个数组的差集，即：$array1 - $array2 - $array3

```php
$array1 = array("a" => "green", "b" => "brown", "c" => "blue", "red");
$array2 = array("a" => "green", "yellow", "red");
$array3 = array("a" => "green", "b" => "brown");
$result = array_diff_assoc($array1, $array2, $array3);
print_r($result);
```
```php
Array
(
    [c] => blue
    [0] => red
)
```


## array_diff_key 使用键名比较计算数组的差集

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-diff-key.php)。

```php
array array_diff_key ( array $array1 , array $array2 [, array $... ] )
```

### 示例：两个数组的差集

```php
$array1 = array('blue'  => 1, 'red'  => 2, 'green'  => 3, 'purple' => 4);
$array2 = array('green' => 5, 'blue' => 6, 'yellow' => 7, 'cyan'   => 8);
$result = array_diff_key($array1, $array2);
print_r($result);
```
```php
Array
(
    [red] => 2
    [purple] => 4
)
```


### 示例：多个数组的差集

```php
$array1 = array('blue'  => 1, 'red'  => 2, 'green'  => 3, 'purple' => 4);
$array2 = array('green' => 5, 'blue' => 6, 'yellow' => 7, 'cyan'   => 8);
$array3 = array('purple' => 9);
$result = array_diff_key($array1, $array2, $array3);
print_r($result);
```
```php
Array
(
    [red] => 2
)
```


## array_diff 计算数组的差集

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-diff.php)。

```php
array array_diff ( array $array1 , array $array2 [, array $... ] )
```

### 示例：两个数组的差集

```php
$array1 = array("a" => "green", "red", "blue", "red", "purple");
$array2 = array("b" => "green", "yellow", "red");
$result = array_diff($array1, $array2);
print_r($result);
```
```php
Array
(
    [1] => blue
    [3] => purple
)
```


### 示例：多个数组的差集

```php
$array1 = array("a" => "green", "red", "blue", "red", "purple");
$array2 = array("b" => "green", "yellow", "red");
$array3 = array(0 => "purple");
$result = array_diff($array1, $array2, $array3);
print_r($result);
```
```php
Array
(
    [1] => blue
)
```




