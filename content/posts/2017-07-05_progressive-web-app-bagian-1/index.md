---
title: "Progressive Web App — Bagian 1"
author: "Putu Alfred Crosby"
date: 2017-07-05T17:15:21.894Z
lastmod: 2019-05-20T16:26:12+07:00

description: ""

subtitle: "Benefit web app offline-first, and intro service worker."
tags:
 - Pwa 
 - JavaScript 

image: "/posts/2017-07-05_progressive-web-app-bagian-1/images/4.jpeg" 
images:
 - "/posts/2017-07-05_progressive-web-app-bagian-1/images/1.png" 
 - "/posts/2017-07-05_progressive-web-app-bagian-1/images/2.png" 
 - "/posts/2017-07-05_progressive-web-app-bagian-1/images/3.png" 
 - "/posts/2017-07-05_progressive-web-app-bagian-1/images/4.jpeg" 


aliases:
    - "/pengenalan-progressive-web-app-pwa-bagian-1-cac0fadbe5f4"
---

#### Benefit web app offline-first, and intro service worker.

Belakangan ini Google sedang gencar mengenalkan teknologi PWA ke perusahan-perusahaan teknologi di Asia Tenggara, khususnya di Indonesia. Pada awal bulan kemarin salah seorang staff di Google menghubungi kami dan menyarankan kami untuk menerapkan teknologi ini ke salah satu situs kami.

Pertanyaannya kenapa kita harus menerapkan PWA?

Sebelumnya kita harus tahu dulu apa itu PWA.
> PWA adalah sebuah aplikasi web yang menggunakan beberapa teknologi modern yang membuat user experience seperti menggunakan Native App (Android/iOS)

Maksudnya “**_seperti menggunakan Native apps_**”?

Native Apps dapat **berjalan secara offline**, **mengirim Push Notifications**, **load** dengan **cepat**, dan **dapat dibuka melalui Home screen**. Supaya lebih jelas, yang kita bicarakan disini adalah modern web yaitu **SPA**(_Single Page Application_) menggunakan framework/library seperti VueJS, AngularJS, Polymer, Preact, React atau yang lainnya. Bagi teman-teman yang belum paham SPA disarankan untuk googling tentang SPA terlebih dahulu 😃

### The Problem

Masalah pertama adalah ketika user tidak memiliki akses internet dan akan menampilkan halaman seperti ini:




![image](/posts/2017-07-05_progressive-web-app-bagian-1/images/1.png)

Tidak ada akses internet



Namun itu bukan masalah terbesar kita, yang lebih berbahaya dari itu adalah ini:




![image](/posts/2017-07-05_progressive-web-app-bagian-1/images/2.png)

Low Signal — source: [https://thenounproject.com/term/low-signal/269791/](https://thenounproject.com/term/low-signal/269791/)



Kenapa itu menjadi masalah terbesar kita? **Karena user dengan internet yang lambat akan menunggu sangat lama dan mungkin selamanya.** Kita tidak tahu paket yang kita kirim sudah sampai server atau belum, atau mungkin jika sudah sampai bisa saja putus ditengah jalan ketika akan dikirim balik ke user (putus tanpa ada kabar 😆 #jleb).

Pernahkah kita mengalaminya?

_Mungkin sebentar lagi halaman ini akan selesai load, hmm mungkin 3 detik lagi, coba tunggu 4 detik, ternyata belum selesai juga, coba tunggu 10 detik lagi ternyata belum selesai._




![image](/posts/2017-07-05_progressive-web-app-bagian-1/images/3.png)

User mendapatkan tampilan seperti ini ketika internet sedang lambat



Menurut data dari Google, 53% orang akan meninggalkan halaman jika memakan waktu lebih dari 3 detik untuk memuat halaman. Masalah besar bukan?

Disinilah Service Worker memberi jawaban untuk masalah ini, kita akan menyimpan shell (kerangka halaman) dan assets (CSS &amp; JS) di Cache Storage yang nantinya akan ditampilkan kepada user. Jadi user tidak perlu mendownload ulang terus-menerus setiap reload halaman, dan bahkan bisa ditampilkan ketika user sedang offline sehingga user tidak perlu melihat gambar dinosaurus seperti diatas.

### The Benefit

Karena disimpan di dalam Cache Storage jadi user hanya perlu mendownload halaman kita sekali saja dan setelah itu user tidak perlu lagi untuk mendownload shell dan assets kita setiap user membuka halaman web. Bagaimana cara kerja Service Worker? Untuk lebih jelasnya teman-teman bisa perhatikan pada gambar di bawah ini:




![image](/posts/2017-07-05_progressive-web-app-bagian-1/images/4.jpeg)

Service Worker bekerja sebagai proxy. Source: [https://vaadin.com/blog/-/blogs/14122731](https://vaadin.com/blog/-/blogs/14122731)



Secara garis besar akan saya jelaskan

1.  Kita berasumsi user belum pernah mengunjungi web kita. Ketika user melakukan request dan melewati SW(Service Worker), SW akan mengecek terlebih dahulu, apakah file sudah tersedia di dalam Cache Storage? Karena ini **pertama kalinya** user mengunjungi halaman kita, maka SW akan mengarahkan request ke web server dan SW juga akan menyimpan file yang sudah di download ke dalam Cache Storage.
2.  Kini shell &amp; assets sudah tersimpan dalam Cache Storage, untuk request selanjutnya sama seperti diatas, request akan melewati SW, dan SW akan mengecek terlebih dahulu di Cache Storage. Karena assets dan shell sudah tersedia di Cache Storage, maka SW akan otomatis mengirimkan file dari Cache Storage untuk ditampilkan ke user.

Jadi SW bertugas sebagai proxy. Sangat powerful bukan? Karena fitur ini bisa meng-hijack request, maka fitur ini **hanya dapat berjalan di HTTPS dan localhost saja.**

### Conclusion

Jadi kembali ke pertanyaan diatas, kenapa kita harus menerapkan PWA?

1.  Web kita bisa berjalan di kondisi jaringan apapun (GPRS/EDGE/3G) 😮
2.  Increase the engagement — Menggunakan Web Push Notifications API
3.  Menambah konversi — [Lihat PWA Case Studies](https://developers.google.com/web/showcase/)

Lalu apa setelah ini? Dimana tutorial nya?

Tutorial akan kita pelajari pada artikel kedua. Jadi tunggu di artikel selanjutnya ya. 😃

**Referensi**:

1.  [http://blog.ionic.io/what-is-a-progressive-web-app/](http://blog.ionic.io/what-is-a-progressive-web-app/)
2.  [https://vaadin.com/blog/-/blogs/14122731](https://vaadin.com/blog/-/blogs/14122731)
3.  [https://developers.google.com/web/progressive-web-apps/](https://developers.google.com/web/progressive-web-apps/)

### PWA — The Series Dalam Bahasa Indonesia

1.  Kalian sedang disini
2.  [Bagian 2](https://medium.com/@alfrcr/tutorial-pwa-progressive-web-app-bahasa-indonesia-627e1f6810d2)

Jika kalian rasa artikel ini bermanfaat jangan lupa dibagikan ke teman yang lain dan juga klik lambang hati ♥️ 😆
