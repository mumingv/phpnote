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


## array_diff_uassoc 用用户提供的回调函数做索引检查来计算数组的差集

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-diff-uassoc.php)。

```php
array array_diff_uassoc ( array $array1 , array $array2 [, array $... ], callable $key_compare_func )
```

### 示例：求两个数组的差集 $array1 - $array2

```php
function key_compare_func($a, $b)
{
    if ($a === $b) {
        return 0;
    }
    return (($a > $b) ? 1 : -1);
}
$array1 = array("a" => "green", "b" => "brown", "c" => "blue", "red");
$array2 = array("a" => "green", "yellow", "red");
$result = array_diff_uassoc($array1, $array2, "key_compare_func");
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


## array_diff_ukey 用回调函数对键名比较计算数组的差集

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-diff-ukey.php)。

```php
array array_diff_ukey ( array $array1 , array $array2 [, array $ ... ], callable $key_compare_func )
```

### 示例：两个数组的差集

```php
function key_compare_func($key1, $key2)
{
    if ($key1 == $key2)
        return 0;
    else if ($key1 > $key2)
        return 1;
    else
        return -1;
}
$array1 = array('blue'  => 1, 'red'  => 2, 'green'  => 3, 'purple' => 4);
$array2 = array('green' => 5, 'blue' => 6, 'yellow' => 7, 'cyan'   => 8);
print_r(array_diff_ukey($array1, $array2, 'key_compare_func'));
```
```php
Array
(
    [red] => 2
    [purple] => 4
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


## array_fill_keys 使用指定的键和值填充数组

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-fill-keys.php)。

```php
array array_fill_keys ( array $keys , mixed $value )
```

```php
$keys = array('foo', 5, 10, 'bar');
$a = array_fill_keys($keys, 'banana');
print_r($a);
```
```php
Array
(
    [foo] => banana
    [5] => banana
    [10] => banana
    [bar] => banana
)
```


## array_fill 用给定的值填充数组

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-fill.php)。

```php
array array_fill ( int $start_index , int $num , mixed $value )
```

### 示例：填充数组，第一个元素的key为正数

```php
$a = array_fill(5, 6, 'banana');
print_r($a);
```
```php
Array
(
    [5] => banana
    [6] => banana
    [7] => banana
    [8] => banana
    [9] => banana
    [10] => banana
)
```


### 示例：填充数组，第一个元素的key为负数

```php
$b = array_fill(-2, 4, 'pear');
print_r($b);
```
```php
Array
(
    [-2] => pear  # 第1个元素的key对应函数的第1个参数
    [0] => pear   # 第2个元素的key为0
    [1] => pear
    [2] => pear
)
```


## array_filter 用回调函数过滤数组中的单元

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-filter.php)。

```php
array array_filter ( array $array [, callable $callback [, int $flag = 0 ]] )
```

### 示例：过滤数组中基数值或偶数值

```php
function odd($var)
{
    return($var & 1);
}

function even($var)
{
    return(!($var & 1));
}

$array1 = array("a"=>1, "b"=>2, "c"=>3, "d"=>4, "e"=>5);
$array2 = array(6, 7, 8, 9, 10, 11, 12);

echo "Odd :\n";
print_r(array_filter($array1, "odd"));
echo "Even:\n";
print_r(array_filter($array2, "even"));
```
```php
Odd :
Array
(
    [a] => 1
    [c] => 3
    [e] => 5
)
Even:
Array
(
    [0] => 6
    [2] => 8
    [4] => 10
    [6] => 12
)
```


### 示例：不使用自定义的判定函数，去除值为FALSE的项

```php
$array1 = array("apple" => 5, "banana" => 0, "pear" => 6);
print_r(array_filter($array1));
```
```php
Array
(
    [apple] => 5
    [pear] => 6
)
```


## array_flip 交换数组中的键和值

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-flip.php)。

```php
array array_flip ( array $trans )
```

