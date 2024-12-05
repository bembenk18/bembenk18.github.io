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

![Mobo STB HG680P](https://raw.githubusercontent.com/bembenk18/Images/main/Armbian-Server/photo_2023-04-10_15-15-27.jpg)

# Spesifikasi
    RAM : 2 GB
    ROM Internal : 8 GB
    CPU : Quad Core Amlogic s905x Cortex-A53 @ up to 1.51 GHz

![Neofetch](https://raw.githubusercontent.com/bembenk18/Images/main/Armbian-Server/neofetch.png)

Dengan spesifikasi tersebut sudah cukup untuk menjalankan Armbian. Untuk Armbian saya pasang pada microSD Sandisk Ultra UHS-I 32GB.

# Topologi

![Topologi](https://raw.githubusercontent.com/bembenk18/Images/main/Armbian-Server/topologi%20stb.drawio%20(2).png)

### Grafana
Untuk visualisasi data
![Grafana](https://raw.githubusercontent.com/bembenk18/Images/main/Armbian-Server/grafana.png)
### MQTT
Untuk record data perangkat IoT, dikombinasikan dengan Grafana & Influxdb
### Adguard Home
Untuk blokir iklan (kecuali iklan youtube) dan konten negatif.
![Adguard](https://raw.githubusercontent.com/bembenk18/Images/main/Armbian-Server/adguard.png)
### Influxdb
Untuk record data perangkat IoT, dikombinasikan dengan Grafana & MQTT

# Akses 
Untuk remote server dari jaringan luar saya menggunakan [Tailscale](https://bembenk18.github.io/posts/ssh-ke-mesin-lokal-dengan-tailscale/)