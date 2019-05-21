---
title: "Chrome Dev Summit 2018, mana yang kalian harus coba implementasikan? ( 1 dari 2)"
author: "Yohan Totting"
date: 2018-11-30T10:30:16.827Z
lastmod: 2019-05-20T16:27:43+07:00

description: ""

subtitle: "Chrome Dev Summit(CDS) 2018 yang merupakan ajang tahunan Google Chrome untuk bertatap muka dengan para pengembang web baru saja…"
tags:
 - Chrome Dev Summit 
 - Progressive Web App 
 - Events 
 - Web Developers 
 - Front End Development 

image: "/posts/2018-11-30_chrome-dev-summit-2018-mana-yang-kalian-harus-coba-implementasikan-1-dari-2/images/1.jpeg" 
images:
 - "/posts/2018-11-30_chrome-dev-summit-2018-mana-yang-kalian-harus-coba-implementasikan-1-dari-2/images/1.jpeg" 


aliases:
    - "/chrome-dev-summit-2018-mana-yang-kalian-harus-coba-implementasikan-1-dari-2-fdb3367f6317"
---

![image](/posts/2018-11-30_chrome-dev-summit-2018-mana-yang-kalian-harus-coba-implementasikan-1-dari-2/images/1.jpeg)

Google Developer Experts Web di CDS 2018



