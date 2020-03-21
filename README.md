Trojan分解自动安装脚本

1、一般情况下，VPS 的 SELinux 处于关闭状态，但是不排除所有，大家检查一下！

/usr/sbin/sestatus -v      ##如果返回参数为 enabled 即为开启，disabled 为关闭
若是开启状态，如何关闭 SELinux 服务？

修改 /etc/selinux/config 文件

将 SELINUX=enforcing 改为 SELINUX=disabled

重启 VPS 以后 SELinux 即为关闭状态
==========================================================

2、安装基础依赖环境
yum -y install wget    ##ContOS Yum 安装 wget
apt-get install wget   ##Debian Ubuntu 安装 wget


本代码分解三部分：


wget -N --no-check-certificate "https://raw.githubusercontent.com/V2RaySSR/Trojansh/master/trojan1.sh" && chmod +x trojan1.sh && ./trojan1.sh

wget -N --no-check-certificate "https://raw.githubusercontent.com/V2RaySSR/Trojansh/master/trojan2.sh" && chmod +x trojan2.sh && ./trojan2.sh

wget -N --no-check-certificate "https://raw.githubusercontent.com/V2RaySSR/Trojansh/master/trojan3.sh" && chmod +x trojan3.sh && ./trojan3.sh

安装成功后访问 https://你的域名 看是否有SSL证书锁和网页
客户端如不能连接，重启服务：systemctl restart trojan
查看运行状态等：systemctl start/stop/status trojan


==========================================================

若需修改密码和配置：
访问VPS: /usr/local/etc/trojan/config.json



安装信息存放在：/usr/local/etc/trojan/配置.txt

你的Trojan配置信息为：

域名：你的域名
密码：
端口：443

==========================================================

