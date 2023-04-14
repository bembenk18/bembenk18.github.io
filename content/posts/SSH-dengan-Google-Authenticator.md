---
title: "Akses SSH Dengan Google Authenticator"
date: 2023-04-14T10:36:25+07:00
draft: true
tags:
- Linux
- Log
---
![Logo](https://cdn-blog.adafruit.com/uploads/2021/09/Untitled-2.png)
Ada banyak cara yang dapat dilakukan untuk mengamankan akses SSH ke server, salah satunya dengan Google Authenticator.

# Installasi
    sudo apt install libpam-google-authenticator -y
![IP](https://raw.githubusercontent.com/bembenk18/Images/main/Google-Auth/1.png)
# Tambahkan Google Authenticator ke HP
    google-authenticator -s ~/.ssh/google_auth

