# 第一个扩展

## 编写扩展


## 编译扩展

使用phpize工具生成configure工具。

```
$ cd /home/work/git/php-src-code/php-5.6.30-dev/ext/mumingv
$ /home/work/git/php-src-code/php56/bin/phpize 
Configuring for:
PHP Api Version:         20131106
Zend Module Api No:      20131226
Zend Extension Api No:   220131226
```

执行configure、make生成扩展。

```
$ ./configure --with-php-config=/home/work/git/php-src-code/php56/bin/php-config
$ make
$ make test
```


## 安装扩展

```
$ make install
Installing shared extensions:     /home/work/git/php-src-code/php56/lib/php/extensions/debug-zts-20131226/
```

```
$ cp /home/work/git/php-src-code/php-5.6.30-dev/ext/mumingv/modules/mumingv.so .
```



