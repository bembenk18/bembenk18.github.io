---
title: "Upgrade Debian 11 to 12"
date: 2023-06-15T07:06:00+07:00
draft: false
tags:
- Log
- Linux
---

![Logo](https://raw.githubusercontent.com/bembenk18/Images/main/upgrade-debian/home.png)

Testing upgrade dari debian 11 ke debian 12 di STB HG680P
##### Posisi sebelum update
![Repo](https://raw.githubusercontent.com/bembenk18/Images/main/upgrade-debian/lsb.png)
##### Ganti repo
![Repo](https://raw.githubusercontent.com/bembenk18/Images/main/upgrade-debian/Screenshot_20230615_071807.png)

Ganti ke **bullseye** menjadi **bookworm** seperti berikut ini

    # sudo nano /etc/apt/sources.list

    deb http://deb.debian.org/debian bookworm main contrib non-free
    deb http://deb.debian.org/debian bookworm -updates main contrib non-free
    deb http://security.debian.org/debian-security bookworm-security main
    deb http://ftp.debian.org/debian bookworm-backports main contrib non-free

#####     Setelah ganti repository lakukan update repository baru
    
    sudo apt update

#####     Upgrade 
    sudo apt upgrade --without-new-pkgs
    sudo apt full-upgrade

#####   Reboot
    sudo systemctl reboot

##### Debian 11 berhasil terpasang 
![Logo](https://raw.githubusercontent.com/bembenk18/Images/main/upgrade-debian/home.png)

**Do it at your own risk**

~Bayu




