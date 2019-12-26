git基本操作

1）下载并安装git

2）配置git：用户名和邮箱
git config --global user.name "用户名"
git config --global user.email "邮箱地址"

3）搭建git服务器（远程仓库）
为了在本地和远程仓库之间进行 免密钥登录，可以配置ssh。
配置ssh:先在本地配置，再发送给远程
先查看是否有.ssh文件，输入命令：cd ~/.ssh
出现no such file or directory表示没有.ssh文件
ssh-keygen -t rsa -C "邮箱地址"  特别注意大小写和空格，用大写的C ！！！三次回车后，就生成了本地ssh了
发送给远程：
打开：https://github.com/settings/keys
测试连通性，看本地仓库和远程仓库是否连接成功，输入命令：ssh -T git@github.com

4）在本地新建git项目。
git init

5）在远程建立git项目：
https://github.com/new

6）本地项目-远程项目关联
输入命令：git remote add origin git@XXX

7）第一次发布项目 （本地-远程）
//文件-暂存区,add后面是“空格 点”就表示当前目录的所有文件（注意：add和点中间有一个空格！！！大坑） 
git add .    
//暂存区-本地分支（默认master）
git commit -m “注释内容” 
git push -u origin master

8）第一次下载项目（远程-本地）：
git clone 


9）提交项目（本地-远程），三步走
在当前工作目录，右键【git bash here】
git add .
git commit -m "提交内容"
git push origin master  （注意：这是非第一次提交，所以没有“-u”）

10）更新项目（远程-本地）
git pull

