---
title: "Install Kamailio VOIP Server"
date: 2024-05-13T11:07:09+07:00
draft: false
---
![Logo](https://www.kamailio.org/wp-images/kamailio-rock-logo.png)
## Pengenalan
Kamailio adalah Server SIP Sumber Terbuka yang kuat, dapat menangani ribuan panggilan per detik. Dapat digunakan untuk membangun platform besar VoIP dan komunikasi real-time seperti pesan instan, keberadaan, dan WebRTC. Fiturnya mencakup komunikasi aman, penyeimbangan beban, otentikasi, dan dukungan untuk berbagai sistem backend. Cocok untuk gateway SIP, PBX, dan server media seperti Asterisk dan FreeSWITCH.

## Proses installasi
### Tambahkan repositori
    root@aml:~# cat /etc/apt/sources.list
    deb http://deb.kamailio.org/kamailio55 buster main
    deb-src http://deb.kamailio.org/kamailio55 buster main

### Install mariadb dan kamailio
    apt install mariadb-server kamailio kamailio-mysql-modules kamailio-ims-modules
### Edit file konfigurasi kamailio (edit baris berikut ini)
    root@aml:~# cat /etc/kamailio/kamctlrc 
    SIP_DOMAIN=192.168.0.100
    DBENGINE=MYSQL
    DBHOST=localhost
    DBPORT=3306
    DBNAME=kamailio
    DB_PATH="/usr/local/etc/kamailio/dbtext"
    DBRWUSER="user"
    DBRWPW="password"
    DBROUSER="user"
    DBROPW="password"
    DBACCESSHOST=192.168.0.100
    DBROOTUSER="root"

### Ini juga
    root@aml:~# cat /etc/default/kamailio
    RUN_KAMAILIO=yes
    USER=kamailio
    GROUP=kamailio
    root@aml:~# 

### Restart service
    sudo service kamailio restart
    netstat -ntulp | grep kamailio
### Jalankan perintah untuk membuat database (ikuti semua intruksi)
    root@aml:~# kamdbctl  create
    MySQL password for root: 
    root@aml:~# 
### Buat user baru
    kamctl add 1234 halo
    * 123: username, halo: password

# Pengujian pada VOIP client
Login ke Linphone dengan user tadi seperti ini
![Linphone](https://raw.githubusercontent.com/bembenk18/Images/main/Kamailio/1.png)
