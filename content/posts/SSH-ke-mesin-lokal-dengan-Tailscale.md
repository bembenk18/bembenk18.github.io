---
title: "SSH Ke Mesin Lokal Dengan Tailscale"
date: 2023-04-14T09:04:06+07:00
draft: false
tags:
- Linux
- Server
- Logs
---

Tailscale adalah aplikasi opensource berbasis WireGuard, tailscale memungkinkan untuk membangun jaringan peer to peer private. Dalam case saya gunakan untuk akses server lokal dirumah.

# Installasi
    curl -fsSL https://tailscale.com/install.sh | sh

# Start Tailscale service
    sudo tailscale up
Saat pertama kali akan diminta login, silahkan login dengan link yang muncul dikonsole, jika berhasil dijalankan kita akan mendapatkan ip seperti dibawah ini:
![Neofetch](https://raw.githubusercontent.com/bembenk18/Images/main/Tailscale/ip.png)
