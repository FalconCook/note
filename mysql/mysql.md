mac启动：系统偏好
版本：mysql -V

linux下的安装 & yum源的用法
https://www.cnblogs.com/black-fact/p/10840332.html

登录
mysql -u root -p
mysql -uroot -proot
默认
root
Root123@
测试
Navicat Premium

查看服务状态
https://blog.csdn.net/chenhanhao0000/article/details/89737329
systemctl status mysqld.service

yum安装的mysql 目录结构
https://www.cnblogs.com/izqq/p/11332125.html

===== 常用操作 ========

查看当前所有的数据库
show databases;

select database();
建库
create database test
选择
use test
建表
create table stuinfo(
    -> id int,
    -> name varchar(20));
查看当前库的所有表
show tables;
查看表结构
desc 表名;
插入
insert into stuinfo(id,name) values(2,'rose');
查询
select * from stuinfo;
修改
update stuinfo set name='lilei' where id=2;
删除
delete from stuinfo where id=2;
版本
select version();

=========

## 对应的实体类，字段要和数据库一样，可以起别名，注意构造函数有参无参都要写
private Integer empId;
private String empName;
private double salary;

varchar在java里对应String
decimal对应BigDecimal
smallint对应Integer

## Mac OS系统下MySQL5.7.20安装详解
http://www.linuxidc.com/Linux/2017-11/148281.htm

========== mac下启动tomcat7.0 =========

## mac下启动tomcat7.0
https://blog.csdn.net/caoxiaohong1005/article/details/53463443

cd /Library/Tomcat/bin /* 此处Library前面必须要加斜杠"/" */
sudo chmod 755 /Library/Tomcat/bin/*.sh
sudo sh start.sh

cd /Library/Tomcat/bin /* 此处Library前面必须要加斜杠"/" */
sudo chmod 755 /Library/Tomcat/bin/*.sh
sudo sh shutdown.sh

lsof -i tcp:8080 /*是否启动*/

==============












## 官网
https://dev.mysql.com/doc/

## mysql 5.7.22 自带的四个数据库
https://blog.csdn.net/cainiao000001/article/details/80502549

## Mysql 字符集及排序规则
https://www.cnblogs.com/shiqi17/p/9441257.html

## linux虚拟机连接主机MySQL
https://blog.csdn.net/mingxin95/article/details/78832129

## Mysql索引
https://juejin.im/post/6844903827708051469


## MySQL 主从数据库
https://juejin.cn/post/6844904065294401544

## 数据库，主键为何不宜太长长长长长长长长？
https://juejin.cn/post/6904470966663905288

## 维护不了就跑路，然后我被坑了！记一次采坑优化记录
https://juejin.cn/post/6906282808369643528

## 天猫面试官：如何设计一个数据库？
https://juejin.cn/post/6905914933020459016

## 主键，不少人以为自己懂了，却不透彻...
https://juejin.cn/post/6906689950427660296
练习一：建表时，可不可以不声明主键？ 可以
练习二：建表时，可不可以不声明主键非空？  可以，插入语句都不能为空
练习三：建表时，可不可以选择多个字段做主键？ 可以
练习四：可不可以主动插入自增主键？ 可以
练习五：建表时，可不可以使用联合自增主键？ 不可以

## 为什么阿里巴巴不建议MySQL使用Text类型？
https://juejin.cn/post/6898479206087262222

### 打工四年总结的数据库知识点
https://juejin.cn/post/6883270227078070286

## Mysql中，21个写SQL的好习惯，你值得拥有呀
https://juejin.cn/post/6889550040558206983

## 查询SQL的执行流程
https://juejin.cn/post/6897388295060684807

## MySQL 三万字精华总结 + 面试100 问，和面试官扯皮绰绰有余（收藏系列）
https://juejin.cn/post/6850037271233331208

================ Navicat ===========

## 我用起来顺手的数据库设计工具
https://mp.weixin.qq.com/s/SJI0x7qQw5JkCvDWou7XaQ

## 干掉Navicat！MySQL官方客户端到底行不行
https://juejin.cn/post/6901085744618536973

## 卸载 Navicat！事实已证明，正版客户端，它更牛逼……
https://juejin.cn/post/6901664308774731784

## sequel pro 教程
https://jingyan.baidu.com/article/8275fc867f432c46a03cf639.html

========= 扩容 ===========

## 炸！亿级数据DB秒级平滑扩容！！！
https://juejin.cn/post/6908979849671966727

## 互联网公司为啥都不用MySQL分区表？
https://juejin.cn/post/6908592735691735054

## 炸！业界难题，跨库分页的几种常见方案
https://juejin.cn/post/6908220694929080333

=========== 索引 =========

## explain | 索引优化的这把绝世好剑
https://juejin.cn/post/6905232255937937415

## 如何避免回表查询？什么是索引覆盖？
https://juejin.cn/post/6904089685233156103

===== binlog ====

## mysql binlog 基础 & 实战
https://juejin.cn/post/6892397821152985102

============= 表锁 ==========

## MySQL表锁，总以为自己懂了
## 频繁插入(insert)的业务，用什么存储引擎更合适？ | 数据库系列
https://juejin.cn/post/6905951225804488712

======== 删除 =======

## 批量删除数据，常见的大坑！！！
https://juejin.cn/post/6897791590660898830

====== 主键 ====

## 为什么MySQL不建议用UUID做MySQL的主键？
https://juejin.cn/post/6903711768502075406

## 数据库允许空值 (null)，往往是悲剧的开始（1 分钟系列）
https://juejin.cn/post/6901488402353520647

======= 其他数据库 =====

## 我们为什么放弃 MongoDB 和 MySQL，选择 TiDB
https://juejin.cn/post/6877727080675868679

======= 引擎 ======

## 你居然还不知道Mysql存储引擎InnoDB分为内存架构、磁盘架构？
https://www.seoxiehui.cn/article-152978-1.html

====== 事务 =====

## 你一定要知道的MySQL之MVCC多版本并发控制
https://juejin.cn/post/6906375939962355725