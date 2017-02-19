# 第一个扩展

## 编写扩展

```
$ cd ~/git/php-src-code/php-5.6.30-dev/ext/
$ mkdir mumingv
$ cd mumingv
$ ls
config.m4  mumingv.c  mumingv.h
```

<font color="red">
说明：mummigv为目录名称，同时也是扩展名称。写一个扩展主要有两部分：配置(config.m4)和扩展代码(mumingv.c/mumingv.h)。
</font>


## 编译扩展

使用phpize工具生成configure工具。

```
$ cd ~/git/php-src-code/php-5.6.30-dev/ext/mumingv
$ phpize 
Configuring for:
PHP Api Version:         20131106
Zend Module Api No:      20131226
Zend Extension Api No:   220131226
```

执行configure、make生成扩展。

```
$ ./configure
$ make
```


## 安装扩展

### 执行`php -i`查询扩展文件应该放置的目录。

```
$ php -i | grep extension_dir
extension_dir => /home/work/git/php-src-code/php56/lib/php/extensions/debug-zts-20131226 => /home/work/git/php-src-code/php56/lib/php/extensions/debug-zts-20131226
```

<font color="red">
说明：如果需要修改扩展文件(如：mumingv.so)放置的目录，需要修改php.ini文件，示例如下。
</font>

```
$ cd /git/php-src-code/php56/etc/
$ vim php.ini
 730 ; Directory in which the loadable extensions (modules) reside.
 731 ; http://php.net/extension-dir
 732 extension_dir = "/home/work/git/php-src-code/php56/ext"
```


### 安装扩展

方法一：执行make install安装，该方法会将扩展拷贝到扩展所在的默认目录。

```
$ cd ~/git/php-src-code/php-5.6.30-dev/ext/mumingv
$ make install
Installing shared extensions:     /home/work/git/php-src-code/php56/lib/php/extensions/debug-zts-20131226/
```

方法二：手工拷贝

```
$ cd ~/git/php-src-code/php-5.6.30-dev/ext/mumingv
$ cp ./modules/mumingv.so /home/work/git/php-src-code/php56/lib/php/extensions/debug-zts-20131226/
```


### 修改配置

增加第733行的配置。

```
$ cd /git/php-src-code/php56/etc/
$ vim php.ini
730 ; Directory in which the loadable extensions (modules) reside.
731 ; http://php.net/extension-dir
732 extension_dir = "/home/work/git/php-src-code/php56/ext"
733 extension=mumingv.so
```


## 查看配置是否生效

```
$ php -r "var_dump(get_loaded_extensions());" | grep mumingv
  string(7) "mumingv"
```

