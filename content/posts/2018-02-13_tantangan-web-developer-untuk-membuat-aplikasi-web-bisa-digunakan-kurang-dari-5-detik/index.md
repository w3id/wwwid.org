---
title: "Tantangan Web Developer Untuk Membuat Aplikasi Web Bisa Digunakan Kurang Dari 5 Detik"
author: "Yohan Totting"
date: 2018-02-13T07:45:58.208Z
lastmod: 2019-05-20T16:27:02+07:00

description: ""

subtitle: "Ada banyak jalan menuju Roma, sama dengan ada banyak cara membuat sebuah aplikasi web dan banyak teknik untuk mengoptimalkan sebuah…"
tags:
 - Web Performance 
 - Challenge 
 - Progressive Web App 

image: "/posts/2018-02-13_tantangan-web-developer-untuk-membuat-aplikasi-web-bisa-digunakan-kurang-dari-5-detik/images/1.png" 
images:
 - "/posts/2018-02-13_tantangan-web-developer-untuk-membuat-aplikasi-web-bisa-digunakan-kurang-dari-5-detik/images/1.png" 
 - "/posts/2018-02-13_tantangan-web-developer-untuk-membuat-aplikasi-web-bisa-digunakan-kurang-dari-5-detik/images/2.png" 


aliases:
    - "/tantangan-web-developer-untuk-membuat-aplikasi-web-bisa-digunakan-kurang-dari-5-detik-70bb7431741d"
---

Ada banyak jalan menuju Roma, sama dengan ada banyak cara membuat sebuah aplikasi web dan banyak teknik untuk mengoptimalkan sebuah aplikasi web. Cara membuat saat ini sudah cukup banyak tutorialnya, tapi bagaimana dengan teknik mengoptimalkannya?

Tantangan ini ingin mengajak teman-teman web developer Indonesia untuk mencoba membuat sebuah aplikasi RSS reader sederhana dengan goal membuat time to interactive dibawah 5 detik di kondisi jaringan 3G yang lambat dan _mobile phone_ dengan spesifikasi menengah rata-rata.




![image](/posts/2018-02-13_tantangan-web-developer-untuk-membuat-aplikasi-web-bisa-digunakan-kurang-dari-5-detik/images/1.png)



Sebagai gambaran teknis untuk bisa mencapai 5 detik sendiri sebenarnya di kondisi jaringan 3G yang lambat (diasumsikan di 400kbps) maka kita sebenarnya cuma punya waktu sekitar **3,4 detik**. Karena sekitar **1,6 detik** itu sudah terpakai untuk waktu pemrosesan request lewat jaringan seperti DNS _query_, TCP _handshake_, atau HTTPS _handshake_. Dan dengan perhitungan 3,4 detik dengan kondisi jaringan 400ms _round trip_ atau kecepatan 400kbps, maka kita hanya punya **budget ukuran file aplikasi kita sekitar 170KB**. Kalau tidak terkompresi dengan GZIP mungkin sekitar 800KB.




![image](/posts/2018-02-13_tantangan-web-developer-untuk-membuat-aplikasi-web-bisa-digunakan-kurang-dari-5-detik/images/2.png)

Time to interactive budget



Nah terinpirasi dari tantangan yang sebelumnya sudah ada di luar seperti di [Hackernews PWA](https://hnpwa.com/) ini. Maka kita ingin mencoba membuat tantangan untuk teman-teman web developer Indonesia. Bagaimana bisa membuat sebuah aplikasi web sederhana yang bisa digunakan dalam waktu 5 detik. Nah aturan tantangannya kurang lebih sebagai berikut:

1.  Membuat sebuah aplikasi _content reader_ dengan menggunakan [_feed_ publication WWWID](https://medium.com/feed/wwwid) ini yang sudah diubah menjadi JSON sehingga bisa dikonsumsi langsung. Silakan menggunakan URL berikut untuk mengakses _feed_ JSON.
`[https://api.rss2json.com/v1/api.json?rss_url=https%3A%2F%2Fmedium.com%2Ffeed%2Fwwwid](https://api.rss2json.com/v1/api.json?rss_url=https%3A%2F%2Fmedium.com%2Ffeed%2Fwwwid)`
2.  Bebas menggunakan _library_ atau _framework_ apapun selama bisa diakses melalui _browser_ modern seperti Chrome, Firefox, Safari, Opera, dll.
3.  Aplikasi content reader ini cukup memiliki 2 halaman, yaitu halaman home dengan daftar _latest feed_ di mana pada daftar konten cukup memunculkan :
* judul artikel
* nama penulis
* _thumbnail_ artikel
* satu paragraf artikel.
* tanggal artikel di-_publish
_Dan halaman konten detail di mana sama seperti daftar konten namun memunculkan konten artikel keseluruhan, bukan hanya 1 paragraf.
4.  Feed bisa di-_filter_ menggunakan kategori, di mana kategori ini bisa diambil dari field _categories_ di tiap konten. _Feed filter_ harus punya _unique_ URL sehingga kita bisa mengakses konten terkait kategori tersebut langsung via URL misalnya `[https://my-reader.app/cat/pwa](https://my-reader.app/cat/pwa)` yang otomatis menampilkan konten PWA saja.
5.  Bisa mencapai skor Lighthouse untuk PWA dan Performance diatas 90.
6.  Melakukan _testing_ menggunakan [Webpagetest mode yang easy](https://www.webpagetest.org/easy) dan mengaktifkan Lighthouse audit pada saat melakukan test.
7.  Menuliskan bagaimana aplikasi web tersebut dikembangkan dan teknik optimasi yang digunakan seperti apa untuk mencapai skor Lighthouse tersebut.
8.  Bergabung di [group Telegram](https://t.me/joinchat/AZxMcA3CBroTKVFIQpV8JA) untuk tanya jawab dan update lebih lanjut. Bergabung di `[_https://t.me/wwwid_pwa_](https://t.me/wwwid_pwa)`
9.  Mendaftarkan aplikasi web tersebut di [**_form_ _submission_**](https://goo.gl/forms/tBfRLWgDXmIvTvr43) __ dengan mencantumkan URL web app, Github repo URL, dan Medium article URL.
10.  Update progress di Twitter dengan hashtag [#WWWIDChallenge](https://mobile.twitter.com/search?q=%23WWWIDChallenge)
11.  [Menambahkan topic](https://help.github.com/articles/classifying-your-repository-with-topics/) `wwwid` dan `wwwidchallenge` di Github repo agar muncul [di daftar repo para peserta tantangan](https://github.com/topics/wwwid).

Tantangan ini hanya sekedar untuk pembelajaran, bukan untuk berkompetisi. Dengan demikian kita bisa melihat bagaimana di setiap _framework/library_ mengoptimasi sebuah aplikasi agar dapat ditampilkan dalam 5 detik. _Update_ akan dilakukan secara bertahap di artikel ini.

### Update

1.  Menambahkan filter kategori di point 4 dan update progress di Twitter via hashtag di point 10 — 12 Feb 2018
2.  Mengganti Lighthouse audit menggunakan Webpagetest di-_point_ 6 — 15 Feb 2018
3.  Menambahkan topic di Github repo untuk membuat list di halaman Github topic di-point 11. — 15 Feb 2018
4.  Menambahkan _URL form submission_ dan menghilangkan score pada submission. Score akan dihitung automatis dengan tes Lighthouse yang tersentralisasi. — 6 Mar 2018
