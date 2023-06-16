---
title: "Upgrade Debian 11 to 12"
date: 2023-06-15T07:06:00+07:00
draft: false
tags:
- Log
- Linux
---
Testing upgrade dari debian 11 ke debian 12 di STB HG680P
### Proses
#### Ganti repo

Ganti ke repository berikut ini

    # sudo nano /etc/apt/sources.list

    deb http://deb.debian.org/debian bookworm main contrib non-free
    deb http://deb.debian.org/debian bookworm -updates main contrib non-free
    deb http://security.debian.org/debian-security bookworm-security main
    deb http://ftp.debian.org/debian bookworm-backports main contrib non-free

#### sudo apt update
#### sudo apt upgrade --without-new-pkgs
#### sudo apt full-upgrade
#### sudo systemctl reboot





