关闭防火墙
systemctl stop firewalld.service
设置防火墙禁止启动
systemctl disabled firewalld.service
查看防火墙状态
firewall-cmd --state

vi /etc/selinux/config

注释  SELINUX=enforcing
注释  SELINUXTYPE=targeted
增加  SELINUX=disabled

重启
shutdown –r now


为“红帽系”的操作系统提供额外的软件包
yum install epel-release –y

将系统包更新到最新版本
yum update

安装扩展
yum install -y gcc gcc-c++ pcre pcre-devel openssl openssl-devel zlib zlib-devel
5.9->6
curl http://download.bt.cn/install/update_to_6.sh|bash

宝塔
yum install -y wget && wget -O install.sh http://download.bt.cn/install/install.sh && sh install.sh

宝塔6
yum install -y wget && wget -O install.sh http://download.bt.cn/install/install_6.0.sh && sh install.sh

---------------------------------------------------------------------------------------------------
安装Shadowsocks

wget --no-check-certificate -O shadowsocks-all.sh https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks-all.sh
chmod +x shadowsocks-all.sh
./shadowsocks-all.sh 2>&1 | tee shadowsocks-all.log

在接下来弹出的版本选择界面中，输入序号4回车，表示选择安装Shadowsocks-libev

然后会分别提示自定义连接密码和服务器端口号，分别在下图红框处输入后回车。如果不知道设置哪个端口，那么直接回车即可。

之后会进入到加密方式选择界面，按需选择输入对应序号回车，这里我们选择序号16的chacha20

稍等片刻后，会询问是否开启简单混淆，鉴于这个功能目前并不完善，可能造成连接不上或连接速度下降，所以这里我们选择不安装，直接回车继续。

之后会提示按任意键开始安装，照做即可：

等几分钟后，就会提示安装成功，并会给出如下图红框处的连接参数，记住这些参数，客户端连接时要用。

打开Shadowsocks客户端，输入相应的连接参数，连接成功后就可以开始科学上网了。

启动SSR：
/etc/init.d/shadowsocks-libev  start
退出SSR：
/etc/init.d/shadowsocks-libev  stop
重启SSR：
/etc/init.d/shadowsocks-libev  restart
SSR状态：
/etc/init.d/shadowsocks-libev  status
卸载
./shadowsocks-all.sh uninstall

---------------------------------------------------------------------------------------------------

