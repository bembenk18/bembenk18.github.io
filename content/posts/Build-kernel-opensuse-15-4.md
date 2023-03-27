---
title: "Build Kernel openSUSE 15.4"
date: 2022-11-23T18:17:44+07:00
draft: false
image: ""
tags:
- Linux
- Log
---

Karena openSUSE Leap mengutamakan kestabilan maka untuk dapat mencoba kernel 6.* saya harus menunggu cukup lama, pada catatan kali ini saya akan coba build kernel 6.* di openSUSE Leap 15.4

## **1. Persiapan**

Install Requirements dan buat folder yang diperlukan
spesifikasi 
    sudo zypper ref && sudo zypper update 
    sudo zypper in -t pattern devel_basis bc openssl openssl-devel dwarves rpm-build libelf-devel elfutils-libelf-devel
    sudo mkdir ~/kernel

## **2. Download kernel**

Download kernel dari https://kernel.org/, saat blog ini dibuat kernel terbaru yaitu 6.0.9

![](https://raw.githubusercontent.com/bembenk18/Images/main/Build-Kernel/image-2-1024x558.png)

Pindahkan & Extract kernel yang sudah di download

    cd ~/kernel
    sudo mv ~/Download/linux*.tar.xz .
    tar -xafv linux*.tar.xz

## **3. Konfigurasi**

    cd linux*
    sudo find /boot/ \( -iname "*config*" -a -iname "*`uname -r`*" \) -exec cp -i -t ./ {} \;
    mv *`uname -r`* .config

Berikan comment pada **CONFIG_MODULE_SIG_KEY** di file *.config*

    ls /boot | konfigurasi grep
    sudo nano .config
    sudo make menuconfig

## **4. Build Kernel**

    sudo make clean

Selanjutnya adalah proses yang paling lama, saya sendiri memakan waktu sesayar 4 jam. Pada langkah ini silahkan sesuaikan dengan spesifikasi hardware,
   
    sudo make rpm-pkg

Setelah selesai silahkan cek dengan perintah

    sudo ls /usr/src/packages/RPMS/x86_64/ | grep kernel

![](https://raw.githubusercontent.com/bembenk18/Images/main/Build-Kernel/image-3.png)


## **5. Install kernel**

Setelah semua selesai saatnya install kernel yang sudah saya build

    sudo su -c "zypper in /usr/src/packages/RPMS/x86_64/kernel*.rpm"

Setelah berhasil install saatnya saya update bootloader dan reboot

    grub2-mkconfig -o /boot/grub2/grub.cfg
    sudo reboot

Cek apakah sudah berhasil terpasang

    uname -r

![](https://raw.githubusercontent.com/bembenk18/Images/main/Build-Kernel/image-4.png)


**Do it at your own risk**

~Bayu 