[Chrome Dev Summit(CDS) 2018](https://developer.chrome.com/devsummit/) yang merupakan ajang tahunan Google Chrome untuk bertatap muka dengan para pengembang web baru saja diselenggarakan beberapa minggu lalu di mana _event_ selama 2 hari tersebut memberikan _insights_ seputar kondisi web saat ini, dan apa yang akan hadir di _web platform_ ke depannya. Terlalu banyak konten yang kadang malah membuat bingung pengembang web, mana yang harus saya coba gunakan terlebih dahulu. CDS sendiri diselenggarakan selama 2 hari, di mana hari pertama adalah _update_ seputar kondisi terkini _web platform_, dan hari kedua adalah apa yang akan hadir di _web platform_. Untuk tahu apa saja yang dibagikan selama 2 hari ini kalian bisa menonton _keynote_ hari pertama dan kedua.




_Day 1 keynote_





Day 2 keynote



Bila kalian masih belum merasa yakin apakah memilih web sebagai _platform_ yang digunakan dalam pengembangan produk, mungkin ada baiknya kalian menonton cerita Spotify dan Starbucks kenapa _web platform_ penting untuk menjangkau pengguna lebih banyak, dan memberikan pengalaman lebih baik bagi pengguna.




Why the web matters



### Mana yang harus saya tonton?

Tulisan ini mencoba mengelompokkan konten-konten yang mungkin relevan dengan apa yang kalian buat. Sehingga teman-teman pengembang web bisa mencoba mengimplementasikan konten tersebut dan siap pada saat teknologi tersebut sudah dirilis secara publik.

Bila kalian belum yakin apakah perlu berinvestasi di _web platform_.

Saya mencoba membuat daftar _playlist_ yang harus ditonton kalau kalian membuat salah satu dari 2 jenis _web app_ berikut:

1.  Web berbasis konten
2.  Web interaktif

### Web berbasis konten

Pengalaman pengguna merupakan kunci utama untuk semua jenis website. Tapi sebagai penyedia konten kita harus mulai dari mana? Video dari Alberto ini bisa memberikan bagaimana kita sebagai penyedia konten bisa memberikan pengalaman baik bertahap bila kita menggunakan _Content Management System_(CMS) dalam mengatur konten kita.




Progressive content management systems



Sebagai penyedia konten, biasanya indikator yang menjadi target adalah banyaknya konten yang dikonsumsi atau biasanya di _analytics tool_ dihubungkan dengan jumlah _page views_. Untuk _page views_, agar pengguna tidak pergi karena terkendala dalam mengakses konten maka ada dua hal penting yang harus diperhatikan yaitu kecepatan tampil halaman atau _loading performance_, serta transisi navigasi antar halaman.

**Bisa ditemukan** Sebelum berbicara kecepatan tampil dan navigasi, tentunya kita harus memastikan konten bisa ditemukan. Google search sebagai salah satu penyumbang trafik terbesar ke penyedia konten belum tentu bisa membaca dan mengindex konten sebuah website. Untuk itu bila kita mengembangkan website dengan teknologi terkini, harus dipastikan agar bisa dibaca oleh Googlebot dengan cara-cara yang dijelaskan di video berikut.




Making web content discoverable



**Kecepatan tampil** Kecepatan tampil pada dasarnya adalah seberapa besar ukuran _file_ yang dimuat untuk menampilkan sebuah halaman website. Namun jenis _file_ yang digunakan ada banyak jenisnya dan tingkat kepentingannya juga berbeda-beda. Video tentang kecepatan website ini mencakup 3 hal penting yang perlu diperhatikan pada saat menampilkan sebuah halaman website yaitu gambar, _font_, dan JavaScript.




Essentials for fast website



**Kecepatan navigasi** Setelah membaca sebuah konten atau masuk di _homepage_, pembaca mungkin akan berpindah ke halaman lainnya untuk membaca konten. Kecepatan navigasi atau perpindahan halaman ini juga berperan penting untuk memastikan pengguna tidak pergi karena menunggu lama. Dan salah satu cara untuk mempercepat navigasi antar halaman adalah menggunakan _service worker_. Bagaimana menggunakan _service worker_ dengan _cache_ dengan tepat agar _cache_ justru tidak memperlambat navigasi. Ada 5 hal yang perlu diperhatikan di video ini?




Caching strategy deep dive



**Tambah cepat dengan web packaging** Membuat website tampil cepat bukanlah perkara mudah, terkadang lebih mudah membuat website cepat dari awal ketimbang memperbaiki website yang lambat. AMP project mencoba menutupi gap ini dengan menggaransi website bisa cepat dengan 3 komponen penting AMP yang salah satunya adalah AMP Cache. AMP Cache yang melakukan _bundle assets_ halaman web saat ini cuma bisa digunakan di _server_ Google sehingga URL konten pada saat diakses masih menggunakan domain Google. Namun kedepannya semua website bisa bisa lebih cepat ditampilkan menggunakan _web packaging_ yang bekerja sama seperti AMP Cache. _Web packaging_ sudah bisa dicoba dan lebih detailnya bisa kalian tonton dari video berikut:




Web packaging dan portals



**Konsumsi video lebih baik** Video merupakan salah satu konten yang semakin mendominasi jaringan internet saat ini karena ukurannya yang jauh lebih besar dibandingkan konten berbasis teks atau audio. Untuk bisa lebih efisien ditransmisikan melalui internet maka dibuatlah format video baru AV1 khusus untuk web. Bukan cuma format yang ukurannya lebih kecil, tapi juga _picture in picture_ API memungkinkan kita menonton video di web secara bersamaan pada saat kita melakukan _browsing_ konten lainnya.




Building modern web media



Itulah beberapa konten [Chrome Dev Summit 2018](https://www.youtube.com/playlist?list=PLNYkxOF6rcIDjlCx1PcphPpmf43aKOAdF) yang kalian wajib tonton kalau kalian membuat website modern berbasis konten. Di seri berikutnya kita akan bagikan video mana yang perlu kalian tonton bila kalian mengembangkan aplikasi website yang lebih interaktif. Interaktif di sini adalah memerlukan input dari pengguna untuk mendapatkan output yang diinginkan. Contohnya adalah _e-commerce_, _image converter_, dan _virtual reality_.

Ingin mendengarkan langsung konten-konten di atas dari Google Developer Expert dan team Tokopedia? Kalian bisa gabung di Chrome Dev Summit Extended Jakarta hari Rabu, 5 Desember 2018. Daftar sekarang di [https://events.withgoogle.com/cds-extended-jkt-tokopedia](https://events.withgoogle.com/cds-extended-jkt-tokopedia).
