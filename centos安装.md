#### 桥接模式：

在bridged模式下，VMWare虚拟出来的操作系统就像是局域网中的一台独立的主机，它可以访问网内任何一台机器。主机网卡和虚拟网卡的IP地址处于同一个网段，子网掩码、网关、DNS等参数都相同。https://blog.csdn.net/u013626215/article/details/88645003

#### NAT模式：

使用NAT模式可以实现在虚拟系统里访问互联网。就是让虚拟系统借助NAT(网络地址转换)功能，通过宿主机器所在的网络来访问公网。宿主机所在局域网其他主机访问不到虚拟机。

#### 更换国内yum：

`mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.backup`

`curl -o /etc/yum.repos.d/CentOS-Base.repo https://mirrors.aliyun.com/repo/Centos-7.repo`

` yum makecache `

`sed -i -e '/mirrors.cloud.aliyuncs.com/d' -e '/mirrors.aliyuncs.com/d' /etc/yum.repos.d/CentOS-Base.repo`

#### Docker安装

##### 安装 yum-utils 包(它提供 yum-config-manager 实用工具)并设置稳定存储库。

`yum remove dockerdocker-client docker-client-latest docker-common docker-latest docker-latest-logrotate docker-logrotate docker-engine`

官网推荐stable镜像库

`yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo`

##### 安装 Docker 引擎

`yum install docker-ce docker-ce-cli containerd.io`

`systemctl start docker`

##### 配置加速镜像

`vi /etc/docker/daemon.json
{
  "registry-mirrors": [
"https://no1pfk8z.mirror.aliyuncs.com",
"https://kfwkfulq.mirror.aliyuncs.com", 
"https://2lqq34jg.mirror.aliyuncs.com", 
"https://pee6w651.mirror.aliyuncs.com",
"https://hub-mirror.c.163.com/",
"https://reg-mirror.qiniu.com"
  ]
}`

`systemctl daemon-reload`

`systemctl restart docker`

##### 卸载

`yum remove docker-ce docker-ce-cli containerd.io`          `rm -rf /var/lib/docker`          `rm -rf /var/lib/containerd`

#### 常用命令

##### scp

`scp xxx.file  username@host:/xx/xx`

##### curl



##### wc -l

`wc -l  xxx.file `  统计行数

#####  pgrep

`pgrep -f abc`   匹配出含abc的进程 并输出进程的pid

 `pgrep -f redis |wc -l`   查看redis启动成功

#### 自启动服务

先创建xxx.service文件，简单的内容如下：

`[Unit]`
`Description=mmmm`

`[Service]`
`Type = simple`
`ExecStart = /home/zqx/project/dockertest/all.sh`

`[Install]`
`WantedBy = multi-user.target`

xxx.service 复制到/etc/systemd/system目录下或者/usr/lib/systemd/目录下 。然后执行`systemctl enable xxx`就可以

常用的命令：(nginx就代表文件名xxx)

systemctl enable nginx # 开机启动 

systemctl is-enabled nginx # 查看服务是否开机启动 

systemctl disable nginx  # 关闭开机启动 

systemctl start nginx  # 启动服务 

systemctl stop nginx # 停止服务 

systemctl restart nginx # 重启服务 

systemctl status nginx # 查看服务状态(详细信息) 

systemctl is-active nginx # 查看服务是否活动 

systemctl kill nginx # 结束服务进程(服务无法停止时) 

systemctl daemon-reload # 添加或修改配置文件后，使改动生效 

systemctl --failed # 查看启动失败的服务

https://page.syao.fun/2020/09/11/linux_systemd.html    配置service文件字段解释

#### 关闭防火墙

`systemctl stop firewalld.service`

`systemctl disable firewalld.service`



#### ubuntu

##### 免密

修改/etc/sudoers 加上下面一行

`%sudo   ALL=(ALL:ALL) NOPASSWD:ALL`
