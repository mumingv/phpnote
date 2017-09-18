# 环境FAQ

## 【Mac】如何安装多个版本的PHP？

### 参考资料

https://www.zybuluo.com/phper/note/137276


## 如何使用Yum安装PHP5.6？

前提：安装epel和remi源。

```
$ sudo yum --enablerepo=remi-safe install php56 php56-php-mbstring
```


## 如何编译安装PHP5.6？

1.下载php5.6.29版本

```
$ wget http://cn2.php.net/distributions/php-5.6.29.tar.gz
$ tar xvzf php-5.6.29.tar.gz 
```

2.配置

安装依赖：

```
$ sudo yum install libxml2-devel libjpeg-devel libpng-devel 
```

说明：
- libxml2-devel：很多功能都依赖该软件
- libjpeg-devel：GD模块依赖；实际包名称为：libjpeg-turbo-devel
- libpng-devel：GD模块依赖；


执行comfigure：

```
$ mkdir -p output/php/etc/ext
$ cd php-5.6.29/
$ ./configure \
--prefix=/home/work/mdp/output/php \
--with-config-file-path=/home/work/mdp/output/php/etc \
--with-config-file-scan-dir=home/work/mdp/output/php/etc/ext \
--enable-opcache \
--enable-fpm \
--with-mysql=mysqlnd \
--with-mysqli=mysqlnd \
--with-pdo-mysql=mysqlnd \
--enable-mbstring \
--with-iconv \
--enable-bcmath \
--with-gd \
--enable-gd-native-ttf \
--enable-exif \
--enable-soap \
--enable-ftp \
--enable-wddx \
--enable-pcntl \
--enable-shmop \
--enable-sysvmsg \
--enable-sysvsem \
--enable-sysvshm \
--enable-sockets \
--with-pear \
--enable-zip
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

```
$ make -j8
$ make install
```

4.配置文件

php配置文件：

```
$ cp php.ini-development /home/work/mdp/output/php/etc/php.ini
```

php-fpm配置文件：

```
$ cp /home/work/mdp/output/php/etc/php-fpm.conf.default /home/work/mdp/output/php/etc/php-fpm.conf
$ sudo cp sapi/fpm/init.d.php-fpm /etc/init.d/php-fpm
$ sudo chmod +x /etc/init.d/php-fpm
$ service php-fpm start
```

加入PATH：

```
$ vim ~/.bash_profile
PATH=$PATH:$HOME/.local/bin:$HOME/bin:/usr/libexec/gcc/x86_64-redhat-linux/4.8.2:/home/work/mdp/output/php/bin
```


## 编译安装PHP5.6后，如何将Nginx的流量转发到该PHP的php-fpm？

1.修改php-fpm配置的listen参数，并重启php-fpm。

```
$ vim /home/work/mdp/output/php/etc/php-fpm.conf。
164 ;listen = 127.0.0.1:9000
165 listen = /home/work/mdp/output/var/php-cgi.sock
$ service php-fpm restart
```

2.修改nginx配置的$php_upstream参数，并重启ngxing。

```
$ vim /home/work/bdp/webserver/conf/vhost/php.conf
#set $php_upstream   'unix:/home/work/bdp/var/php-cgi.sock';
set $php_upstream   'unix:/home/work/mdp/output/var/php-cgi.sock';
$ /home/work/bdp/webserver/loadnginx.sh restart
```


## 如何使用Nginx搭建文件服务器？

示例：

```
location / {
    root /home/users/yinjie05/baidu/share;
    autoindex on;  # 开启目录浏览，必选
    autoindex_exact_size off;  # 显示文件大小(on显示字节数，off显示k、m、g等单位)，可选
    autoindex_localtime on;  # 显示时间(on表示服务器时间)，可选
    charset utf-8;  # 服务器字符编码，浏览器根据该配置进行解码
}
```


