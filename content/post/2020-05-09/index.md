---
Title: Emacs di Browser
Slug: emacs-di-browser
Date: 2020-05-09 20:28:08
Status: published
Category: How-To
Tags: [emacs, x11]
Cover: cover.png
---


Dengan menggunakan **Xpra** dari [xpra.org](https://xpra.org/trac/wiki/Clients/HTML5), kita dapat meneruskan X client ke dalam web browser.
Dalam posting ini saya akan mengikuti contoh dalam dokumentasi dengan perintah sebagai berikut:

```shell
$ xpra start --bind-tcp=0.0.0.0:10000 --start=emacs
```

Kemudian kita buka browser dan buka halaman localhost:10000. Berikut video tangkapan layar. 


<video controls style="width: 100%;">
  <source src="screen.webm" type="video/webm">
  <source src="screen.mp4" type="video/mp4">
Your browser does not support the video tag.
</video>


Dalam video diatas saya sudah membuka terminal emulator *xterm* dan *st*.
Dipojok kiri atas terdapat menu seperti panel menu pada *desktop manager* pada umumnya (XFCE dll).
Dengan menggunakan port 0.0.0.0, kita juga dapat membuka halaman web dari komputer lain dalam satu jaringan.
