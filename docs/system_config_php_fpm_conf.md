# 系统配置 php-fpm.conf

## pm.status_path

该配置用于查看PHP进程的状态。

PHP配置

```
pm.status_path = /status
```

NGINX配置

```
# 系统监测
location ~ ^/(status|ping)$ {
    fastcgi_pass unix:/{{ENV_PATH}}/var/php-cgi.sock;
    include fastcgi_params;
    fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
}
```

查看整体状态

```
http://www.foo.bar/status
http://www.foo.bar/status?json
http://www.foo.bar/status?html
http://www.foo.bar/status?xml
```

查看各进程状态

```
http://www.foo.bar/status?full
http://www.foo.bar/status?json&full
http://www.foo.bar/status?html&full
http://www.foo.bar/status?xml&full
```

### 示例：查询整体状态（json格式）

```
http://<IP>:<PORT>/status?json
```
```
{
pool: "www",
process manager: "static",
start time: 1533108711,
start since: 2094,
accepted conn: 81,
listen queue: 0,
max listen queue: 0,
listen queue len: 0,
idle processes: 7,
active processes: 1,
total processes: 8,
max active processes: 6,
max children reached: 0,
slow requests: 0
}
```

### 示例：查询所有进程状态（json格式）

```
http://<IP>:<PORT>/status?json&full
```
```
{
  "pool": "www",
  "process manager": "static",
  "start time": 1533108711,
  "start since": 2254,
  "accepted conn": 84,
  "listen queue": 0,
  "max listen queue": 0,
  "listen queue len": 0,
  "idle processes": 7,
  "active processes": 1,
  "total processes": 8,
  "max active processes": 6,
  "max children reached": 0,
  "slow requests": 0,
  "processes": [
    {
      "pid": 3107,
      "state": "Idle",
      "start time": 1533108711,
      "start since": 2254,
      "requests": 11,
      "request duration": 826,
      "request method": "GET",
      "request uri": "/status?json",
      "content length": 0,
      "user": "-",
      "script": "-",
      "last request cpu": 0,
      "last request memory": 262144
    },
    ...
    {
      "pid": 3112,
      "state": "Running",
      "start time": 1533108711,
      "start since": 2254,
      "requests": 11,
      "request duration": 2221,
      "request method": "GET",
      "request uri": "/status?json&full",
      "content length": 0,
      "user": "-",
      "script": "-",
      "last request cpu": 0,
      "last request memory": 0
    }
  ]
}
```


## ping.path

该配置用于查看PHP进程的心跳(PING/PONG测试)。

PHP配置

```
ping.path = /ping
```

NGINX配置

```
# 系统监测
location ~ ^/(status|ping)$ {
    fastcgi_pass unix:/{{ENV_PATH}}/var/php-cgi.sock;
    include fastcgi_params;
    fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
}
```

### 示例

```
http://<IP>:<PORT>/ping
```
```
pong
```


