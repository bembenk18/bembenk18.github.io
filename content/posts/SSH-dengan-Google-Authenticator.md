---
title: "Akses SSH Dengan Google Authenticator"
date: 2023-04-14T10:36:25+07:00
draft: false
tags:
- Linux
- Log
---
![Logo](https://cdn-blog.adafruit.com/uploads/2021/09/Untitled-2.png)
Ada banyak cara yang dapat dilakukan untuk mengamankan akses SSH ke server, salah satunya dengan Google Authenticator.

# Installasi
    sudo apt install libpam-google-authenticator -y

![Installasi](https://raw.githubusercontent.com/bembenk18/Images/main/Google-Auth/1.png)

# Tambahkan Google Authenticator ke HP
    google-authenticator -s ~/.ssh/google_auth
Setelah muncul QR code scan dengan Google Authenticator pada HP, Kemudian masukan kode yang muncul ke terminal 

![Scan](https://raw.githubusercontent.com/bembenk18/Images/main/Google-Auth/2.png)

dan ikuti panduannya hingga selesai.

![Scan](https://raw.githubusercontent.com/bembenk18/Images/main/Google-Auth/3.png)
# Konfigurasi 2FA SSH
Tambahkan baris berikut pada file  **/etc/pam.d/sshd**

    auth required pam_google_authenticator.so secret=/home/${USER}/.ssh/google_auth nullok
![Hehe](https://raw.githubusercontent.com/bembenk18/Images/main/Google-Auth/4.png)

Edit baris berikut pada file  **/etc/ssh/sshd_config**

    ChallengeResponseAuthentication no
menjadi

    ChallengeResponseAuthentication yes

![Hehe](https://raw.githubusercontent.com/bembenk18/Images/main/Google-Auth/5.png)

# Restart Service SSH
    sudo systemctl restart sshd

# Pengujian
Inputkan kode yang didapat 

![Test](https://raw.githubusercontent.com/bembenk18/Images/main/Google-Auth/6.png)

