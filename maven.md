## 官网
http://maven.apache.org/download.cgi

## maven仓库的优先级顺序

1，在本地仓库中寻找，本地仓库在conf/settings.xml里配，如果没有则进入下一步。
2，在全局应用的私服仓库中寻找，默认没有用户应用，所有还是看全局应用，如果没有则进入下一步。
3，在项目自身的私服仓库中寻找，默认不在项目里配，如果没有则进入下一步。
4，在中央仓库中寻找，在maven-model-builder-3.5.2文件夹里配置，如果没有则终止寻找。

补充：
1，如果在找寻的过程中，如果发现该仓库有镜像设置，则用镜像的地址代替。
2，如果仓库的id设置成“central”，则该配置会覆盖maven默认的中央仓库配置。

所以最有可能找的是镜像的地址，在conf/settings.xml里配

https://blog.csdn.net/sayyy/article/details/80452214
https://juejin.im/post/5a9fa4d5f265da23a4045ce8
https://juejin.im/post/5a4a5e2bf265da4322418d7f
https://juejin.im/post/5cb5cc48f265da035d0c7178

## 中央仓库、阿里云镜像
https://mvnrepository.com/artifact/junit/junit
https://maven.aliyun.com/mvn/view

## pom.xml详解
https://juejin.im/post/5cb5cc0ff265da0359486892

## eclipse建maven项目，添加web.xml
https://www.bilibili.com/video/av36557763/?p=22

## Maven配置文件中，mirror和repository的区别及中央仓库配置大全
https://msd.misuland.com/pd/4146263467944318236

## Maven私服Nexus3.x环境构建
https://www.cnblogs.com/kevingrace/p/6201984.html

## 理解Maven中的SNAPSHOT版本和正式版本
https://www.cnblogs.com/huang0925/p/5169624.html

## mvn clean -U install -Dmaven.test.skip=true -P test

-U https://www.jianshu.com/p/7e94b7de21a9
-D -P https://www.cnblogs.com/aiqingcao/p/12747237.html
跳过测试 https://blog.csdn.net/keith_walker/article/details/78853811

## eclipse Maven 生命周期 与构建目标冲突
https://www.jianshu.com/p/26bd2f737676

## Maven Profile按环境打包
https://juejin.im/post/6844903735496278030

## <optional>true</optional>
当其他项目继承本项目时，如果dependences中加上了<optional>true</optional>，表示当前依赖不向下传递。