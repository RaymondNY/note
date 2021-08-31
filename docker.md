#### 资料

https://www.cnblogs.com/kevingrace/category/839227.html?page=3

#### redis安装

##### docker command

`docker run --name myredis -p 6379:6379 -d redis --requirepass "mypassword"`

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

