---
title: "Membuat WordPress Tampil dan Bisa Digunakan Dalam 5 Detik"
author: "Yohan Totting"
date: 2017-11-14T11:34:40.118Z
lastmod: 2019-05-20T16:26:28+07:00

description: ""

subtitle: "Web yang modern saat ini mencoba menaikkan standar kecepatan tampil di layar yang rata-rata 19 detik di 3G menjadi 5 detik atau kurang…"
tags:
 - WordPress 
 - Progressive Web App 
 - Web Performance 

image: "/posts/2017-11-14_membuat-wordpress-tampil-dan-bisa-digunakan-dalam-5-detik/images/1.png" 
images:
 - "/posts/2017-11-14_membuat-wordpress-tampil-dan-bisa-digunakan-dalam-5-detik/images/1.png" 
 - "/posts/2017-11-14_membuat-wordpress-tampil-dan-bisa-digunakan-dalam-5-detik/images/2.png" 
 - "/posts/2017-11-14_membuat-wordpress-tampil-dan-bisa-digunakan-dalam-5-detik/images/3.png" 
 - "/posts/2017-11-14_membuat-wordpress-tampil-dan-bisa-digunakan-dalam-5-detik/images/4.png" 
 - "/posts/2017-11-14_membuat-wordpress-tampil-dan-bisa-digunakan-dalam-5-detik/images/5.png" 
 - "/posts/2017-11-14_membuat-wordpress-tampil-dan-bisa-digunakan-dalam-5-detik/images/6.gif" 
 - "/posts/2017-11-14_membuat-wordpress-tampil-dan-bisa-digunakan-dalam-5-detik/images/7.png" 


aliases:
    - "/membuat-wordpress-tampil-dan-bisa-digunakan-dalam-5-detik-6b8b0f0e8ff6"
---

![image](/posts/2017-11-14_membuat-wordpress-tampil-dan-bisa-digunakan-dalam-5-detik/images/1.png)

TwentySeventeen — WordPress Default Theme



Web yang modern saat ini mencoba menaikkan standar kecepatan tampil di layar yang rata-rata 19 detik di 3G menjadi 5 detik atau kurang. Dengan demikian potensi kehilangan user yang tidak ingin menunggu lebih dari 3 detik bisa dihindari.

WordPress adalah CMS paling populer di dunia dengan angka penggunaan sekitar 24% dari semua website yang ada di internet. Dan karena WordPress dikembangkan sejak lama, maka metode pengembangan web dengan WordPress secara default belum cukup optimal untuk kondisi jaringan _cellular_ yang masih sebagian besar di 2G dan spesifikasi rendah dari sebagian besar smart phone yang digunakan.

