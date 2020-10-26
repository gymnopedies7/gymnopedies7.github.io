---
title: "Mysql Errors"
categories:
  - Mysql
  - Web
tags:
  - 웹개발
  - Django
  - mysql
thumbnail: /assets/image/github.jpg
toc: True
toc_sticky: True
---

[apt dpkg error](https://blog.miyu.pe.kr/953)
[mysql reinstall](https://velog.io/@michael00987/MYSQL-%EC%84%A4%EC%B9%98-%EC%9E%AC%EC%84%A4%EC%B9%98)

## How to solve for Mysql Reinstall error
sudo killall mysqld
sudo systemctl disable mysql.service
sudo rm -rf /lib/systemd/system/mysql.service
sudo rm -rf /usr/lib/systemd/system/mysql.service
sudo rm -rf /etc/systemd/system/multi-user.target.wants/mysql.service
sudo rm -rf /var/lib/systemd/deb-systemd-helper-enabled/multi-user.target.wants/mysql.service
sudo rm -rf /var/cache/apt/archives/mysql-server-*.deb

sudo apt-get install -f
sudo dpkg --configure -a

sudo apt-get install --reinstall mysql-server-8.0

