---
title: "Cisco Packet Tracer Opensuse"
date: 2023-03-27T15:20:56+07:00
draft: true
---


![Image alt](https://raw.githubusercontent.com/bembenk18/Images/main/CPT/1.png)
Di website [netacad](https://www.netacad.com/) Cisco Packet Tracer hanya tersedia untuk Ubuntu/Debian dengan format .deb, jadi secara default tidak tersedia di distro rpm based. Untuk itu perlu memasang secara manual.

## 1. Download

Download file installasi untuk Ubuntu/Debian dari web [netacad](https://www.netacad.com/)

## 2. Unpack file .deb

    mkdir /tmp/cpt
    cp CiscoPacketTracer_820_Ubuntu_64bit.deb /tmp/cpt 
    ar -xv CiscoPacketTracer_820_Ubuntu_64bit.deb 
    mkdir control
    tar -C control -Jxf control.tar.xz 
    mkdir data
    tar -C control -Jxf data.tar.xz 
    cd data

## 3. Install
    
    cp -r usr /
    cp -r opt /

**Tumbleweed**

    ln -s /usr/lib64/libdouble-conversion.so.3.1.5 /usr/lib64/libdouble-conversion.so.1

## 4. Update icon

    xdg-desktop-menu install /usr/share/applications/cisco-pt.desktop
    xdg-desktop-menu install /usr/share/applications/cisco-ptsa.desktop
    update-mime-database /usr/share/mime
    gtk-update-icon-cache --force --ignore-theme-index /usr/share/icons/gnome
    xdg-mime default cisco-ptsa.desktop x-scheme-handler/pttp

## 5. Symlink

    ln -sf /opt/pt/packettracer /usr/local/bin/packettracer


**~Bayu**