## 教程
https://www.bilibili.com/video/av21303002?from=search&seid=16215451616347408931

## 文档：网盘->java->linux

## 镜像下载
https://www.cnblogs.com/zuxing/articles/8718591.html

## 虚拟机安装要点:
动态分配空间     设置root密码     2G内存


## 帮助
xxx -h

## 剪切
mv dubbo-admin.war apache-tomcat-7.0.91/webapps/

## 移动当前目录下的子文件下的子文件夹下的所有avi文件
mv */*/*.avi 123

## 文件夹复制
cp -r XXX XXX

## 将 /home/user1目录下的所有东西拷到/root/temp/下而不拷贝user1目录本身。
## 即格式为：cp -Rf 原路径/ 目的路径/
cp -rf /home/user1/* /root/temp/
-f:强制覆盖不提示，不加会提示

## 场景：123文件夹里的文件夹下的flv文件全部复制到某处
cp */*.flv ../124

## 文件夹/文件改名
mv default.conf access_mod.conf

##删除
rm -rf solr_home

## 新建一个文件 如 touch index.js 就会在当前目录下新建一个index.js文件。

## 创建目录:     mkdir
## 多级目录:     mkdir -p

## 解压
tar zxvf apache-maven-3.0.5-bin.tar.gz

## -c解压到指定目录，
tar -zxvf apache-maven-3.0.5-bin.tar.gz -C /opt/module/
tar -zxf jdk-7u79-linux-x64.gz -C /opt/module/

## zxvf的意思
https://zhidao.baidu.com/question/397860961.html

解压zip文件到当前目录
unzip filename.zip

unzip
unzip -o -d /home/sunny myfile.zip
把myfile.zip文件解压到 /home/sunny/
-o:不提示的情况下覆盖文件；
-d:-d /home/sunny 指明将文件解压缩到/home/sunny目录下；

端口占用
https://blog.csdn.net/Joker_Fei/article/details/73743937
lsof -i tcp:port 将port换成被占用的端口
kill PID


## SSH远程登陆
ssh root@10.8.30.214
## mac链接linux
ssh root@192.168.56.102
key保存在这个位置，可以删除     /Users/chen/.ssh/known_hosts

关于Virtualbox网络设置了解NAT模式后无法SSH连接的问题
https://blog.51cto.com/bingoo/1729017




## 防火墙
https://blog.csdn.net/ViJayThresh/article/details/81284007

状态： systemctl status firewalld.service
关闭： systemctl stop firewalld.service
开机禁用 ： systemctl disable firewalld.service
启动：systemctl start firewalld.service
随系统开启启动  ： systemctl enable firewalld.service

用户和用户组
https://www.cnblogs.com/liangyongfeng/p/5465590.html
[root@chen ~]# groupadd police
[root@chen ~]# groupadd bandit
[root@chen ~]# useradd -g police jack
[root@chen ~]# useradd -g police jerry
[root@chen ~]# useradd -g bandit xh
[root@chen ~]# useradd -g bandit xq

设密码
passwd jerry

jack创建一个文件，自己可以读写，本组人可以读，其它组没人任何权限
vi jack01.txt
ls -l
-rw-r--r--
chmod 640 jack01.txt
ls -l
-rw-r-----

jack 修改文件，其他组可以读，本组人可以读写
chmod o=r,g=rw jack01.txt
ls -l
-rw-rw-r--.

xh  投靠 警察
usermod -g police xh

使用 jack  给他的家目录 /home/jack 的所在组一个 rx 的权限
[jack@chen home]$ chmod g=rx jack/
ls -l
drwxr-x--- jack
xh 需要重新注销在到 jack 目录就可以操作 jack 的文件

Linux实操-组管理和权限管理
https://www.jianshu.com/p/1cf32462cf93
1 用 root 登录，建立用户 mycentos,自己设定密码

su root
useradd mycentos
pwd mycentos

2.用 mycentos 登录，在主目录下建立目录 test/t11/t1

su mycentos
cd ~
mkdir -p test/t11/t1

3.在 t1 中建立一个文本文件 aa,用 vi 编辑其内容为 ls –al

cd ~/test/t11/t1
touch aa
vim aa

4.改变 aa 的权限为可执行文件[可以将当前日期追加到一个文件],运行该文件./aa

chmod a+x aa
date >> aa
./aa

5.删除新建立的目录 test/t11/t1

rm -rf ~/test/t11/t1

6.删除用户 mycentos 及其主目录中的内容

userdel -r mycentos

7.将 linux 设置成进入到图形界面的

init 5

8.重新启动 linux 或关机

reboot

快捷键
https://www.cnblogs.com/chenhuan001/p/6306741.html

whereis nginx

//yum查看已安装的软件包
yum list installed
//卸载
yum remove xxx

//环境变量配置
vi /etc/profile

#JAVA_HOME
JAVA_HOME=/opt/module/jdk1.8.0_201
PATH=$JAVA_HOME/bin:$PATH
export JAVA_HOME PATH

#HADOOP_HOME
export HADOOP_HOME=/opt/module/hadoop-2.7.7
export PATH=$PATH:$HADOOP_HOME/bin
export PATH=$PATH:$HADOOP_HOME/sbin

//生效
source /etc/profile
或者
logout

//检查
echo $PATH
echo $JAVA_HOME/

touch wc.input
vi wc.input

//配置hadoop，使用符号链接，让三种配置形态共存
ln -s pesudo hadoop

//设置主机名字
hostnamectl set-hostname

//linux:Centos7mini版 enp0s3改eth0
https://blog.csdn.net/liangweihua123/article/details/87098483

//
# curl http://www.linux.com

//CentOS 7.x系统添加70-persistent-net.rules文件，来实现网卡名称自定义
https://blog.csdn.net/gpcsy/article/details/83010112



