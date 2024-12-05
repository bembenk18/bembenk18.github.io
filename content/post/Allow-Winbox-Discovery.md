---
title: "Allow Winbox Discovery"
date: 2023-11-18T13:18:23+07:00
draft: false
tags:
- Linux
- OpenSUSE
- Firewall
---

Secara default winbox di openSUSE tidak menampilkan Neighbors karena terblokir oleh firewall. Kita harus allow manual.

    sudo firewall-cmd --permanent --service=winbox-discover --add-port=5678/udp
    sudo firewall-cmd --zone=public --add-service=winbox-discover --permanent 
    sudo firewall-cmd --reload
