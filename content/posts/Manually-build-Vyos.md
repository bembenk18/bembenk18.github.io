---
title: "Manually Build Vyos"
date: 2024-07-10T10:20:20+07:00
draft: false
---
![logo](https://vyos.io/images/pages/index/vyos.svg)

Kapan kita perlu build Vyos manual? karena di website Vyos hanya tersedia versi Rolling Release untuk versi gratis.
## Requirements
- Debian Jessie untuk VyOS 1.2 (crux)
- Debian Buster untuk VyOS 1.3 (equuleus)
- Debian Bookworm untuk VyOS 1.4 (sagitta)
- Debian Bookworm untuk VyOS 1.5 & rolling release
## Clone repository
```
# VyOS 1.2 (crux)
$ git clone -b crux --single-branch https://github.com/vyos/vyos-build

# VyOS 1.3 (equuleus)
$ git clone -b equuleus --single-branch https://github.com/vyos/vyos-build

# VyOS 1.4 (sagitta)
$ git clone -b sagitta --single-branch https://github.com/vyos/vyos-build

# VyOS 1.5 (circinus,current)
$ git clone -b current --single-branch https://github.com/vyos/vyos-build
```
## Start Build
```
$ cd vyos-build

# VyOS 1.2 (crux) and VyOS 1.3 (equuleus)
$ ./configure --architecture amd64 --build-by "j.randomhacker@vyos.io"
$ sudo make iso

# VyOS 1.4 (sagitta)
$ sudo make clean
$ sudo ./build-vyos-image iso --architecture amd64 --build-by "j.randomhacker@vyos.io"

# VyOS 1.5 (circinus,current)
$ sudo make clean
$ sudo ./build-vyos-image generic --architecture amd64 --build-by "j.randomhacker@vyos.io"
```

Jika berhasil maka hasil build akan berada dalam folder **build**