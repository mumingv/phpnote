# 面向对象的PHP

## 理解面向对象的概念

面向对象（OO）的开发方法试图在系统中引入对象的分类、关系和属性，从而有助于程序开发和代码重用。


### 类和对象

对象可以是物理对象，也可以是概念性对象。

面向对象软件由一系列具有属性和操作的自包含对象组成。

对象的属性是与对象相关的特性或变量；对象的操作是对象可以执行的、用来改变其自身或对外部产生影响的方法、行为或函数。

封装也叫数据隐藏。从本质上来说，访问一个对象中的数据只能通过对象的操作来实现，对象的操作也就是对象的接口。

在软件中，我们用不同的变量作为对象的句柄（唯一标识符）。

对象可以按照类来进行分类。类是表示彼此之间可能互不相同，但是必须具有一些共同点的对象集合。


### 多态性

面向对象的语言必须支持多态性，多态性是指不同的类对同一操作可以有不同的行为。

多态性与其说是对象的特性，不如说是行为的特性。在PHP中，只有类的成员函数可以是多态的。


### 继承

继承允许我们在类之间创建层次关系。子类将从它的父类继承属性和操作。

子类也叫做派生类；父类也叫做超类。


## 在PHP中创建类、属性和操作

### 类的结构 `class`

使用关键字`class`声明一个类。

```clike
class classname {
    public $attribute1;
    public $attribute2;
    function operation1() {
    }
    function operation2($param1, $param2) {
    }
}
```


### 构造函数 `__construct()`

构造函数可以手工进行调用，但一般都不会这么做。构造函数一般用于在创建对象时自动调用。

构造函数一般用于执行一些初始化任务，如：设置属性的初始值或者创建该对象需要的其他对象。

```clike
class classname {
    function __construct($param) {
        echo 'Constructor called with parameter: '.$param.PHP_EOL;
    }
}

$obj = new classname('mumingv');
```

```clike
Constructor called with parameter: mumingv
```

说明：PHP支持函数重载，即可以提供多个具有相同名称以及不同参数数量或参数类型的函数。

但是，构造函数不能重载。

```clike
class classname {
    function __construct($param) {
        echo 'Constructor called with parameter: '.$param.PHP_EOL;
    }
    function __construct($param1, $param2) {
        echo 'Constructor called with parameter: '.$param1.' & '.$param2.PHP_EOL;
    }
}

$obj = new classname('mumingv');
```

提示错误

```clike
Fatal error: Cannot redeclare classname::__construct() in /home/work/git/php/books/my_php_and_mysql_web_develop/chapter_06/example.php on line 16
```


### 析构函数 `__destruct()`

析构函数用于在销毁一个类对象之前执行一些操作或完成一些功能，析构通常在所有对该类对象的引用都被重置或超出作用域时自动发生。

重要说明：析构函数不能带有任何参数。

```clike
class classname {
    function __construct($param) {
        echo 'Constructor called with parameter: '.$param.PHP_EOL;
    }
    function __destruct() {
        echo 'Destructor called with no parameter'.PHP_EOL;
    }
}

$obj = new classname('mumingv');
```

```clike
Constructor called with parameter: mumingv
Destructor called with no parameter
```


## 类的实例化 `new`

使用类创建一个对象，就叫做创建一个实例或者叫做实例化一个对象。类的实例化需要提供给构造函数所需要的参数。

```clike
class classname {
    function __construct($param) {
        echo 'Constructor called with parameter: '.$param.PHP_EOL;
    }
    function __destruct() {
        echo 'Destructor called with no parameter'.PHP_EOL;
    }
}

$obj = new classname('mumingv');
```

```clike
Constructor called with parameter: mumingv
Destructor called with no parameter
```


## 使用类的属性 `$this->attribute` `__get()` `__set()`

当需要在类中通过一个操作设置或访问属性时，可以使用`$this->attribute`进行引用。需要注意的是，`attribute`前面不需要加`$`。

```clike
class classname {
    public $attribute;
    function operation($param) {
        $this->attribute = $param;
        echo $this->attribute;
    }
}

$obj = new classname();
$obj->operation('great');
```
```clike
great
```

从类的外部直接访问类的属性是糟糕的使用方式。需要将对属性的访问（包括读取或设置）封装起来。

PHP中可以使用`__get()`和`__set()`函数来实现对所有属性的读取或设置操作。这样做的好处是能够使得属性的访问入口单一化，便于维护和管理。

```clike
class classname {
    private $attribute;
    function __get($attrName) {
        echo "__get($attrName) is called.".PHP_EOL;
        return $this->$attrName;
    }
    function __set($attrName, $attrValue) {
        echo "__set($attrName, $attrValue) is called.".PHP_EOL;
        $this->$attrName = $attrValue;
    }
}

$obj = new classname();
$obj->attribute = 'mumingv';  // call __set('attribute', 'mumingv') function
echo $obj->attribute;  // call _get('attribute') function

```

```clike
__set(attribute, mumingv) is called.
__get(attribute) is called.
mumingv
```

重要说明：
1. 只有当`$attribute`的访问修饰符为`private`或`protected`，才会默认调用`__get()`和`__set()`函数。
2. 如果`$attribute`的访问修饰符为`public`，则在类的外部就直接能够访问了，此时就不会再调用`__get()`和`__set()`函数。


## 使用`public`、`protecetd`和`private`关键字控制访问

三个访问修饰符，用来修饰属性或者方法（操作）：
1. `public`：可以在类的内部和外部进行访问，可以被继承；
2. `protected`: 只可以在类的内部进行访问、不能在类的外部进行访问，可以被继承；
3. `private`: 只可以在类的内部进行访问、不能在类的外部进行访问，不可以被继承；

如果属性或方法不加访问修饰符的话，默认使用`public`。






