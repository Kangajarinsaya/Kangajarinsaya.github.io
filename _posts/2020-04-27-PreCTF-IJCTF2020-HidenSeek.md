---
title : WriteUp PreCTF - IJCTF2020
published : true
---

Hello ini Content pertama saya yang mengenai CTF yakkk. pada tanggal 25-04-2020 ada event CTF yang diselenggarakan oleh orang luar nama CTFnya itu ***IJCTF***. nah biasanya sebelum memulai CTF aslinya pihak penyelenggara ngadain dulu PreCTF buat manas manasin pemain lah kali :). nah disini saya akan membahas salah satu soal di preCTF tersebut. nah di content berikutnya juga bakalan ada WriteUp CTF nya ***IJCTF*** (bukan preCTF ya). langsung aja gas pembahasannya 

***
Di discord ***IJCTF*** diberikan sebuah file zip yang berisi beberapa text dan tentunya pasti ada flagnya didalam yakk
nah pertama ketika di extract file `unzip.zip` nya dan check isinya itu berisi beberapa `file text` dan `1 file zip`

soalnya bisa didownload [disini](https://github.com/linuxjustin/IJCTF/blob/master/chall/unzip.zip).

![](..\image\CTF\hidenseek\hidenseek1.png)

lalu saya coba unzip lagi flag.zip nya tetapi meminta password tentu saya tidak punya :), kemudian saya cek file hasil unzip tersebut tidak mendapatkan apapun yang ada malah "tr0ll3d" ketika dicoba pun bukan password flag.zip itu. 

![](..\image\CTF\hidenseek\hidenseek2.png)

kemudian saya cek kembali dan menemukan satu file yang di `hide` ketika zip itu diextract (atau lihat gambar pertama)

![](..\image\CTF\hidenseek\hidenseekaja.png)

kemudian saya lihat isi dari file ".0" itu dan didapatkan sebuah password yang ditulis secara vertical yaitu : `warlock_rootx`

![](..\image\CTF\hidenseek\hidenseek3.png)

lalu gocha password betul dan didapatkan flagnya 

![](..\image\CTF\hidenseek\hidenseekfinal.png)

`FLAG : ijctf{d0t_f1l3s_4r3_h1dd3n__R3m3mb3r?}`

Good Luck, May be Useful 
Mantap!
```ha
*Keterangan : 
    (Basic Linux Command)
    -ls = melihat semua isi yang ada di dalam folder (tidak termasuk hidden file) | (tambahkan "-al" untuk melihat hidden files)
    -cat = melihat isi file yang dipilih
    -unzip = mengextrack file zip
```
