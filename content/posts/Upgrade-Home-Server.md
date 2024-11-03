---
title: "Upgrade Home Server"
date: 2024-10-31T10:25:29+07:00
draft: false
tags:
- Server
- Linux
---
Masih ingat dengan postingan home server [ini](https://bembenk18.github.io/posts/home-server-armbian/)? Karena makin besar keperluan komputasi akhirnya memutuskan untuk upgrade ke mesin yang lebih besar.

Ada beberapa pertimbangan diantaranya adalah ukuran yang kecil dan kosumsi daya bisa serendah mungkin tapi tetap powerffull, beberapa kriteria adalah sebagai berikut:

- Dell Wyse 5070
- Dell Optiplex 3050
- Lenovo Thinkcentre M710Q

Dari 3 pilihan diatas akhirnya memutuskan meminang Thinkcentre M710Q dengan spesifikasi:

- [Core i3 7100T 2C/4T 3.40 GHz 35W](https://www.intel.co.id/content/www/id/id/products/sku/97485/intel-core-i37100t-processor-3m-cache-3-40-ghz/specifications.html)
- 16 GB DDR4 2400

PC ini saya beli tanpa SSD, karena sudah ada SSD M.2 Sata copotan laptop (Catat M.2). Setelah sampai gas langsung install Proxmox di mesin ini, karena gak ada keyboard akhirnya install di laptop dulu kemudian pindah ke mesin ini. Setelah booting lah kok gak terdeteksi? dan ternyata hanya support SSD NVME bukan M.2 Sata (LOL).

Untungnya masih ada SSD Sata 128GB copotan laptop, gas langsung install dan berhasil boot dengan aman sentosa.