### 交换键和值

```php
$trans = array("a" => 1, "b" => 2, "c" => 3);
$trans = array_flip($trans);
print_r($trans);
```
```php
Array
(
    [1] => a
    [2] => b
    [3] => c
)
```


### 交换键和值，含有多个值相同的项，则只保留最后一个

```php
$trans = array("a" => 1, "b" => 2, "c" => 2);
$trans = array_flip($trans);
print_r($trans);
```
```php
Array
(
    [1] => a
    [2] => c  # key为"b"的项被丢弃
)
```


## array_intersect_assoc 带索引检查计算数组的交集

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-intersect-assoc.php)。

```php
array array_intersect_assoc ( array $array1 , array $array2 [, array $ ... ] )
```

### 示例：获取两个数组的交集（键和值都相同才会保存到结果中）

```php
$array1 = array("a" => "green", "b" => "brown", "c" => "blue", "red");
$array2 = array("a" => "green", "b" => "yellow", "blue", "red");
$result_array = array_intersect_assoc($array1, $array2);
print_r($result_array);
```
```php
Array
(
    [a] => green
```


## array_intersect_key 使用键名比较计算数组的交集

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-intersect-assoc.php)。

```php
array array_intersect_key ( array $array1 , array $array2 [, array $ ... ] )
```

### 示例：获取两个数组的交集（键相同就会保存到结果中）

```php
$array1 = array('blue'  => 1, 'red'  => 2, 'green'  => 3, 'purple' => 4);
$array2 = array('green' => 5, 'blue' => 6, 'yellow' => 7, 'cyan'   => 8);
print_r(array_intersect_key($array1, $array2));
```
```php
Array
(
    [blue] => 1
    [green] => 3
)
```


## array_intersect_uassoc 带索引检查计算数组的交集，用回调函数比较索引

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-intersect-assoc.php)。

```php
array array_intersect_uassoc ( array $array1 , array $array2 [, array $ ... ], callable $key_compare_func )
```

### 示例：获取两个数组的交集，用户提供自定义比较函数
```php
$array1 = array("a" => "green", "b" => "brown", "c" => "blue", "red");
$array2 = array("a" => "GREEN", "B" => "brown", "yellow", "red");
$result = array_intersect_uassoc($array1, $array2, "strcasecmp");
print_r($result);
```
```php
Array
(
    [b] => brown
)
```


## array_intersect_ukey 用回调函数比较键名来计算数组的交集

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-intersect-ukey.php)。

```php
array array_intersect_ukey ( array $array1 , array $array2 [, array $... ], callable $key_compare_func )
```

### 示例：获取两个数组的交集

```php
function key_compare_func($key1, $key2)
{
    if ($key1 == $key2)
        return 0;
    else if ($key1 > $key2)
        return 1;
    else
        return -1;
}
$array1 = array('blue'  => 1, 'red'  => 2, 'green'  => 3, 'purple' => 4);
$array2 = array('green' => 5, 'blue' => 6, 'yellow' => 7, 'cyan'   => 8);
print_r(array_intersect_ukey($array1, $array2, 'key_compare_func'));
```
```php
Array
(
    [blue] => 1
    [green] => 3
)
```


## array_intersect 计算数组的交集

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-intersect.php)。

```php
array array_intersect ( array $array1 , array $array2 [, array $ ... ] )
```

### 示例：获取两个数组的交集

```php
$array1 = array("a" => "green", "red", "blue");
$array2 = array("b" => "green", "yellow", "red");
$result = array_intersect($array1, $array2);
print_r($result);
```
```php
Array
(
    [a] => green
    [0] => red
)
```


### 示例：获取多个数组的交集

```php
$array1 = array("a" => "green", "red", "blue");
$array2 = array("b" => "green", "yellow", "red");
$array3 = array("c" => "green", "blue");
$result = array_intersect($array1, $array2, $array3);
print_r($result);
```
```php
Array
(
    [a] => green
)
```


