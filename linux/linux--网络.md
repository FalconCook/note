## 网卡
上网配置:
vi     /etc/sysconfig/network-scripts/ifcfg-eth0
ONBOOT=yes激活网卡
service networkrestart

//重启网络
systemctl restart network
或者 service network restart

centos网卡配置文件地址:/etc/sysconfig/network-scripts

静态ip的配置
HWADDR=08:00:27:8d:53:bd
TYPE=Ethernet
PROXY_METHOD=none
BROWSER_ONLY=no
BOOTPROTO=static    //动态：dhcp
DEFROUTE=yes
IPV4_FAILURE_FATAL=no
IPV6INIT=yes
IPV6_AUTOCONF=yes
IPV6_DEFROUTE=yes
IPV6_FAILURE_FATAL=no
IPV6_ADDR_GEN_MODE=stable-privacy
NAME=eth0
UUID=23fcb311-5792-4382-afc8-c6d6a8f35376
DEVICE=eth0
ONBOOT=yes

IPADDR=192.168.101.133
GATEWAY=0.0.0.0
NETMASK=255.255.255.0
DNS1=114.114.114

注意：route查看路由得到0.0.0.0网关
 修改后，一定要 重启服务

            - systemctl start network.service
            - reboot 重启系统

初版
TYPE=Ethernet
PROXY_METHOD=none
BROWSER_ONLY=no
BOOTPROTO=dhcp
DEFROUTE=yes
IPV4_FAILURE_FATAL=no
IPV6INIT=yes
IPV6_AUTOCONF=yes
IPV6_DEFROUTE=yes
IPV6_FAILURE_FATAL=no
IPV6_ADDR_GEN_MODE=stable-privacy
NAME=enp0s3
UUID=124b7438-310a-40fa-8782-c30422a37feb
DEVICE=enp0s3
ONBOOT=yes

//设置静态IP,参考SGG_Linux.docx
//配置文件
//网关要和主机路由一致，dns要和网关一致
TYPE=Ethernet
PROXY_METHOD=none
BROWSER_ONLY=no
BOOTPROTO=static
DEFROUTE=yes
IPV4_FAILURE_FATAL=no
IPV6INIT=yes
IPV6_AUTOCONF=yes
IPV6_DEFROUTE=yes
IPV6_FAILURE_FATAL=no
IPV6_ADDR_GEN_MODE=stable-privacy
NAME=enp0s3
UUID=124b7438-310a-40fa-8782-c30422a37feb
DEVICE=enp0s3
ONBOOT=yes

IPADDR=192.168.101.20
GATEWAY=192.168.101.1
DNS1=192.168.101.1

网卡好文：https://www.cnblogs.com/boltkiller/p/12696501.html

mac地址 
ip add 
link/ether 08:00:27:9e:50:d2

//网络配置
vi /etc/udev/rules.d/70-persistent-net.rules
vi /etc/sysconfig/network-scripts/ifcfg-eth0
vi /etc/sysconfig/network
vi /etc/hosts

//IP查看
ip add

虚拟机centos无法上网
http://baijiahao.baidu.com/s?id=1597809303775176940&wfr=spider&for=pc
