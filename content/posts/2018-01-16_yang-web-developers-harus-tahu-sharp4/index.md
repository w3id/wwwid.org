---
title: "Yang Web Developers Harus Tahu #4"
author: "Yohan Totting"
date: 2018-01-16T04:28:26.868Z
lastmod: 2019-05-20T16:26:49+07:00

description: ""

subtitle: "Memulai 2018 biasanya dengan merencanakan kira-kira apa yang akan dilakukan selama setahun ke depan. Termasuk kira-kira akan belajar…"
tags:
 - Newsletter 
 - Front End Development 
 - Web Development 

image: "/posts/2018-01-16_yang-web-developers-harus-tahu-sharp4/images/1.gif" 
images:
 - "/posts/2018-01-16_yang-web-developers-harus-tahu-sharp4/images/1.gif" 
 - "/posts/2018-01-16_yang-web-developers-harus-tahu-sharp4/images/2.png" 
 - "/posts/2018-01-16_yang-web-developers-harus-tahu-sharp4/images/3.png" 
 - "/posts/2018-01-16_yang-web-developers-harus-tahu-sharp4/images/4.png" 
 - "/posts/2018-01-16_yang-web-developers-harus-tahu-sharp4/images/5.png" 
 - "/posts/2018-01-16_yang-web-developers-harus-tahu-sharp4/images/6.png" 
 - "/posts/2018-01-16_yang-web-developers-harus-tahu-sharp4/images/7.gif" 


aliases:
    - "/yang-web-developers-harus-tahu-4-63cbcf9ca3f"
---

Memulai 2018 biasanya dengan merencanakan kira-kira apa yang akan dilakukan selama setahun ke depan. Termasuk kira-kira akan belajar library atau framework apa, atau akan membuat sesuatu dan merilisnya ke publik dalam setahun ke depan. Apapun itu rencana kalian mudah-mudahan pilihan artikel ini bisa membantu mempermudah rencana kalian.

### Berita Terbaru

