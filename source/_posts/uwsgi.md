---
title: uwsgi
date: 2018-10-12 15:28:27
tags:
---

部署静态文件
在运行nginx之前，您必须收集静态文件夹中的所有Django静态文件。首先你需要编辑pg / settings.py添加：

STATIC_ROOT = os.path.join(BASE_DIR, "static/")

然后跑

```bash
python manage.py collectstatic
```

uwsgi 配置文件
[uwsgi]
#//path/to/your
chdir           = /home/pg
module          = pg.wsgi
master          = true
processes       = 10
socket          = 0.0.0.0:8001
#chmod-socket    = 664
# clear environment on exit
vacuum          = true
stats=/etc/uwsgi/pg.status
#用于重启uwsgi
pidfile=/etc/uwsgi/pg.pid


nginx配置文件

upstream django {
   # server unix:///path/to/your/pg/pg.sock; # for a file socket
    server unix:///home/pg/pg.sock; # for a file socket
}

# configuration of the server
server {
    # the port your site will be served on
    listen      80;
    # the domain name it will serve for
    server_name localhost; # substitute your machine's IP address or FQDN
    charset     utf-8;

    # max upload size
    client_max_body_size 75M;   # adjust to taste
        location / {
        include        uwsgi_params;
        #和uwsgi.ini socket一样
        uwsgi_pass     0.0.0.0:8001;
    }

    # Django media
    location /media  {
        # //path/to/your
        alias /home/pg/media;  # your Django project's media files - amend as required
    }

    location /static {
        # //path/to/your
        alias /home/pg/static; # your Django project's static files - amend as required
    }

    # Finally, send all non-media requests to the Django server.
    #location / {
    #    uwsgi_pass  django;
    #    include     /home/pg/uwsgi_params; # the uwsgi_params file you installed
    #}
}
