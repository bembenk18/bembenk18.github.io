---
title: "SSH Ke Mesin Lokal Dengan Tailscale"
date: 2023-04-14T09:04:06+07:00
draft: false
tags:
- Linux
- Server
- Log
---
![Tailscale Logo](https://brands.home-assistant.io/_/tailscale/logo.png)

Tailscale adalah aplikasi opensource berbasis WireGuard, tailscale memungkinkan untuk membangun jaringan peer to peer private. Dalam case saya gunakan untuk akses [Home server](https://bembenk18.github.io/posts/home-server-armbian/).

# Installasi
    curl -fsSL https://tailscale.com/install.sh | sh

# Start Tailscale service
    sudo tailscale up
Saat pertama kali akan diminta login, silahkan login dengan link yang muncul dikonsole, jika berhasil dijalankan kita akan mendapatkan ip seperti dibawah ini:
![IP](https://raw.githubusercontent.com/bembenk18/Images/main/Tailscale/ip.png)

# Web Interface
Untuk mempermudah mengelola service Tailscale menyediakan web interface di [link berikut](https://login.tailscale.com/admin/machines)
![Web Interface](https://raw.githubusercontent.com/bembenk18/Images/main/Tailscale/web.png)

# Test akses SSH
Test akses SSH ke server 
![Test SSH](https://raw.githubusercontent.com/bembenk18/Images/main/Tailscale/ssh.png)

# Dokumentasi
Repo dan dokumentasi tentang Tailscale bisa diakses di https://github.com/tailscale

# Kesimpulan
Dengan menggunakan Tailscale kita bisa membuat jaringan private yang mudah dan aman untuk akses server lokal dari internet.