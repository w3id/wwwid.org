---
title: "Yang Web Developers Harus Tahu #5"
author: "Yohan Totting"
date: 2018-02-05T02:51:56.283Z
lastmod: 2019-05-20T16:26:58+07:00

description: ""

subtitle: "Who love Monday?? Nah sudah memasuki Februari dan saatnya untuk update terbaru untuk kalian biar tetap tahu perkembangan di dunia web. Kali…"
tags:
 - Web Development 
 - Front End Development 
 - Progressive Web App 

image: "/posts/2018-02-05_yang-web-developers-harus-tahu-sharp5/images/1.gif" 
images:
 - "/posts/2018-02-05_yang-web-developers-harus-tahu-sharp5/images/1.gif" 
 - "/posts/2018-02-05_yang-web-developers-harus-tahu-sharp5/images/2.png" 
 - "/posts/2018-02-05_yang-web-developers-harus-tahu-sharp5/images/3.jpeg" 


aliases:
    - "/yang-web-developers-harus-tahu-5-24b0024c2371"
---

Who love Monday?? Nah sudah memasuki Februari dan saatnya untuk update terbaru untuk kalian biar tetap tahu perkembangan di dunia web. Kali ini bagian artikel menarik kami ubah menjadi konten menarik karena beberapa konten bukan cuma berupa tulisan tapi juga berupa video. Dan ini dia yang kalian harus tahu sebagai web developers. Have an amazing week guys!

### Berita Terbaru

