---
title: "Cerita mendapatkan FlightFeeder dari FlightAware"
date: 2025-03-29T04:50:07+07:00
draft: false
---
Saya kenal dunia ADS-B saat scroll post lama di group Orange Pi Indonesia dan tidak sengaja membaca post tentang ADS-B untuk tracking penerbangan. ADS-B (Automatic Dependent Surveillance-Broadcast) merupakan teknologi pengawasan penerbangan yang menggunakan transponder untuk memancarkan informasi posisi, kecepatan, ketinggian dan arah pesawat melalui gelombang radio.

![img](https://www.sportys.com//media/wysiwyg/blog/13_-_Navigating_and_Automation_in_the_21st_Century.png)

Untuk post yang saya sebut diatas, kita bertindak sebagai Ground Station yang akan mengirimkan data ke layanan pelacakan pesawat (FlightAware, Flightradar24, Airnav, dsb). Sebenarnya kita bisa build sendiri perangkat untuk melacaknya denggan raspberry pi, namun kali ini saya akan bahas tentang mendapatkan secara gratis dari FlightAware.

Awal saya apply feeder gratis dari FlightAware pada Juli 2023, tetapi ditolak karena tempat saya terhalang oleh bangunan lain. Selanjutnya saya coba apply lagi pada bulan Maret 2025 karena ditempat saya sudah ada tower yang lebih tinggi dari gedung tersebut dan akhirnya request ini di acc. Proses pengiriman start pada tanggal 13 Maret dan tiba pada 24 Maret, pengiriman melalui UPS dan selanjutnya diserahkan ke kurir lokal. Semua proses diatas  tidak dikenakan biaya sepeserpun mulai dari pengiriman, cukai, hingga tiba depan rumah (kalau semisal ada biaya kita bisa ajukan ganti ke FlightAware).

Isi paket pengiriman antara lain sebagai berikut:

- Flight Feeder orange
- Antenna 1090mhz
- T-shirt
- Adaptor set raspberry pi
- 1090mhz band pass signal filter
- Kabel coaxial 15M
- Kabel lan cat 5e 1.5M

Installasinya cukup mudah, hanya perlu colok adaptor dan colok lan ke modem, selanjutnya dia akan dapat ip dhcp.  Setelah sekitar 15 menit online maka akan dapat email kalau feeder kita sudah online, untuk akses web feeder kita bisa buka ip yang tertera di layar feeder.
![](https://raw.githubusercontent.com/bembenk18/Images/refs/heads/main/FlightAware/halaman-awal.png)

Tampilan tracking jika diakses local:
![](https://raw.githubusercontent.com/bembenk18/Images/refs/heads/main/FlightAware/local-tracking.png)

Untuk feeder saya ini jarak terjaun saat ini ada di sekitaran palangkaraya, dengan jarak 600km. Penempatan antenna tidak terlalu tinggi, sementara hanya saya tempatkan di pohon dengan ketinggian kurang lebih 5M dengan pandangan LOS kearah Utara dan Barat (jika ditempatkan diatas tower dengan ketinggian 15M mungkin akan lebih luas lagi pandangannya).

Dokumentasi:
- Penampakan antenna
![](https://raw.githubusercontent.com/bembenk18/Images/refs/heads/main/FlightAware/antenna.jpeg)
![](https://raw.githubusercontent.com/bembenk18/Images/refs/heads/main/FlightAware/antenna-2.jpeg)

- Penampakan FlightFeeder orange, adaptor set, dan band filter
![](https://raw.githubusercontent.com/bembenk18/Images/refs/heads/main/FlightAware/perangkat.jpeg)

Jika ingin apply bisa merujuk tautan berikut ini: https://www.flightaware.com/adsb/

Sekian
~Bembenk
  
  

