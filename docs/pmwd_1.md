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



























