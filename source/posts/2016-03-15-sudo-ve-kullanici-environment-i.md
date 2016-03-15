---
title: "sudo ve kullanıcı environment’ı"
date: Mar 15, 2016 20:35
tags: unix,sudo,linux,osx
subtitle: Kullanıcının değişkenlerini muhafaza etmek
---

`sudo` yapabilen bir kullanıcınız olsun. **root** yetkisiyle işlem yapmak
istediğinizde doğal olarak `sudo KOMUT` şeklinde kullanırsınız.READ_MORE

Örneğin `deployer` adında bir kullanıcınız var, bu kullanıcı `sudoers` grubunda.
Hatta bu kullanıcı `vim` kullanıyor ve her türlü konfigürasyon ve ince ayara
sahip.

Normal olarak `root` kullanıcısı kötü günler için duruyor. Hatta login bile
olamıyor güvenlik sebebiyle.

Eğer `deployer` şunu yaparsa: `sudo vim /etc/nginx/nginx.conf` `nginx.conf`
dosyasını açıp **edit** yani yazma hakkı’na sahip olacak ama bir eksikle.
Açılan `vim` hiçbir şekilde kendi configürasyonunu okumamış, aynen `root`
olarak, sıfır konfigürasyonla açılmış.

İşte bu kadar uzun anlatımdan sonra, yapmanız gereken tek şey:

```bash
sudo -E vim /etc/nginx/nginx.conf
```

`-E` ne ? derseniz: `man sudo`

    # os x
    The -E (preserve environment) option will override the env_reset option
    in sudoers(5).  It is only available when either the matching command
    has the SETENV tag or the setenv option is set in sudoers(5).  sudo
    will return an error if the -E option is specified and the user does
    not have permission to preserve the environment.
    
    # ubuntu; -E ya da --preserve-env
    Indicates to the security policy that the user wishes to preserve their 
    existing environment variables.  The security policy may return an error 
    if the user does not have permission to preserve the environment.

Yani `sudo`’yu çalıştıran kullanıcının **ENV** değişkenlerini koru! Bu püf
noktasını [Thoughtbot][link]’un blog yazısından aldım.

[link]: https://robots.thoughtbot.com/executing-elevated-commands-in-your-current-environment