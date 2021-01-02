案例1
DROP TABLE IF EXISTS `dept`;

CREATE TABLE `dept` (
  `deptno` BIGINT(20) NOT NULL DEFAULT 0,
  `dname` VARCHAR(60) CHARACTER SET utf8 COLLATE utf8_general_ci NULL DEFAULT NULL,
  `db_source` VARCHAR(20) CHARACTER SET utf8 COLLATE utf8_general_ci NULL DEFAULT NULL
) ENGINE = INNODB CHARACTER SET = utf8 COLLATE = utf8_general_ci ROW_FORMAT = COMPACT;

INSERT INTO `dept` VALUES (1, '开发部', 'clouddb01');
INSERT INTO `dept` VALUES (2, '人事部', 'clouddb01');
INSERT INTO `dept` VALUES (3, '财务部', 'clouddb01');
INSERT INTO `dept` VALUES (4, '市场部', 'clouddb01');
INSERT INTO `dept` VALUES (5, '运维部', 'clouddb01');

案例2

DROP DATABASE IF EXISTS cloudDB01;
CREATE DATABASE cloudDB01 CHARACTER SET UTF8;
USE cloudDB01;

CREATE TABLE dept
(
  deptno BIGINT NOT NULL PRIMARY KEY AUTO_INCREMENT,
  dname VARCHAR(60),
  db_source VARCHAR(60)
);

INSERT INTO dept(dname,db_source) VALUES('开发部',DATABASE());
INSERT INTO dept(dname,db_source) VALUES('人事部',DATABASE());
INSERT INTO dept(dname,db_source) VALUES('财务部',DATABASE());
INSERT INTO dept(dname,db_source) VALUES('市场部',DATABASE());
INSERT INTO dept(dname,db_source) VALUES('运维部',DATABASE());

SELECT * FROM dept;

案例3：建表与测试

CREATE TABLE IF NOT EXISTS `t_act`(
  `actno` VARCHAR(100),
  `balance` INT,
   PRIMARY KEY ( `actno` )
)ENGINE=InnoDB DEFAULT CHARSET=utf8;
+

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.SQLException;

/**
 * 测试连接
 * @author cracker
 *
 */
public class JdbcMysql {
    public static void main(String[] args) {
        Connection conn = null;
        String actno = "001";
        double balance = 5000;
        PreparedStatement ps = null;
        int count = 0;
        //加载驱动类
        try {
            Class.forName("com.mysql.jdbc.Driver");
            //Class.forName("com.mysql.cj.jdbc.Driver");
            conn=DriverManager.getConnection("jdbc:mysql://localhost:3306/cracker","root","root");
            System.out.println("连接成功");
            String sql = "insert into t_act(actno,balance) values(?,?)";
            //4.进行SQL语句预编译
            ps = conn.prepareStatement(sql);
            //5.进行赋值
            ps.setString(1, "002");
            ps.setDouble(2, 5000);
            //6.执行SQL语句
            count = ps.executeUpdate();
            System.out.println(count);
        } catch (ClassNotFoundException e) {
            // TODO Auto-generated catch block
            e.printStackTrace();
        } catch (SQLException e) {
            // TODO Auto-generated catch block
            e.printStackTrace();
        }
    }
}

案例4

use test

CREATE TABLE IF NOT EXISTS goods(
id INT NOT NULL AUTO_INCREMENT,
  name VARCHAR(100),
price double,
  store INT,
version INT,
PRIMARY KEY (id)
)ENGINE=InnoDB DEFAULT CHARSET=utf8;

INSERT INTO goods VALUES (1, '华为手机', 1999, -17, 0);

案例4

CREATE DATABASE `jdbc_template` ;

USE `jdbc_template`;

DROP TABLE IF EXISTS `employee`;

CREATE TABLE `employee` (
  `emp_id` int(11) NOT NULL AUTO_INCREMENT,
  `emp_name` char(100) DEFAULT NULL,
  `salary` double DEFAULT NULL,
  PRIMARY KEY (`emp_id`)
) ENGINE=InnoDB AUTO_INCREMENT=7 DEFAULT CHARSET=gb2312;

