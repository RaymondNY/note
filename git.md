#### git

运行 ssh-keygen -t rsa -C "youremail@example.com"  生成id_rsa.pub文件，复制内容到github就可以ssh传输了

#### 代理

`git config --global http.proxy 127.0.0.1:1080`为全局的 git 项目都设置代理