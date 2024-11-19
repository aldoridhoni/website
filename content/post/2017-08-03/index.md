---
Title: Magit, kelola git dalam Emacs
Slug: magit-kelola-git-dalam-emacs
Date: 2017-08-03 02:18:37
Status: Published
Tags: [emacs]
Category: How-To
---
### Paket Magit

[![Magit Popup Help][img]][link]

[img]: magit.png
[link]: magit.png (click to enlarge)

Magit adalah sebuah paket yang berkerja sebagai sistem pengelolaan *versioning system* Git dalam Emacs.

### Mengaktifkan paket dengan 'use-package'

Tambahkan kutipan kode elisp berikut di file init emacs anda.

```emacs-lisp
(use-package magit
  :ensure t)
```

### Alur kerja umum

1. Buka magit-status `M-x` + `magit-status` .
2. Buffer status akan terbuka, pilih file yang ingin di _stage_ dengan tombol `s`.
3. Kalau sudah terpilih semua, tekan `c` dan `c` untuk commit.
4. Setelah selesai menulis pesan komit, tekan `C-c` + `C-c`.
5. Balik lagi ke magit status buffer. Untuk push tekan `P` dan `u`.
6. Tekan tombol `q` untuk keluar dari buffer.

Untuk membuka halaman pembantu tekan `C-c` + `C-c` atau `?`.


Referensi manual : <http://magit.vc/manual/magit/index.html>