Bila kalian memasang WordPress secara default dia menggunakan _template_ Twentyseventeen bawaan dimana bila diaudit dengan tool [Lighthouse](https://developers.google.com/web/tools/lighthouse/) maka hasilnya adalah sebagai berikut.




![image](/posts/2017-11-14_membuat-wordpress-tampil-dan-bisa-digunakan-dalam-5-detik/images/2.png)



### Mengoptimalkan [Critical Rendering Path](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/)

Dan bila dianalisa lebih lanjut penyebab _loading_ lebih dari 5 detik tersebut karena banyaknya [_critical requests_](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/analyzing-crp) yang dibutuhkan untuk menampilkan _website_ WordPress tersebut.




![image](/posts/2017-11-14_membuat-wordpress-tampil-dan-bisa-digunakan-dalam-5-detik/images/3.png)



Padahal kalau melihat list di-atas, untuk sekedar menampilkan website tersebut harusnya cukup menggunakan _HTML document_ awal dan CSS untuk layout. File Javascript lainnya cuma digunakan untuk berinteraksi, yaitu pada saat _website_ sudah ditampilkan.

Merujuk dari hasil audit Lighthouse di atas menunjukan _first meaningfull paint_ adalah 6,7 detik, penyebabnya adalah _fonts_, _scripts_ dan CSS files yang di-_load_ di halaman WordPress tersebut memblok parsing HTML yang ada di-halaman WordPress sehingga butuh waktu lama browser bisa menampilkan halaman karena harus menunggu semua fonts, scripts dan css files selesai dipanggil dan di-_parsing_. Padahal _fonts_ dan _scripts_ tidak terlalu berpengaruh terhadap _layout_ halaman.

Untuk itu, saya mencoba untuk membuat _loading_ _fonts_, Javascripts, dan CSS file tersebut tidak mem-block proses rendering halaman. Pada Javascripts file, solusinya cukup mudah, cukup dengan menambahkan _attribute async_ atau _defer_ pada Javascripts _file tags_ tersebut.




Yang perlu diperhatikan di sini adalah _async defer_ membuat file tidak digaransi bisa di-_load_ secara berurutan, sehingga Javascript file yang butuh _library_ lain di-_load_ sebelumnya ada kemungkinan akan bermasalah karena file tersebut selesai di-_load_ sebelum file yang dibutuhkan selesai di-load. Salah satu contohnya adalah jQuery _library_ yang banyak dibutuhkan oleh JQuery _plugins_ lainnya.

Setelah mencoba menghilangkan _scripts_ dan _custom fonts loading_ di tema dari yang tadinya total 8 _critical request_, turun menjadi cuma 1 _critical request_. WordPress hasil audit Lighthouse naik hampir 2 kali lipat. Dan _first meaningful paint_ bahkan turun dari 6,7 detik menjadi 1,8 detik atau menghemat 4,9 detik.




![image](/posts/2017-11-14_membuat-wordpress-tampil-dan-bisa-digunakan-dalam-5-detik/images/4.png)

Critical request turun dari 8 jadi 1





![image](/posts/2017-11-14_membuat-wordpress-tampil-dan-bisa-digunakan-dalam-5-detik/images/5.png)

Hasil setelah menghapus scripts dan CSS files dari critical render assets



### Membuat Gambar Ditampilkan Setelah Selesai Di-render

Yang berikutnya dari hasil audit Lighthouse, yang disarankan adalah bagaimana gambar-gambar yang ukurannya terlalu besar, jumlah yang cukup banyak, dan di-_load_ walaupun berada di luar tampilan layar. Solusinya adalah bagaimana untuk menampilkan gambar-gambar tersebut setelah halaman selesai di-_load_ terutama untuk gambar yang tidak muncul di layar pada saat pertama kali di-_load_.

Teknik yang biasa dilakukan adalah _lazy load_, di mana _attribute src_ yang memuat lokasi file gambar di _server_ diganti dengan _thumbnail_ kecil yang kadang dibuat _blur_ dengan format _base64 string_. Format _string_ membuat gambar bisa di-_embed_ langsung di halaman HTML tanpa perlu request terpisah. Yang perlu dipastikan adalah ukuran _base64_ ini cukup kecil sehingga tidak membuat file HTML kita menjadi terlalu besar. Dan lokasi file gambar sebenarnya disimpan di attribute data-src sebagai referensi. Contoh berikut adalah bagaimana mem-_filter_ tag `&lt;img&gt;` dan mengganti _attribute_ `src` dengan `data-lazy-src` lalu menggunakan 1 _pixel base64_ image warna abu-abu sebagai gambar sementara.




Hasil `img` tag yang sudah di-filter seperti berikut di mana yang ditampilkan di awal adalah _image_ gif dengan 1 _pixel_ warna abu-abu.

Lalu tentunya setelah halaman selesai di-_render_, kita masih perlu untuk mengubah kembali _tag_ `img` tersebut ke gambar aslinya. Dan untuk itu diperlukan Javascript file yang akan mengembalikan _attribute_ `src` yang sebenarnya dari `data-lazy-src` .


Menampilkan gambar dengan Intersection Observer API



Dari Javascript di-atas bisa dilihat setelah halaman selesai di-_render_ baru kita melakukan perubahan gambar dengan mengubah _attribute_ `src` menggunakan lokasi gambar sebenarnya yang ada di `data-lazy-src`. Tapi perubahan itu tidak langsung, melainkan dengan mengecek terlebih dahulu apakah gambar tersebut tampil di layar atau tidak. Karena terkadang gambar masih berada di bawah dan perlu _scrolling_ terlebih dahulu agar muncul di layar. Untuk itu kita menggunakan [_Intersection Observer API_] (https://developer.mozilla.org/en-US/docs/Web/API/Intersection_Observer_API)untuk membuat tiap gambar hanya akan ditampilkan bila sudah mendekati layar pada saat di-_scrolling_.

### Intersection Observer API




![image](/posts/2017-11-14_membuat-wordpress-tampil-dan-bisa-digunakan-dalam-5-detik/images/6.gif)

Intersection Observer dengan threshold



Dengan [_Intersection Observer API_](https://developer.mozilla.org/en-US/docs/Web/API/Intersection_Observer_API), kita bisa mengecek bila suatu elemen tampil di layar seperti contoh berikut. Pada kasus di atas, kita menggunakan _threshold_ 50 _pixel_ sehingga bila halaman di-_scrolling_ dan posisi atas gambar berjarak 50 pixel dari posisi bawah layar maka gambar langsung ditampilkan pada layar dengan mengembalikan _attribute_ `src` ke lokasi gambar yang sebenarnya. Ini juga bisa berguna bila kita ingin melakukan _lazy loading_ pada bagian komentar di WordPress.

### Hasil Test Terakhir

Setelah melakukan optimasi pada critical rendering parts dan _images loading_ berikut hasil akhir audit Lighthouse pada _performance_ website WordPress kita.




![image](/posts/2017-11-14_membuat-wordpress-tampil-dan-bisa-digunakan-dalam-5-detik/images/7.png)

Audit Final Lighthouse



Dari hasil di atas bisa dilihat bahwa dengan melakukan dua optimasi saja di _critical rendering path_ dan _lazy_ _loading_ gambar maka kita bisa menaikkan nilai audit [Lighthouse](https://developers.google.com/web/tools/lighthouse/) kita dari **49** menjadi **95**, _first meaningful paint_ di **1,4 detik**, serta _time to interactive_ menjadi **3 detik**. Seperti judul di atas, bagaimana kita bisa membuat WordPress bisa ditampilkan kurang dari 5 detik.Source code untuk theme Twentyseventeen yang sudah dimodifikasi bisa diakses di [**repo Github ini**](https://github.com/tyohan/twentyseventeen-pwa).
