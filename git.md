#### git

运行 ssh-keygen -t rsa -C "youremail@example.com"  生成id_rsa.pub文件，复制内容到github就可以ssh传输了

#### 代理

`git config --global http.proxy 127.0.0.1:1080`为全局的 git 项目都设置代理

1080为翻墙软件端口

查看代理：

git config --global --get http.proxy
git config --global --get https.proxy


取消代理：

git config --global --unset http.proxy
git config --global --unset https.proxy



#### 跨平台拉取代码问题

https://blog.csdn.net/ljheee/article/details/82946368