## array_key_exists 检查给定的键名或索引是否存在于数组中

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-key-exists.php)。

```php
bool array_key_exists ( mixed $key , array $search )
```

### 示例：检查key是否在数组当中

```php
$search_array = array('first' => 1, 'second' => 4);
if (array_key_exists('first', $search_array)) {
        echo "The 'first' element is in the array\n";
}
```
```php
The 'first' element is in the array
```


### 示例：isset() 对于数组中为 NULL 的值不会返回 TRUE，而 array_key_exists() 会返回TRUE

```php
$search_array = array('first' => null, 'second' => 4);
if (isset($search_array['first'])) {
    echo "isset: The 'first' element is in the array\n";
} else {
    echo "isset: The 'first' element is not in the array\n";  // 打印该行
}

if (array_key_exists('first', $search_array)) {
    echo "array_key_exists: The 'first' element is in the array\n";  // 打印该行
} else {
    echo "array_key_exists: The 'first' element is not in the array\n";
}
```
```php
isset: The 'first' element is not in the array
array_key_exists: The 'first' element is in the array
```


## array_keys 返回数组中部分的或所有的键名

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-keys.php)。

```php
array array_keys ( array $array [, mixed $search_value [, bool $strict = false ]] )
```

### 示例：返回所有键名

```php
$array = array(0 => 100, "color" => "red");
print_r(array_keys($array));
```
```php
Array
(
    [0] => 0
    [1] => color
)
```


### 示例：返回指定的值对应的键名

```php
$array = array("blue", "red", "green", "blue", "blue");
print_r(array_keys($array, "blue"));
```
```php
Array
(
    [0] => 0
    [1] => 3
    [2] => 4
)
```


### 示例：返回指定的值对应的键名，使用严格的比较

```php
$array = array("blue", "red", "green", "blue", "blue");
print_r(array_keys($array, "blue", true));
```
```php
Array
(
    [0] => 0
    [1] => 3
    [2] => 4
)
```


## array_map 为数组的每个元素应用回调函数

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-map.php)。

```php
array array_map ( callable $callback , array $array1 [, array $... ] )
```

### 示例：一个数组参数

```php
function cube($n)
{
    return($n * $n * $n);
}
$a = array(1, 2, 3, 4, 5); 
$b = array_map("cube", $a);
print_r($b);
```
```php
Array
(
    [0] => 1
    [1] => 8
    [2] => 27
    [3] => 64
    [4] => 125
)
```


### 示例：两个数组参数

```php
function add($m, $n)
{
    return($m + $n);
}
$a = array(1, 2, 3, 4, 5);
$b = array(1, 2, 3, 4, 5);
$c = array_map("add", $a, $b);
print_r($c);
```
```php
Array
(
    [0] => 2
    [1] => 4
    [2] => 6 
    [3] => 8
    [4] => 10
)
```


## array_merge_recursive 递归地合并一个或多个数组

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-merge-recursive.php)。

### 示例：递归合并数组

```php
$ar1 = array("color" => array("favorite" => "red"), 5);
$ar2 = array(10, "color" => array("favorite" => "green", "blue"));
$result = array_merge_recursive($ar1, $ar2);
print_r($result);
```
```php
Array
(
    [color] => Array
        (
            [favorite] => Array
                (
                    [0] => red
                    [1] => green
                )

            [0] => blue
        )

    [0] => 5
    [1] => 10
)
```


## array_merge 合并一个或多个数组

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-merge.php)。

```php
array array_merge ( array $array1 [, array $... ] )
```

<font color="red">说明：
1. 如果两个字符串key值相同，则后面的直接丢弃，不会覆盖前面的；
2. 如果两个数字key值相同，则不会丢弃，所有的数字key值均会重新编号；
</font>

### 示例：合并数组

