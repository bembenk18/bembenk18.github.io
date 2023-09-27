---
title: "Bongkar Apk Undangan Online"
date: 2023-09-27T16:15:20+07:00
draft: true
---
# Abstraksi
Bermula dari seseorang yang mengirimkan aplikasi dengan nama UNDANGAN.apk di salah satu group, lalu saya kepikiran untuk membongkar aplikasi tersebut.
## Informasi dasar file
| Nama      : | UNDANGAN.apk | 
|--------|------|
|   |    | 

| MD5        : | 5668b313d21604a67e2b50f58d516dff | 
|--------|------|
|   |    | 

| SHA1        : | b60bf67c109ed43a7af4a70ca3a18f8d212a2598 | 
|--------|------|
|   |    | 

| SHA256       : | 125c855d439895581bedf1b30bb779313058feb7f114f32167d45d427f27fe0c | 
|--------|------|
|   |    | 

## Hasil decompile file apk
Setelah decompile bisa kita lihat terdapat file Manifest dengan nama AndroidManifest.xml, difile ini berisi informasi dasar terkait aplikasi android seperti izin dan nama package

![Decompile](https://raw.githubusercontent.com/bembenk18/Images/main/Bongkar%20apk%20undangan%20online/Screenshot_20230927_151105.png)
## Analisa AndroidManifest.xml
Dari sini terlihat SDK yang digunakan adalah versi 32 yaitu Android 13 (Tiramisu), spesifikasi minimum yaitu SDK 26 yaitu Android 8 (Oreo).
Nama package dari aplikasi ini adalah **com.google.androidsmsotpteski**.

![](https://github.com/bembenk18/Images/blob/main/Bongkar%20apk%20undangan%20online/Screenshot_20230927_151033.png?raw=true)

Izin yang diperlukan aplikasi ini antara lain:

![](https://github.com/bembenk18/Images/blob/main/Bongkar%20apk%20undangan%20online/Screenshot_20230927_151136.png?raw=true)
1. **Izin menerima SMS:** dengan akses ini pelaku dapat membaca SMS dari hp si korban yang mana sangat berbahaya jika SMS tersebut adalah kode OTP
2. **Izin akses Internet:** ini mengizinkan aplikasi untuk mengakses internet yang mana akan digunakan untuk forward SMS ke telegram pelaku

Terdapat pula potongan kode yang mengindikasikan source aplikasi ini berasal dari [**SmsEye**](https://github.com/AbyssalArmy/SmsEye)

![](https://github.com/bembenk18/Images/blob/main/Bongkar%20apk%20undangan%20online/SMS.png?raw=true)

## Analisa Akun Telegram Pelaku
Ketika kita buka folder assets kita akan menemukan file yang menarik bernama url.txt, token.txt, dan id.txt

![](https://github.com/bembenk18/Images/blob/main/Bongkar%20apk%20undangan%20online/assets.png?raw=true)

**Isi dari file diatas adalah sebagai berikut:**
1. url.txt

![](https://github.com/bembenk18/Images/blob/main/Bongkar%20apk%20undangan%20online/url.png?raw=true)

2. token.txt
File ini berisi informasi token telegram bot pelaku yang digunakan untuk mengirim kode OTP ke akun telegram pelaku

![](https://github.com/bembenk18/Images/blob/main/Bongkar%20apk%20undangan%20online/token.png?raw=true)

3. id.txt
File ini berisi id telegram pelaku yang digunakan menerima pesan dari bot, terlihat id telegram pelaku adalah **6215803741**


![](https://github.com/bembenk18/Images/blob/main/Bongkar%20apk%20undangan%20online/id.png?raw=true)
