---
title: "JavaScript, Sosial Media, dan SEO"
author: "Pradita Utama"
date: 2018-07-20T19:37:23.169Z
lastmod: 2019-05-20T16:27:28+07:00
featured: true
description: ""

subtitle: "Tren membangun website menggunakan framework dan library JavaScript saat ini sedang tinggi-tingginya. Bahkan perkembangan framework dan…"
tags:
 - Front End Development 
 - Prerender 
 - SEO 
 - Javascript Tips 

image: "/posts/2018-07-20_javascript-sosial-media-dan-seo/images/7.png" 
images:
 - "/posts/2018-07-20_javascript-sosial-media-dan-seo/images/1.png" 
 - "/posts/2018-07-20_javascript-sosial-media-dan-seo/images/2.png" 
 - "/posts/2018-07-20_javascript-sosial-media-dan-seo/images/3.png" 
 - "/posts/2018-07-20_javascript-sosial-media-dan-seo/images/4.png" 
 - "/posts/2018-07-20_javascript-sosial-media-dan-seo/images/5.png" 
 - "/posts/2018-07-20_javascript-sosial-media-dan-seo/images/6.png" 
 - "/posts/2018-07-20_javascript-sosial-media-dan-seo/images/7.png" 
 - "/posts/2018-07-20_javascript-sosial-media-dan-seo/images/8.png" 
 - "/posts/2018-07-20_javascript-sosial-media-dan-seo/images/9.png" 
 - "/posts/2018-07-20_javascript-sosial-media-dan-seo/images/10.png" 


aliases:
    - "/javascript-sosial-media-dan-seo-d9c4940e60fd"
---

Tren membangun website menggunakan framework dan library JavaScript saat ini sedang tinggi-tingginya. Bahkan perkembangan framework dan library JavaScript sangat cepat sekali. Periode 2000an awal website menggunakan JavaScript paling sering untuk validasi form atau hal yang fancy. Kemudian JavaScript digunakan untuk membuat seluruh halaman website karena kemudahan dari framework dan library yang tersedia.

Kalau melihat grafik dibawah ini terlihat framework dan library apa yang popular di frontend engineers.


![image](/posts/2018-07-20_javascript-sosial-media-dan-seo/images/1.png)

