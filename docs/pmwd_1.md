# PHP快速入门 

## 开始之前：了解PHP

略。


## 创建一个示例应用：Bob的汽车零部件商店

### 创建订单表单

[代码示例](https://github.com/mumingv/php/blob/master/books/my_php_and_mysql_web_develop/source/chapter_01/orderform.html)

```markup
<form action="processorder.php" method="post">
    <table border="0">
        <tr bgcolor="#cccccc">
            <td width="150">Item</td>
            <td width="15">Quantity</td>
        </tr>
        <tr>
            <td>Tires</td>
            <td align="center"><input type="text" name="tireqty" size="3" maxlength="3" /></td>
        </tr>
        ...
        <tr>
            <td colspan="2" align="center"><input type="submit" value="Submit Order" /></td>
        </tr>
    </table>
</form>
```
`<form>`元素的`action`属性值就是用户点击“Submit”按钮时将要载入的URL；`method`属性值表示将表单中的数据发送到URL的方法，可以是`get`方法（表单数据附加在URL的末尾），也可以是`post`方法（以单独消息的形式发送）。


### 表单处理

action中指定的php脚本processorder.php，代码如下：
```markup
<html>
    <head>
        <title>Bob's Auto Parts - Order Results</title>
    </head>
    <body>
        <h1>Bob's Auto Parts</h1>
        <h2>Order Results</h2>
    </body>
</html>
```
可以看出，php文件的内容可以是纯html。


## 在HTML中嵌入PHP

### PHP标记

`<?php`和`?>`叫做PHP标记，PHP标记可以告诉Web服务器PHP代码的开始和结束，也就是说，其可以隔离PHP代码和HTML代码。

PHP标记一共有4种风格。

风格1：XML风格（默认）
```clike
<?php
    echo '<p>Order processed.</p>';
?>
```

风格2：PHP短标记
```clike
<?
    echo '<p>Order processed.</p>';
?>
```
说明：使用PHP短标记，需要打开php.ini的如下开关(此开关默认关闭)。
```clike
short_open_tag = On
```

风格3：script风格
```clike
<script language="php">
        echo '<p>Order processed.</p>';
</script>
```
说明：PHP默认支持script风格的标记，无需对应的开关。

风格4：ASP风格
```clike
<%
    echo '<p>Order processed.</p>';
%>
```
说明：使用ASP风格的PHP标记，需要打开php.ini的如下开关(此开关默认关闭)。
```clike
asp_tags = On
```


### PHP语句

略。


### 空格

间隔字符（如：空格、TAB、回车、换行），都被认为是空格字符。PHP会忽略这些空格字符，同样，浏览器也会忽略HTML的这些空格字符。


### 注释

PHP支持C、C++和Shell这三种语言风格的注释。分别是：`/**/` `//` `#`

当注释符遇到结束标记`?>`，有不同的表现，如下：

对于`//`和`#`，`?>`会结束注释，`?>`后面的内容会被当作HTML：
```clike
<?php
echo 'header';
// Comment ?> Here is HTML.
```
```clike
<?php
echo 'header';
# Comment ?> Here is HTML.
```

对于`/* */`，`?>`会被当作注释的一部分：
```clike
<?php
echo 'header';
/* Comment ?> Here is COMMENT.*/
```


## 添加动态内容

### 调用函数

略。


### 使用date()函数

略。


## 访问表单变量

### 简短、中等以及冗长风格的表单变量


|风格|示例|对应的php.ini配置|
|--|---|--|
|简短风格|$tireqty|register_globals = On <br /> 注：默认配置为Off，PHP 5.4.41版本已不支持设置为On，设置为On的话启动php-fpm时将会提示启动失败|
|中等风格|$_POST['tireqty']|默认支持，无需配置，推荐使用该方式|
|冗长风格|$HTTP_POST_VARS['tireqty']|register_long_arrays = On <br /> 注：默认配置为Off，PHP 5.4.41版本已不支持设置为On，设置为On的话启动php-fpm时将会提示启动失败|

注：简短风格和冗长风格的配置改为On后，对应的启动失败信息如下：

```clike
$ ./php-fpm start
Starting php_fpm <br />
<b>Fatal error</b>:  Directive 'register_globals' is no longer available in PHP in <b>Unknown</b> on line <b>0</b><br />
failed
```
```clike
$ ./php-fpm start
Starting php_fpm <br />
<b>Fatal error</b>:  Directive 'register_long_arrays' is no longer available in PHP in <b>Unknown</b> on line <b>0</b><br />
failed
```

`$_GET`、`$_POST`以及`$_REQUEST`这些数组被称为超级全局变量（superglobal）。


### 字符串的连接

使用点号`.`连接字符串。

插值（interpolation）是指用一个字符串来代替一个变量的操作。插值操作只是双引号引用的字符串特性之一。简而言之，双引号中的变量会被替换成变量的值，而单引号中的变量则不会。

### 变量和文本

变量是表示数据的符号，文本（字符串）是数据本身。

字符串的表示方法：单引号、双引号、heredoc（多行字符串）。其中单引号字符串不会插补（插值），而双引号字符串和heredoc字符串会插补（插值）。

heredoc是一种perl风格的字符串表示方法，通常用来输出html页面，其使用方式为：
```clike
<?php
$var1 = 'boy';
echo <<<EOT
<html>
    <head>
        <title>heredoc示例</title>
    </head>
    <body>
        <p>I'm a $var1!</p>
    </body>
</html>
EOT;
?>
```
其中，EOT标记字符串的开始和结束，当然也可以使用任何其他标记，如：STRING。

变量一般分为：局部变量、全局变量、超级全局变量。其中，超级全局变量是指系统内置的变量，如：`$_POST`。


## 理解标识符

标识符是一个名称，可以表示变量、函数或者类的名称。

使用PHP标识符的几个规则：
1. 和C语言一致：由字母、数字、下划线组成，且不能以数字开头；
2. 函数名称不区分大小写，但其他标识符名称(如：变量名称和类名称)都是区分大小写的；
3. 和C语言一致：变量名称可以和函数名称相同；


## 检查变量类型

重要说明：PHP不要求使用变量之前先声明变量，直接使用即可。


### PHP的数据类型

|数据类型              |类型名称|分类            |说明                                                          |     
|----------------------|--------|----------------|--------------------------------------------------------------| 
|整数 (Integer)        |int     |标量数据类型    |                                                              | 
|浮点数 (Float/Double) |double  |标量数据类型    |                                                              | 
|字符串 (String)       |string  |标量数据类型    |                                                              | 
|布尔值 (Boolean)      |bool    |标量数据类型    |取值：true、false                                             | 
|数组 (Array)          |array   |                |只能保存相同类型的数据                                        |
|对象 (Object)         |object  |                |保存类的实例                                                  |
|空 (NULL)             |null    |                |变量为空的3种场景：1、没有被赋值；2、被赋值为NULL；3、被重置；|
|资源 (resource)       |resource|                |由特定的内置函数返回的类型，如：数据库连接等外部资源          |
        

### 类型强度

PHP是一种弱类型语言，或者叫做动态类型语言。变量的类型是由赋给变量的值所确定的。

### 类型转换

类型转换方法和C语言相同，在变量名称前的括号内加上目标类型即可。

当然，也可以使用PHP的内置函数来测试并设置类型。如何设置类型？

### 可变变量

PHP比较灵活，除了可以改变变量的值，还可以改变变量的类型和变量的名称。相比而言，C语言只能改变变量的值。

变量名称可以改变的原理是：可以使用一个变量来存储另一个变量的名称。

示例：
```clike
$varname = 'tireqty';
$$varname = 5;
```
其等价于
```clike
$tireqty = 5;
```


## 声明和使用常量
PHP的常量等同于C语言中的宏，定义之后就无法更改。

PHP的常量定义使用define函数：
```clike
define('TIREPRICE', 100);
```

重要说明：
1. 常量名称一般使用大写，当然小写的话语法上也没有什么问题；
2. 使用常量时，不需要在常量名称前加`$`符号，也就是说`$`符号是专门用来修饰变量的；
3. PHP默认内置了好多常量，可以使用`phpinfo()`函数查看；
4. 常量只能保存整数、浮点数、字符串和布尔值这四种数据类型；


## 理解变量的作用域
作用域是指变量的可见范围，通常有：函数作用域、全局作用域。

关于作用域的几个规则：
1. 函数内部的局部变量，作用域在函数内部，当函数结束时变量消失；
2. 函数内部声明的全局变量，其名称要与全局变量名称一致；？？？
3. 函数内部声明的静态变量，会改变生命期，作用域不变；
4. 函数外部的全局变量，作用域在整个程序；
5. 内置超级全局变量，作用域在整个程序；
6. 常量，作用域在整个程序；

超级全局变量列表：

|变量        |说明                                  | 
|------------|--------------------------------------|
|$GLOBALS    |全局变量数组(该变量不带下划线)        |
|$_SERVER    |服务器环境变量数组                    |
|$_ENV       |环境变量数组                          |
|$_GET       |GET方法传递给PHP的变量数组            |
|$_POST      |POST方法传递给PHP的变量数组           |
|$_COOKIE    |cookie变量数组                        |
|$_FILES     |文件上传相关的变量数组                |
|$_REQUEST   |所有用户输入的变量数组, 包括: $_GET、$_POST和$_COOKIE（注意：不包含$_FILES）|
|$_SESSION   |会话变量数组                          |


## 使用操作符

PHP的操作符总计分为7大类：算术、字符串、赋值、比较、逻辑、位、其他。

### 算术操作符

下面的减号`-`也可以作为一元操作符，表示负值。

|操作符|名称|示例|
|------|----|----|
|+| 加 | $a + $b |
|-| 减 | $a - $b | 
|*| 乘 | $a * $b |
|/| 除 | $a / $b |
|%| 余 | $a % $b |


|操作符|名称|示例|
|------|----|----|
|-     |负号|$a = -1;|

重要说明：
1. 算术操作符通常用于整数或双精度类型(float或double)的数据；
2. 算术操作符如果应用于字符串，PHP会将这些字符串转换成一个数字。<br />具体转换方式如下：<br />
    a. 如果字符串中包含的全部是数字，则将其转换成整数；<br />
    b. 如果字符串中包含字母`e`或`E`，会将其当作数值的科学记数法，并将它转换成浮点数；<br />
    c. 如果字符串中包含除了字母`e`和`E`之外的字母，则会在字符串开始寻找数字并进行最长数字匹配，并将这些匹配的数字转换成整数；如果字符串的第一个字符不是数字，则将其转换为0；


### 字符串操作符

注：C语言没有字符串操作符。

|操作符|名称|示例|
|------|----|----|
|.| 连接操作符|$a = 'Hello';<br /> $b = 'world';<br /> $result = $a.$b<br />|


### 赋值操作符

#### 基本赋值操作符 `=`

赋值运算和其他运算（如：`$a + $b`）一样，也是有返回值的。如：
```clike
$b = 6 + ($a = 5)
```
表达式`($a = 5)`的返回值即为`$a`的值，所以`$b`的值就是11。


#### 复合赋值操作符 `+=` `-=` `*=` `/=` `%=` `.=`

每一个算术操作符和字符串连接操作符都有一个对应的复合赋值操作符。如下：

|操作符| 示例|
|----|----|
|+=|$a += $b|
|-=| $a -= $b|
|*=| $a *= $b|
|/=| $a /= $b|
|%=| $a %= $b|
|.=| $a .= $b|


#### 前置&后置递增递减操作符 `++` `--`

|操作符|示例|
|----|----|
|++| ++$a <br /> $a++|
|--| --$a <br /> $a--|


#### 引用操作符 `&`

| 操作符| 示例|
|----|----|----|
|&| $a = 5;<br /> $b = &$a;<br /> $a = 7;  // $b也变成了7|

重要说明：
1. 和C语言不同的是，`&$a`表示获得`$a`的引用，而不是获得`$a`的地址。简单讲，引用就是别名，不是指针；
2. 如果需要去除`$`a和`$b`的关系，可以使用重置函数`unset($a)`来处理；


### 比较操作符

比较操作符表达式根据比较结果返回true或false。

所有比较操作符：

|操作符| 名称| 示例|
|----|----|----|
|==| 等于| $a == $b|
|=== |恒等于| $a === $b|
|!=| 不等| $a != $b|
|!==| 不恒等| $a !== $b|
|<>| 不等| $a <> $b|
|<| 小于| $a < $b|
|>| 大于| $a > $b|
|<= |小于等于| $a <= $b|
|>=| 大于等于| $a >= $b|


### 逻辑操作符

参与逻辑运算的操作数都是逻辑值，即：下面示例中的`$a`和`$b`都是逻辑值。

|操作符| 示例|
|------|-----|
|&&| $a && $b|
|&#124;&#124;| $a &#124;&#124; $b|
|!| !$a|
|and| $a and $b|
|or| $a or $b|
|xor| $a xor $b|

重要说明：
1. 操作符`and`和`or`的优先级比`&&`和`||`低；
2. `xor`的运算规则是：`$a`和`$b`的逻辑值相同（同为`true`或`false`）则结果为`false`；不同则结果为`true`。


### 位操作符

位操作符列表：

|操作符| 示例|
|------|-----|
|&| $a & $b|
|&#124;| $a &#124; $b|
|~| ~$a|
|^| $a ^ $b|
|<<| $a << $b|
|>>| $a << $b|


### 其他操作符

#### 三元操作符 `?:`

三元操作符类似于条件语句if-else的表达式版本。如：
```clike
(($grade >= 50) ? 'Passed' : 'Failed')
```

#### 错误抑制操作符 `@`

错误抑制操作符`@`可以用于任何表达式之前，即可以位于任何有值的或者可以计算出值的表达式之前。如：
```clike
$a = @(57 / 0)
```
提示：如果启用了php.ini中的track_errors特性，错误信息将会被保存在全局变量`$php_errormsg`当中。

#### 执行操作符 ``

``为反向引号，其中的命令会被当作系统的命令来执行，命令的结果就是表达式的值。

|操作符| 示例|
|------|-----|
|``| $out = \`ls -la\`;<br />echo $out;|

注：执行系统命令除了这种方法之外，还有其他的方法，在后续章节描述。

#### 数组操作符

|操作符| 名称| 示例             |    说明|
|------|-----|------------------|--------|
|[] | 访问元素| | |
|=>| 访问元素| | |
|+| 联合| $arr1 + $arr2         | 数组并集|
|==| 等价| $arr1 == $arr2       | 两个数组含有相同的键值对，<br />返回true|
|===| 恒等| $arr1 === $arr2     | 两个数组含有相同的键值对和<br />相同的顺序，返回true|
|!=| 非等价| $arr1 != $arr2     | 两个数组不等价，返回true|
|<>|  非等价| $arr1 <> $arr2    | 两个数组不等价，返回true|
|!==| 非恒等| $arr1 !== $arr2   | 两个数组不恒等，返回true|

重要提示：不能将标量类型与数组类型进行比较。

### 类型操作符 `instanceof`

类型操作符在面向对象编程中使用，用来检查一个对象是否是特定类的实例。[示例代码](https://github.com/mumingv/php/blob/master/books/my_php_and_mysql_web_develop/chapter_01/instanceof.php)如下：

```clike
class sampleClass {};
$myObject = new sampleClass();
if ($myObject instanceof sampleClass) {
    echo "myObject is an instance of sampleClass";
}
```
```clike
$ php instanceof.php 
myObject is an instance of sampleClass
```



## 计算表单总金额

代码：[processorder.php](https://github.com/mumingv/php/blob/master/books/my_php_and_mysql_web_develop/chapter_01/processorder.php)

线上演示：[计算表单总金额](http://123.56.21.232:8094/chapter_01/orderform.html)


## 理解操作符的优先级和结合性

操作符具有两个重要的属性：优先级、结合性。

优先级：是指操作符的执行顺序。

结合性：是指在操作符的优先级相同的情况下的执行顺序，这种执行顺序分三种，分别是：左（从左到右）、右（从右到左）、不相关。

操作符的优先级（从高到低排列）和结合性列表如下：

|优先级 |结合性|操作符          |
|:-----:|:----:|:--------------:|
|1      |不相关|()              |
|2      |不相关|New             |
|3      |右    |[]              |
|4      |右    |!  ~  ++  -- (int)  (double)  (string)  (array)  (object)  @    |
|5      |左    |*  /  %         |
|6      |左    |+  -  .         |
|7      |左    |<<  >>          |
|8      |不相关|<  <=  >  >=    |
|9      |不相关|==  !=  ===  !==|
|10     |左    |&               |
|11     |左    |^               |
|12     |左    ||               |
|13     |左    |&&              |
|14     |左    |||              |
|15     |左    |?:              |
|16     |左    |=  +=  -=  *=  /=  %=  .=  &=  |=  ^=  ~=  <<= >>=  |
|17     |右    |print           |
|18     |左    |and             |
|19     |左    |xor             |
|20     |左    |or              |
|21     |左    |,               |

几点说明：
1. print和echo本质上也是操作符，而不是一个真正的函数，使用的时候将要显示的字符串放在它们后面即可；
2. 对于print，也可以用函数的形式进行调用，则它的返回值为1；
3. 对于print，其执行的速度比echo要慢；
4. 逻辑操作符有两种形式，分别是：`&& || !` （与、或、非）以及`and or xor`（与、或、异或）；
5. 与逻辑操作符对应的位操作符有：`& | ^`（与、或、异或）；


## 使用可变函数

### 获取和设置变量类型

|函数|功能              |
|----|------------------|
|gettype|获取变量类型   |
|settype|设置变量类型   |

说明：
1. 对应gettype函数，如果变量类型不是标准类型，则返回"unknown type"（未知类型）；
2. 对于mixed（混合）数据类型，很多函数可以使用其作为参数类型或者返回类型，PHP语言本身并无mixed类型的定义，其含义是函数可以支持接收多种（或者任意）的标准数据类型作为参数类型或返回值类型；

#### 类型测试函数

|函数           |功能              |
|---------------|------------------|
|is_int is_integer is_long |检查变量是否为整数      |
|is_double is_float is_real|检查变量是否为浮点数    |
|is_string      |检查变量是否为字符串|
|is_bool        |检查变量是否为布尔值|
|is_array       |检查变量是否为数组  |
|is_object      |检查变量是否为对象  |
|is_null        |检查变量是否为null  |
|is_resource    |检查变量是否为资源  |
|is_scalar      |检查变量是否为标量（整数、浮点数、字符串、布尔值）|
|is_numeric     |检查变量是否为数字或者数字字符串|
|is_callable    |检查变量是否为函数名称|


### 获取和设置变量状态

|函数           |功能              |
|---------------|------------------|
|is_set         |检查变量是否存在  |
|unset          |销毁变量          |
|empty          |检查变量是否存在并且为空|


### 变量的数据类型转换（重解释）

|函数           |功能              |
|---------------|------------------|
|intval         |将变量转为整数    |
|Intval         |将变量转换为不同进制的整数|
|floatval       |将变量转为浮点数  |
|strval         |将变量转为字符串  |


## 分支语句（根据条件进行决策）

### if
```
if (condition) {
    expression;
}
```

### if...else
```
if (condition) {
    expression;
} else {
    expression;
}
```

### if...else if...else
```
if (condition) {
    expression;
} else if (condition) {
    expression;
} else {
    expression;
}
```

### if...elseif...else
```
if (condition) {
    expression;
} elseif (condition) {
    expression;
} else {
    expression;
}
```

### switch
```
switch (condition) {
    case xxx:
        expression;
        break;
    case xxx:
        expression;
        break;
    case xxx:
        expression;
        break;
    default:
        expression;
        break;
}
```
说明：switch语句的条件condition一般为变量，且只能支持简单的数据类型，即：整数、浮点数、字符串。


## 循环语句（通过迭代实现重复动作）

### for
```
for (expression, condition, expression) {
    expression;
}
```

### while
```
while (condition) {
    expression;
}
```

### do...while
```
do {
    expression;
} while (condition);
```

### foreach（仅针对数组）
```
foreach ($array as $key => $value) {
    expression;
}
```


## 从控制结构或脚本中跳出

几个用于跳出的关键字：
1. break：跳出循环（和switch分支）；
2. continue: 继续下一次循环；
3. exit: 退出程序；

|控制结构|break |continue   |exit   |
|:------:|:----:|:---------:|:-----:|
|if      |N     |N          |YES    |
|switch  |YES   |N          |YES    |
|for     |YES   |YES        |YES    |
|while   |YES   |YES        |YES    |
|foreach |?     |?          |?      |


## 使用可替换的控制结构语法

类似shell脚本的写法，使用：endif, endswitch, endwhile, endfor, endforeach。

示例：
```
if (condition):
    expression;
endif;
```

## 使用declare

declare用来设置代码块的执行指令，也就是设置后续代码如何运行的规则。

语法：
```
declare (directive) {
    // block
}
```

目前declare只实现了一个执行命令：ticks；其可以通过ticks=n来设置，它允许在代码块内部每隔n行代码运行特定的函数。常用来做代码调试和性能测试。

