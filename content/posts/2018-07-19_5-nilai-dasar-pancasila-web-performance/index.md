---
title: "5 Nilai Dasar Pancasila Web Performance"
author: "Yahya Fadhlulloh Al-Fatih"
date: 2018-07-19T08:03:23.347Z
lastmod: 2019-05-20T16:27:24+07:00

description: ""

subtitle: "Salah satu alasan utama munculnya user bounce adalah turunnya performance dari web, terdapat dua faktor penyebab web performance menurun…"

image: "/posts/2018-07-19_5-nilai-dasar-pancasila-web-performance/images/2.gif" 
images:
 - "/posts/2018-07-19_5-nilai-dasar-pancasila-web-performance/images/1.png" 
 - "/posts/2018-07-19_5-nilai-dasar-pancasila-web-performance/images/2.gif" 
 - "/posts/2018-07-19_5-nilai-dasar-pancasila-web-performance/images/4.gif" 


aliases:
    - "/5-nilai-dasar-pancasila-web-performance-1f5ef575c3d5"
---

S
alah satu alasan utama munculnya user bounce adalah turunnya performance dari web, terdapat dua faktor penyebab web performance menurun, penurunan web performance atau jaringan usernya memang lambat, tapi hal yang paling mudah untuk di tingkatkan adalah websitenya, tapi ada masalah lain jika kita berbicara tentang websitenya, disaat developer atau sys engineer sudah melakukan segala hal untuk meningkatkan web performance kadang masih saja kebingungan “what else to do” supaya performance ini naik.




![image](/posts/2018-07-19_5-nilai-dasar-pancasila-web-performance/images/1.png)

comic by xkcd



