---
title: https
date: 2018-08-27 17:00:56
tags:
---

### 下载letsencrypt并且生成证书
```bash
git clone https://github.com/letsencrypt/letsencrypt
cd letsencrypt
./letsencrypt-auto certonly
```
### 生成的证书在/etc/letsencrypt/live 目录下

cert.pem  Apache服务器端证书
chain.pem  Apache跟证书和中继证书
fullchain.pem  nginx搜需要的ssl_certificate文件
privkey.pem  安全证书key文件

