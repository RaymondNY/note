#### 资料

https://www.cnblogs.com/kevingrace/category/839227.html?page=3

#### docker命令

https://www.kancloud.cn/woshigrey/docker/935883

#### redis安装

##### docker command

`docker run --name redis --restart always -p 6379:6379 -d redis --requirepass "Xad@8031009"`

##### docker-compose 

services:
  redis:
    container_name: 'myredis'
    image: 'redis'
    restart: always
    ports:

      - 6379:6379
        command: redis-server --requirepass mypassword

##### 参考

https://jueee.github.io/2021/03/2021-03-14-Docker%E5%90%AF%E5%8A%A8Redis%E5%B9%B6%E6%B7%BB%E5%8A%A0%E5%AF%86%E7%A0%81/



#### mysql安装

`docker run --name mysql --restart=always -p 3306:3306  -e MYSQL_ROOT_PASSWORD=123456 -d mysql:5.7.35`

更多的参数见下面官方docker库介绍

https://github.com/docker-library/docs/tree/master/mysql



#### docker和宿主机时间统一

https://blog.csdn.net/xinluke/article/details/52050371

