---
title: "Setup Fail2Ban Zimbra"
date: 2023-03-26T13:47:58+07:00
draft: false
tags:
- Linux
- Server
- Log
---
## **0.**

    sudo -u zimbra -
    zmprov mcf +zimbraMailTrustedIP 127.0.0.1 +zimbraMailTrustedIP {IP of Server}
    zmcontrol restart

## **1. Install Fail2Ban**

    yum install epel-release -y
    yum install fail2ban -y

## **2. Buat file jail.conf**

*Jika ingin whitelist IP tambahkan pada baris ignoreip

 nano /etc/fail2ban/jail.local

    [DEFAULT]
    # "ignoreip" can be a list of IP addresses, CIDR masks or DNS hosts.
    # Fail2ban will not ban a host which matches an address in this list.
    # Several addresses can be defined using space (and/or comma) separator.
    #ignoreip = 127.0.0.1/8 ::1 10.137.26.29/32
    ignoreip = 127.0.0.1/8 IP-ADDRESS-OF-ZIMBRA-SERVER/32 WHITELIST-IP

    banaction = route

## **3. Buat file jail untuk Zimbra**

 nano /etc/fail2ban/jail.d/zimbra.local

    [zimbra-smtp]
    enabled = true
    filter = zimbra-smtp
    port = 25,465,587
    logpath = /var/log/zimbra.log
    maxretry = 3
    findtime = 86400
    bantime = 86400
    action = route

    [zimbra-web]
    enabled = true
    filter = zimbra-web
    port = 80,443,7071,9071
    logpath = /opt/zimbra/log/mailbox.log
    maxretry = 5
    findtime = 86400
    bantime = 86400
    action = route

## **4. Buat file jail untuk SSH**

 nano /etc/fail2ban/jail.d/sshd.local

    [sshd]
    enabled = true
    port = 22
    maxretry = 3
    findtime = 600
    bantime = 3600

## **5. Buat filter untuk Zimbra**

 nano /etc/fail2ban/filter.d/zimbra-web.conf 

    [Definition]
    failregex = .*ip=<HOST>;.*authentication failed for .*$

    ignoreregex =

 nano /etc/fail2ban/filter.d/zimbra-smtp.conf

    [Definition]
    failregex = postfix\/submission\/smtpd\[\d+\]: warning: .*\[<HOST>\]: SASL \w+ authentication failed: authentication failure$
                postfix\/smtps\/smtpd\[\d+\]: warning: .*\[<HOST>\]: SASL \w+ authentication failed: authentication failure$

    ignoreregex =

## **6. Enable**

    systemctl restart fail2ban
    systemctl status fail2ban
    systemctl enable fail2ban

## **7. Cek status**

    fail2ban-client status


## ***Ban & Unban***

    fail2ban-client set sshd banip 10.137.26.29
    fail2ban-client set sshd unbanip 10.137.26.29

# Sumber: https://blog.zimbra.com/2022/08/configuring-fail2ban-on-zimbra/