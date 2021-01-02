## 端口范围
https://bbs.csdn.net/topics/350247272
一般的应用程序使用1024到4999来进行通讯

## 端口占用
终端输入：lsof -i tcp:port 将port换成被占用的端口(如：8086、9998)
kill PID
https://blog.csdn.net/Joker_Fei/article/details/73743937

## gem操作
首先我们需要来安装这个游戏，githug 是用 Ruby 编写的，可通过如下命令安装：
gem install githug

如果遇到权限问题，请加上sudo：
sudo gem install githug

## 环境变量
https://www.jianshu.com/p/f1adedbda0d3
https://www.cnblogs.com/davidgu/p/6186282.html

编辑、永久生效
vi ~/.bash_profile
source ~/.bash_profile

临时生效
export PATH=$PATH:/opt/gradle/gradle-6.6.1/bin




Mac终端 vi/vim 的简单使用
https://www.cnblogs.com/fanxiaocong/p/7070130.html

//mac安装telnet
brew install telnet

mac机环境

java -version
java version "1.8.0_111"

mvn -v
Apache Maven 3.5.2

IDEA 2018.1.6

springboot 1.5.9

mac 查看mysql版本

https://blog.csdn.net/wangjun5159/article/details/51118850

mac下navicat的破解
https://www.jianshu.com/p/f3ef78deadaa

安装包在网盘

mac下mysql乱码解决

查看命令
show variables like'character_set_%';
show variables like'collation_%';

临时更改命令
set character_set_database=utf8;

长久解决命令
https://www.cnblogs.com/liangjiahao713/p/8097942.html

mac 启动Tomcat
./startup.sh
https://blog.csdn.net/u010277446/article/details/54931490

## homebrew

软件安装目录在哪儿
$ brew info gradle
https://blog.csdn.net/resilient/article/details/80780315
https://blog.csdn.net/q258523454/article/details/107174003/

安装、卸载、常用命令
https://juejin.im/post/6844904190175608846

检查是否成功
brew doctor

关闭gradle自动更新
$ vim ~/.bash_profile
$ export HOMEBREW_NO_AUTO_UPDATE=true
-

安装指定版本软件
https://blog.csdn.net/matt8/article/details/105033965/

## 系统缓存
/Users/chen/Library/Caches 可以删除