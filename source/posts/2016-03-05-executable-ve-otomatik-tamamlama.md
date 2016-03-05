---
title: executable ve otomatik tamamlama
date: Mar 05, 2016 18:37
tags: completion,osx
---
Bazı durumlarda, **executable** yani çalışabilir uygulama, kendisiyle ilgili
dosyaları `tab-completion` yani tab’e basarak tamamlamayabilir.READ_MORE

Örneğin **sqlite** uygulaması kuruluysa, otomatik olarak `*.sqlite` ya da
`*.sqlite3` ya da `*.db` dosylarını otomatik olarak algılamasını bekleriz.

`foo.db` dosyasını açmak için; `sqlite [TAB]` yaptığımızda hemen `foo.db`’nin
otomatik gelmesi şeklinde olmalıdır. Nasıl ki grafik arayüzlü ortamda, `*.pdf`
dosyasına tıklanınca otomatik olarak ilgili açıcının dosyası açması gibi
düşünebilirsiniz.

Mantık olarak istediğiniz executable’ın istediğiniz dosyalarla tamamlama bazında
ilişkilenmesini sağlayabilirsiniz;

```bash
complete -f -X '!*.@(sqlite?(3)|db)' sqlite3
```

Bundan böyle, `*.sqlite`, `*.sqlite3` ve `*.db` dosyaları **sqlite3** ile
ilişkilendi. `-X` pattern alıyor. `!` paternin tersini yapıyor, yani bu
kurala uymayanları tamamlama gibi :)

Daha detaylı bilgi [burada][01].

[01]: https://www.gnu.org/software/bash/manual/html_node/Programmable-Completion-Builtins.html#Programmable-Completion-Builtins