hadoop001: HWADDR=08:00:27:8d:53:bd IPADDR=192.168.1.101
08:00:27:8b:ec:4b 192.168.1.102
08:00:27:17:f8:b0

//开关机
https://www.cnblogs.com/3daytears/p/7749976.html

//传文件
[root@chen module]# scp -r /opt/module root@hadoop102:/opt/

//操作其他机器
scp -r root@hadoop102:/opt/software/ root@hadoop102:/opt

//root权限改成XXX
# chown XXX:XXX -R module/ software/

//免密登录
https://juejin.im/post/5c6b956f5188256e7e48a5bf

//在/usr/local/bin这个目录下存放的脚本，可以在系统任何地方直接执行，需要制定路径。

//文件或目录的权限就被修改为777(可读可写可执行)
chmod 777 XXX

//linux -- #!/bin/bash
#!/bin/bash是指此脚本使用/bin/bash来解释执行。
其中，#!是一个特殊的表示符，其后，跟着解释此脚本的shell路径。
bash只是shell的一种，还有很多其它shell

#!/bin/bash
#1 获取输入参数个数，如果没有参数，直接退出
pcount=$#
if((pcount==0)); then
echo no args;
exit;
fi

#2 获取文件名称
p1=$1
fname=`basename $p1`
echo fname=$fname

#3 获取上级目录到绝对路径
pdir=`cd -P $(dirname $p1); pwd`
echo pdir=$pdir

#4 获取当前用户名称
user=`whoami`

#5 循环
for((host=103; host<105; host++)); do
        #echo $pdir/$fname $user@hadoop$host:$pdir
        echo --------------- hadoop$host ----------------
        rsync -rvl $pdir/$fname $user@hadoop$host:$pdir
done

//拼接
$ cat blk_1073741836>>tmp.file
$ cat blk_1073741837>>tmp.file
$ tar -zxvf tmp.file



linux用户组

#groupadd group
# useradd chen
# passwd chen
# usermod -G group chen

# visudo
     es ALL=(ALL) ALL

切换
# su chen

软连接、硬连接
https://juejin.im/post/576e259e165abd00546eedb5
ln -s 源文件 目标文件

虚拟机磁盘扩容
重要     https://bugxia.com/581.html
https://juejin.im/post/5c809af96fb9a049b82b3cc5
https://blog.csdn.net/don_chiang709/article/details/82797256

linux目录
https://juejin.im/post/5a28f3516fb9a045055e0604

烂泥：【解决】Linux使用vim出现E325:ATTENTION错误
https://www.ilanni.com/?p=4892


Systemd 入门教程：命令篇
http://www.ruanyifeng.com/blog/2016/03/systemd-tutorial-commands.html

Linux 管理服务开机启动、查看开机启动服务（旧）
https://blog.csdn.net/aswedo/article/details/90345065

Centos7 服务 service 设置命令 systemctl 用法 （替代service 和 chkconfig）
https://www.cnblogs.com/devilmaycry812839668/p/8481760.html

列出所有已经安装的服务及状态（可为人所读,  内容简略、清晰）
systemctl list-unit-files
以树形列出正在运行的进程，它可以递归显示控制组内容
systemd-cgls
启动一个服务：systemctl start postfix.service
关闭一个服务：systemctl stop postfix.service
重启一个服务：systemctl restart postfix.service
显示一个服务的状态：systemctl status postfix.service
在开机时启用一个服务：systemctl enable postfix.service
在开机时禁用一个服务：systemctl disable postfix.service
查看服务是否开机启动：   systemctl is-enabled postfix.service
查看已启动的服务列表：   systemctl list-unit-files | grep enabled
查看启动失败的服务列表：   systemctl --failed

CentOS7进单用户模式更改密码
https://blog.51cto.com/14132521/2411578?source=dra

centos7 设置当前运行级别和默认运行级别
https://blog.csdn.net/capecape/article/details/78528761

mac pagedown按键
https://jingyan.baidu.com/article/cbcede077bbbb302f40b4db9.html



shell
pwd
/root/shell

vi myShell.sh

#!/bin/bash
echo "hello,world!"

//可执行权限
chmod 744 myShell.sh

./myShell.sh
或者
sh myShell.sh

linux6个终端可以实现不同用户登录
https://zhidao.baidu.com/question/311614778.html

centos7不再使用inittab方式来设置开机不自启图形界面
https://blog.csdn.net/know9163/article/details/81126220

SSH与Telnet区别
https://blog.csdn.net/krischao/article/details/44785957

查看自带jdk
rpm -qa | grep jdk

## 进程 
https://www.cnblogs.com/aipiaoborensheng/p/7676364.html
kill -9 PID 杀死进程

看有没有 sshd 服务
ps -aux | grep sshd
查看进程的父进程
ps -ef | more
sshd的父进程
ps -ef | grep sshd

查看进程和结束进程
ps aux|grep nginx
kill -s TERM 13050(第二列)

## CentOS7搭建FastDFS
https://www.cnblogs.com/tc520/p/6822412.html
https://blog.csdn.net/m0_37797991/article/details/73381739

192.168.56.102:8888     不要加上http://











## 仅主机什么意思
https://blog.csdn.net/zkuncn/article/details/78452098

## Linux export 命令
https://www.runoob.com/linux/linux-comm-export.html

## Linux 学习笔记
https://juejin.cn/post/6907164712790835208

## kill -9 和 kill -15 的区别
https://blog.csdn.net/chuixue24/article/details/107689316

## 别小看tail 命令，它难倒了技术总监
https://juejin.cn/post/6891437856196460552

## 还在百度Linux命令？推荐一套我用起来特顺手的命令！
https://juejin.cn/post/6877337031605911566