---
title : WriteUp - DeepCTF 2020
published : true
---

Hello ya kembali membahas WriteUp CTF seperti sebelumnya.pada tanggal 03-04-2020 ada event CTF yang diselenggarakan oleh orang luar nama CTFnya itu ***DEEPCTF***, ***DEEPCTF*** emang lebih dahulu dibanding ***IJCTF*** tapi saya bikin WUnya baru sekarang gpp kali yakkkk.langsung saja gas WriteUp nya

***
## Category : WEB
* Oh JS!

Disini diberikan [link](http://140.238.254.6:8002/) menuju sebuah website yang berisi `administrator Panel.`

![](..\image\CTF\ohjs\ohjs.png)

nah seperti kita tahu bahwa salah satu cara untuk mencari hint di Web CTF ini bisa dengan cara melihat `source codenya` terlebih dahulu, untuk mengetahui cara kerja website ini untuk apa, dengan begitu kita bisa mendapatkan informasi untuk melanjutkan step berikutnya.

berikut view source tersebut : 
![](..\image\CTF\ohjs\ohjs1.png)

terlihat didalam source code itu terdapat method POST untuk `Username` Dan `Password`. dan dapat dilihat juga dibagian `function validate()"` itu ada banyak tanda `"[]()!+"`, kalo kita tahu `Esolang Language` atau `Joke language` kita dapat mengetahui bahwa itu adalah `JSFuck` dari esolang language, langsung saja saya coba decode menggunakan link [disini](https://enkhee-osiris.github.io/Decoder-JSFuck/) dan didapati Username,Password dan link .php

![](..\image\CTF\ohjs\ohjs2.png)

langsung saja copy paste link dan menuju ke link tersebut 
dan didapatkan lah Flagnya

![](..\image\CTF\ohjs\ohjs3.png)
```ruby
FLAG : d33p{g0tta_kn0w_y0ur_J4v4Scr1pt}
```
mudah kah ? hanya perlu mengetahui `esolang language` dan `basic web` untuk melihat source code, kita dapat flag nya deh


***

## [](#header-2)Category : Crypto

* Warm Up

![](..\image\CTF\warmup\warmup.png)

ini pasti bisa bagi yang tau `konversi bilangan Biner, Hexa, Octal, Decimal` langsung aja di konversi ke ascii.
saya pake online tool web aja hehe

![](..\image\CTF\warmup\warmup1.png)
```ruby
Flag : d33p{Ju5t_4_N0rm4l_Ch4ll__Isn`t_1t?}
```

* Ali3nCalling

![](..\image\CTF\aliencalling\aliencalling.png)

di soal ini kita diberikan sebuah gambar yang isinya seperti ini. 

![](..\image\CTF\aliencalling\aliencalling1.png)

setelah saya ingat ingat diwebsite `enigmator` itu ada sebuah symbol yang menyerupai gambar tersebut, lalu saya coba mengunjungi web tersebut mencari sebuah decoder yang sesuai dengan encoding tersebut lalu ditemukan lah encoding yang bernama `pigpen Cipher` ya terus tinggal klik aja symbol nya sesuaiin dapet deh flagnya 

![](..\image\CTF\aliencalling\aliencallingfinal.png)

eitss, tunggu dulu tidak semua hasil decode itu adalah flagnya, flagnya itu hanya bagian yang terujung (anda jangan tertipu) yaitu `OUTOFTHEWORLDCIPHER`

lalu sesuaikan flagnya dengan ketentuan disoal yaitu `lowercase` udah deh gitu aja 
```ruby
Flag : d33p{outoftheworldcipher}
```
* Ali3nAgain

![](..\image\CTF\alienagain\alienagain.png)

di soal ini diberikan sebuah gambar seperti ini 

![](..\image\CTF\alienagain\alienagain2.png)

disoal ini saya tidak menemukan simbol di website `enigmator`, lalu saya mencoba searching `mbah gugle lah.` setelah beberapa kali mencari, didapatkan salah satu website yang encoding nya itu simbolnya sesuai dengan gambar yaitu : `Futurama Alien Language`. saya dapatkan infonya dari website [disini](https://foo-manroot.github.io/post/ctf/ciberseg/write-up/crypto/2019/01/23/ciberseg-2019-crypto.html)

lalu decode deh diwebsite [d.code](https://www.dcode.fr/futurama-alien-alphabet). sesuaikan simbolnya and good job you get a flag

![](..\image\CTF\alienagain\alienagainfinal.png)

jangan lupa flag disesuaikan **`yakkkkk`** harus `Uppercase` liat di soal nyuakk
```ruby
Flag : d33p{POWERRANGERSPDFORCEWON}
```
* WTf`ish

![](..\image\CTF\brainf\brainf.png)

disoal ini diberikan text yang berisi : 
```
++++++++++[>+>+++>+++++++>++++++++++<<<<-]>>>>.<-------------------..>++++++++++++.+++++++++++.<++++++++++++++++++++++++++++++++++++.+++++++++++++++++.-------.>-------.<--.-----------.>------------.---.------.<------------------.>+++++++++++++++++++.-----------------.++++++++.+++++.<++++.<+++++...>>+++++++++++++++.
```

bisa kita ketahui itu adalah `brainfuck` dari `esolang language` sama seperti `JSFuck` langsung aja decode secara online. dapet deh flagnya 

![](..\image\CTF\brainf\brainf1.png)
```ruby
lag : d33p{What_The_BrainF###}
```
* RSA 1.0

![](..\image\CTF\rsasatukosong\rsa.png)

nah disoal ini diberikan text yang berisi :
```
n=99403780699278363705617724107392416087334310715398778338124709736954091101954779586016351855873144416857965814267653566199133049127561468788015928148773150828312692547018173408079873947734995983392683281966120098505717566949918890305896534370669528370174789731819349366100756703422853461957874622210882984991

p=12821033464604691952119977327257058231949915333155906986544158416335450219984219070292809030391388001948272955865276723152883246737705404608104256335092339

c=11956190223138005271009322807586172860662424947284260332491084433305621445657343034852249316066402104658909306289495404312909771887386244446015588894745467590153867256937662894156498037593066899526384276716686647405770112762878557574979773847622072624529992852600974839946969273545086793019273308981047747227

e=0x10001
```
langsung aja deh ga usah basa basi, pake Tools `RsaCTFTools` dari github
kalian bisa cek [disini](https://github.com/Ganapati/RsaCtfTool)

![](..\image\CTF\rsasatukosong\rsa1.png)
```ruby
Flag : d33p{An0th3r_S1mpl3_RSA_D3fe4t3d}
```
gitu aja sih WriteUp ***DeepCTF*** dari saya 

Good Luck, may be Useful Mantap!

maaf juga banyaknya cuma basicnya karna saya juga masih belajar ngehehe
```ha
Keterangan : 
        - Esolang Language : https://esolangs.org/wiki/Language_list
        - Uppercase = Huruf Kapital example : (ABCDEFGHIJKL)
        - Lowercase = Huruf kecil example :(abcdefghijkl)
        - nanti Update beberapa Write Up lagi dan di content ini, tidak terpisah
```     
        
***iklan di foto abaikan :(**