---
title: "Yang Web Developers Harus Tahu #3"
author: "Yohan Totting"
date: 2018-01-01T23:55:13.023Z
lastmod: 2019-05-20T16:26:43+07:00

description: ""

subtitle: "Edisi ke 3 ini menutup 2017 dan menyambut 2018. Beberapa artikel adalah rangkuman atau kilas balik dari 2017. Sudah siapkah kalian…"
tags:
 - Newsletter 
 - Front End Development 
 - Web Development 

image: "/posts/2018-01-01_yang-web-developers-harus-tahu-sharp3/images/1.png" 
images:
 - "/posts/2018-01-01_yang-web-developers-harus-tahu-sharp3/images/1.png" 
 - "/posts/2018-01-01_yang-web-developers-harus-tahu-sharp3/images/2.png" 
 - "/posts/2018-01-01_yang-web-developers-harus-tahu-sharp3/images/3.png" 


aliases:
    - "/yang-web-developers-harus-tahu-3-895e320f1a46"
---

Edisi ke 3 ini menutup 2017 dan menyambut 2018. Beberapa artikel adalah rangkuman atau kilas balik dari 2017. Sudah siapkah kalian #_MakeTheWebGreatAgain_ di 2018? Silakan memulai dengan membaca artikel pilihan berikut.

### Berita Terbaru

