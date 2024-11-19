---
Title: Aktifasi Natural Scrolling
Slug: aktifasi-natural-scrolling
Date: 2019-05-28 15:32:13
Category: how-to
Tags: [linux]
Status: published
---


Natural Scrolling adalah penggeseran layar seperti pada layar touch screen. Jadi ketika scroll tangan digerakan keatas, layar turun kebawah dan sebaliknya.
Pada sistem desktop Linux seperti GNOME dan KDE, biasanya ada pilihan pada setting input untuk mengaktifkan natural scrolling ini. Untuk yang menggunakan X11 dengan window manager, biasanya menggunakan perintah dibawah ini yang ditempatkan pada file .xinitrc:

```shell
xmodmap -e "pointer = 1 2 3 5 4"
```

Untuk pilihan khusus seperti hanya menyalakan natural scrolling pada TouchPad dapat melakukan perubahan property lewat alat `xinput`, ganti id dan nama dengan nama hardware yang ingin diubah. 

```shell
xinput
xinput list-prop [id]
xinput --set-prop "SynPS/2 Synaptics TouchPad" "libinput Natural Scrolling Enabled" 1
```
    
Khusus untuk firefox bisa juga dicapai dengan membalik nilai multiplier dari 100 menjadi -100.
Buka halaman `about:config` dan cari `mousewheel.default.delta_multiplier_y`.
Kemudian ubah nilai menjadi `-100`.

