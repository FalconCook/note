//格式化
# bin/hdfs namenode -format
//单节点启动
# cd /opt/module/hadoop-2.7.7/ && sbin/start-dfs.sh

//问题：java_home找不到
//手动配置java_home环境
vi hadoop-env.sh

http://10.8.30.112:50070

//上传文件
# bin/hdfs dfs -put wcinput/wc.input /usr/chen/input
//查看
# bin/hdfs dfs -cat /usr/chen/input/wc.input
//文件系统下载(当前)
# hadoop fs -get /usr/chen/output/part-r-00000 ./
//删除
# hadoop fs -rmr /usr/chen/output

http://10.8.30.147:8088