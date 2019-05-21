---
title: "Yang Web Developers Harus Tahu #7"
author: "Yohan Totting"
date: 2018-03-20T04:33:32.305Z
lastmod: 2019-05-20T16:27:14+07:00

description: ""

subtitle: "Edisi minggu pertama bulan Maret ini terlewat berhubung terlalu banyak hal lain yang harus dibereskan. Tapi semoga kalian tidak kelewat…"
tags:
 - Newsletter 
 - Front End Development 
 - Web Development 

image: "/posts/2018-03-20_yang-web-developers-harus-tahu-sharp7/images/1.png" 
images:
 - "/posts/2018-03-20_yang-web-developers-harus-tahu-sharp7/images/1.png" 
 - "/posts/2018-03-20_yang-web-developers-harus-tahu-sharp7/images/2.png" 
 - "/posts/2018-03-20_yang-web-developers-harus-tahu-sharp7/images/3.png" 
 - "/posts/2018-03-20_yang-web-developers-harus-tahu-sharp7/images/4.png" 


aliases:
    - "/yang-web-developers-harus-tahu-7-d21f5495a303"
---

Edisi minggu pertama bulan Maret ini terlewat berhubung terlalu banyak hal lain yang harus dibereskan. Tapi semoga kalian tidak kelewat beberapa konten menarik seputar web development. Untuk melengkapi bacaan kalian, silakan dinikmati pilihan konten dalam 2 minggu terakhir.

### **Berita Terbaru**

[**Stack Overflow 2018 Developer Survey**](https://medium.freecodecamp.org/stack-overflow-2018-developer-survey-faac8d3eb357)




![image](/posts/2018-03-20_yang-web-developers-harus-tahu-sharp7/images/1.png)

Kapan developers bangun pagi?



Stack Overflow sebagai sumber jawaban segala masalah programmer merilis hasil survey mereka terhadap developer, dan _insight_ menarik bisa kalian temukan di sini terkait bagaimana tren, kondisi, dan gambaran developer global.

[**Smooshgate FAQ**](https://developers.google.com/web/updates/2018/03/smooshgate)

FAQ ini mencoba memberikan gambaran terkait kasus [Mootools](https://mootools.net/), sebuah kumpulan tools JavaScript yang melakukan implementasi `Array.prototype.flatten` sebelum native API dirilis di browser. Permasalahan muncul pada saat implementasi Mootools ternyata konflik dengan API standar dan berakibat semua website yang menggunakan fungsi Mootools tersebut menjadi _error_ pada saat _native_ API untuk `Array.prototype.flatten` dirilis di Firefox Nightly dan berakibat sebuah [website besar tidak bisa menampilkan widget](https://bugzilla.mozilla.org/show_bug.cgi?id=1443630).

### Konten Menarik

[**Hadiah Untuk Programmer**](https://sekolahkoding.com/buku/hadiah-untuk-programmer)

[Hilman](https://mobile.twitter.com/Hilmanrdn) dari [Sekolah Koding](https://sekolahkoding.com) memberikan hadiah untuk kalian para programmer berupa kumpulan tulisan menarik dari pengalaman dia dan sangat berguna bagi kalian yang baru memulai pemrograman terutama di web. Opini dan pandangan pribadi Hilman saya rasa banyak berkaitan dengan programmer muda yang banyak saya ajak ngobrol.

[**Overview of JavaScript Testing**](https://medium.com/welldone-software/an-overview-of-javascript-testing-in-2018-f68950900bc3)




![image](/posts/2018-03-20_yang-web-developers-harus-tahu-sharp7/images/2.png)

Hasil menjalankan testing di source code



Testing merupakan hal wajib dalam programming demi mengurangi bug, dan _code conflict_. Dan seiring makin populernya JavaScript sebagai bahasa pemrograman untuk membangun web, _mobile app_, dan API maka testing merupakan hal wajib untuk dipelajari bagi programmer JavaScript. Artikel ini memberikan gambaran bagaimana JavaScript testing seharusnya dimulai dari _unit testing_, _integration testing_, dan _functional testing_.

[**Adaptive Atau Responsive Web Design**](https://medium.com/bliblidotcom-techblog/adaptive-atau-responsive-web-design-f138bfebdd97)




![image](/posts/2018-03-20_yang-web-developers-harus-tahu-sharp7/images/3.png)

Responsive vs Adaptive Web Design



Dalam membangun sebuah web pilihan untuk membuat _mobile web_ terpisah dengan _desktop_ atau responsive menjadi sebuah pertanyaan. Di mana saya sendiri lebih memilih _responsive design_ karena kode sumber yang dimaintain cukup satu. Bagaimana dengan kalian? Baca aja kelebihan dan kekurangan dari masing-masing pendekatan tersebut.

[**Asynchronous Clipboard API**](https://developers.google.com/web/updates/2018/03/clipboardapi)




![image](/posts/2018-03-20_yang-web-developers-harus-tahu-sharp7/images/4.png)



Sebelumnya kita bisa menggunakan `[Document.execCommand()](https://developers.google.com/web/updates/2015/04/cut-and-copy-commands)` untuk _copy paste text_ di _web app_ kita namun fungsi tersebut pemanggilannya _synchronous_. Untuk text ukuran kecil mungkin tidak berdampak buruk tapi kalau kalian mencoba meng-_copy_ text ukuran besar seperti sebuah artikel dengan ribuan kata maka hal tersebut bisa berdampak pada performance. Fungsi ini mencoba mengatasi hal tersebut dan juga isu keamanan di _permission_.

### Tools, Frameworks, dan Libraries

[**Puppeteer Script Untuk Simulasi Google Search Bot Crawler**](https://github.com/GoogleChromeLabs/puppeteer-examples/blob/master/google_search_features.js)

Salah satu isu modern framework dengan ES6 adalah tidak bisa dibaca dengan baik oleh Google Bot. Kalau kalian familiar dengan tool Render As Google di [Webmaster Tool](https://www.google.com/webmasters/tools/home) maka script ini akan membantu kalian untuk mencoba mengecek langsung website kalian apakah bisa dibaca oleh Google Crawler dengan baik. Pada dasarnya menggunakan Puppeteer dengan Chrome 41 rendering, sama dengan versi [Chrome engine yang digunakan oleh Google Crawler](https://developers.google.com/search/docs/guides/rendering).

[**Readme Checklist Untuk Project Open Source**](https://github.com/ddbeck/readme-checklist)

_Open source_ merupakan salah satu cara developer berbagi dan menunjukkan kemampuan coding-nya. Namun tentu agar orang lain bisa dengan mudah mengerti dan tertarik untuk berkontribusi di _project_ tersebut maka README menjadi sangat penting untuk memberikan gambaran terkait proyek tersebut. Checklist ini memberitahu apa saja yang perlu diperhatikan pada saat menulis file README _open source project_ kalian.

[**DOMCurl, JavaScript library untuk CURL**](https://medium.com/dev-channel/domcurl-curl-javascript-1dfd2f81aab)

Kalau [Puppeteer](https://github.com/GoogleChrome/puppeteer) menggunakan _headless browser_ [Puppeteer](https://github.com/GoogleChrome/puppeteer) untuk melakukan akses ke sebuah website tampak terlalu berlebihan bagi kalian mungkin kalian bisa mencoba DOMCurl ini yang konsepnya mirip dengan CURL, library yang biasa kalian gunakan di CLI, PHP, atau _server script_ lainnya untuk mengakses website programmatically
