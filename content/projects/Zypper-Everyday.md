---
title: "Zypper Everyday"
date: 2023-01-26T14:29:55+07:00
draft: false
---
Tes

Karena openSUSE Leap mengutamakan kestabilan maka untuk dapat mencoba kernel 6.* kita harus menunggu cukup lama, pada coretan kali ini kita akan coba build kernel 6.* di openSUSE Leap 15.4

**1. Persiapan**

Install Requirements dan buat folder yang diperlukan

    sudo zypper ref && sudo zypper update 
    sudo zypper in -t pattern devel_basis bc openssl openssl-devel dwarves rpm-build libelf-devel elfutils-libelf-devel
    sudo mkdir ~/kernel




