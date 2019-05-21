---
title: "Yang Web Developer Harus Tahu #1"
author: "Yohan Totting"
date: 2017-12-04T01:34:55.552Z
lastmod: 2019-05-20T16:26:35+07:00

description: ""

subtitle: "Ini adalah newsletter pertama dari WWWID untuk secara rutin memberikan update terkini untuk para web developer agar tahu perkembangan dan…"
tags:
 - Front End Development 
 - Web Development 

image: "/posts/2017-12-04_yang-web-developer-harus-tahu-sharp1/images/2.png" 
images:
 - "/posts/2017-12-04_yang-web-developer-harus-tahu-sharp1/images/1.png" 
 - "/posts/2017-12-04_yang-web-developer-harus-tahu-sharp1/images/2.png" 
 - "/posts/2017-12-04_yang-web-developer-harus-tahu-sharp1/images/3.png" 


aliases:
    - "/yang-web-developer-harus-tau-1-5259c953881f"
---

Ini adalah newsletter pertama dari [WWWID](https://medium.com/wwwid) untuk secara rutin memberikan update terkini untuk para web developer agar tahu perkembangan dan tren pengembangan web seperti teknik, _tools_, _libraries_, dan _frameworks_. Berikut adalah apa yang _web developer_ harus tahu edisi pertama.

### Berita Terbaru

[**Firefox Developers 58 Release Notes**](https://hacks.mozilla.org/2017/11/new-in-firefox-58-developer-edition/?utm_source=frontendfocus&amp;utm_medium=email)




![image](/posts/2017-12-04_yang-web-developer-harus-tahu-sharp1/images/1.png)

Firefox DevTool Terbaru



Rilis terbaru Firefox Developers yang berbasis Quantum Engine ini datang dengan beragam tool terbaru untuk _web developers_ seperti _devtool_ terbaru, dukungan _font display_ di CSS, serta dukungan WebVR secara default.

[**Safari Technology Preview Release 44**](https://webkit.org/blog/8035/release-notes-for-safari-technology-preview-44/)**  
**Dukungan [Payment Request API](https://medium.com/wwwid/web-payment-request-api-dan-kemungkinan-adopsinya-di-indonesia-7cda8aee7a57) muncul di release terbaru Safari ini. Walaupun belum maksimal tapi dukungan ini menjadi berita baik bagi web developer terutama yang membuat aplikasi _e-commerce_.

[**Web Share Target API Supported in Chrome**](https://groups.google.com/a/chromium.org/forum/?utm_medium=email&amp;utm_source=footer#!msg/blink-dev/_oUskZTzQxg/bhckklGRBQAJ)**  
**Salah satu yang masih dirasakan _miss_ di PWA adalah kemampuan untuk menerima intent share dari aplikasi lain. Misalnya [Twitter Lite](https://mobile.twitter.com) saat ini belum bisa melakukan _tweet_ dengan konten yang kalian ingin _share_ dari Chrome. Tapi dengan [Web Share Target API](https://wicg.github.io/web-share-target/) ini, PWA akan bisa muncul di daftar pilihan aplikasi yang ingin kita gunakan untuk _share_ konten.

### Artikel Menarik

[**The Cost Of Javascript**](https://medium.com/dev-channel/the-cost-of-javascript-84009f51e99e)




![image](/posts/2017-12-04_yang-web-developer-harus-tahu-sharp1/images/2.png)

_Best practices_ untuk optimasi Javascript



Gambar terkadang diasumsikan menjadi sumber utama yang membuat loading terasa lambat, padahal file gambar tidak memperlambat _rendering_ di _browsers_. Justru file Javascript yang sebenarnya terkadang menjadi pokok masalah sebenarnya.

[**Best Request is No Request, Revisited**](https://alistapart.com/article/the-best-request-is-no-request-revisited)**  
**Salah satu _golden rule performance_ di web adalah bagaimana melakukan minimalisasi request sesedikit mungkin. Karena _roundtrips_ yang diperlukan untuk melakukan _requests_ berdampak pada waktu _loading_ suatu halaman web. Tapi dengan makin tingginya adopsi HTTP2 apakah _golden rule_ tersebut masih berlaku?

[**Images Filters Using WebGL**](https://www.youtube.com/watch?v=yyUuW9VQYqw&amp;list=PLNYkxOF6rcIBykcJ7bvTpqU7vt-oey72J&amp;index=37)**  
**Web bukan cuma sekedar untuk menampilkan konten, tapi bisa menjadi aplikasi foto _editor_ tanpa perlu di-install. Video ini menunjukkan bagaimana menggunakan WebGL untuk melakukan _filtering_ pada file gambar layaknya aplikasi Instagram.

[**Learn CSS Grid In 5 Minutes**](https://medium.freecodecamp.org/learn-css-grid-in-5-minutes-f582e87b1228)**  
**Membuat layout tampilan di halaman web merupakan sesuatu yang pasti dilakukan oleh _web developer_. Beberapa teknik layout dengan CSS _frameworks_ yang ada perlahan tergantikan dengan _feature_ _native_ di CSS sehingga kebutuhan akan framework bisa dikurangi. Salah satu fitur _native_ terbaru tersebut ada CSS Grid yang memungkinkan kita membuat _layout grid_ dengan lebih mudah.

[**Take Control Your Scroll**](http://2017%20All%20Articles%20November%20Dynamic%20import%28%29%20Take%20control%20of%20your%20scroll:%20customizing%20pull-to-refresh%20and%20overflow%20effects%20October%20September%20August%20July%20June%20May%20April%20March%20February%20January%202016%202015%202014%202013%202012%202011%20Contents%20Background%20Scroll%20boundaries%20and%20scroll%20chaining%20The%20pull-to-refresh%20effect%20Introducing%20overscroll-behavior%20Prevent%20scrolls%20from%20escaping%20a%20fixed%20position%20element%20The%20chatbox%20scenario%20The%20page%20overlay%20scenario%20Disabling%20pull-to-refresh%20Disabling%20overscroll%20glow%20and%20rubberbanding%20effects%20Full%20demo%20Internal:%20Count:%2037,%20Average:%204.5%20Take%20control%20of%20your%20scroll:%20customizing%20pull-to-refresh%20and%20overflow%20effects)**  
**Pada saat menggunakan aplikasi PWA terkadang pada saat kita berlebihan _scroll_ ke bawah secara _default_ aplikasi akan melakukan _refresh_ halaman karena itu adalah _default behaviour_ dari _browsers_. Untuk mencegahnya kalian bisa menggunakan CSS `overscroll-behavior`.

[**A Pinterest PWA Performance Case Study**](https://medium.com/@addyosmani/a-pinterest-progressive-web-app-performance-case-study-3bd6ed2e6154)**  
**Pinterest baru meluncurkan _mobile web_ terbaru mereka yang fokus untuk performance di _mobile_. Aplikasi PWA ini dikembangkan dengan React dan fokus pada _critical rendering path_ untuk memastikan _loading_ dan interaktif bisa kurang dalam 5 detik.

### Tools, Library, dan Framework

[**Bankai, The Friendly Web Compiler**](https://medium.com/choojs/bankai-the-friendly-web-compiler-35f1916679cc)




![image](/posts/2017-12-04_yang-web-developer-harus-tahu-sharp1/images/3.png)

Bankai web server



Bukan jamannya lagi menginstall MAMP, atau WAMP sebagai web server di komputer yang digunakan untuk _development_. Tapi tool seperti Bankai ini memudahkan kita untuk development dengan HTTP2 server dengan _live reloading_. Serta membantu kita untuk melakukan _build_ untuk _production_ dengan fitur optimasi seperti minify, tree shaking, flatten, dan lainnya.

[**Critical 1.0** ](https://github.com/addyosmani/critical/releases/tag/v1.0.0)**  
**_Critical_ CSS adalah style yang diperlukan untuk menampilkan tampilan yang akan terlihat pertama kali pada saat diakses. Dengan tool critical terbaru ini kita bisa melakukan ekstraksi _critical_ CSS tersebut dengan meng-_embed_-nya secara inline di _file_ HTML kita.
