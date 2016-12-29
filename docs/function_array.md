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

### 统计数组中各value出现的次数

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
