[**Ranking Google Search akan terpengaruh oleh page speed**](https://webmasters.googleblog.com/2018/01/using-page-speed-in-mobile-search.html)**  
**Sebelumnya page speed sudah berpengaruh pada ranking hasil pencarian Google Search, tapi hanya di desktop. Berhubung [data menunjukkan bahwa kecepatan sebuah halaman adalah hal yang penting](https://www.thinkwithgoogle.com/marketing-resources/data-measurement/mobile-page-speed-new-industry-benchmarks/), maka per Juli 2018 search ranking pada mobile juga akan dipengaruhi oleh page speed. Jadi segera tingkatkan halaman website kalian di mobile.

[**WebAssembly code dikompilasi lebih cepat dengan streaming compiler di Firefox**](https://hacks.mozilla.org/2018/01/making-webassembly-even-faster-firefoxs-new-streaming-and-tiering-compiler/)




![image](/posts/2018-02-05_yang-web-developers-harus-tahu-sharp5/images/1.gif)

Streaming compiler WebAssembly



JavaScript merupakan salah satu faktor yang menggunakan sumber daya paling besar dalam menampilkan sebuah halaman _website_. Salah satu kelemahannya adalah JavaScript baru bisa di-_parsing_ dan dikompilasi setelah file selesai di-_download_. Dengan _streaming compiler_ pada WebAssembly, kode akan siap dijalankan karena kode sudah mulai dikompilasi dari _byte_ pertama diterima tanpa harus menunggu _byte codes_ selesai di-_download_.

[**Chrome user experieces report sudah tersedia per negara**](https://developers.google.com/web/updates/2018/01/crux)




![image](/posts/2018-02-05_yang-web-developers-harus-tahu-sharp5/images/2.png)

Query yang menampilkan data per negara



Laporan yang sebelumnya dirilis dan [bisa digunakan langsung di Big Query](https://bigquery.cloud.google.com/dataset/chrome-ux-report:all) sekarang sudah dilengkapi dengan laporan per negara termasuk Indonesia. Ini memudahkan untuk melakukan query dan melihat insight spesifik pada suatu negara.

[**Progressive Web App di Firefox 58 Quantum**](https://hacks.mozilla.org/2018/01/firefox-58-the-quantum-era-continues/)**  
**Add to homescreen yang merupakan salah satu fitur utama dari aplikasi Progressive Web App(PWA) diluncurkan di Firefox 58 bersamaan dengan deretan fitur lainnya termasuk streaming compiler di WebAssembly yang sudah dibahas di atas.

### **Konten Menarik**

[**Journey to create a web-app to load under 50KB**](https://medium.com/@tjmonsi/journey-to-create-a-web-app-to-load-under-50kb-on-first-load-creating-element-lite-bcc1452a8c6a)




![image](/posts/2018-02-05_yang-web-developers-harus-tahu-sharp5/images/3.jpeg)



Tantangan web developer saat ini adalah bagaimana membuat website bisa [tampil dan interaktif dalam 3 detik](https://medium.com/dev-channel/the-cost-of-javascript-84009f51e99e). Dan cara ini tidak mudah karena untuk bisa mencapai itu batas maksimal ukuran website adalah 50KB. Dan untuk lebih baik lagi, [harus bisa interaktif dalam 3 detik](https://www.thinkwithgoogle.com/data-gallery/detail/mobile-site-abandonment-three-second-load/) dimana batas maksimal ukuran website kita adalah 50KB. Di artikel ini, [Toni](https://medium.com/@tjmonsi) [Google Developer Expert](https://developers.google.com/experts/) of Web Technology mencoba menunjukkan bagaimana dia mencoba membuat website dengan ukuran kurang dari 50KB.

[**Payment Request API di Microsoft Edge**](https://www.youtube.com/watch?v=uccDswZXUPk)**  
**Payment Request API bisa menjadi solusi untuk kompleksitas flow pembayaran di mobile. Di video ini, Microsoft Edge menunjukkan bagaimana kalian bisa menggunakan Payment Request API di website kalian untuk mengumpulkan informasi yang dibutuhkan dalam proses checkout seperti data pengiriman dan pembayaran.

[**Tantangan buat para web developers**](https://paul.kinlan.me/challenges-for-web-developers/)**  
**Paul Kinlan, lead dari Chrome dan Web Developer Relation team di Google menuliskan tantangan apa saja yang dialami oleh para web developers di seluruh dunia. Kalau kalian web developers, mungkin frustasi yang kalian rasakan bukan cuma ada di kalian, tapi juga di web developers lainnya. Kalian tidak sendirian.

[**Search Engine Optimization di Single Page Application(SPA)**](https://medium.com/dev-channel/polymer-2-and-googlebot-2ad50c5727dd)**  
**Salah satu kekhawatiran developer pada saat ingin mengimplementasikan PWA dengan app shell architecture adalah apakah tetap bisa di-index oleh search engine. Artikel ini membahas bagaimana mengoptimalkan SPA kalian terutama di Polymer agar tetap bisa di-index oleh Google Search. Walaupun pembahasan dengan Polymer tapi secara teknis tetap bisa diaplikasikan di _framework_ lainnya.

[**Menggunakan fungsi Chrome Dev Tool secara programmatically**](https://developers.google.com/web/updates/2018/01/devtools-without-devtools)**  
**Masih terkait Puppeteers, artikel ini menunjukkan bagaimana kalian bisa menggunakan fungsi di [Chrome Dev Tool] (https://developers.google.com/web/tools/chrome-devtools/)dan membuat script yang bisa dirancang untuk menganalisa web kalian. Kalian bisa menghitung ukuran file setiap jenis assets seperti CSS, gambar, dan JavaScript, atau menganalisa CSS dan JavaScript yang tidak terpakai di sebuah halaman, dan [fungsi lainnya](https://github.com/GoogleChrome/puppeteer/tree/master/examples/).

### **Tools, Frameworks, dan Libraries**

[**Webpack 2017, a year in review**](https://medium.com/webpack/webpack-2017-a-year-in-review-9f4a760fddd4)**  
**Tahun 2017 adalah tahun di mana Webpack menjalani transisi besar menjadi produk jangka panjang. Di tulisan ini [Sean Larkin](https://medium.com/@TheLarkInn) mencoba menuliskan apa saja yang terjadi dalam setahun terakhir selama 2017. Dimulai dari pembentukan team contributor, hingga perjalanannya mencapai versi 4.

[**Puppeteers rilis versi 1.0**](https://developers.google.com/web/tools/puppeteer/)**  
**Puppeteers adalah NodeJS library yang digunakan untuk mengontrol Chrome Headless. Dan mereka baru saja merilis major version 1.0. Dengan Puppeteers 1.0 ini kalian bisa mengotomasi apa yg ingin kalian lakukan pada halaman web. Misalnya _screenshot_, _generate PDF_, _automation testing_, atau _prerender_ untuk SPA.

[**Parcel rilis versi 1.5**](https://medium.com/@devongovett/parcel-v1-5-0-released-source-maps-webassembly-rust-and-more-3a6385e43b95)**  
**Parcel, salah satu _web application bundler_ yang fokus pada kemudahan tanpa konfigurasi merilis versi terbaru 1.5 setelah 2 bulan baru merilis versi 1.0. Selain mudah, proses _bundle_-nya juga diklaim sangat cepat. Pada rilis ini salah satu yang patut diperhatikan adalah dukungan pada WebAssembly yang memungkinkan untuk menggunakan script Rust langsung di aplikasi.
