---
title: "Yang Web Developers Harus Tahu Di #IO18"
author: "Yohan Totting"
date: 2018-05-15T10:31:19.824Z
lastmod: 2019-05-20T16:27:20+07:00

description: ""

subtitle: "Selesai sudah hajat tahunan Google Developers, Google IO 2018 di Mountain View yang menjadi ajang tahunan untuk mengundang para developers…"
tags:
 - Io18 
 - Web Development 
 - Progressive Web App 

image: "/posts/2018-05-15_yang-web-developers-harus-tahu-di-sharpio18/images/1.jpeg" 
images:
 - "/posts/2018-05-15_yang-web-developers-harus-tahu-di-sharpio18/images/1.jpeg" 


aliases:
    - "/yang-web-developers-harus-tahu-di-io18-aed9a4878c8"
---

![image](/posts/2018-05-15_yang-web-developers-harus-tahu-di-sharpio18/images/1.jpeg)

Google I/O 2018

Selesai sudah hajat tahunan Google Developers, [Google IO 2018](https://events.google.com/io/) di Mountain View yang menjadi ajang tahunan untuk mengundang para developers dari seluruh dunia untuk bisa mendapatkan update terkini terkait platform teknologi yang dimiliki Google dan berinteraksi dengan orang-orang di belakangnya sehingga para developers bisa membangun aplikasi atau fungsi di atas _platform_ tersebut. Dan tulisan ini akan memberikan rekapan apa saja yang perlu kalian tahu terkait web platform dan bagaimana kalian sebagai pengembang bisa mengadopsi perkembangan tersebut. Berikut adalah pilihan beberapa video dari sesi web di Google IO 2018 yang sudah kita pilih, dan dilengkapi deskripsi singkat terkait video tersebut.

### _The web: state of the union_






Bagaimana web platform terus beradaptasi untuk memberikan pengalaman lebih baik untuk pengembang dan pengguna? Beberapa yang menarik di antaranya adalah browser supports untuk komponen penting seperti [_service workers_](https://developers.google.com/web/fundamentals/primers/service-workers/), dan [_web assembly_](https://webassembly.org/) sudah diadopsi untuk semua major browsers. Selain itu, [_prototype web packaging_](https://github.com/WICG/webpackage) sudah bisa dicoba untuk mendapatkan kecepatan tampil seperti halaman AMP.

### Building a seamless web






Web terus berkembang dan browser juga berusaha agar para pengembang web bisa lebih mudah dalam membuat web yang memberikan pengalaman baik bagi penggunanya. Karena itu ada beberapa hal yang sedang dirancang di dalam browser seperti web packaging, layering API, dan best practices policies yang dirancang agar pengalaman web yang baik bisa distandarisasi.

### PWAs: building bridges to mobile, desktop, and native






Bagaimana PWA bisa memberikan pengalaman yang lebih baik? Empat point penting menjadi kunci utama yaitu _Fast, Integrating, Reliable, Engaging (FIRE)_. Bagaimana 4 poin tersebut diimplementasikan di dunia nyata? Kalian bisa melihat beberapa contoh implementasi PWA dan dampaknya di Starbucks, Google Search, dan Google Map.

**What’s new in Chrome DevTools**






_Debugging asynchronous code_ yang menggunakan fungsi _await_ sebelumnya tidaklah mudah. Karena kalian tidak bisa menggunakannya di _console_ tanpa _wrapper function_. Namun di [Chrome DevTools](https://developer.chrome.com/devtools) terbaru kalian bisa langsung menggunakannya. Selain itu fungsi _step into debugging_ di _asynchronous code_ juga berfungsi baik di mana sebelumnya kita tidak bisa melakukan debugging step in di _asynchronous code._

### Build awesome media experiences on the web






Talk ini sangat menarik bila kalian membuat web yang banyak menyajikan media seperti video. Dengan API baru yang ada di web, kalian bisa membuat tampilan video _picture in picture(PIP)_ yang sudah tersedia di Android Oreo pada aplikasi web kalian. Selain itu ada juga web API baru untuk menampilkan konten secara remote seperti layaknya Google Cast, sehingga kalian bisa membuat sebuah aplikasi _receiver_ yang siap menerima lemparan konten untuk ditampilkan. Serta gambaran video _codec_ terbaru yang mampu melakukan kompresi video 2,5GB menjadi hanya 300MB.

### Web performance made easy






Bagaimana mempercepat performance sebuah website? Di talk ini kalian akan mendapatkan langkah-langkah bagaimana mengoptimalkan _performance web_ kalian mulai dari optimasi _critical resources, code splitting, font loading_, serta optimalisasi gambar. Selain itu, ada _library_ baru yaitu [guess.js](https://github.com/guess-js/guess) yang akan mempelajari pola akses penggunjung website kalian dengan _machine learning_ dan akan melakukan [_prefetch_](https://developers.google.com/web/fundamentals/performance/resource-prioritization#prefetch) otomatis untuk halaman yang sering dikunjungi berikutnya dari halaman tersebut.

### Web Components and the Polymer Project: Polymer 3.0 and beyond






Update terkini untuk perkembangan web components yang sudah diadopsi secara native di mayor browsers. Dan mengikuti perkembangan JS module yang sudah didukung juga di mayor browsers, maka Polymer library untuk web components juga berpindah dari HTML import ke JS module di rilis terbaru Polymer 3.0. Dengan demikian kalian bisa menggunakan Webpack atau bundler app lainnya yang menggunakan JS module pada Polymer 3.0.

### Make your WordPress site progressive






Buat kalian WordPress developers, talk ini memberikan best practices di WordPress site untuk memberikan peningkatan pengalaman secara progresif di WordPress site. Ada juga plugin AMP versi terbaru dan bagaimana plugin tersebut bisa membantu mengkonversi keseluruhan WordPress web kalian menjadi AMP site yang bisa tampil dengan sangat cepat tanpa banyak melakukan perubahan source code.

### PWA starter kit: build fast, scalable, modern apps with Web Components






Kalau dulu kita punya [Bootstrap](https://getbootstrap.com/) yang menjadi boilerplate setiap kita memulai sebuah project baru sekarang sudah banyak tool sesuai framework masing-masing. Namun kalau kalian ingin memulai project baru dengan web component tanpa framework kalian bisa mencoba [PWA starter kit](https://github.com/Polymer/pwa-starter-kit). Di talk ini juga dijelaskan terkait Redux pattern untuk menghubungkan states antar komponen. Untuk kalian yang ingin memahami lebih jauh bagaimana arsitektur sebuah aplikasi web modern, sesi ini wajib kalian tonton.

### Deliver search-friendly JavaScript-powered websites






Salah satu ketakutan pengembang terhadap _single page application(SPA)_ adalah susah untuk di-index oleh mesin pencari. Padahal aplikasi modern dengan arsitektur _single page application_ merupakan standar saat ini. Sesi ini akan membantu kalian untuk mengoptimalkan aplikasi web modern kalian agar tetap bisa di-index oleh mesin pencari seperti Google Search. Ada beberapa pola dan _best practic_e yang perlu diikuti agar aplikasi web modern kalian bisa tetap terbaca dan ditemukan di mesin pencari.

### What’s new with sign up and sign in on the web






Keamanan selalu menjadi hal yang sangat penting dalam pengembangan aplikasi. Namun kadang keamanan mengorbankan kenyamanan karena prosesnya kadang terlalu kompleks. Bahkan dalam pengembangannya juga kadang cukup rumit. Dengan API baru untuk keamanan identitas di web maka kemudahan pengguna untuk daftar atau masuk hanya dengan sekali klik atau tap ke halaman website terproteksi akan jadi lebih baik. Bahkan bagaimana menggunakan finger print sebagai akses kunci masuk ke dalam website. Developer akan lebih mudah dalam implementasinya karena API ini akan menjadi dukungan standar yang ada di dalam browser tanpa harus menggunakan library khusus.

### Introducing .app domain names and how to secure them






Google meluncurkan [Top Level Domain (TLD) bernama .app](https://www.registry.google/) ke publik dengan tujuan agar user mudah mengingat nama domain dan memiliki kesan bagi user. Tidak seperti TLD lainnya, ketika kita mengakses domain .app maka langsung mengarah ke HTTPS secara default. Hal ini dikarenakan karena domain .app menggunakan teknik [HTTP Strict Transport Security](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security) (HSTS). Jika kamu datang ke Google I/O 2018, kamu beruntung karena Google membagikan TLD .app cuma — cuma ke kamu. Di video ini akan membahas lebih mendalam mengapa .app ini lahir dan bagaimana cara kamu menggunakannya.

### What’s new in web accessibility






Kini Accessibility (A11y) menjadi salah satu prioritas yang wajib diperhatikan oleh developer dalam mengembangkan produk yang ditujukan kepada kalangan disabilitas. Pada video di atas, terdapat hal menarik yang patut dicoba antara lain [accessibility tab pane, color contrast ratio](https://developers.google.com/web/updates/2018/01/devtools#a11y), style CSS baru yakni _:focus-visible_ untuk membedakan hasil fokus antara keyboard dan mouse serta [Accessibility Object Model (AOM)](http://wicg.github.io/aom/explainer.html), sebuah low-level API yang didesain untuk memberikan developer kendali penuh untuk terhadap A11y di website mereka.

### Mana yang kalian ingin tahu lebih dalam?

Silakan memberikan respon di artikel ini untuk memberikan mana yang harus kita kupas lebih dalam di artikel berikutnya.

Terima kasih untuk [Satya Kresna Adi Pratama](https://medium.com/u/2645da69fbda) atas kontribusinya ke artikel ini.
