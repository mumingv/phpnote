# 安装PHP和扩展

## PHP

### YUM安装PHP56

前提：安装epel和remi源。

```
$ sudo yum --enablerepo=remi-safe install php56 php56-php-mbstring
```


### 编译安装PHP56

1.下载php5.6.29版本

```
$ wget http://cn2.php.net/distributions/php-5.6.29.tar.gz
$ tar xvzf php-5.6.29.tar.gz 
```

2.配置

```
$ mkdir -p output/php/etc/ext
$ cd php-5.6.29/
$ ./configure \
--prefix=/home/work/mdp/output/php \
--with-config-file-path=/home/work/mdp/output/php/etc \
--with-config-file-scan-dir=home/work/mdp/output/php/etc/ext \
--enable-opcache\
--enable-fpm \

```

各配置参数的含义如下：

|配置                               |类别&含义                  |bdp     |
|-----------------------------------|---------------------------|--------|
|--prefix=/home/work/mdp/output/php |指定安装目的目录           |y|
|--with-config-file-path=/home/work/mdp/output/php/etc|指定php.ini配置所存放的目录|y|
|--with-config-file-scan-dir=home/work/mdp/output/php/etc/ext|指定各扩展的配置所存放的目录|y|
|--enable-opcache                   |优化选项。使能opcache。**PHP5.4版本没有。**|n|
|--enable-fpm                       |FPM。使能fpm                    |y|
|--with-mysql=mysqlnd               |MySQL。使能mysql，指定myslq安装目录；一般不指定目录，而使用mysqlnd参数代替|y|
|--with-mysqli=mysqlnd              |MySQL。指定mysql配置文件；一般不指定文件，而使用mysqlnd参数代替|y|
|--with-pdo-mysql=mysqlnd           |MySQL。使能PDO，指定mysql安装目录；一般不指定目录，而使用mysqlnd参数代替|y|
|--enable-mbstring                  |国际化与字符编码。使能多字节字符串           |y|
|**--with-iconv**                   |国际化与字符编码。         |y, 未指定目录|
|**--with-mcrypt**                  |加密。是否要自定目录???    |y, /home/yeshiquan/bdp/dep/libmcrypt|
|**--with-mhash**                   |加密。是否要指定目录???    |y, --with-mhash=/home/yeshiquan/bdp/dep/mhash|
|**--with-openssl**                 |加密。是否要指定目录???    |y, /home/yeshiquan/bdp/dep/openssl|
|--enable-bcmath                    |数学。|y|
|**--with-gd**                      |图像图像。|y，未指定目录|
|--enable-gd-native-ttf             |图像图像。|y|
|--enable-exif                      |图形图像。|y|
|**--with-jpeg-dir**                |图形图像。|y, /home/yeshiquan/bdp/dep/libjpeg|
|**--with-png-dir**                 |图形图像。|y, /home/yeshiquan/bdp/dep/libpng|
|**--with-freetype-dir**            |图像图像。|y, /home/yeshiquan/bdp/dep/freetype|
|--enable-soap                      |Web服务。使能soap。**依赖libxml。**|y|
|--enable-ftp                       |FTP。|y|
|--enable-wddx                      |wddx。使能wddx。**依赖libxml。**|y|
|--enable-pcntl                     |进程、信号及内存。|y|
|--enable-shmop                     |进程、信号及内存。|y|
|--enable-sysvmsg                   |进程、信号及内存。|y|
|--enable-sysvsem                   |进程、信号及内存。|y|
|--enable-sysvshm                   |进程、信号及内存。|y|
|--enable-sockets                   |socket。使能socket。|y|
|**--with-curl**                    |curl。使能curl。|y, /home/yeshiquan/bdp/dep/curl|
|--with-pear                        |PEAR。指定PEAR的安装目录，默认目录为[PREFIX/lib/php]|y, 未指定目录|
|**--with-zlib**                    |压缩与归档。|y, /home/yeshiquan/bdp/dep/zlib|
|--enable-zip                       |压缩与归档。|y|
|**--with-bz2**                     |压缩与归档。|n|
|**--with-t1lib**                   |            |y，/home/yeshiquan/bdp/dep/t1lib|
|**--with-libxml-dir**              |            |y, /home/yeshiquan/bdp/dep/libxml2/bin/xml2-config|




3.编译




## gd


## exif


## redis

### 使用Yum安装

```
# yum install php-redis
```

说明：php-redis其实就是php-pecl-redis，如下所示。

```
# yum list installed | grep redis
php-pecl-redis.x86_64              2.2.8-1.el7                         @epel  
```

查看redis扩展是否安装成功。

```
$ php -m | grep redis
redis
```


### 访问Redis




## xml-rpc


