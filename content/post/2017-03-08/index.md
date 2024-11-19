---
Title:  Download Tile Map
Date: 2017-03-08
Status: Published
Category: How-To
---

### Tile Map

Peta yang ada di Web sekarang ini banyak menggunakan _tile map_. Tile map menampilkan peta memakai gambar-gambar kecil dalam grid berbentuk persegi. Gambar yang diunduh sesuai dengan luas yang sedang dilihat pada level zoom, bujur maupun lintang tersebut. Gambar-gambar kecil tersebut biasanya berformat PNG karena memiliki ketajaman yang lebih baik dibandingkan format JPEG terutama pada garis dan batas antara dua warna.

Pada umumnya peta _tile map_ ini memiliki zoom dari 1 yaitu mencakup keseluruhan bumi dan zoom 17 untuk melihat rumah-rumah. Jumlah gambar pada setiap level adalah perkalian antara x (bujur) dan y (lintang). Berikut tabel jumlah gambar per level.

| Level  | X | Y | Jumlah |
| -------| - | - | ------ |
| 2 | 0-3 | 0-3 | 16 |
| 3 | 0-7 | 0-7 | 64 |
| 4 | 0-15 | 0-15 | 256 |
| 5 | 0-31 | 0-31 | 1024 |
| 6 | 0-63 | 0-63 | 4096 |
| 7 | 0-127 | 0-127 | 16384 |
| 8 | 0-255 | 0-255 | 65536 |
| 9 | 0-511 | 0-511 | 262144 |

### Unduh

Pengunduhan gambar dengan jumlah banyak tersebut penulis menggunakan _curl_. Berikut perintah yang digunakan untuk melakukan pengunduhan.

```shell
curl --output '#1_#2.png' 'http://a.tiles.telegeography.com/maps/submarine-cable-map-2014/6/[0-63]/[0-63].png'
```

### Gabung Gambar

Penggabungan gambar menggunakan program [ImageMagick](https://www.imagemagick.org/).

<script src="https://gist.github.com/aldoridhoni/bd61a5e9bd14e293d9b9c4b852a63c4b.js"></script>

### Hasil

- [Submarine Map 2014 (28MB)](https://drive.google.com/open?id=0B8qWpTm08gGuQkgtYzVRSU91TGs)
- [Google Maps Composite (19MB)](https://drive.google.com/open?id=0B8qWpTm08gGuc2tHWldkZFRMMms)