```php
$array1 = array("color" => "red", 2, 4);
$array2 = array("a", "b", "color" => "green", "shape" => "trapezoid", 4);
$result = array_merge($array1, $array2);
print_r($result);
```
```php
Array
(
    [color] => green
    [0] => 2
    [1] => 4
    [2] => a
    [3] => b
    [shape] => trapezoid
    [4] => 4
)
```


## array_multisort 对多个数组或多维数组进行排序

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-multisort.php)。

```php
bool array_multisort ( array &$arr [, mixed $arg = SORT_ASC [, mixed $arg = SORT_REGULAR [, mixed $... ]]] )
```

### 示例：对多个数组进行排序

```php
$ar1 = array(10, 100, 100, 0);
$ar2 = array(1, 3, 2, 4);
array_multisort($ar1, $ar2);
var_export($ar1);
```
```php
array (
    0 => 0,
    1 => 10,
    2 => 100,
    3 => 100,
)
```
```php
var_export($ar2);
```
```php
array (
    0 => 4,
    1 => 1,
    2 => 2,
    3 => 3,
)
```


### 示例：对多维数组按行进行排序

```php
$ar = array(
    array("10", 11, 100, 100, "a"),
    array(   1,  2, "2",   3,   1)
);
array_multisort($ar[0], SORT_ASC, SORT_STRING,
    $ar[1], SORT_DESC, SORT_NUMERIC);
var_export($ar);
```
```php
array (
    0 => 
    array (
        0 => '10',
        1 => 100,
        2 => 100,
        3 => 11,
        4 => 'a',
    ),
    1 => 
    array (
        0 => 1,
        1 => 3,
        2 => '2',
        3 => 2,
        4 => 1,
    ),
)
```


## array_pad 用值将数组填补到指定长度

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-pad.php)。

```php
array array_pad ( array $input , int $pad_size , mixed $pad_value )
```

### 示例：填充数组，在数组尾部进行填充

```php
$input = array(12, 10, 9); 
$result1 = array_pad($input, 5, 0); 
print_r($result1);
```
```php
Array
(
    [0] => 12
    [1] => 10
    [2] => 9
    [3] => 0
    [4] => 0
)
```


### 示例：填充数组，在数组头部进行填充

```php
$result2 = array_pad($input, -7, -1);
print_r($result2);
```
```php
Array
(
    [0] => -1
    [1] => -1
    [2] => -1
    [3] => -1
    [4] => 12
    [5] => 10
    [6] => 9
)
```


### 示例：如果目标长度小于当前长度，则不进行填充

```php
$result3 = array_pad($input, 2, "noop");
print_r($result3);
```
```php
Array
(
    [0] => 12
    [1] => 10
    [2] => 9
)
```


## array_pop 将数组最后一个单元弹出（出栈）

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-pop.php)。

```php
mixed array_pop ( array &$array )
```

### 示例：将元素弹出栈，返回值为弹出的元素

```php
$stack = array("orange", "banana", "apple", "raspberry");
$fruit = array_pop($stack);
print_r($fruit);
echo PHP_EOL;
print_r($stack);
```
```php
raspberry
Array
(
    [0] => orange
    [1] => banana
    [2] => apple
)
```


## array_product 计算数组中所有值的乘积

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-product.php)。

```php
number array_product ( array $array )
```

### 示例：计算数组所有元素的乘积

```php
$a = array(2, 4, 6, 8); 
echo "product(a) = " . array_product($a) . "\n";
```
```php
product(a) = 384
```


### 示例：对空数组计算乘积

```php
$a = array();
echo "product(a) = " . array_product($a) . "\n";
```
```php
product(a) = 1
```


## array_push 将一个或多个单元压入数组的末尾（入栈）

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-push.php)。

```php
int array_push ( array &$array , mixed $var [, mixed $... ] )
```

<font color="red">
说明：<br/>
1. 该函数和语句 "$array[] = $var" 功能相同；<br/>
2. 返回值为元素插入后，数组中元素的总个数；<br/>
</font>

