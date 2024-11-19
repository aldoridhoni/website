---
Title: Windows 10 Bahasa Indonesia
Slug: windows-10-bahasa-indonesia
Date: 2019-03-18 14:05:01
Category: How-To
Tags: [win10]
Status: published
---

Bahasa Indonesia untuk antarmuka Windows 10 sebelum versi 1809 diinstall menggunakan
file berformat _cab_ seperti [lp_0d84b5067XXXXX.cab](http://download.windowsupdate.com/c/msdownload/update/software/updt/2018/04/lp_0d84b5067992656ca28b7f02da7f288fe2705ec7.cab) dan Language Interface Packs (LIPs). 
Pada Windows 10 versi 1809 berubah menjadi __Local Experience Packs__ (LXP). 
LXP tersebut bisa diunduh melalui layanan Windows Store.


Berikut ini saya akan menulis langkah-langkah untuk menginstall file LXP tersebut secara manual.

- Saya lansir dari stackoverflow untuk menampilkan revisi sistem operasi:

```powershell
(Get-ItemProperty "HKLM:\SOFTWARE\Microsoft\Windows NT\CurrentVersion").BuildLabEx -match '^[0-9]+\.[0-9]+' |  % { $matches.Values }
```

- Pergi ke link [`https://store.rg-adguard.net`](https://store.rg-adguard.net)
- Masukkan link windows store berikut untuk "Pengalaman Lokal Bahasa Indonesia"

`https://www.microsoft.com/en-us/p/paket-pengalaman-lokal-bahasa-indonesia/9p4x3n4sdk8p`

- Unduh sesuai dengan versi os anda.
- Setelah selesai unduh, install menggunakan perintah `Add-AppxPackage -Path` di PowerShell. Untuk mendapatkan path file, tekan tombol __Shift__ sambil klik kanan tetikus dan pilih 'Copy as Path'. 

```powershell
Add-AppxPackage -Path "C:/Users/user/Download/Microsoft.LanguageExperiencePackid-id_17134.8.10.0_neutral__8wekyb3d8bbwe.Appx"
```

- Langkah terakhir aktifkan bahasa melalui Setting > Time & Language. Jika belum muncul di pilihan bahasa interface, pilih 'Add Language'.
