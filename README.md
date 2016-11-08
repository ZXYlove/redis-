# redis-
缓存技术

REmote DIctionary Server(Redis) 是一个由Salvatore Sanfilippo写的key-value存储系统。

Redis是一个开源的使用ANSI C语言编写、遵守BSD协议、支持网络、可基于内存亦可持久化的日志型、Key-Value数据库，并提供多种语言的API。

它通常被称为数据结构服务器，因为值（value）可以是 字符串(String), 哈希(Map), 列表(list), 集合(sets) 和 有序集合(sorted sets)等类型。

 Redis优点

    异常快速 : Redis是非常快的，每秒可以执行大约110000设置操作，81000个/每秒的读取操作。

    支持丰富的数据类型 : Redis支持最大多数开发人员已经知道如列表，集合，可排序集合，哈希等数据类型。
    这使得在应用中很容易解决的各种问题，因为我们知道哪些问题处理使用哪种数据类型更好解决。

    操作都是原子的 : 所有 Redis 的操作都是原子，从而确保当两个客户同时访问 Redis 服务器得到的是更新后的值（最新值）。
    MultiUtility工具：Redis是一个多功能实用工具，可以在很多如：缓存，消息传递队列中使用（Redis原生支持发布/订阅），在应用程序中，如：Web应用程序会话，网站页面点击数等任何短暂的数据
    
    安装、配置
安装

下载路径： http://redis.io/download
安装命令
$ wget http://download.redis.io/releases/redis-3.0.2.tar.gz
$ tar xzf redis-3.0.2.tar.gz
$ cd redis-3.0.2
$ make

启动
$ src/redis-server

客户端
$ src/redis-cli
redis> set foo bar
OK
redis> get foo
"bar"

配置

redis的配置示例文件在%REDIS_HOME%下的redis.conf
里面包含很多默认配置
使用配置可以这样：$ redis-server /etc/redis/6379.conf
daemonize 如果需要在后台运行，把该项改为yes

pidfile 配置多个pid的地址，默认在/var/run/redis.pid

bind 绑定ip，设置后只接受自该ip的请求

port 监听端口，默认为6379

timeout 设置客户端连接时的超时时间，单位为秒

loglevel 分为4级，debug、verbose、notice、warning

logfile 配置log文件地址

databases 设置数据库的个数，默认使用的数据库为0

save   设置redis进行数据库镜像的频率，保存快照的频率。  
    第一个参数表示多长时间，第二个表示执行多少次写操作。
    在一定时间内执行一定数量的写操作时，自动保存快照。可设置多个条件。

rdbcompression 在进行镜像备份时，是否进行压缩

Dbfilename 镜像备份文件的文件名

Dir 数据库镜像备份的文件放置路径

Slaveof 设置数据库为其他数据库的从数据库 

Masterauth 主数据库连接需要的密码验证

Requirepass 设置登录时需要使用的密码

Maxclients 限制同时连接的客户数量

Maxmemory 设置redis能够使用的最大内存

Appendonly 开启append only模式

appendfsync 设置对appendonly.aof文件同步的频率

vm-enabled 是否虚拟内存的支持

vm-swap-file 设置虚拟内存的交换文件路径

vm-max-memory 设置redis使用的最大物理内存大小

vm-page-size 设置虚拟内存的页大小

vm-pages 设置交换文件的总page数量

vm-max-threads 设置VMIO同时使用的线程数量

glueoutputbuf 把小的输出缓存存放在一起

hash-max-zipmap-entries 设置hash的临界值

activerehashing 重新hash