### 示例：入栈操作
```php
$stack = array("orange", "banana");
$number = array_push($stack, "apple", "raspberry");
print_r($stack);
print_r($number);
```
```php
Array
(
    [0] => orange
    [1] => banana
    [2] => apple
    [3] => raspberry
)
4
```


## array_rand 从数组中随机取出一个或多个单元

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-rand.php)。

```php
mixed array_rand ( array $input [, int $num_req = 1 ] )
```

### 示例：随机获取一个元素的键名，返回键名单个值 

```php
$input = array("Neo", "Morpheus", "Trinity", "Cypher", "Tank");
$rand_key = array_rand($input);
print_r($rand_key);  // 4
echo "\n";
```


### 示例：随机获取两个元素的键名，返回包含多个键名的数组

```php
$rand_keys = array_rand($input, 2);
print_r($rand_keys);
```
```php
Array
(
    [0] => 0
    [1] => 2
)
```


## array_reduce 用回调函数迭代地将数组简化为单一的值

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-reduce.php)。

```php
mixed array_reduce ( array $input , callable $function [, mixed $initial = NULL ] )
mixed callback ( mixed &$result , mixed $item )
```

### 示例：简化数组，计算数组中所有元素的和

```php
function rsum($v, $w)
{
    $v += $w;
    return $v;
}
$a = array(1, 2, 3, 4, 5);
$b = array_reduce($a, "rsum");
print_r($b);
echo "\n";
```
```php
15
```


### 示例：简化数组，计算数组中所有元素的积

<font color="red">说明：第三个参数为初始值。</font>

```php
function rmul($v, $w)
{
    $v *= $w;
    return $v;
}
$a = array(1, 2, 3, 4, 5);
$c = array_reduce($a, "rmul", 10);
print_r($c);
echo "\n";
```
```php
1200
```


### 示例：简化空数组

```php
function rsum2($v, $w)
{
    $v += $w;
    return $v;
}
$x = array();
$d = array_reduce($x, "rsum2", "No data to reduce");
print_r($d);
echo "\n";
```
```php
No data to reduce
```


## array_replace_recursive 使用传递的数组递归替换第一个数组的元素

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-replace-recursive.php)。

```php
array array_replace_recursive ( array $array1 , array $array2 [, array $... ] )
```

### 示例：使用一个数组作为替换数组

```php
$base = array('citrus' => array( "orange") , 'berries' => array("blackberry", "raspberry"), );
$replacements = array('citrus' => array('pineapple'), 'berries' => array('blueberry'));
$basket = array_replace_recursive($base, $replacements);
print_r($basket);
```
```php
Array
(
    [citrus] => Array
        (
            [0] => pineapple
        )

    [berries] => Array
        (
            [0] => blueberry
            [1] => raspberry
        )
)
```


### 示例：使用两个数组作为替换数组

```php
$base = array('citrus' => array("orange") , 'berries' => array("blackberry", "raspberry"), 'others' => 'banana' );
$replacements = array('citrus' => 'pineapple', 'berries' => array('blueberry'), 'others' => array('litchis'));
$replacements2 = array('citrus' => array('pineapple'), 'berries' => array('blueberry'), 'others' => 'litchis');
$basket = array_replace_recursive($base, $replacements, $replacements2);
print_r($basket);
```
```php
Array
(
    [citrus] => Array
        (
            [0] => pineapple
        )

    [berries] => Array
        (
            [0] => blueberry
            [1] => raspberry
        )

    [others] => litchis
)
```


## array_replace 使用传递的数组替换第一个数组的元素

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-replace.php)。

```php
array array_replace ( array $array1 , array $array2 [, array $... ] )
```

### 示例：使用一个数组作为替换数组

