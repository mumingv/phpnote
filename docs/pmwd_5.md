# 代码重用与函数编写

## 代码重用的好处

在理想的情况下，一个新的项目是将已有的可重新利用的组件进行组合，从而降低开发难度。


### 成本

略。


### 可靠性

略。


### 一致性

略。


## 使用`require()`和`include()`函数

`require()`和`include()`的功能是一样的，就是将一个文件载入到PHP脚本中。

两者唯一的区别是在函数调用失败后的行为，`require()`会报致命的错误，而`include()`只会报一个警告。

`require()`和`include()`都有对应的变体函数，分别是`require_once()`和`include_once()`，它们的作用是为了防止在一个PHP脚本中重复引入一个文件。该功能类似于C语言头文件开头的`#ifndef`语句。
```clike
#ifndef _XXX_H
#define _XXX_H
...
#endif
```

从速度上比较，`require()`和`include()`的速度要比`require_once()`和`include_once()`快一些。


### 文件扩展名和`require()`函数

被引入的文件，并不要求其扩展名一定要为`.php`的，其他任意的扩展名都可以。

`require()`的处理逻辑是：先将文件包含进来，然后再将其当作PHP代码执行。


### 使用`require()`制作Web站点的模板

对于在文档树中的扩展名不是`.php`的文件，如果该文件中包含了PHP代码，恶意用户是能够查看到其源码的。为了避免这种情况，可以将其放在文档树之外。

如果希望将一个文件当作纯文本或者HTML，不希望执行其中可能存在的PHP代码，则可以使用`readfile()`函数进行读取，该函数会回显文件内容并且不会对其进行解析。但是，如果该文件内的文本是用户提供的话，就可能存在安全问题。


### 使用配置项`auto_prepend_file`和`auto_append_file`

`auto_prepend_file`和`auto_append_file`在配置文件`php.ini`中，用来设置页眉和页脚，可以保证它们在每个页面的前后被载入。

说明：对于Apache服务器，可以对单个目录进行不同配置选项的修改。对于自动添加页眉和页脚的功能，需要在该目录中创建一个名为`.htaccess`的文件。使用`.htaccess`方法的一个缺点是目录中每个被读取和被解析的文件每次都要进行处理，而不是只在启动时处理一次，所以性能会有所降低。


## 在PHP中使用函数

函数是一个给出了调用接口的自包含模块。

### 调用函数

略。


### 调用未定义的函数

调用未定义的函数，PHP会报一个错误信息：`Call to undefined function`。

可能原因：
1. 函数名称拼写错误；
2. 对于系统函数，可能是函数不存在于当前PHP版本当中；
3. 对于扩展函数，可能是扩展没有被载入PHP。

扩展知识：`gd`是图像生成和处理库，可以参考：[资料](http://php.net/manual/zh/book.image.php)。


### 理解字母大小写和函数名称

说明：函数名称不区分大小写，但变量名称区分大小写。


## 理解为什么要定义自己的函数

略。


## 了解基本的函数结构

说明：通过PHP标记，可以在函数内部嵌入HTML。

### 可变函数

可变函数是指函数的名称存储在变量当中，使用下面的方式进行调用。
```clike
$function_name();
```


## 使用参数

获取参数信息的相关函数，可以参考：[Function handling 函数](http://php.net/manual/zh/book.funchand.php)。


## 理解作用域

作用域的详细规则不再描述，下面是一些注意事项：
1. 使用`require()`和`include()`不会影响作用域。如果用在函数内部，就是函数作用域；如果用在函数外部，就是全局作用域。
2. 关键字`global`用于将函数内部变量的作用域转为全局作用域。
3. 如果使用`unset($var)`删除了一个变量，则随变量附带的作用域自动消失。


## 参数的引用传递和值传递

参数的引用传递和值传递，在函数定义形式上有所区分，在调用形式上则是完全一致的。

值传递
```clike
function increment($value, $amount = 1) {
    ...
} 
```

引用传递
```clike
function increment(&$value, $amount = 1) {
    ...
} 
```

两种参数传递方式都可以通过下面的形式进行调用
```clike
increment($number, 1);
```


## 使用`return`关键字

略。


## 实现递归

说明：对于递归函数的调用，如果代码有问题一直不停地调用自身的话，可能会导致两个结果：
1. 内存耗尽；
2. 达到系统规定的最大调用次数而停止。


### 名称空间

名称空间是一个抽象的容器。它可以包含自定义函数、类以及常量。

使用名称空间的优点如下：
1. 名称空间中的所有函数、类以及常量都将自动冠以名称空间的前缀。
2. 对于非全路径的函数、类以及常量，会先查看名称空间中是否存在，如果不存在才会查看全局空间。


## 进一步学习

学习资料：
1. 关于语言的一些通用特性，可以参考书籍：[Deitel's C++ How To Program](https://item.jd.com/11957867.html)。
