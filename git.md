## 场景：git删除已经push的远程文件
git rm --cached product-crud.iml

git commit -m 'delete something'

git push -u origin master

## 场景：本地有一个原项目。要上传到github。

GitHub创建repository

git clone https://github.com/cracker13/spring-boot.git

cd spring-boot/

git status

git add -A

git commit -a -m"first commit."

git push

## 场景：本地有多个demo要上传到GitHub

GitHub新建一个repository

clone下来，进入repository目录

把项目源文件复制过去

提交，readme.md上面标注用什么jar包

==============

## GitHub设置SSH KEY
https://www.jianshu.com/p/e93edea128a3
https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/

## 讲解 ssh-keygen -t rsa -b 4096 命令表达的意思
https://blog.csdn.net/qq_15957557/article/details/107022959

## eclipse提交GitHub
https://blog.csdn.net/bendanany/article/details/78891804

## idea提交GitHub
https://www.cnblogs.com/jinjiyese153/p/6796668.html

## Github获取私人的token
https://blog.csdn.net/bing900713/article/details/80222188


## 发给你一个gitLab账号
https://blog.csdn.net/qq_41770012/article/details/79854595
1.新建git文件夹、进入
2.git clone https://github.com/cracker13/mytomcat.git
2.更改、git pull
3.以后用再拉取

## 一个仓库存放多个项目
https://blog.csdn.net/bbc2005/article/details/78879551
用https地址会自动调用用户名、密码

## GitHub desktop使用
1.先在在网站建好一个repository
2.GitHub desktop登录
3.导进去
4.放入新文件
5.commit、push


## git、svn区别
- svn集中式、git分布式
- svn保存一组基本文件和每个文件与初始版本的差异，git存储散列值，如果没有变化，保存上一个版本的引用

## 在公司推代码注意切name、email
git config –-global user.name ‘james’
git config –-global user.email ‘james@gupaoedu.com’

## 如何升级Mac自带的Git
https://blog.csdn.net/WinstonLau/article/details/88140511


## git fetch & pull详解
https://juejin.im/post/6844903921794859021

## 查看fetch、push地址
git remote -v

## Git merge和rebase分支合并命令的区别
https://juejin.im/post/6844903603694469134

![](images/文件冲突前.png "文件冲突前") ![](images/文件解决冲突.png "文件解决冲突")

## GitHub下载单个文件
https://www.cnblogs.com/lllcccddd/p/11264054.html