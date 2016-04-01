---
title: "önceki aktif dizine dönme"
date: Apr 01, 2016 22:56
tags: change directory, cd, gnu/linux
author:
 name: "Adil ÖZTAŞER"
 email: "a@oztaser.com"
 link: "http://oztaser.com"
 bio: "Özgür Yazılım"
---
Gün içerisinde kullanmaktan en fazla hoşlandığım olay aslında bu. Bir projede
dizinler içinde kaybolduğum zamanlarda geldiğim dizine (genellikle kök dizine) dönmek.

Bu iş için kullandığımız komutta aslında bildiğimiz change directory (cd) komutu. ```cd -```

Gayet basit ve etkili bir komut bence şuda örnek:


    adil@debian ~ $ pwd
    /home/adil
    adil@debian ~ $ cd /var/www/html/
    adil@debian /var/www/html $ cd -
    /home/adil
    adil@debian ~ $