insert into `employee`(`emp_id`,`emp_name`,`salary`) values (1,'Susan',5000.23),(2,'Julian',4234.77),(3,'Papu',9034.51),(4,'Babala',8054.33),(5,'Kasier',6039.11),(6,'Owen',7714.11);

//将emp_id = 5的记录的salary字段更新为1300.00
update employee SET salary = ? where emp_id = ?

//插入
insert into employee(emp_name,salary) value (?,?)

//查询emp_id = 5的数据库记录，封装为一个java对象返回
select emp_id empID,emp_name empName,salary from employee where emp_id = ?

//查询salary>4000的数据库记录，封装为List集合返回
select emp_id empID,emp_name empName,salary from employee where salary>?

//查询最大的salary
sql = "select Max(salary) from employee;";

//使用带有具名参数的SQL语句插入一条员工记录，并以Map形式传入参数值
insert into employee(emp_name,salary) values (:empName,:salary)

案例5

CREATE DATABASE `project_crowd` CHARACTER SET utf8;
use project_crowd;
drop table if exists t_admin;

create table t_admin
(
id int not null auto_increment, # 主键
login_acct varchar(255) not null, # 登录账号
user_pswd char(32) not null, # 登录密码
user_name varchar(255) not null, # 昵称
email varchar(255) not null, # 邮件地址
create_time char(19), # 创建时间
primary key (id)
);

案例6

CREATE TABLE `project_crowd`.`t_role` (
     `id` INT NOT NULL,
     `name` CHAR ( 100 ),
     PRIMARY KEY ( `id` )
);

ALTER TABLE `project_crowd`.`t_role` CHANGE `id` `id` INT ( 11 ) NOT NULL AUTO_INCREMENT;

insert into `t_role` (`id`, `name`) values('1','PM - 项目经理');
insert into `t_role` (`id`, `name`) values('2','SE - 软件工程师');
insert into `t_role` (`id`, `name`) values('3','PG - 程序员');
insert into `t_role` (`id`, `name`) values('4','TL - 组长');
insert into `t_role` (`id`, `name`) values('5','GL - 组长');
insert into `t_role` (`id`, `name`) values('6','QA - 品质保证');
insert into `t_role` (`id`, `name`) values('7','QC - 品质控制');
insert into `t_role` (`id`, `name`) values('8','SA - 软件架构师');
insert into `t_role` (`id`, `name`) values('9','CMO / CMS - 配置管理员');

案例7

CREATE TABLE t_menu (
id INT ( 11 ) NOT NULL auto_increment,
pid INT ( 11 ),
NAME VARCHAR ( 200 ),
url VARCHAR ( 200 ),
icon VARCHAR ( 200 ),
PRIMARY KEY ( id )
);

案例8

CREATE TABLE `project_crowd`.`inner_role_auth` (
     `id` INT NOT NULL AUTO_INCREMENT,
     `role_id` INT,
     `auth_id` INT,
     PRIMARY KEY (`id`)
);

案例9

CREATE TABLE t_member (
id INT ( 11 ) NOT NULL auto_increment,
loginacct VARCHAR ( 255 ) NOT NULL,
userpswd CHAR ( 200 ) NOT NULL,
username VARCHAR ( 255 ),
email VARCHAR ( 255 ),
authstatus INT ( 4 ) COMMENT '实名认证状态0 - 未实名认证， 1 - 实名认证申
请中， 2 - 已实名认证',
usertype INT ( 4 ) COMMENT ' 0 - 个人， 1 - 企业',
realname VARCHAR ( 255 ),
cardnum VARCHAR ( 255 ),
accttype INT ( 4 ) COMMENT '0 - 企业， 1 - 个体， 2 - 个人， 3 - 政府',
PRIMARY KEY ( id )
);


===============  ===========

## 删除
delete from t_employee where id>1;

## 外键表查询
select k.*, l.* from t_key k, t_lock l where k.id=1 and k.lockid = l.id