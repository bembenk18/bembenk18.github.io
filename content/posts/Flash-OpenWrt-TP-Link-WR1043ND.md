---
title: "Flash OpenWrt TP Link WR1043ND"
date: 2024-09-14T14:57:38+07:00
draft: false
tags:
- Linux
- Networking
---
# Pendahuluan

Saat ini internet di rumah saya memiliki kecepatan 30Mb/s, namun baru sadar kalau speed wireless dari mikrotik RB941 mentok 15Mb/s pada jarak 5 meter (mungkin karena cuma pakai antena internal saja). Setelah mencari router yang cocok, ada 2 pilihan sebagai berikut:

| Model                    | Wireless  | Port RJ45   | Harga          |
| ------------------------ | --------- | ----------- | -------------- |
| Mi 4 Gigabit             | 2.4G & 5G | 3 / Gigabit | 350k           |
| TP-Link TL WR1043ND v2.1 | 2.4G      | 5 / Gigabit | < 150K (Bekas) |

Setelah beberapa pertimbangan akhirnya pilih TP-Link dengan harga 128k (diskon jadi 78k wkwkwk), karena ini router tua jadi beberapa fitur sudah tertinggal, jadi agar lebih optimal maka saya akan coba flash dengan firmware OpenWrt. Disini saya pakai firmware ROOter

### Spesifikasi

| Model                | TL-WR1043ND v2.1        |
| -------------------- | ----------------------- |
| CPU                  | Qualcomm Atheros QCA955 |
| CPU MHz              | 720                     |
| CPU Core             | 1                       |
| Flash                | 8MB                     |
| RAM                  | 64MB                    |
| Ethernet 1Gbit ports | 5                       |
| USB                  | 1x2.0                   |


# Instalasi firmware

### Persiapan

1. Download firmware dari https://www.ofmodemsandmen.com/ (sesuaikan versi atau akan brick)
2. Ekstrak file yang sudah didownload
3. Ada beberapa firmware, untuk pertama flash pakai yang ada label factory (baca pdf agar jelas)

## Install firmware

1. Login ke web interface router
2. Masuk ke **System Tools >> Firmware Upgrade**

   ![img](https://raw.githubusercontent.com/bembenk18/Images/main/Openwrt-WR1043ND/1.png)
3.
