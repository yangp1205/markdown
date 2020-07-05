# 在Nginx上部署Django（uwsgi）

* _使用Ubuntuserver16.04TLS_

## 安装nginx、python3、pip3

```zsh
sudo apt install python3 nginx python3-pip
```

## 建立python3虚拟环境下的Django项目

* 在系统环境下安装uwsgi

```zsh
# 未安装过uwsgi
sudo apt-get install libpcre3 libpcre3-dev
sudo pip3 install uwsgi
# 已安装uwsgi，启动后报错
sudo pip3 uninstall uwsgi
sudo apt-get install libpcre3 libpcre3-dev
sudo pip3 install uwsgi -I --no-cache-dir #禁用缓存安装
```

* 安装python3虚拟环境
* 在python3虚拟环境中安装Django,并建立项目

```zsh
pip install django
django-admin startproject projectname
cd projectname
python mange.py startapp appname
#以下省略
```

## 配置uwsgi

* 可以建立一个和projectname同级文件夹来处理uwsgi

```zsh
mkdir django_uwsgi
cd django_uwsgi
vim uwsgi.ini
```

* 建立uwsgi的配置文件

``` ini
[uwsgi]
chdir = /home/ubuntu/django_wechat
home = /home/ubuntu/.virtualenvs/env_django
module = mytestsite.wsgi:application

master = True
processes = 4

max-requests = 5000
post-buffering = 65535
buffer-size = 65535
harakiri-verbose = True
harakiri = 20

socket = 127.0.0.1:8001
uid = ubuntu
gid = ubuntu

pidfile = /home/ubuntu/django_uwsgi/master.pid
daemonize = /home/ubuntu/django_uwsgi/uwsgi_wechat.log
vacuum = True
pcre = True
debug = True
enable-threads = True
```

* 启动uwsgi

```zsh
cd django_uwsgi
sudo uwsgi --ini uwsgi.ini --enable-threads 
#加--enable-threads可在python3中使用多线程服务
```

## 配置Nginx服务

* 基本操作

```bash
sudo services nginx start\stop\retart
#配置文件路径
/etc/nginx/
#日志文件
/var/log/nginx/
```

* 配置Django服务site

```zsh
cd /etc/nginx/sites-available
vim mysite.conf
```

* Nginx配置文件

```nginx
server{
    listen 80;
    server_name wechat.com;
    charset utf-8;

    client_max_body_size 75M;

    location /static {
        alias /home/ubuntu/django_wechat/static;
    }

    location / {
        uwsgi_pass 127.0.0.1:8001;
        include /etc/nginx/uwsgi_params;
    }
}
```

* 启动站点

```zsh
#删除默认的default链接
sudo rm default
#使用软连接
sudo ln -s /etc/nginx/sites-available/mysite.conf /etc/nginx/sites-enabled/mysite.conf
```

* 启动nginx，即可通过浏览器访问