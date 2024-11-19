---
Title: Compile Emacs-nox pada CentOS 7
Slug: compile-emacs-nox-pada-centos-7
Date: 2017-04-29 08:57:50
Status: published
Tags: [linux, emacs]
Category: How-To
---


### Apa itu Emacs
[Emacs](https://www.gnu.org/s/emacs/) adalah teks editor yang dibangun oleh Richard Stallman untuk proyek GNU. Emacs mulai dibangun dari pertengahan 70-an dan masih aktif dikembangkan sampai saat ini.

### Kenapa Compile?
Emacs yang ada dari package manager CentOS memiliki paket Emacs dengan versi 24.3. Versi minimal yang saya butuhkan adalah versi 24.4.

### Instalasi Kebutuhan
- Install `dnf` sebagai pengganti `yum`.

```shell
yum install dnf
```
        

- Install grup aplikasi untuk development + ncurses.

```shell
dnf -y group install 'Development Tools'
dnf -y install ncurses-devel
```
        

## Download Emacs
- Buat folder untuk menampung *source code*.
```shell
mkdir -p "$HOME/src"
cd "$HOME/src"
```

- Unduh source code dan ekstrak file.

```shell
curl http://ftp.gnu.org/gnu/emacs/emacs-25.2.tar.xz | tar xJ
```

### Konfigurasi Emacs tanpa X
- Buat folder untuk build :

```shell
mkdir -p "$HOME/src/emacs-25.2_build"
cd "$HOME/src/emacs-25.2_build"
```
        

- Konfigurasi :
```shell
../emacs-25.2/configure \
        --with-x=no \
        --without-dbus \
        --without-gconf \
        --without-gsettings \
        --without-pop \
        --without-xpm \
        --without-jpeg \
        --without-tiff \
        --without-gif \
        --without-png \
        --without-rsvg \
        --without-imagemagick \
        --without-sound \
        --without-xim \
        --without-all
```

- Mulai proses build :

```shell
make -j4 -sw
```

### Uji coba
Hasil kompilasi dapat dilihat dalam folder **src** dan dapat langsung dijalankan dengan `./emacs`. Untuk menginstall jalankan perintah `make install`.
