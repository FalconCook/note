教程
https://www.bilibili.com/video/av68136734?p=2

安装
http://nginx.org/en/linux_packages.html

mac安装
https://www.cnblogs.com/tandaxia/p/8810648.html
启动     sudo nginx
配置目录  /usr/local/etc/nginx

Nginx官方版本说明##Mainline version&Stable version
https://blog.csdn.net/open_data/article/details/44409359

启动
/usr/sbin/nginx -c /etc/nginx/nginx.conf

配置虚拟主机
在/etc/nginx/conf.d的default.conf

server {
  listen 80;
  server_name www.xuecheng.com;

  #charset koi8-r;
  #access_log /var/log/nginx/host.access.log main;

  ssi on;
  ssi_silent_errors on;

  location / {
  root /usr/app/xc-ui-pc-static-portal;
  index index.html index.htm;
  }

  #error_page 404 /404.html;

  # redirect server error pages to the static page /50x.html
  #
  error_page 500 502 503 504 /50x.html;
  location = /50x.html {
  root /usr/share/nginx/html;
  }

  # proxy the PHP scripts to Apache listening on 127.0.0.1:80
  #
  #location ~ \.php$ {
  # proxy_pass http://127.0.0.1;
  #}

  # pass the PHP scripts to FastCGI server listening on 127.0.0.1:9000
  #
  #location ~ \.php$ {
  # root html;
  # fastcgi_pass 127.0.0.1:9000;
  # fastcgi_index index.php;
  # fastcgi_param SCRIPT_FILENAME /scripts$fastcgi_script_name;
  # include fastcgi_params;
  #}

  # deny access to .htaccess files, if Apache's document root
  # concurs with nginx's one
  #
  #location ~ /\.ht {
  # deny all;
  #}
}

root alias 区别
https://segmentfault.com/a/1190000015408906

==========

## Nginx翻译
https://juejin.im/post/6844903510199238670

## Nginx 初探
https://juejin.im/post/6844903957949579271

## Nginx 由浅入深
https://juejin.im/post/6844904198480347149

https://juejin.im/post/6844903829159280654

https://juejin.im/post/6844903855105245198

https://juejin.im/post/6844903785274277902

## Nginx看这一篇文章就够了！
https://juejin.cn/post/6904607058776047629

