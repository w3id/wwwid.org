---
title: "Yang Web Developers Harus Tahu #2"
author: "Yohan Totting"
date: 2017-12-20T02:15:04.748Z
lastmod: 2019-05-20T16:26:37+07:00

description: ""

subtitle: "Sebagai newsletter kedua dan menjelang tutup tahun 2017 beberapa konten menarik yang dimasukkan adalah gambaran perjalanan komunitas web…"

image: "/posts/2017-12-20_yang-web-developers-harus-tahu-sharp2/images/1.png" 
images:
 - "/posts/2017-12-20_yang-web-developers-harus-tahu-sharp2/images/1.png" 
 - "/posts/2017-12-20_yang-web-developers-harus-tahu-sharp2/images/2.png" 
 - "/posts/2017-12-20_yang-web-developers-harus-tahu-sharp2/images/3.png" 
 - "/posts/2017-12-20_yang-web-developers-harus-tahu-sharp2/images/4.png" 
 - "/posts/2017-12-20_yang-web-developers-harus-tahu-sharp2/images/5.png" 
 - "/posts/2017-12-20_yang-web-developers-harus-tahu-sharp2/images/6.png" 


aliases:
    - "/yang-web-developers-harus-tahu-2-6843a1e3e36e"
---

Sebagai newsletter kedua dan menjelang tutup tahun 2017 beberapa konten menarik yang dimasukkan adalah gambaran perjalanan komunitas web developers dan karyanya selama 2017. Dan ini dia yang kalian harus tahun di pertengahan Desember 2017 ini.

### Berita Terbaru