[**Web Advent Today**](http://web.advent.today/)

Rangkuman 10 tulisan oleh praktisi web untuk menghitung mundur ke 2018 sangat menarik diikuti untuk melihat perspektif mereka akan perkembangan web di 2017 dan apa yang mereka harapkan di 2018. Di tiap artikel ada link ke blog post dari masing-masing author yang menurut saya sangat menarik untuk dibaca untuk penutup 2017 dan pembuka 2018.

[**Frontend in 2017: The important parts**](https://blog.logrocket.com/frontend-in-2017-the-important-parts-4548d085977f)




![image](/posts/2018-01-01_yang-web-developers-harus-tahu-sharp3/images/1.png)

NPM downloads of Angular, React, and Vue  
Source: npmtrends.com



Rangkuman tentang _front end development_ di 2017 terutama di sisi _tools_ dan _frameworks_ yang membantu para pengembang web untuk dapat lebih produktif.

[**Totally Tooling Tips Holiday Special: 2017 Year in Review**](https://www.youtube.com/watch?v=8f0LZAihqZI&amp;list=PLNYkxOF6rcIB3ci6nwNyLYNU6RDOU3YyL&amp;index=1)




![image](/posts/2018-01-01_yang-web-developers-harus-tahu-sharp3/images/2.png)



Masih seputar tools, Addy Osmani dan Matt Gaunt memberikan rangkuman _tools_ favorit mereka di 2017 di [Youtube channel, Totally Tooling Tips Google Chrome Developers](https://www.youtube.com/playlist?list=PLNYkxOF6rcIB3ci6nwNyLYNU6RDOU3YyL). Tools merupakan alat bantu yang mempercepat dan memudahkan kita dalam menulis kode dan melakukan optimasi dalam aplikasi kita dengan mengotomasi beberapa fungsi dan memberikan informasi atau _insight_ terkait kode aplikasi kita.

[**Microsoft Edge Support Service Workers**](https://blogs.windows.com/msedgedev/2017/12/19/service-workers-going-beyond-page/)

Akhirnya browser Microsoft Edge memberikan dukungan pada _service workers_ di _preview build_. Dengan demikian dua _browsers_ populer Safari dan Microsoft Edge menutup 2017 dengan dukungan resmi mereka terhadap _service workers_ menyusul Chrome, Firefox, Opera, UC Browsers, dan Samsung Internet. Service workers sendiri adalah salah satu komponen utama di _Progressive Web Apps_ (PWA).

### Artikel Menarik

[**Myth Buster JavaScript**](https://mythbusters.js.org)

Walaupun ini bukan artikel tapi sebuah _e-book_ berbasis web yang bisa menjadi referensi menarik para pengembang JavaScript terutama yang _concern_ dengan _performance_ aplikasi yang dikembangkan. Dengan e-book ini pengembang JavaScript bisa menerapkan _best practice_ dalam mengembangkan aplikasinya.

[**Tinder PWA Case Study**](https://medium.com/@addyosmani/a-tinder-progressive-web-app-performance-case-study-78919d98ece0)




![image](/posts/2018-01-01_yang-web-developers-harus-tahu-sharp3/images/3.png)



Salah satu case study yang sangat menarik untuk dibaca bagaimana implementasi _Progressive Web App_s(PWA) pada Tinder berdampak pada metrics mereka. Cocok dibaca buat kamu yang sedang mempertimbangkan platform mana yang ingin kalian fokuskan untuk produk startupmu.

[**Enter Audio Worklet**](https://developers.google.com/web/updates/2017/12/audio-worklet)

Web Audio API merupakan salah satu API yang menarik buat saya. Walaupun Web Audio API di web sudah berjalan di _thread_ terpisah dengan User Interface(UI) _rendering thread_ tapi _trigger_-nya masih bergantung pada _event handler_ yang bersifat _asynchronous_ yang ada di UI rendering. Sehingga kalau UI kalian cukup aktif, maka _latency_ tetap susah dihindari. Audio Worklet adalah API _processor_ baru yang akan menggantikan _ScriptProcessorNode._ Audio Worklet diharapkan bisa memberikan _zero latency_ dan _synchronous rendering._

[**Catatan dari Rian Yulianto Tentang Belajar JavasScript**](https://medium.com/kode-dan-kodean/catatan-aktivitas-programming-2017-dan-apa-yang-akan-dipelajari-di-tahun-2018-cb8a5ed83448)

Tulisan dari [Rian Yulianto](https://medium.com/@kucingmeongs), developer Bandung bagaimana dia memulai belajar JavaScript dari latar belakang Android Developers. Menurut saya sangat menarik dibaca buat kalian yang ingin memulai belajar JavaScript tapi bingung harus mulai dari mana.

### Tools, Libraries, dan Frameworks

[**Lazy Load Router With VueJS**](https://medium.com/js-dojo/build-a-lazy-load-router-with-vue-js-and-the-latest-browser-features-a1b52fe52dda)

_Router_ adalah komponen wajib [_Single Page Application_(SPA)](https://developers.google.com/web/fundamentals/architecture/app-shell) yang memungkinkan sebuah halaman ditampilkan berdasarkan URL yang dimuat di _browser_ tanpa harus melakukan pemanggilan halaman penuh ke _server_. Di artikel ini kalian bisa belajar bagaimana membuat _router_ tersebut dengan VueJS _library_ dan metode _lazy-load_.

[**WebVR Polyfill 0.10.0**](https://github.com/googlevr/webvr-polyfill/releases/tag/v0.10.0)

Rilis terakhir di WebVR _Polyfill_ buat kalian yang tertarik bermain-main dengan WebVR. Dengan _polyfill_ ini kalian bisa membuat konten _virtual reality_(VR) yang bisa dimainkan di iOS Safari. Saat ini Firefox dan Chrome sudah mendukung VR akan tetapi di iOS Safari hanya tersedia di _nightly build_.

[**Internet Monitoring With Puppeteer**](https://gist.github.com/ebidel/3dacce879beda9d6aca98bd86d19165b)

[Puppeteer](https://github.com/GoogleChrome/puppeteer) adalah [Chrome Headless](https://developers.google.com/web/updates/2017/04/headless-chrome) API Library yang memungkinkan kalian mengontrol sebuah _browser_ dan melakukan sebuah otomasi seperti di contoh ini. Puppeteer sendiri bisa digunakan untuk melakukan _functional testing_ di aplikasi web kalian ataupun otomasi seperti melakukan _screen capture_ pada web.

[**Lighthouse 2.6 Updates**](https://developers.google.com/web/updates/2017/12/lighthouse)

[Lighthouse](https://developers.google.com/web/tools/lighthouse/) yang merupakan standard audit web oleh Google mendapatkan _update_ terbaru dengan perbaikan di audit _performance_. Beberapa tambahan audit antara lain _boot time_ JavaScript, penanganan _cache_ yang tidak efisien di aset statis, serta _redirect website_.
