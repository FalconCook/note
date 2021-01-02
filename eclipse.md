eclipse

maven报错
https://blog.csdn.net/qq_34301871/article/details/65631100

错误：Archive for required library:
https://blog.csdn.net/tengdazhang770960436/article/details/53105509

maven打war包报错
右键javaeetools->generate……

Java compiler level does not match the version of the instal
https://blog.csdn.net/chszs/article/details/8125828

eclipse，代码中有错误，项目中却不显示红叉
https://www.cnblogs.com/simith/p/7400227.html

maven项目找不到包，maven引的配置文件对不对

lombok
https://www.cnblogs.com/caozx/p/9510354.html

错误：
java.lang.ClassNotFoundException: com/cracker/service//DS_Store
解决：
ls -al
rm -rf .DS_Store

错误：eclispe 父工程 maven model 出不来
解决：重启eclipse

字体调整
Basic->Text Font

elipse快捷键

查看接口实现类 command+T
xml格式化 Ctrl+Shift+F

maven工程经验

多点工程右击->maven->update project

lombok
https://www.cnblogs.com/caozx/p/9510354.html

mac快捷键
https://www.jianshu.com/p/07a535947a8a

Eclipse自动下载源码--Java Source Attacher插件
https://syc001.iteye.com/blog/2363168

eclipse xml对齐
https://blog.csdn.net/javaious/article/details/21083399

解决java compiler level does not match the version of the installed java project facet
https://blog.csdn.net/chszs/article/details/8125828

奇技淫巧：在spring官网上下载历史版本的spring插件，springsource-tool-suite
https://blog.csdn.net/u010203767/article/details/69211072

工作集(working set)
下拉->select working set

改@author
https://blog.csdn.net/lianggeblog/article/details/7267475

myeclipse

安装
编程->安装包
https://www.cnblogs.com/jiaoxiangjie/p/9555124.html

把方法内变量抽取成全局变量
refactor->convert local variable to field

mysql 1366错误

在查mysql 1366的错误原因时，发现一些有趣的回答。地址为：http://zhidao.baidu.com/question/59029575.html

不过，还是有人给出了比较好的解决方法：

http://www.phplamp.org/2008/11/mysql-1366-problem-solution/
MySQL 1366错误大致描述如下

  1. SQL Error: 1366: Incorrect string value: "\xE8\xAF\xA6\xE7\xBB\x86…" for column "address" at row 1

解决办法：检查数据库此字段的字符集与整理字符集是否与SQL语句传递数据的字符集相同；不相同则会引发MySQL1366错误。

修改MySQL该字段的字符集与整理规则即可。假设数据表为phplamp, SQL语句的字符集为utf8，出错的字段为address：
MySQL 1366 错误解决办法

  1. #检查数据表所有字段的状态
  2. ->show full columns from phplamp;
  3. #发现address字段的Collation项非utf8，修改它！
  4. ->alter table phplamp change name name varchar(100) character set utf8 collate utf8_unicode_ci not null default '';

修改完字段的字符集后可以再使用show full columns from table_name命令检查一下，以确保万无一失。假如您的SQL字符集为GBK或是GB2312或是其它的话，只需要将数据表字段的字符集更改为其相应的编码即可。

再送上一个MySQL的命令：
修改数据表的字符集与整理

  1. ->show full columns from table_name;

MyEclipse源码关联

Ctrl+右键点击HttpServlet，出现source not found,去tomcat官网下载源码，添加jar包即可。

## MyEclipse添加jstl插件
add build->Myeclipse library->...