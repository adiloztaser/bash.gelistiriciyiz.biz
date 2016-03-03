---
title: ls çıktısını sıralamak
date: Mar 03, 2016 09:38
tags: sort
---

`ls` komutu ile istediğimiz bir dizinin listesini görebiliriz.READ_MORE

örneğin `ls -al` dediğimizde;

    total 176K
    drwxr-xr-x 6 vigo staff  204 Mar  2 16:37 .
    drwxr-xr-x 5 vigo staff  170 Mar  2 16:37 ..
    -rw-r--r-- 1 vigo staff 158K Mar  2 09:33 cover.jpg
    -rw-r--r-- 1 vigo staff  161 Mar  2 09:30 favicon.png
    -rw-r--r-- 1 vigo staff 3.3K Mar  2 09:03 gelistiriciyiz.biz-logo.png
    -rw-r--r-- 1 vigo staff 8.0K Mar  2 09:28 logo.png

şeklinde bir çıktı alırız. Aslında bu çıktı **kolonlardan** oluşur. İlgili
kolona göre sıralama yapabiliriz. Örnekte;

    -rw-r--r--  1    vigo staff  161 Mar  2  09:30 favicon.png
    (1)         (2)  (3)  (4)    (5) (6) (7) (8)   (9)

Toplam **9** kolon bulunuyor. Dosya boyuna göre sıralamak için;

```bash
ls -al | sort -k 5    # 5. kolon
ls -al | sort -rk 5   # 5. kolon’a göre tersten
```

gibi kullanabilirsiniz. Sadece `ls` ile değil, `sort` komutunu benzer
kolon çıktı veren her tür metin işleminde de kulanabilirsiniz.