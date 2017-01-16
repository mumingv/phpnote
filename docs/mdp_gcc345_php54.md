# mdp构建(基于开发机)

odp:

```
http://gitlab.baidu.com/odp/install-basic-env/tree/master
```

## 构建环境

```
$ gcc --version
gcc (GCC) 3.4.5 20051201 (Red Hat 3.4.5-2)
Copyright (C) 2004 Free Software Foundation, Inc.
This is free software; see the source for copying conditions.  There is NO
warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.
```


## 注意事项

1. openssl编译必须使用openssl-OpenSSL_1_0_0o，不能使用openssl-0.9.8g；
2. curl编译必须使用curl-7.46.0，不能使用curl-7.21.0；

```
export LD_LIBRARY_PATH=/home/users/yinjie05/bdp/dep/openssl/lib:/home/users/yinjie05/bdp/dep/zlib/lib
```


