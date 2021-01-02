## 下载、安装
https://www.cnblogs.com/fanjingfeng/p/9849697.html
https://juejin.im/post/5bea84e3e51d450d050236bd

学成在线文档
要点
tracker.conf
base_path=/home/fastdfs/
storage.conf
base_path=/home/fastdfs
store_path0=/home/fastdfs/fdfs_storage

ip即本机ip

nginx-fdfs.conf拷nginx.conf的

  //nginx-fdfs.conf关键配置
  server {
  listen 80;
  server_name 10.8.30.148;

  #charset koi8-r;

  #access_log logs/host.access.log main;

  location /group1/M00/ {
  root /home/fastdfs/fdfs_storage/data;
  ngx_fastdfs_module;
  }

  //mac下的nginx配置
  #图片服务
  upstream img_server_pool1{
  server 10.8.30.148:80 weight=10;
  }
  upstream img_server_pool2{
  server 10.8.30.148:80 weight=10;
  }

  #图片服务
  server {
  listen 8080;
  server_name img.xuecheng.com;

  #个人中心
  location /group1 {
  proxy_pass http://img_server_pool1;
  }
  location /group2 {
  proxy_pass http://img_server_pool2;
  }
  }

fastdfs
进程 ps aux|grep dfs
杀死 kill -9 第二列
tracker
配置 cd /etc/fdfs && vi tracker.conf
启动 /usr/bin/fdfs_trackerd /etc/fdfs/tracker.conf restart
日志 cd /home/fastdfs/tracker/logs && cat trackerd.log
storage
配置 cd /etc/fdfs && vi storage.conf
启动 /usr/bin/fdfs_storaged /etc/fdfs/storage.conf restart
日志 cd /home/fastdfs/storage/logs && cat storaged.log
nginx
启动 /usr/local/nginx/sbin/nginx -c /usr/local/nginx/conf/nginx-fdfs.conf
重启 /usr/local/nginx/sbin/nginx -s reload