```php
$base = array("orange", "banana", "apple", "raspberry");
$replacements = array(0 => "pineapple", 4 => "cherry");
$replacements2 = array(0 => "grape");
$basket = array_replace($base, $replacements, $replacements2);
print_r($basket);
```
```php
Array
(
    [0] => grape
    [1] => banana
    [2] => apple
    [3] => raspberry
    [4] => cherry
)
```


## array_reverse 返回一个单元顺序相反的数组

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-reverse.php)。

```php
array array_reverse ( array $array [, bool $preserve_keys = false ] )
```

### 示例：颠倒数组，key值重新编号

```php
$input  = array("php", 4.0, array("green", "red"));
$result = array_reverse($input);
print_r($result);
```
```php
Array
(
    [0] => Array
    (
        [0] => green
        [1] => red
    )

    [1] => 4
    [2] => php
)
```


### 示例：颠倒数组，key值保留

```php
$input  = array("php", 4.0, array("green", "red"));
$result_keyed = array_reverse($input, true);
print_r($result);
```
```php
Array
(
    [2] => Array
    (
        [0] => green
        [1] => red
    )

    [1] => 4
    [0] => php
)
```


## array_search 在数组中搜索给定的值，如果成功则返回相应的键名

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-search.php)。 

### 示例：在数组中搜索值

```php
$array = array(0 => 'blue', 1 => 'red', 2 => 'green', 3 => 'red');
$key = array_search('green', $array); // $key = 2;
echo($key."\n");
$key = array_search('red', $array);   // $key = 1;
echo($key."\n");
```


## array_shift 将数组开头的单元移出数组

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-shift.php)。

```php
mixed array_shift ( array &$array )
```

### 示例：移除开头的单元，数组的key值会自动调整

```php
$stack = array("orange", "banana", "apple", "raspberry");
$fruit = array_shift($stack);
var_export($stack);
echo PHP_EOL;
```
```php
array (
  0 => 'banana',
  1 => 'apple',
  2 => 'raspberry',
)
```


## array_slice 从数组中取出一段

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-slice.php)。

```php
array array_slice ( array $array , int $offset [, int $length = NULL [, bool $preserve_keys = false ]] )
```

### 示例：截取数组第2个元素一直到最后一个元素

```php
$input = array("a", "b", "c", "d", "e");
$output = array_slice($input, 2);      // returns "c", "d", and "e"
var_export($output);
```
```php
array (
    0 => 'c',
    1 => 'd',
    2 => 'e',
)
```


### 示例：截取数组倒数第二个元素

```php
$input = array("a", "b", "c", "d", "e");
$output = array_slice($input, -2, 1);  // returns "d"
var_export($output);
```
```php
array (
    0 => 'd',
)
```


### 示例：获取数组的前三个元素

```php
$input = array("a", "b", "c", "d", "e");
$output = array_slice($input, 0, 3);   // returns "a", "b", and "c"
var_export($output);
```
```php
array (
    0 => 'a',
    1 => 'b',
    2 => 'c',
)
```


### 示例：获取数组元素的同时，保留原key值

```php
$input = array("a", "b", "c", "d", "e");
print_r(array_slice($input, 2, -1, true));
```
```php
Array
(
    [2] => c
    [3] => d
)
```


## array_splice 把数组中的一部分去掉并用其它值取代

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-splice.php)。

```php
array array_splice ( array &$input , int $offset [, int $length = 0 [, mixed $replacement ]] )
```

<font color="red">
关于参数$length：</ br>
1. 如果省略 length，则移除数组中从 offset 到结尾的所有部分；
2. 如果指定了 length 并且为正值，则移除这么多单元；
3. 如果指定了 length 并且为负值，则移除从 offset 到数组末尾倒数 length 为止中间所有的单元；
4. 当给出了 replacement 时要移除从 offset 到数组末尾所有单元时，用 count($input) 作为 length； 
</font>

### 示例：删除数组中第二个及之后的元素

