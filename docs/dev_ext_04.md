# 配置编译环境

## 安装软件

编译依赖：
- **autoconf** - Generate configuration scripts
- **automake** - Generate Makefile.in for configure from Makefile.am
- **libtool** - Provide generalized library-building support services
- **re2c** - convert regular expressions to C/C++
- **bison & bison-devel** - Generate a deterministic LR or generalized LR (GLR) parser employing
- libxml2 & libxml2-devel 

<font color="red">
说明：编译依赖的版本参考：[PHP手册](http://php.net/git.php)。需要注意的是，PHP5.3及其之前的版本对软件版本的要求比较苛刻，版本不一致会导致编译不成功！
</font>

安装命令如下：

```
$ sudo yum install autoconf automake libtool re2c bison bison-devel
```


## 下载源码

官方网站下载php源码，[链接](http://php.net/downloads.php)。

```
$ curl --location --output php-5.6.30.tar.gz http://cn2.php.net/get/php-5.6.30.tar.gz/from/this/mirror
```

<font color="red">
说明：不建议使用github版本，因为没有对应的configure文件，而使用buildconf工具的话会提示下面的错误。
</font>

```
$ wget https://github.com/php/php-src/archive/PHP-5.6.30.zip
```
```
$ ./buildconf 
You should not run buildconf in a release package.
use buildconf --force to override this check.
```


## 编译

```
$ ./configure --prefix=/home/work/git/php-src-code/php56/ --enable-debug --enable-maintainer-zts
$ make
$ make install
```

