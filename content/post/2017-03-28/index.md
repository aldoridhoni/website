---
Title: Diff of diff in fish
Slug: diff-of-diff-in-fish
Date: 2017-03-28 11:13:47
Status: published
Category: How-To
Tags: [fish]
---


Dalam podcast #4 [Destroy All Software](https://www.destroyallsoftware.com/), Gary memberikan sebuah contoh perintah diff dalam shell zsh.

-   Diff /dev/null ?
```shell
diff -u <(cat /dev/null) <(cat /dev/null)
```

-   Diff dari keluaran `git diff`.
```shell
diff -u <(git diff master~5..master~1) <(git diff master~4..master)
```

-   Diff dari website google.
```shell
diff -u <(curl www.google.com | tidy) <(curl www.google.fr | tidy)
```

Program **diff** digunakan untuk menampilkan perbedaan antara dua file. Perintah di atas pada intinya menjadikan proses yang ada di dalam kurung (subshell) untuk dijalankan dan mengarahkan hasil tersebut ke sebuah file pipe.

Penulis mencoba membuat perintah tersebut dalam shell fish. Perintah yang digunakan sedikit berbeda karena proses yang ada di dalam kurung diarahkan ke fungsi **psub**.

```shell
diff -u (cat /dev/null | psub) (cat /dev/null | psub)
```

### Screen record
<script type="text/javascript" src="https://asciinema.org/a/6z1rw1kdkj7kswkqzcjxbv3uo.js" id="asciicast-6z1rw1kdkj7kswkqzcjxbv3uo" async data-preload="1" data-loop="1"></script>
