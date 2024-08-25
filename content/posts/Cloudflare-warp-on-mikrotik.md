---
title: "Setup Cloudflare Warp on Mikrotik"
date: 2024-08-25T05:46:19+07:00
draft: false
tags:
- Mikrotik
- Networking
---
Sesuai sabda pak Anton Wibowo tentang VPN dibawah ini, maka saya akan coba setup Cloudflare Warp di Mikrotik
![](https://raw.githubusercontent.com/bembenk18/Images/main/WARP/1.png)

Karena disini kita akan pakai Wireguard maka wajib menggunakan RouterOS versi 7.

# Buat akun Warp
- Untuk membuat akun disini saya akan pakai tools ini https://github.com/ViRb3/wgcf (Silahkan dibaca sendiri tutorialnya:v)
- Setelah itu kita akan mendapatkan file wgcf-profile.conf yang berisi
    ```
    ➜  Network cat wgcf-profile.conf 
    [Interface]
    PrivateKey = mAmDoyJ8Qf/2sEyuhjhPytLDtx8ioiEaJh3q8K8iE3u2U=
    Address = 172.16.0.2/32
    Address = 2606:4700:110:84ca:7d82:b1d:7534:56f9/128
    DNS = 1.1.1.1, 1.0.0.1, 2606:4700:4700::1111, 2606:4700:4700::1001
    MTU = 1280
    [Peer]
    PublicKey = bmXOC+F1FxEHF9jjiK2H5/1SUtzH0JuVo51h2wPfgyo=
    AllowedIPs = 0.0.0.0/0
    AllowedIPs = ::/0
    Endpoint = engage.cloudflareclient.com:2408
    ➜  Network 
    ```
# Setup Mikrotik
- Buat Wireguard baru dan sesuaikan dengan config profile yang sudah kita dapatkan (Edit pada bagian MTU & Private key)
![](https://raw.githubusercontent.com/bembenk18/Images/main/WARP/2.png)
- Buat Wireguard Peer sesuaikan juga Public Key, Endpoint dan Endpoint Port dengan profile
![](https://raw.githubusercontent.com/bembenk18/Images/main/WARP/3.png)
- Buat address baru dengan IP 172.16.0.2/32 dan Interface **WARP**
![](https://raw.githubusercontent.com/bembenk18/Images/main/WARP/4.png)
- Ubah DNS ke 1.1.1.1
- Buat Routing Table baru dengan nama **Cloudflare**
- Tambahkan Route baru dengan gateway **WARP**
![](https://raw.githubusercontent.com/bembenk18/Images/main/WARP/5.png)
- Buat NAT baru dengan Out Interface **WARP** dan action masquerade (Pastikan nat ini berada paling atas)
```
 /ip firewall nat add action=masquerade chain=srcnat disabled=no log=no log-prefix="" out-interface=WARP
```
- Tambahkan mange baru
```
/ip firewall mangle set *1 action=mark-routing chain=prerouting disabled=no log=no log-prefix="" new-routing-mark=Cloudflare  passthrough=no src-address=192.168.xx.xx-192.168.xx.xx
```

# Testing

### Sebelum Routing
Terlihat traffic masih mengarah ke ISP
![](https://raw.githubusercontent.com/bembenk18/Images/main/WARP/6.png)

### Setelah Routing
Terlihat traffic sudah mengarah ke Cloudflare
![](https://raw.githubusercontent.com/bembenk18/Images/main/WARP/7.png)


# Catatan
- Ini akan routing semua traffic
- Untuk apa harus routing dengan VPN? Sesuai arahan pak Anton biar gak bisa di intip oleh ISP dan pemerintah

