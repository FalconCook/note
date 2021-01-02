两个文件
build.gradle
settings.gradle 不用怎么动


build.gradle内容

group 'com.cracker'
version '1.0'

//插件
apply plugin: 'java'
apply plugin: 'war'
apply plugin: 'idea'
apply plugin: 'maven'

//源代码兼容性、目标代码兼容性，这两个需要保持一致
sourceCompatibility = 1.8
targetCompatibility = 1.8

//maven中央库

repositories {
	mavenCentral()
}

//私服，jar包先从私服获取
repositories {
    maven { url 'http://maven.aliyun.com/nexus/content/groups/public' }
    maven { url 'http://maven.aliyun.com/nexus/content/repositories/jcenter' }
}

//规范目录
sourceSets {
	main {
		java {
			srcDir 'src/main/java'
		}
		resources {
			srcDir 'src/main/resources'
		}
	}
}


//依赖的三个坐标信息
//jar包缓存在/Users/chen/.gradle
//providedCompile部署不会丢到war包里面，比如servlet这些服务器自带的包
dependencies {
    compile 'org.projectlombok:lombok:1.16.8';
    compile 'mysql:mysql-connector-java:5.1.34';
    compile 'cglib:cglib:3.2.8'
    testCompile '.......'
    providedCompile '.......'
}


//gradle命令
//依赖树
gradle buildDependents 
//依赖结构
gradle dependents 

//gradle建议使用命令


//建议使用utf-8编码。配置好这两个项目就不会出现乱码
task.withType(JavaCompile) {
	options.encoding = "UTF-8"
}

[compileJava, javaDoc, compileTestJava]*.opstions*.encoding = "UTF-8"

## 安装 && 路径
通过homebrew安装
brew info gradle

## 配置IntelliJ IDEA本地gradle
https://www.jianshu.com/p/8e2c9297f873

## idea推荐（强制）的gradle工作目录 /Users/chen/.gradle

## 使用哪个jvm && java home路径
gradle -v
echo $JAVA_HOME

## gradlew和gradle的区别
https://www.cnblogs.com/felixzh/p/10050209.html