```php
$input = array("red", "green", "blue", "yellow");
array_splice($input, 2);
var_export($input);
```
```php
array (
    0 => 'red',
    1 => 'green',
)
```


### 示例：删除数组中除了首尾之外的所有元素

```php
$input = array("red", "green", "blue", "yellow");
array_splice($input, 1, -1);
var_export($input);
```php
```
array (
    0 => 'red',
    1 => 'yellow',
)
```


### 示例：替换元素（多个元素替换成一个）

```php
$input = array("red", "green", "blue", "yellow");
array_splice($input, 1, count($input), "orange");
var_export($input);
```
```php
array (
    0 => 'red',
    1 => 'orange',
)
```


### 示例：替换元素（一个元素替换成多个）

```php
$input = array("red", "green", "blue", "yellow");
array_splice($input, -1, 1, array("black", "maroon"));
var_export($input);
```
```php
array (
    0 => 'red',
    1 => 'green',
    2 => 'blue',
    3 => 'black',
    4 => 'maroon',
)
```


### 插入元素

```php
$input = array("red", "green", "blue", "yellow");
array_splice($input, 3, 0, "purple");
var_export($input);
```
```php
array (
    0 => 'red',
    1 => 'green',
    2 => 'blue',
    3 => 'purple',
    4 => 'yellow',
)
```


## array_sum 计算数组中所有值的和

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-sum.php)。

```php
number array_sum ( array $array )
```

### 示例：计算数组中所有值的和，整数求和

```php
$a = array(2, 4, 6, 8);
echo "sum(a) = " . array_sum($a) . "\n"; //sum(a) = 20
```
```php
sum(a) = 20
```


### 示例：计算数组中所有值的和，浮点数求和

```php
$b = array("a" => 1.2, "b" => 2.3, "c" => 3.4);
echo "sum(b) = " . array_sum($b) . "\n"; //sum(b) = 6.9
```
```php
sum(b) = 6.9
```


## array_udiff_assoc 带索引检查计算数组的差集，用回调函数比较数据

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-udiff-assoc.php)。

```php
array array_udiff_assoc ( array $array1 , array $array2 [, array $ ... ], callable $data_compare_func )
```

### 示例：两个数组的差集

```php
class cr {
    private $priv_member;
    function cr($val)
    {
        $this->priv_member = $val;
    }

    static function comp_func_cr($a, $b)
    {
        if ($a->priv_member === $b->priv_member) return 0;
        return ($a->priv_member > $b->priv_member)? 1:-1;
    }
}

$a = array("0.1" => new cr(9), "0.5" => new cr(12), 0 => new cr(23), 1=> new cr(4), 2 => new cr(-15),);
$b = array("0.2" => new cr(9), "0.5" => new cr(22), 0 => new cr(3), 1=> new cr(4), 2 => new cr(-15),);

$result = array_udiff_assoc($a, $b, array("cr", "comp_func_cr"));
print_r($result);
```
```php
Array
(
    [0.1] => cr Object
        (
            [priv_member:cr:private] => 9
        )

    [0.5] => cr Object
        (
            [priv_member:cr:private] => 12
        )

    [0] => cr Object
        (
            [priv_member:cr:private] => 23
        )
)
```


## array_udiff_uassoc 带索引检查计算数组的差集，用回调函数比较数据和索引

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-udiff-uassoc.php)。

```php
array array_udiff_uassoc ( array $array1 , array $array2 [, array $ ... ], callable $data_compare_func , callable $key_compare_func )
```

### 示例：两个数组的差集