[**Autofill Di Browsers Bisa Mencuri Data Kalian**](https://github.com/anttiviljami/browser-autofill-phishing)




![image](/posts/2018-01-16_yang-web-developers-harus-tahu-sharp4/images/1.gif)

Demo auto fill mengisi data _fields_ tersembunyi



Fitur _auto fill form_ di browser terkadang memudahkan tapi bisa juga dimanfaatkan untuk mencuri data _credentials_ pengguna seperti password atau kartu kredit. Dengan menyembunyikan _input fields_ dari tampilan namun tetap terisi pada saat kita mengaktifkan _auto fill_ maka kita bisa mendapatkan data _credentials_ tersebut. Nah sebagai web developers, informasi ini jangan digunakan justru untuk mencuri data tapi sebagai pembelajaran agar kalian mengerti bagaimana browsers berfungsi dan berpikir bagaimana agar web bisa lebih aman.

[**Real World Data in Pagespeed Insight**](https://developers.googleblog.com/2018/01/real-world-data-in-pagespeed-insights.html)




![image](/posts/2018-01-16_yang-web-developers-harus-tahu-sharp4/images/2.png)

Hasil test Pagespeed dengan data Chrome User Experience report



[Pagespeed Insight](https://developers.google.com/speed/pagespeed/insights) adalah tool untuk mengukur kecepatan tampil sebuah website. Dan Pagespeed Insight ini sekarang sudah mengintegrasikan hasil tes dengan [Chrome Experience Repor](https://developers.google.com/web/tools/chrome-user-experience-report/)t sehingga kalian akan bisa membandingkan hasil tes kalian dengan rata-rata kecepatan tampil berdasarkan data Chrome Experience report.

[**Total Economic Impact AMP terhadap E-Commerce dan Publishers**](https://developers-id.googleblog.com/2018/01/total-economic-impact-amp-terhadap.html)

Baru-baru ini [Accelerated Mobile Page (AMP)](https://www.ampproject.org/), yaitu _library_ yang membantu kalian membangun aplikasi _mobile_ web yang bisa tampil dengan sangat cepat di _mobile_ merilis dampak kecepatan loading di _mobile_ terhadap _e-commerce_ dan _publishers_ dari perspektif ekonomi. Laporan yang patut kalian baca agar paham kenapa website kalian harus loading kurang dari 5 detik di _mobile_.

### Artikel Menarik

[**Permission On The Web Suck**](https://philna.sh/blog/2018/01/08/permissions-on-the-web-suck/)




![image](/posts/2018-01-16_yang-web-developers-harus-tahu-sharp4/images/3.png)



_Permission_ adalah permintaan akses ke pengguna untuk bisa menggunakan fitur yang bersifat _privacy_. Dan di web, permintaan akses hingga saat ini masih agak kurang baik bagi pengguna. Lihat saja bagaimana web yang ada meminta notifikasi _push_ tanpa memberikan alasan kenapa mereka meminta akses tersebut. Artikel ini memberikan gambaran bagaimana harusnya permintaan akses tersebut bisa lebih baik.

[**Web Based Voice Command Recognition**](http://smus.com/web-voice-command-recognition/)

Kalau kalian familiar dengan _personal assistant_ seperti Siri atau Google Assistant, tentu kalian familiar dengan pengenalan suara. Artikel ini menunjukan kemampuan dari web untuk bisa melakukan fungsi serupa tanpa harus mengirim data ke _server_. Menggunakan _library_ [DeeplearnJS](https://deeplearnjs.org/) contoh ini menunjukkan bagaimana dia bisa mengenali jawaban _yes_ dan _no_. Contoh sederhana untuk kalian memulai _machine learning_ di web.

[**JavaScript Startup Optimization**](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/javascript-startup-optimization/)




![image](/posts/2018-01-16_yang-web-developers-harus-tahu-sharp4/images/4.png)

Proses rendering di browser



Rata-rata aplikasi web modern sekarang dibangun dengan _framework_ modern yang menjalankan hampir semua fungsi di browser dengan konsep [_application shell_](https://developers.google.com/web/fundamentals/architecture/app-shell). Dan fungsi tersebut tentu ditulis dengan JavaScript, dan dampaknya adalah ukuran kode JavaScript yang makin besar dan tentu membutuhkan waktu untuk _parsing_ lebih lama. Artikel ini mencoba memberikan arahan ke _developers_ bagaimana kalian bisa mengoptimalkan kode kalian agar lebih cepat diparsing dan dijalankan oleh _browsers_.

[**Server Rendering, Code Splitting, and Lazy Loading with React Router v4**](https://medium.com/airbnb-engineering/server-rendering-code-splitting-and-lazy-loading-with-react-router-v4-bfe596a6af70)

Transisi dari monolith app hingga menjadi app shell app seperti di Airbnb ini menarik untuk inspirasi developer. Dimulai dari Ruby, lalu server rendering dengan [Hypernova](https://github.com/airbnb/hypernova) library yang dikembangkan Airbnb untuk kebutuhan server rendering, hingga akhirnya menerapkan universal rendering dengan React router v4.

### Tools, Libraries, dan Frameworks

[**Workerize**](https://github.com/developit/workerize-loader)




![image](/posts/2018-01-16_yang-web-developers-harus-tahu-sharp4/images/5.png)



[Jason Miller](https://twitter.com/_developit), developer yang membuat [Preact](https://preactjs.com/), library alternatif untuk [React](https://reactjs.org/) merilis library baru untuk memindahkan load modules ke thread terpisah di workers thread. Ide ini menarik karena dengan memisahkan thread untuk module, maka module tersebut tidak akan mengganggu thread utama untuk rendering tampilan.

[**Minimum Configuration WordPress PWA**](https://wordpress.org/plugins/mcw-pwa/)

[WordPress](https://wordpress.org) adalah CMS paling populer di Indonesia karena kemudahan penggunaan, tersedia gratis, serta fleksibilitas kostumasinya untuk fungsi tambahan. Nah [Progressive Web App sendiri] (https://developers.google.com/web/progressive-web-apps/)bertujuan untuk meningkatkan pengalaman pembaca WordPress site yang salah satunya dengan mempercepat waktu loading website. Dan plugin Minimum Configuration WordPress PWA ini memudahkan pemilik WordPress site untuk mengadopsi PWA tanpa perlu mengerti teknis web programming.

[**Lighthouse 2.7 dengan SEO Audit**](https://developers.google.com/web/updates/2018/01/lighthouse)




![image](/posts/2018-01-16_yang-web-developers-harus-tahu-sharp4/images/6.png)



Akhirnya salah satu kebutuhan wajib developer untuk melakukan _search engine optimization_ (SEO) bisa lebih mudah dengan rilis terbaru dari [Lighthouse audit tool](https://developers.google.com/web/tools/lighthouse/) ini. Dengan demikian developers bisa memahami _best practice_ untuk mengoptimalkan website mereka untuk _search engine indexing_.

[**Chrome Debugging dari Visual Studio Code**](https://code.visualstudio.com/blogs/2017/12/20/chrome-debugging)




![image](/posts/2018-01-16_yang-web-developers-harus-tahu-sharp4/images/7.gif)

Chrome Debugging with Visual Studio Code



Kalau kalian masih terbiasa melakukan _debugging_ dengan _console.log()_ maka sudah saatnya kalian mengefesiensikan proses _debugging_ dengan _tool_ yang tepat. Dengan [Visual Studio Code](https://code.visualstudio.com), kalian bisa melakukan _debugging_ dengan _set break_ di posisi kode tertentu di Visual Studio Code kalian dan melihat _state_ dari beberapa _variables_ langsung di [Chrome Dev Tool](https://developers.google.com/web/tools/chrome-devtools/).