diambil dari [https://hackernoon.com/the-status-of-javascript-libraries-frameworks-2018-beyond-3a5a7cae7513](https://hackernoon.com/the-status-of-javascript-libraries-frameworks-2018-beyond-3a5a7cae7513)



Jadi apa hubungan antara JavaScript, Sosial Media, dan SEO. Ada mitos begini
> website yang dibangun penuh menggunakan JavaScript (ReactJS, Vue, Angular) tidak akan bisa dibaca oleh bot mesin pencari dan efeknya akan sangat jelek di SEO score-nya.

Sedangkan SEO kadang masih sangat dibutuhkan untuk suatu produk dan merek mendapatkan [leads](https://en.wikipedia.org/wiki/Lead_generation). Leads can become customers. Customers bisa menjadi revenue. Ya walau leads bisa datang dari banyak channel, tapi sekarang siapa sih yang tidak menggunakan mesin pencari?

Layanan sosial media juga kesulitan untuk membaca halaman website yang dibuat penuh menggunakan JavaScript.

Jawabannya **ya** dan **tidak**.

### **Sosial Media**

Suka tidak suka, Facebook bisa jadi masih menjadi salah satu leads generator terbanyak di Indonesia. Karena Indonesia adalah pengguna Facebook paling banyak nomor 4 di bumi menurut artikel [ini](http://www.thejakartapost.com/life/2018/03/04/indonesia-fourth-highest-number-of-facebook-users-in-the-world.html). Pemasaran menggunakan Facebook sepertinya masih sangat efektif, seefektifnya persebaran hoaks di Indonesia.

Apakah Facebook bisa membaca website yang dibangun menggunakan JavaScript?

Sayang sekali **tidak bisa**. Jika ada sebuah website dibuat menggunakan ReactJS dan dibagikan tautannya di Facebook, maka Facebook tidak akan bisa membaca metadata halaman tersebut.

Kita buktikan. Website [Tech in Asia Indonesia](https://id.techinasia.com) dibuat seluruhnya menggunakan ReactJS dan jika tertarik teknologi apa saja yang digunakan ada di artikel [ini](https://id.techinasia.com/teknologi-web-tech-in-asia-indonesia) tulisan dari [Pramesti Hatta K.](https://medium.com/u/ef69225df6f0)

Note: Website TIA ID works well di seluruh search engine dan sosial media. Khusus untuk tulisan ini, saya sengaja mengubah konfigurasi :)

Hasil ketika dibagikan di Facebook seperti gambar dibawah. Semua meta dan title tidak bisa dibaca oleh Facebook. Tidak hanya ReactJS, ternyata Facebook memang belum bisa membaca halaman JavaScript.




![image](/posts/2018-07-20_javascript-sosial-media-dan-seo/images/2.png)



Bandingkan dengan gambar dibawah. Seluruh meta dan title, bahkan gambar bisa dibaca oleh Facebook. Ini tautan yang sama dan konten yang sama.




![image](/posts/2018-07-20_javascript-sosial-media-dan-seo/images/3.png)



### Bot Search Engine

Oke, search engine paling populer di bumi adalah Google. Google punya spider bot untuk crawl ke website kita. Jaman dahulu kala ketika website masih menggunakan file HTML biasa, Google dengan senang hati dan bahagia menjelajah website kita dan extract informasi di halaman tertentu untuk keperluan pencarian pengguna lain. No problem, as simple as Google bot datang ke URL, kemudian baca, dan selesai. Anggap bot tersebut pengguna biasa yang mengunjungi website kita, hanya saja bot tersebut memperkenalkan diri sebagai ‘Googlebot/2.1’.

Itu jika halamannya murni HTML.

Ketika tulisan ini dibuat, Google Bot menggunakan browser Chrome 41. Seharusnya Chrome 41 sudah bisa membaca halaman JavaScript. Ada tools dari Google untuk melihat dari sudut pandang Google Bot. Hasilnya begini jika halaman tersebut semuanya JavaScript.




![image](/posts/2018-07-20_javascript-sosial-media-dan-seo/images/4.png)



Ternyata Google bisa baca JavaScript!

Bagaimana dengan search engine lainnya? Jika SEO bukan hal utama, ya sudah biarkan tidak usah repot. Tapi jika SEO yang utama bagaimana?

### Solusi

#### **Server-Side Rendering**

Jika ada kasus di atas dan kita bicara kepada frontend developer muda dan trendy, jawabannya pasti **Server-Side Rendering** atau SSR**.** Apa itu SSR? yaitu seluruh request halaman akan dirender menjadi HTML biasa di server kemudian dikirimkan ke client (browser) sudah dalam bentuk HTML.

Semua user senang dan bahagia. Tidak ada lagi masalah. Masalah utama hanya mengubah website production yang sudah terlanjur dibuat menjadi SSR. Gak terlalu sulit kok, tapi juga gak mudah. Good luck! /S

Teknik SSR ada banyak di internet, tidak akan saya bahas disini.

#### **Prerender**

Perhatikan gambar dibawah, mirip dengan SSR. Tapi berbeda karena prerender lebih bertujuan menyajikan HTML statis ke browser dan menghapus JavaScript di halaman tersebut. Misalnya ada suatu website dibuat menggunakan ReactJS dan pada menu ada fitur dropdown menggunakan javascript. Di prerender, menu tersebut tidak akan bisa berfungsi, tapi seluruh konten website sudah menjadi HTML.




![image](/posts/2018-07-20_javascript-sosial-media-dan-seo/images/5.png)

diambil dari prerender.io



Contoh live, silakan buka dan view source halaman berikut ini [http://rendeer.techinasia.com/https://id.techinasia.com/apple-pay-cara-baru-transaksi-pembayaran](http://rendeer.techinasia.com/https://id.techinasia.com/apple-pay-cara-baru-transaksi-pembayaran)

Seluruh halaman menjadi HTML.

Oh iya, **Rendeer** adalah solusi prerender yang dibuat oleh Engineering Tech in Asia dan kami gunakan di website kami.




![image](/posts/2018-07-20_javascript-sosial-media-dan-seo/images/6.png)

hasil view source prerender



Jika kita buka dan view souce halaman [https://id.techinasia.com/apple-pay-cara-baru-transaksi-pembayaran](https://id.techinasia.com/apple-pay-cara-baru-transaksi-pembayaran)

Terlihat masih halaman ReactJS




![image](/posts/2018-07-20_javascript-sosial-media-dan-seo/images/7.png)

Hasil view source tanpa prerender



Yang dibutuhkan oleh bot mesin pencari dan sosial media adalah halaman yang sudah dalam bentuk HTML. Prerender bisa kita buat sendiri atau memakai layanan pihak ketiga dan biasanya berbayar.

Kita bisa membuat konfigurasi prerender seperti ini, ini hanya pseudo code saja. Logikanya seperti dibawah ini.

REQUEST(https://abc/def)  
PRERENDER ← [http://0.0.0.0/](http://0.0.0.0/)  
IF IS_BOT(USER) THEN  
RETURN PRERENDER + [https://abc/def](https://abc/def)  
/* tampilkan halaman hasil dari server prerender */  
ELSE  
RETURN [https://abc/def](https://abc/def)   
/* kasih halaman asli (ReactJS, Vue, Angular, dsb) */  
END IF

Jika menggunakan NGINX, bisa memanfaatkan proxy_pass untuk melewatkan request URL tertentu ke format URL prerender.

Client → [https://abc/def](https://abc/def) → [http://rendeer.techinasia.com/](http://rendeer.techinasia.com/https://id.techinasia.com/apple-pay-cara-baru-transaksi-pembayaran)[https://abc/def](https://abc/def)

Sehingga client atau browser akan tetap request [https://abc/def](https://abc/def)

Tech in Asia juga ada solusi prerender sendiri dan sudah digunakan di production. Open source dan free, silakan ikut kontribusi.

[https://github.com/techinasia/rendeer](https://github.com/techinasia/rendeer)

#### **Cara ‘Blibli’**

Saya tidak tahu namanya, tapi mas [Irfan Maulana](https://medium.com/u/d09eac079a9c) ketika masih di Blibli melakukan cara ini di blibli.com, jadi ya namanya “cara blibli” :)

Trik yang dilakukan oleh Blibli ini bertujuan agar ketika tautan dibagikan di Facebook tetap muncul metadata dan title.

Tekniknya, ketika ada request dari bot Facebook maka si Facebook akan disajikan halaman sangat-sangat sederhana sekali yang hanya berisi title dan metadata yang diperlukan oleh Facebook.

Tanpa CSS dan JavaScript :D




![image](/posts/2018-07-20_javascript-sosial-media-dan-seo/images/8.png)

Hasil dibagikan di Facebook



Kok bisa? ya bisa, karena supaya bisa dibagikan di Facebook hanya dibutuhkan metadata dan title. Mari kita view source tautan [ini](https://www.blibli.com/p/samsung-gear-sport-smartwatch-blue-o/ps--SAO-60034-00045) menggunakan user agent Facebook ‘facebookexternalhit/1.1’

Saya menggunakan extension User Agent Switcher di Chrome.




![image](/posts/2018-07-20_javascript-sosial-media-dan-seo/images/9.png)

Hasil menggunakan user agent Facebook. Tanpa CSS.





![image](/posts/2018-07-20_javascript-sosial-media-dan-seo/images/10.png)

source jika menggunakan user agent Facebook



Jadi Blibli hanya menyajikan halaman tanpa CSS, tanpa konten. Hanya metadata, judul, dan satu gambar :D

IMHO, ini salah satu cara cerdas dan efisien demi bisa dibagikan di Facebook haha.

### Kesimpulan

Jika SEO dan sosial media sharing sangat penting untuk suatu website JavaScript, ada setidaknya 3 solusi. Tidak ada solusi terbaik, karena harus disesuaikan dengan kebutuhan.
