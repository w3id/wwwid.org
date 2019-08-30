---
title: "Panduan Memulai Pengembangan Web Modern (PWA)"
author: "Yohan Totting"
date: 2018-08-27T08:29:02.623Z
lastmod: 2019-05-20T16:27:37+07:00
featured: true
description: ""

subtitle: "Panduan ini akan menjadi dasar bagaimana sebuah web modern atau biasa disebut Progressive Web App(PWA) dikembangkan. Karena sebagian besar…"
tags:
 - Progressive Web App 
 - Guides And Tutorials 
 - Web Development 
 - Front End Development 

image: "/posts/2018-08-27_panduan-memulai-pengembangan-web-modern-pwa/images/2.png" 
images:
 - "/posts/2018-08-27_panduan-memulai-pengembangan-web-modern-pwa/images/1.png" 
 - "/posts/2018-08-27_panduan-memulai-pengembangan-web-modern-pwa/images/2.png" 
 - "/posts/2018-08-27_panduan-memulai-pengembangan-web-modern-pwa/images/3.png" 
 - "/posts/2018-08-27_panduan-memulai-pengembangan-web-modern-pwa/images/4.jpeg" 


aliases:
    - "/panduan-memulai-pengembangan-web-modern-pwa-1e9d334fad14"
---

Panduan ini akan menjadi dasar bagaimana sebuah _web modern_ atau biasa disebut [_Progressive Web App_(PWA)](https://developers.google.com/web/progressive-web-apps/) dikembangkan. Karena sebagian besar permasalahan web pada saat sudah berjalan adalah arsitektur yang kurang baik serta perancangan awal yang tidak disesuaikan dengan kebutuhan pengguna. Panduan ini akan memberikan gambaran bagaimana arsitektur dan perancangan sebuah aplikasi modern web tanpa menggunakan framework apapun, namun tetap bisa diterapkan di framework apapun.

### **Kriteria Modern Web**

Untuk kebutuhan website modern yang fokus pada kebutuhan pengguna, makan kita mendefinisikan modern web sebagai berikut:

**Aman**

Menggunakan protokol HTTPS sehingga menjamin konten tidak diubah di jaringan (biasanya terinjeksi iklan oleh operator, atau script berbahaya oleh virus atau hacker). Serta proses transmisi data dari pengguna ke _server_ tidak dipindai oleh pihak yang tidak diinginkan. Misalnya proses input data kartu kredit di _website e-commerce_.

**Cepat**

Dapat dimuat dan digunakan dalam waktu 5 detik di jaringan 3G dengan spesifikasi perangkat mobile menengah.

**Stabil**

*   Dapat diakses walaupun kondisi jaringan sedang _offline_ atau sangat lambat.
*   Bisa beradaptasi dengan spesifikasi dan kondisi perangkat serta jaringan sehingga tetap nyaman digunakan walaupun diperangkat dengan spesifikasi rendah dan jaringan yang lambat.

**Membuat betah dan nyaman**

*   Tampilan yang nyaman diakses dari ukuran layar perangkat _mobile_, _tablet_, atau _desktop_.
*   Mampu memberikan respon terhadap interaksi (klik mouse atau tap) secara instant (kurang dari 200ms)
Tidak melakukan sesuatu yang menganggu kenyamanan pengguna dalam mengakses konten atau layanan.

**Terintegrasi**

*   Memberikan fungsi yang dibutuhkan layaknya sebuah aplikasi seperti notifikasi, login dengan sidik jari, dan lainnya.
*   Bisa diakses dengan mudah lewat layar utama hanya dengan menekan _icon_, tanpa harus mengetik alamat pada _browser_.
*   Memudahkan pengguna dalam membagikan konten tanpa harus _copy paste_ alamat URL konten.

Daftar lebih detail bisa dilihat di [checklist PWA ini](https://developers.google.com/web/progressive-web-apps/checklist).

### **Menentukan Arsitektur**

Berdasarkan kriteria modern web di atas, maka arsitektur akan berperan penting untuk mencapai hal di atas. Karena ada beberapa yang tidak mungkin dicapai tanpa penerapan arsitektur yang tepat. Dan arsitektur yang mendukung semua hal di atas adalah arsitektur _Application Shell_ atau biasa disebut _Single Page Application_(SPA). SPA adalah arsitektur yang memungkinkan kita berpindah halaman di web tanpa harus melakukan proses loading halaman secara keseluruhan. Pada saat pengguna berpindah halaman, maka hanya konten di tengah halaman saja yang akan diperbaharui. Sedangkan bagian _header_ yang biasa memuat _logo, menu_, dan _search bar_ biasanya tidak berubah. Terkadang elemen navigasi lainnya yang tidak berubah juga adalah _footer_(bagian bawah halaman), dan _sidebar/drawer_ (bagian samping yang biasa menjadi navigasi di perangkat _mobile_).




![image](/posts/2018-08-27_panduan-memulai-pengembangan-web-modern-pwa/images/1.png)

Single Page Application dengan aristektur application shell (sumber: [https://developers.google.com/web/fundamentals/architecture/app-shell](https://developers.google.com/web/fundamentals/architecture/app-shell))



Pilihan arsitektur SPA ini biasanya kurang familiar dengan pengembang PHP, Python, Ruby atau server side scripting lainnya karena biasanya pengembang biasanya secara _default_ akan menggunakan arsitektur _Multi Page Application_(MPA). MPA adalah arsitektur di mana aplikasi web berpindah halaman dengan melakukan loading halaman keseluruhan termasuk _header_, _footer_, dan _sidebar_ halaman _web_ walaupun bagian tersebut masih sama. Kekurangan arsitektur ini adalah pengguna akan melihat jeda perpindahan halaman, karena _browser_ akan menimpa keseluruhan halaman yang tampil dengan halaman baru. Berbeda dengan arsitektur SPA yang hanya mengganti bagian konten tengah saja.

Karena itu, bagi pengembang yang menggunakan bahasa pemrograman _server side scripting_, pertimbangkan untuk memisahkan arsitektur aplikasi di mana aplikasi _server side script_ berfungsi untuk mengirimkan data atau hanya untuk untuk proses _rendering_ pertama. Namun selanjutnya untuk navigasi atau perpindahan antar halaman akan ditangani oleh _client side_, atau JavaScript di halaman _web_.

Untuk memudahkan, beberapa _library/framework_ populer sebenarnya sudah menggabungkan konsep SPA dengan _server side rendering_ beberapa contohnya adalah:

*   [Nuxt](https://nuxtjs.org/) untuk pengguna [VueJS](https://vuejs.org/)
*   [React DOM](https://reactjs.org/docs/react-dom-server.html) untuk pengguna [ReactJS](https://reactjs.org/)
*   Kombinasi antara [Laravel](https://laravel.com/) + [Laravel Mix] (https://laravel.com/docs/5.6/mix)+ [VueJS](https://vuejs.org/)

Terkait bagaimana penggunaan setiap framework, silakan mengecek dokumentasi masing-masing.

### **Persiapan**

Sebelum memulai pengembangan ada baiknya menyiapkan beberapa hal penting yang akan memudahkan pengembang.

**Tools Pengembangan**

Tool pengembangan tentu menjadi pilihan yang akan memudahkan dalam proses pengembangan. Di panduan ini tidak akan membahas terlalu jauh, karena biasanya setiap pilihan framework sudah memiliki _tool_ pengembangan sendiri. Dan setiap pengembang juga sudah memiliki _code editor_ favorit. Tapi beberapa hal yang mungkin bisa membantu dalam pengembangan web modern adalah:

*   _Web server_ yang mendukung SPA, dapat membuka aplikasi SPA tanpa harus mengakses _root_. Biasanya ini sama dengan penyetelan _friendly_ URL di MPA, dimana semua URL di _website_ tersebut disetel untuk mengarah ke _file index_ bila file tidak ditemukan.
*   _Browser debugging tool_ yang mendukung _responsive layout_, _debugging service worker_, _cache storage_, _performance_, _network_, dan lainnya. [Chrome Dev Tools](https://developers.google.com/web/tools/chrome-devtools/) bisa menjadi pilihan awal bila belum memiliki preferensi.



![image](/posts/2018-08-27_panduan-memulai-pengembangan-web-modern-pwa/images/2.png)

Tampilan proses debugging yang secara default selalu menampilkan mobile layout di Chrome Dev Tools.



*   _Build tools_ yang digunakan untuk mem-_bundle_ semua aset aplikasi web untuk siap di-_deploy_ ke server. _Build tools_ yang popular saat ini adalah Webpack dan Parcel. Lebih jauh terkait _build tools_ akan dibahas terpisah.

**Target Dasar Pengguna**

Tentukan kira-kira target dasar pengguna _website_ yang akan dibuat seperti apa. Dalam menentukan kita bisa melakukan pengecekan pada beberapa referensi dan yang perlu diperhatikan dari sisi pengguna adalah:

*   Jenis perangkat yang digunakan (_mobile, tablet,_ atau _desktop_).
*   Spesifikasi perangkat (spesifikasi rendah, menengah, atau tinggi).
*   Kondisi jaringan (Wifi, 4G, 3G, atau 2G) termasuk apakah kemungkinan _offline_ cukup tinggi, misalnya akan digunakan di gunung atau di hutan.
*   Jenis atau versi _browser_ yang digunakan oleh pengguna, apakah pengguna menggunakan _modern browsers_(Chrome, Firefox, Safari, Edge,Opera, dan lain-lain) yang selalu diperbaharui, atau tidak.

Terkadang kita bisa mengasumsikan faktor-faktor di atas berdasarkan jenis websitenya. Sebagai contoh, bila sifatnya adalah profil perusahaan maka kita berasumsi perangkat _mobile, tablet_, dan _desktop_ spesifikasi menengah dengan jaringan 3G. Yang sering jadi kesalahan adalah beberapa pengembang fokus pada desktop pada saat mengembangkan website profil perusahaan karena pada saat presentasi ke klien, memang menggunakan laptop dan wifi. Tapi pada saat klien ingin menunjukkan ke partner pada saat ketemu di _event_, mereka menggunakan perangkat _mobile_ di jaringan 3G yang padat pengguna, dan klien tidak bisa menunjukkan profil perusahaannya karena _layout_ berantakan di _mobile_, atau terlalu berat karena di _mobile_, atau bahkan tidak tampil karena di jaringan 3G padat dan lambat. Jadi pastikan kita memahami kapan aplikasi web akan digunakan, perangkat apa, dan di jaringan apa.

**Tentukan Sumber Daya Kritis**

[Sumber daya kritis](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/) di aplikasi web adalah file yang dibutuhkan oleh sebuah web untuk dapat menampilkan sesuatu di layar dengan baik. Bila file ini tidak terunduh semua, maka browser tidak akan dapat menampilkan sesuatu di layar. File ini biasanya terdiri dari:

*   HTML dokumen halaman yang akan ditampilkan
*   CSS file yang digunakan untuk layout halaman
*   JavaScript file yang digunakan untuk menampilkan halaman. Ini biasanya merupakan library UI yang menggunakan JavaScript. Misalnya jQuery UI,
*   Fonts, bila tidak diatur dengan benar bisa jadi font membuat konten teks tidak ditampilkan sampai font selesai diunduh.

Biasanya bila kita menggunakan arsitektur Single Page App(SPA), hal ini biasanya diatur oleh build tool yang kita gunakan misalkan Webpack, atau Parcel. Bila kita tidak menggunakan arsitektur SPA dan memasukkan manual file JavaScript, CSS, dan fonts ke halaman HTML kita maka akan diperlukan proses optimasi yang sebaiknya:

*   Ukuran file sekecil mungkin. Ini bisa dicapai dengan membuang spasi, komentar, kode tidak terpakai, dan kompresi _file_.
*   Jumlah file sesedikit mungkin karena ini berhubungan dengan jumlah request. Ini biasanya dibantu build tool untuk mengabungkan aset statis kita ke dalam satu file yang sama.
*   _Round trip_ atau proses bolak balik meminta ke _server_ seminimal mungkin, ini biasanya terjadi bila ada CSS atau JavaScript yang memanggil atau memasukkan _file_ lain. Contohnya hindari penggunaan import di file CSS. Usahakan hanya terjadi satu round trip dimana file HTML yang menjadi referensi file mana saja yang dibutuhkan untuk menampilkan sesuatu di layar.

Jadi di awal pengembangan, silakan tentukan berapa file kritis maksimal dan berapa total ukuran dari file kritis ini. Dan ini bisa dimasukkan dalam anggaran kecepatan yang menjadi topik berikutnya.

**Tentukan Anggaran Kecepatan**

Kecepatan tampil sebuah _website_ sangat bergantung terhadap seberapa besar ukuran _file_ yang dimuat oleh _browser_, spesifikasi perangkat, dan kecepatan jaringan. Karena itu sebelum kita bisa menentukan anggaran kecepatan website, kita harus menentukan target dasar pengguna seperti yang dijelaskan di atas.

Kalau kita menetapkan target kecepatan tampil dan bisa digunakan aplikasi _web_ kita pada 5 detik, maka untuk perangkat Android harga 2 jutaan, dan jaringan 3G yang berkisar 400 Kbps perhitungannya akan sebagai berikut:

1,6 detik akan digunakan untuk _DNS lookup_ dan _TLS handshaking_.

Sisa 3,4 detik untuk melakukan _download_ dan pemrosesan keseluruhan file. Dan kalau kita kalkulasi maka di jaringan 400Kbps

400 Kbps = 50KB/s

50KB/s * 3,4 = **170KB**

Dengan perhitungan di atas, kita hanya punya anggaran kecepatan sebesar **170KB ukuran _file_ yang bisa dikirim**. Ini belum termasuk waktu pemrosesan, karena setiap _file_ seperti HTML, CSS, JS tentunya setelah di-_download_ perlu di-_parsing_ dan di-_compile_. Untungnya _file_ seperti HTML, CSS, dan JS bisa dikompres. **Sehingga ukuran 170KB kalau tidak dikompres akan berkisar 0,7 MB atau sekitar 700KB.**


![image](/posts/2018-08-27_panduan-memulai-pengembangan-web-modern-pwa/images/3.png)

Gambaran anggaran kecepatan untuk 170KB menggunakan framework (sumber: [https://medium.com/dev-channel/the-cost-of-javascript-84009f51e99e](https://medium.com/dev-channel/the-cost-of-javascript-84009f51e99e))



Jadi usahakan dalam membuat aplikasi web yang cepat bila ingin ditampilkan dalam 5 detik, maka hasil build untuk di-_deploy_ ke _server_ maksimal total ukurannya adalah 700KB. Coba kita lihat beberapa perbandingan ukuran file _default_ bila kita menggunakan _library_ atau _framework_. Di Indonesia, _library_ [Bootstrap](https://getbootstrap.com/) adalah salah satu _library_ populer terutama di pengembang PHP. Bila kita menggunakan Bootstrap dalam website kita maka kurang lebih anggaran kecepatan kita menjadi:

**Bootstrap CSS dan JavaScript**

CSS 21KB tanpa dikompres menjadi 138KB

JS 20KB tanpa dikompres menjadi 69KB

Total 41KB tanpa dikompres menjadi **207KB**

Kalau cuma menggunakan CSS dan JS files dari Bootstrap kita sudah menghabiskan 200KB dari total 700KB. Sehingga sisa yang bisa kita gunakan adalah sekitar 500KB.

Lalu kita butuh jQuery karena beberapa plugin atau themes Bootstrap bergantung pada jQuery.

jQuery v3 30KB tanpa dikompres menjadi 84KB

Sisa anggaran kecepatan 500–84 = **416KB**.

Nah dengan demikian bila kita menggunakan library Bootstrap dan jQuery maka sisa ukuran file yang bisa kita gunakan pada load awal aplikasi kita pada saat pertama kali dibuka adalah 416KB saja. Dan ini mungkin akan kombinasi antara HTML, fonts, gambar, serta library lainnya yang mungkin kita gunakan seperti corousel, dialog window, dan lainnya.

**Dengan atau Tanpa _Build Tools_**

Untuk bisa membuat kode yang kita bikin bisa teroptimasi seperti kode yang lebih kecil, dan hanya memuat kode yang dipakai saja di dalam aplikasi bila kita menggunakan _library_ maka kita memerlukan _tool_ untuk membantu kita. Pertanyaannya apakah kita ingin menggunakan _build tools_ atau hanya ingin membuat ukuran _file_ lebih kecil?

Bila kita tidak ingin terlalu kompleks, pilihannya bisa hanya sekedar melakukan _minify_ pada _file_ kita. Atau bahkan kalau kita tidak ingin melakukan _minify_, pastikan kita memasang _gzip compression_ di _web server_ kita agar _response web server_ akan selalu terkompresi.

Namun bila ingin lebih optimal, maka kita memerlukan _build tools_ seperti [Webpack](https://webpack.js.org/) atau [Parcel](https://parceljs.org/). _Build tools_ bisa membantu kita untuk melakukan optimasi kode kita seperti:

*   _minify_ kode dengan membuang kode yang tidak perlu seperti space dan komentar.
*   _tree shaking_, atau membuang kode yang tidak terpakai dalam aplikasi kita. Ini berguna bila kita menggunakan library dalam aplikasi kita.
*   _code spliting_, atau memisahkan kode kita berdasarkan halaman web sehingga kode yang dimuat di halaman tersebut hanyalah kode yang terpakai di halaman tersebut.
*   _code transform_, melakukan transformasi kode kita agar bisa berjalan di versi browser yang kita targetkan.

Webpack adalah _build tool_ paling populer karena muncul sebelum Parcel. Parcel sendiri mulai populer karena kemudahan penggunaannya yang mengusung _zero configuratio_n, dalam artian bisa langsung digunakan tanpa konfigurasi. Beberapa hal yang perlu disiapkan pada saat kita memasang _build tools_ sebelum memulai pengembangan adalah:

*   Atur _build tools_ agar sesuai dengan anggaran kecepatan yang sudah kita set sebelumnya. Sebagai contoh adalah total ukuran aplikasi kita setelah di-build adalah 170KB sesuai yang kita jabarkan di anggaran kecepatan kita sebelumnya. Kalau kalian menggunakan Webpack, kalian bisa melakukan konfigurasi anggaran kecepatan kalian seperti dijelaskan di [dokumentasi Webpack](https://webpack.js.org/configuration/performance/) ini. Untuk _tool_ lain, bila tidak memiliki pengaturan untuk anggaran kecepatan, bisa mengecek dengan _manual_ setiap _build_ pastikan agar hasil _build_ tidak melebihi ukuran maksimal yang sudah diset di anggaran kecepatan.

![image](/posts/2018-08-27_panduan-memulai-pengembangan-web-modern-pwa/images/4.jpeg)

Warning bila hasil build melebihi maksimal anggaran kecepatan pada Webpack (sumber: [https://medium.com/webpack/webpack-performance-budgets-13d4880fbf6d](https://medium.com/webpack/webpack-performance-budgets-13d4880fbf6d))



*   Tentukan [target build](https://webpack.js.org/concepts/targets/) kita untuk JavaScript versi berapa, apakah ES5 atau ES6. Atau mungkin sesuai versi browser, misalnya 2 versi terakhir dari browser modern. Saya biasanya membuat 2 target build. Satu untuk versi yang bisa jalan di search engine crawler(Googlebot menggunakan Chrome versi 41), dan satu untuk 2 versi terakhir browser.

### **Kesimpulan**

Dalam mempersiapkan pengembangan web, tentunya kita harus sesuai dengan target pengguna kita. Sehingga kita bisa merancang aplikasi web kita sesuai dengan kondisi pengguna. Sehingga pengguna bisa mengakses dan menggunakan aplikasi web kita dalam kondisi apapun. Dan untuk memudahkan kita dalam proses pengembangan kedepannya maka sangat penting untuk memperhatikan pemilihan arsitektur, dan anggaran kecepatan dalam aplikasi web kita. Karena mengubah 2 hal ini di dalam aplikasi web kita bisa dibilang akan sangat rumit dan terkadang memaksa pengembang untuk memulai pengembangan web dari awal lagi karena tidak dapat memenuhi kebutuhan penggunaannya.
