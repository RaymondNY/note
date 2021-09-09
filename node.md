#### 安装方式-----命令安装

centos下,确认系统是否安装过epel-release包

`yum info epel-release`

如果有相关已安装的信息，则说明已经安装，如果提示没有安装则执行安装命令

`yum install epel-release`

安装一个旧版本的nodejs

`yum install nodejs`

安装n，n是nodejs管理工具

`npm install -g n`

安装指定版本

`n 14.17.3`

切换nodejs版本

`n`

而 n 默认安装路径是 /usr/local，若你的 node 不是在此路径下，n 切换版本就不能把bin、lib、include、share 复制该路径中，所以我们必须通过N_PREFIX变量来修改 n 的默认node安装路径。

```bash
which node
/usr/local/bin/node #我的路径地址
```

将下面两行代码插入到文件,/etc/profile 执行source使修改生效

```bash
export N_PREFIX=/usr/local #node实际安装位置
export PATH=$N_PREFIX/bin:$PATH
```

#### 查看npm默认参数

`npm config ls -l`

#### 修改npm和yarn镜像和命令

https://www.cnblogs.com/cjh1996/p/12688383.html#scroller-2   

#### 查看项目中是否安装某个组件

` npm ls packname`

`npm ls -g`  查看全局的组件