Pada dasarnya kadang kita suka melewati hal hal mendasar yang sebenarnya harus dipahami dulu sebelum mengeluarkan keputusan dalam meningkatkan performance. Penulis membuat **Pancasila Web Performance** yang dimaksudkan agar kita sebagai developer web mempunyai landasan landasan dalam meningkatkan web performance. **Pancasila Web Performance** ini dibuat dari kumpulan kesalahan para [expert](https://www.keycdn.com/blog/web-performance-advice/) dalam meningkatkan web performance, pengalaman ini penulis olah menjadi landasan landasan utama dalam membangun web performance.

Tujuan utama penulis membuat istilah Pancasila adalah, supaya hal ini yang selalu diingat oleh kita, pada saat ada pertanyaan “apa lagi yang kurang buat meningkatkan performance?” semoga jawabannya bisa ditemukan pada **Pancasila Web Performance** ini, berikut nilai dasar pancasila Web Performance yang penulis buat :




![image](/posts/2018-07-19_5-nilai-dasar-pancasila-web-performance/images/2.gif)



### **1. Image Optimization adalah segalanya**

Kadang kita sebagai developer terlalu fokus pada scripting performance padahal disisi lain banyak media konten yang membebani web, pelaku utamanya adalah gambar! rata rata halaman di [load sekitar 2200 KB dan sekitar 1440 KB nya adalah gambar](https://httparchive.org/reports/state-of-the-web?start=latest), artinya 60% halaman itu dibebankan oleh gambar!

Banyak beberapa cara untuk mengoptimalkan gambar :

*   compressing
*   jangan menjalankan GZIP
*   cache image
*   File Type (PNG, Webp, JPG)

### 2. Menggunakan 3rd party script atau framework seminim mungkin

Bagian ini sudah jelas dan semua orang paham kalau 3rd party scripting atau framework mampu menurunkan performance web, alasan utamanya adalah dari dependency hell dalam arti lain synchronous load script dimana script tersebut memungkinkan men-load script lain lagi yang membuat load makin lama, Chat bot, analytic, retargeting, ads, social widget, external CSS script yang di load di head secara synchronous, dll.

Terkadang divisi marketing atau divisi non-dev-ops yang punya hak mengontrol 3rd party script atau framework ini sering kali gagal dalam memanage 3rd party dependecies, yang benar adalah mempunyai strategi dalam pemasangan 3rd party yang diselaraskan dengan User Experience.

Beberapa tools yang dapat menghapus 3rd party yang tidak digunakan :

*   [https://github.com/uncss/uncss](https://github.com/uncss/uncss)
*   [https://github.com/geuis/helium-css](https://github.com/geuis/helium-css)
*   [https://github.com/webpack-contrib/purifycss-webpack](https://github.com/webpack-contrib/purifycss-webpack)
*   [CSS Remove and combine chrome plugin](https://chrome.google.com/webstore/detail/cdfmaaeapjmacolkojefhfollmphonoh)
*   snyk.io (package scanner buat check availability plugin dan vulnerability plugin)

### 3. Mengurangi beban “setiap halaman”

Kadang kita sebagai developer beranggapan tolak ukur web performance kita lebih baik dengan melakukan web performance test pada halaman index , padahal belum tentu hal tersebut menentukan web performance lebih baik atau tidak, karena masih banyak dia yang halamannya penuh dengan gambar, dia yang halamannya penuh dengan chart, dan dia yang halamannya penuh dengan [dependecy hell](https://en.wikipedia.org/wiki/Dependency_hell).

Kita tidak bisa menyalahkan dia yang halamannya penuh dengan chart karena mungkin dia dibuat untuk menampilkan data chart. Ada beberapa cara efektif untuk meningkatkan performance dari spesifik halaman, contoh dengan implementasi lazyload pada halaman yang berat, karena lazy load sendiri berfungsi utama di load pada saat media/ content tersebut dibutuhkan.
> “Menggunakan lazyload untuk setiap penggunaan spesifik halaman, supaya setiap halaman di load seminim mungkin” — Galih pratama



![image](https://cdn-images-1.medium.com/max/800/0*FlyqhWp86PrMs0Py)



kalau membicarakan lazy load artinya ga jauh dengan asynchronous, yes, the almighty **asynchronous,** kapan dan dimana saja tempat yang cocok untuk penggunaan lazy load ini tergantung dengan kebutuhan, contohnya halaman listing item, comment section pada artikel.

### 4. Mengurangi segala “render blocking”

Salah satu kelemahan developer kalau menggunakan library JS atau CSS kadang tidak menggunakan minification atau defer untuk optimalisasi web

ada beberapa poin yang bisa dijalankan untuk mengurangi render blocking :

*   Jangan berketergantungan terhadap Javascript untuk load page
*   try server-side-rendering atau service worker
*   bundling all important JS in one file
*   Optimisasi file CSS dan JS

Ada beberapa artikel dari medium yang cukup membantu dalam mengurangi masalah render blocking ini

[Berbagai best practice dalam memuat halaman website](https://medium.com/wwwid/berbagai-best-practice-dalam-memuat-halaman-website-20def6652adf)

[Service Worker Tanpa Application Shell Untuk Mempercepat Navigasi Antar Halaman Web](https://medium.com/wwwid/service-worker-tanpa-application-shell-untuk-mempercepat-navigasi-antar-halaman-6b0d01fbe94b)


### **5. Menggunakan perceived performance sebagai tolak ukur**

Pada umumnya kalau berbicara tentang web performance biasanya kecepatan adalah segalanya, kadang tolak ukur ini muncul dari berbagai banyak hal dari segi metric seperti, berapa detik user akses halaman, keefektifan penggunaan CDN, Time to First Byte, Compress Transfer (kadang compress transfer ini malah bisa menjadi masalah), Penggunaan keep alive, atau penggunaan cache static content. Kadang hasil dari metrik tersebut membuat kita over-analyze data, yang perlu kita lakukan adalah kita lirik dalam bentuk user perspektif.

Dengan menganalisa user perspektif, perceived performance bisa menjadi tolak ukur yang cocok untuk performance web, karena perceived performance ini menggunakan skala seberapa cepat user berfikir tanpa perlu bertanya untuk menggunakan website, hal ini bisa menjadi hal lebih penting daripada “kecepatan” itu sendiri.

Untuk mengukur perceived performance dapat menggunakan best practice atau checklist, beberapa contoh tolak ukur perceived performance :

*   Response Time, berikut waktu reaksi user pada saat buka website> **0–100ms** — Instant> **100–300ms** — Small perceptible delay> **300–1000ms** — Machine is working> **1000+ms** — Likely mental context switch> **10,000+ms** — Task is abandoned

*   Asynchronous Loading, hal yang bisa membuat user merasa wajar pada saat menunggu content yang halamannya berat.



![image](/posts/2018-07-19_5-nilai-dasar-pancasila-web-performance/images/4.gif)

loading


[Let people do; Asynchronous loading is for users not just computers](https://medium.com/ben-and-dion/let-people-do-asynchronous-loading-is-for-users-not-just-computers-40987de0e221)
Thanks buat nyempetin baca tulisan gabut gw ini, pada dasarnya penulis membuat tulisan ini sangat panjang dan bahkan sempat membuat checklist web performance, penulis membayangkan apakah akan cukup membantu jika penulis merelease checklist web performance dan long version dari tulisan ini🤔 ?

Let me know menarik untuk dibuat atau ada masukan lain thanks 🐣~Referensi

[http://blog.teamtreehouse.com/perceived-performance](http://blog.teamtreehouse.com/perceived-performance)  
[https://medium.com/wwwid/berbagai-best-practice-dalam-memuat-halaman-website-20def6652adf](https://medium.com/wwwid/berbagai-best-practice-dalam-memuat-halaman-website-20def6652adf)  
[https://www.keycdn.com/blog/blocking-the-dom/](https://www.keycdn.com/blog/blocking-the-dom/)  
[https://www.keycdn.com/blog/web-performance-advice-2018/](https://www.keycdn.com/blog/web-performance-advice-2018/)  
[https://www.keycdn.com/blog/web-performance-advice/](https://www.keycdn.com/blog/web-performance-advice/)  
[https://developers.google.com/web/fundamentals/performance/critical-rendering-path/render-blocking-css](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/render-blocking-css)  
[https://developers.google.com/speed/pagespeed/insights](https://developers.google.com/speed/pagespeed/insights)  
[https://www.wpbeginner.com/wp-tutorials/how-to-fix-render-blocking-javascript-and-css-in-wordpress/](https://www.wpbeginner.com/wp-tutorials/how-to-fix-render-blocking-javascript-and-css-in-wordpress/)  
[https://medium.com/wwwid/service-worker-tanpa-application-shell-untuk-mempercepat-navigasi-antar-halaman-6b0d01fbe94b](https://medium.com/wwwid/service-worker-tanpa-application-shell-untuk-mempercepat-navigasi-antar-halaman-6b0d01fbe94b)  
[https://medium.com/wwwid/yang-web-developer-harus-tau-1-5259c953881f](https://medium.com/wwwid/yang-web-developer-harus-tau-1-5259c953881f)  
[https://medium.com/wwwid/tantangan-web-developer-untuk-membuat-aplikasi-web-bisa-digunakan-kurang-dari-5-detik-70bb7431741d](https://medium.com/wwwid/tantangan-web-developer-untuk-membuat-aplikasi-web-bisa-digunakan-kurang-dari-5-detik-70bb7431741d)

[https://www.keycdn.com/blog/perceived-performance/](https://www.keycdn.com/blog/perceived-performance/)