```php
class cr {
    private $priv_member;
    function cr($val)
    {
        $this->priv_member = $val;
    }

    static function comp_func_cr($a, $b)
    {
        if ($a->priv_member === $b->priv_member) return 0;
        return ($a->priv_member > $b->priv_member)? 1:-1;
    }

    static function comp_func_key($a, $b)
    {
        if ($a === $b) return 0;
        return ($a > $b)? 1:-1;
    }
}
$a = array("0.1" => new cr(9), "0.5" => new cr(12), 0 => new cr(23), 1=> new cr(4), 2 => new cr(-15),);
$b = array("0.2" => new cr(9), "0.5" => new cr(22), 0 => new cr(3), 1=> new cr(4), 2 => new cr(-15),);

$result = array_udiff_uassoc($a, $b, array("cr", "comp_func_cr"), array("cr", "comp_func_key"));
print_r($result);
```
```php
Array
(
    [0.1] => cr Object
        (
            [priv_member:cr:private] => 9
        )

    [0.5] => cr Object
        (
            [priv_member:cr:private] => 12
        )

    [0] => cr Object
        (
            [priv_member:cr:private] => 23
        )

)
```


## array_udiff 用回调函数比较数据来计算数组的差集

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-udiff.php)。

```php
array array_udiff ( array $array1 , array $array2 [, array $ ... ], callable $data_compare_func )
```

### 示例：两个数组的差集

```php
class cr {
    private $priv_member;
    function cr($val)
    {   
        $this->priv_member = $val;
    }   

    static function comp_func_cr($a, $b) 
    {   
        if ($a->priv_member === $b->priv_member) return 0;
        return ($a->priv_member > $b->priv_member)? 1:-1;
    }   
}
$a = array("0.1" => new cr(9), "0.5" => new cr(12), 0 => new cr(23), 1=> new cr(4), 2 => new cr(-15),);
$b = array("0.2" => new cr(9), "0.5" => new cr(22), 0 => new cr(3), 1=> new cr(4), 2 => new cr(-15),);
$result = array_udiff($a, $b, array("cr", "comp_func_cr"));
print_r($result);
```
```php
Array
(
    [0.5] => cr Object
        (
            [priv_member:cr:private] => 12
        )

    [0] => cr Object
        (
            [priv_member:cr:private] => 23
        )
)
```


## array_uintersect_assoc 带索引检查计算数组的交集，用回调函数比较数据

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-uintersect-assoc.php)。

```php
array array_uintersect_assoc ( array $array1 , array $array2 [, array $ ... ], callable $data_compare_func )
```

### 示例：计算数组的交集

<font color="red">说明：函数strcasecmp是不区分大小写比较字符串。</font>

```php
$array1 = array("a" => "green", "b" => "brown", "c" => "blue", "red");
$array2 = array("a" => "GREEN", "B" => "brown", "yellow", "red");
print_r(array_uintersect_assoc($array1, $array2, "strcasecmp"));
```
```php
Array
(
    [a] => green
)
```


## array_uintersect_uassoc 带索引检查计算数组的交集，用回调函数比较数据和索引

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-uintersect-uassoc.php)。

```php
array array_uintersect_uassoc ( array $array1 , array $array2 [, array $ ... ], callable $data_compare_func , callable $key_compare_func )
```

### 示例：计算数组的交集

```php
$array1 = array("a" => "green", "b" => "brown", "c" => "blue", "red");
$array2 = array("a" => "GREEN", "B" => "brown", "yellow", "red");
print_r(array_uintersect_uassoc($array1, $array2, "strcasecmp", "strcasecmp"));
```
```php
Array
(
    [a] => green
    [b] => brown
)
```


## array_uintersect 计算数组的交集，用回调函数比较数据

函数原型及说明，请参考：[官方文档](http://php.net/manual/zh/function.array-uintersect.php)。

```php
array array_uintersect ( array $array1 , array $array2 [, array $ ... ], callable $data_compare_func )
```

### 示例：计算数组的交集

```php
$array1 = array("a" => "green", "b" => "brown", "c" => "blue", "red");
$array2 = array("a" => "GREEN", "B" => "brown", "yellow", "red");
print_r(array_uintersect($array1, $array2, "strcasecmp"));
```
```php
Array
(
    [a] => green
    [b] => brown
    [0] => red
)
```














