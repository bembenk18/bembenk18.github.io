---
title: "Home Server Armbian"
date: 2023-04-10T14:48:52+07:00
draft: false
tags:
- Linux
- Server
---

Armbian adalah salah satu distro linux yang mendukung processor arm64 dengan  
spesifikasi rendah, salah satunya adalah STB HG680P yang banyak beredar dengan harga under 300k. STB ini juga bisa dijadikan alternative dari Raspberry Pi yang harganya semakin naik.

![Mobo STB HG680P](https://raw.githubusercontent.com/bembenk18/Images/main/Armbian%20Server/photo_2023-04-10_15-15-27.jpg)

# Spesifikasi
    RAM : 2 GB
    ROM Internal : 8 GB
    CPU : Amlogic s905x Cortex-A53 @ up to 1.51 GHz
    GPU : 5-Core GPU

Dengan spesifikasi tersebut sudah cukup untuk menjalankan Armbian. Untuk Armbian saya pasang pada microSD Sandisk Ultra UHS-I 32GB.

# Topologi

![Topologi](https://raw.githubusercontent.com/bembenk18/Images/main/Armbian%20Server/topologi%20stb.drawio%20(2).png)

### Grafana
Jalan di port 3030
### MQTT
### Adguard Home
Untuk blokir iklan dan konten negatif, web interface jalan di port 4040.
### Influxdb