[**The State of JavaScript 2017**](https://stateofjs.com/)




![image](/posts/2017-12-20_yang-web-developers-harus-tahu-sharp2/images/1.png)

Laporan trend dan perkembangan JavaScript di 2017



Sebuah survey ke 20.000 web developers untuk mencari tahu bagaimana perkembangan JavaScript selama 1 tahun ini. Laporan ini bisa memberi gambaran buat web developers terkait trend akan penggunaan JavaScript beserta tools, libraries, dan frameworks yang populer di komunitas web developers.

[**WhatWG Merangkul Browsers Engines**](https://blog.whatwg.org/working-mode-changes)




![image](/posts/2017-12-20_yang-web-developers-harus-tahu-sharp2/images/2.png)

Tweet bersama menunjukkan dukungan para browser engines pada WHATWG



[WHATWG](http://whatwg.org) adalah organisasi yang fokus pada implementasi standard di browsers. Sebelumnya mereka fokus di spesifikasi dan advokasi standard ini tanpa dukungan resmi dari _browser engines_ yang ada. Tapi per akhir tahun ini bersama-sama dengan Google, Mozilla, Apple, dan Microsoft mereka sepakat membentuk [_steering group_](https://github.com/whatwg/sg) untuk dapat menyusun standarisasi implementasi bersama di semua browser engines mereka. Harapan kita sebagai pengembang web tentunya lebih mudah dalam mengembangkan web sehingga implementasi bisa lebih konsisten di semua _browsers_.

[**State of Vue.JS 2017**](https://www.monterail.com/state-of-vuejs-report?portalId=1667658&amp;hsFormKey=bd988f532a9fcd878a6f5d1c57e14442&amp;submissionGuid=a84ae15f-8e6a-49aa-a0df-326307c8c16b#module_150892825232422)

Selain laporan tahunan terkait JavaScript secara _general_ seperti di atas, salah satu agency pengembangan aplikasi dan web yaitu [Monterail](https://www.monterail.com) juga melakukan riset perkembangan [Vue](https://vuejs.org/) di kalangan web developers. Hasil risetnya bisa teman-teman akses [di halaman ini.](https://www.monterail.com/state-of-vuejs-report?portalId=1667658&amp;hsFormKey=bd988f532a9fcd878a6f5d1c57e14442&amp;submissionGuid=a84ae15f-8e6a-49aa-a0df-326307c8c16b#module_150892825232422) Yang menarik dari laporan ini adalah beberapa studi kasus dari beberapa perusahaan yang menggunakan [Vue.JS](https://vuejs.org/).

### Artikel Menarik

[**Rendering AJAX-Crawling Pages**](https://webmasters.googleblog.com/2017/12/rendering-ajax-crawling-pages.html)

Salah satu tantangan dari _Single Page Application_(SPA) adalah optimasi untuk _search engine_ (SEO) yang memerlukan usaha lebih dibandingkan dengan _server rendered pages_. Artikel dari Google Webmaster Tool ini memberikan panduan bagaimana mengoptimalkan website dengan AJAX agar dapat dibaca oleh Google _crawler_. Selain itu Google Webmaster Tools juga memberikan update untuk [SEO starter guide](https://webmasters.googleblog.com/2017/12/a-revamped-seo-starter-guide_12.html) untuk bisa mengakomodasi SPA.

[**Getting Your Website Ready For Mobile First Indexing**](https://webmasters.googleblog.com/2017/12/getting-your-site-ready-for-mobile.html)

Sama seperti artikel di atas, Google Webmaster Tool ingin memastikan bahwa pengembang web bisa fokus pada optimalisasi akses website menggunakan mobile device. Panduan ini membantu para pengembang web bisa mengoptimalkan website-nya agar dapat di-index oleh Google Crawler.

[**Netflix and React**](https://jakearchibald.com/2017/netflix-and-react/)




![image](/posts/2017-12-20_yang-web-developers-harus-tahu-sharp2/images/3.png)

Pernyataan yang di-tweet dan berujung menjadi thread panjang



Sebuah tweet yang menjadi diskusi panjang di Twitter karena pernyataan _engineer_ Netflix yang menyatakan dengan mengeluarkan React dari aplikasi, mereka mendapatkan peningkatan _performance_ lebih dari 50%. Jake Archibald mencoba mengulas bagaimana sebenarnya peningkatan 50% performance itu terjadi.

[**Async CSS**](https://www.filamentgroup.com/lab/async-css.html)

Teknik _asynchronous loading_ dengan _attribute_ _async_ cuma bisa digunakan pada script, bukan pada link yang biasa digunakan untuk memuat CSS di halaman web. Dan seperti kita tahu, bahwa CSS merupakan [_critical resources_ yang juga _rendering blocking_](http://Flash%20of%20Unstyled%20Content%22%20%28FOUC%29). Artikel ini menjelaskan bagaimana kita bisa membuat CSS menjadi tidak _blocking_ sehingga halaman web kita bisa tampil lebih cepat.

[**23 Minutes of Works For Better Fonts Loading**](https://www.zachleat.com/web/23-minutes/)




![image](/posts/2017-12-20_yang-web-developers-harus-tahu-sharp2/images/4.png)

`_glyphhanger_` _command output, automatically subsetting both web fonts._



Selain CSS, _font_ merupakan [_critical resources_](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/) __ yang terkadang agak susah untuk kita lupakan karena ingin agar _typography_ kita bisa terlihat lebih baik. [Bila _font_ belum dimuat, maka _browsers_ tidak akan menampilkan konten text di halaman website.](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/webfont-optimization)

[**Santa Tracker**](https://www.youtube.com/watch?list=PLNYkxOF6rcIAQ-xb-Y04twWvKJU6N2UVm&amp;time_continue=1&amp;v=k-xHlo634jM)




![image](/posts/2017-12-20_yang-web-developers-harus-tahu-sharp2/images/5.png)

Santa Village di web Santa Tracker



Natal sudah dekat dan seperti biasa Google punya Santa Tracker yang bisa dimainkan hanya dengan membuka [websitenya](https://santatracker.google.com/). Di series video ini, Sam yang mengembangkan Santa Tracker bercerita tentang pengembangnya serta bagaimana kalian bisa melakukan _clone_ pada [repo Github](https://github.com/google/santa-tracker-web) dan menjalankan Santa Tracker dari komputer kalian sendiri.

### Tools, Libraries, dan Frameworks

[**Introducing Turbo: 5x Faster Than Yarn and NPM**](https://medium.com/@ericsimons/introducing-turbo-5x-faster-than-yarn-npm-and-runs-natively-in-browser-cc2c39715403)




![image](/posts/2017-12-20_yang-web-developers-harus-tahu-sharp2/images/6.png)

Turbo, package management yang dirancang lebih cepat dari Yarn dan NPM



Package management sudah menjadi bagian utama dalam pengembangan website dan salah satu yang menjadi kendala adalah banyaknya package dependencies yang dibutuhkan sehingga butuh lama untuk melakukan setup. Karena itu salah satu package management terbaru Turbo mencoba mengurangi waktu setup dengan performance 5x lebih cepat dari package management populer seperti [Yarn](https://yarnpkg.com) dan [NPM](https://www.npmjs.com/).

[**Webpack With Service Worker**](https://webpack.js.org/guides/progressive-web-application/)

Webpack sebelumnya menggunakan [SW-Precache](https://github.com/GoogleChromeLabs/sw-precache) sebagai service worker plugin. Sebelum akhirnya memasukkan [Workbox](https://developers.google.com/web/tools/workbox/) yang merupakan library lanjutan untuk service worker yang dikembangkan setelah oleh Google. Workbox sendiri adalah library untuk membantu penggunaan service worker yang memberikan kemudahan konfigurasi namun bisa juga digunakan untuk fungsi yang lebih _advance_.

[**Using Trusted Web Activity**](https://developers.google.com/web/updates/2017/10/using-twa)

Setelah diumumkan di [Chrome Dev Summit](https://medium.com/wwwid/pembelajaran-yang-saya-dapatkan-dari-chrome-dev-summit-untuk-indonesia-95adb25aad56), akhirnya panduan penggunaan Trusted Web Activity dipublikasi di web Google Developers Web. Dengan adanya panduan ini web developers akhirnya bisa melakukan bundle Progressive Web App(PWA) mereka dan mempublikasikannya di Google Play.

[**Real User Experiences Test**](https://ruxt.dexecure.com/)

Di Chrome Dev Summit, Chrome team juga merilis [_user experiences report_](https://developers.google.com/web/tools/chrome-user-experience-report/) __ yang bisa diakses menggunakan [Big Query](https://bigquery.cloud.google.com/dataset/chrome-ux-report:chrome_ux_report). Namun untuk memudahkan dalam melakukan menampilkan data, [Dexecure](https://dexecure.com/) merilis sebuah website tool yang memudahkan kita mengakses data tersebut menggunakan form sederhana.
