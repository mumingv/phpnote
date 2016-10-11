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


## 理解标识符

标识符是一个名称，可以表示变量、函数或者类的名称。

使用PHP标识符的几个规则：
1. 和C语言一致：由字母、数字、下划线组成，且不能以数字开头；
2. 函数名称不区分大小写，但其他标识符名称(如：变量名称和类名称)都是区分大小写的；
3. 和C语言一致：变量名称可以和函数名称相同；


## 检查变量类型

重要说明：PHP不要求使用变量之前先声明变量，直接使用即可。


### PHP的数据类型

|数据类型              |分类            |说明                                                          |     
|----------------------|----------------|--------------------------------------------------------------| 
|整数 (Integer)        |标量数据类型    |                                                              | 
|浮点数 (Float/Double) |标量数据类型    |                                                              | 
|字符串 (String)       |标量数据类型    |                                                              | 
|布尔值 (Boolean)      |标量数据类型    |取值：true、false                                             |                  
|数组 (Array)          |                |只能保存相同类型的数据                                        |                       
|对象 (Object)         |                |保存类的实例                                                  |             
|空 (NULL)             |                |变量为空的3种场景：1、没有被赋值；2、被赋值为NULL；3、被重置；|
|资源 (resource)       |                |由特定的内置函数返回的类型，如：数据库连接等外部资源          |
        

### 类型强度

PHP是一种弱类型语言，或者叫做动态类型语言。变量的类型是由赋给变量的值所确定的。

### 类型转换

类型转换方法和C语言相同，在变量名称前的括号内加上目标类型即可。

当然，也可以使用PHP的内置函数来测试并设置类型。如何设置类型？

### 可变变量

PHP比较灵活，除了可以改变变量的值，还可以改变变量的类型和变量的名称。相比而言，C语言只能改变变量的值。

变量名称可以改变的原理是：可以使用一个变量来存储另一个变量的变量名称。

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
1、常量名称一般使用大写，当然小写的话语法上也没有什么问题；
2、使用常量时，不需要在常量名称前加$符号，也就是说$符号是专门表示变量的；
3、PHP默认内置了好多常量，可以使用phpinfo()函数查看；
4、常量只能保存整数、浮点数、字符串和布尔值这四种数据类型；


## 理解变量的作用域
作用域是指变量的可见范围，通常有：函数作用域、全局作用域。

关于作用域的几个规则：
1、函数内部的局部变量，作用域在函数内部，当函数结束时变量消失；
2、函数内部声明的全局变量，其名称要与全局变量名称一致；？？？
3、函数内部声明的静态变量，会改变生命期，作用域不变；
4、函数外部的全局变量，作用域在整个程序；
5、内置超级全局变量，作用域在整个程序；
6、常量，作用域在整个程序；

超级全局变量列表：

|变量        |说明                                  | 
|$GLOBALS    |全局变量数组(就这个变量不带下划线)    |
|$_SERVER    |服务器环境变量数组                    |
|$_ENV       |环境变量数组                          |
|$_GET       |GET方法传递给PHP的变量数组            |
|$_POST      |POST方法传递给PHP的变量数组           |
|$_COOKIE    |cookie变量数组                        |
|$_FILES     |文件上传相关的变量数组                |
|$_REQUEST   |所有用户输入的变量数组, 包括: $_GET、$_POST和$_COOKIE（注意：不包含$_FILES）|
|$_SESSION   |会话变量数组                          |


























