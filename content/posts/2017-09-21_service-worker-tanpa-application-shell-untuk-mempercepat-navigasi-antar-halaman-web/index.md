---
title: "Service Worker Tanpa Application Shell Untuk Mempercepat Navigasi Antar Halaman Web"
author: "Yohan Totting"
date: 2017-09-21T04:18:28.766Z
lastmod: 2019-05-20T16:26:15+07:00

description: ""

subtitle: "Seminggu lalu saya disibukkan oleh 2 Google events yaitu Progressive Web App Road Show Indonesia yang diadakan di 2 kota yaitu Jakarta dan…"
tags:
 - Progressive Web App 
 - Service Worker 
 - Server Side Rendering 
 - Web Performance 

image: "/posts/2017-09-21_service-worker-tanpa-application-shell-untuk-mempercepat-navigasi-antar-halaman-web/images/1.png" 
images:
 - "/posts/2017-09-21_service-worker-tanpa-application-shell-untuk-mempercepat-navigasi-antar-halaman-web/images/1.png" 
 - "/posts/2017-09-21_service-worker-tanpa-application-shell-untuk-mempercepat-navigasi-antar-halaman-web/images/2.png" 
 - "/posts/2017-09-21_service-worker-tanpa-application-shell-untuk-mempercepat-navigasi-antar-halaman-web/images/3.png" 


aliases:
    - "/service-worker-tanpa-application-shell-untuk-mempercepat-navigasi-antar-halaman-6b0d01fbe94b"
---

Seminggu lalu saya disibukkan oleh 2 Google events yaitu [Progressive Web App Road Show Indonesia](https://events.withgoogle.com/progressive-web-app-roadshow-indonesia/) yang diadakan di 2 kota yaitu Jakarta dan Yogyakarta. Dan salah satu yang ingin saya highlight adalah kata _progressive_. Bahwa dalam _Progressive Web App_, kita bisa meningkatkan _experience_ dari sebuah web app secara bertahap, tidak harus langsung sekaligus. Bahkan tidak perlu menulis ulang aplikasi web kita untuk menjadikannya _Progressive Web App_.

Sebagian besar developer yang saya kenal adalah _backend developer_ yang berawal dari _server side script_ seperti PHP, Ruby, Python, dan lainnya. Terutama PHP dengan WordPress yang merupakan CMS paling popular di Indonesia. Dan teman-teman ini hampir semuanya mengembangkan aplikasi tanpa menggunakan application shell sama sekali. Karena _pattern_ [_application shell_](https://developers.google.com/web/fundamentals/architecture/app-shell) hanya populer di kalangan front end developer, karena mereka biasanya mengembangkan aplikasi web menggunakan pattern [Single Page Application(SPA)](https://medium.com/@NeotericEU/single-page-application-vs-multiple-page-application-2591588efe58).

Jadi apa yang bisa dilakukan bila teman-teman hanya memiliki sebuah web dengan _server rendered scripts_? Kalian bisa memulai dengan [service worker](https://developers.google.com/web/fundamentals/getting-started/primers/service-workers) yang akan mempercepat navigasi antar halaman. Nah apakah service worker bisa diterapkan tanpa [_application shell_](https://developers.google.com/web/fundamentals/architecture/app-shell)? Jawabannya: Ya, bisa! Buktinya kalian bisa lihat hasil _experiment_ di bawah ini.

Saya mencoba mensimulasikan sebuah _server rendered website_ dengan 3 halaman html yaitu index.html, about.html, dan contact.html. Ketiganya adalah file html dengan struktur lengkap seperti _&lt;html&gt;_, _&lt;head&gt;_, dan _&lt;body&gt;_ yang kita asumsikan adalah halaman hasil _server rendered_ dari PHP, Python, atau lainnya. Di halaman web ini cuma _title_ dari masing-masing halaman.
`&lt;!doctype html&gt;``&lt;html lang=&#34;en&#34;&gt;``&lt;head&gt;``&lt;meta charset=&#34;utf-8&#34;&gt;``&lt;title&gt;NON SPA - Service Worker&lt;/title&gt;``&lt;meta name=&#34;description&#34; content=&#34;Testing service worker without application shell&#34;&gt;``&lt;meta name=&#34;author&#34; content=&#34;Yohan Totting&#34;&gt;``&lt;meta name=&#34;viewport&#34; content=&#34;width=device-width, initial-scale=1&#34;&gt;``&lt;/head&gt;``&lt;body&gt;``&lt;div id=&#34;menu&#34;&gt;&lt;a href=&#34;/index.html&#34;&gt;Home&lt;/a&gt; | &lt;a href=&#34;/about.html&#34;&gt;About&lt;/a&gt; | &lt;a href=&#34;/contact.html&#34;&gt;Contact&lt;/a&gt;&lt;/div&gt;``&lt;div id=&#34;main-container&#34;&gt;``&lt;h1&gt;Home&lt;/h1&gt;``&lt;/div&gt;``&lt;script&gt;``if (&#39;serviceWorker&#39; in navigator) {``window.addEventListener(&#39;load&#39;, function() {``navigator.serviceWorker.register(&#39;/service-worker.js&#39;).then(function(registration) {``// Registration was successful``console.log(&#39;ServiceWorker registration successful with scope: &#39;, registration.scope);``}, function(err) {``// registration failed :(``console.log(&#39;ServiceWorker registration failed: &#39;, err);``});``});``}&lt;/script&gt;``&lt;/body&gt;``&lt;/html&gt;`

Tanpa mengubah apapun di halaman html tersebut hanya dengan melakukan injeksi _script_ untuk _service worker_, kita bisa langsung [melakukan cache](https://developers.google.com/web/fundamentals/instant-and-offline/offline-cookbook/) untuk setiap halaman statis hanya dengan mendeklarasikan halaman yang ingin kita _cache_ di _script service worker_ kita. Kalian bisa mengecek apakah halaman dikembalikan dari _service worker_ atau dari _server_ menggunakan tab networks di Chrome Dev Tools dan hasilnya seperti di bawah ini.




![image](/posts/2017-09-21_service-worker-tanpa-application-shell-untuk-mempercepat-navigasi-antar-halaman-web/images/1.png)

File about.html didapatkan dari service worker



Setelah service worker terpasang, maka setiap _request_ ke server dari web tersebut akan dicegat oleh service worker, dan kita bisa melakukan _processing_ di mana di contoh ini hanya melakukan pengecekan di cache dan bila tersedia maka hasil dari cache akan dikembalikan langsung ke halaman web untuk ditampilkan. Kalian bisa melihat beda _response time_ dengan atau tanpa service worker di bawah ini




![image](/posts/2017-09-21_service-worker-tanpa-application-shell-untuk-mempercepat-navigasi-antar-halaman-web/images/2.png)

Response time di simulasi slow 3G tanpa service worker





![image](/posts/2017-09-21_service-worker-tanpa-application-shell-untuk-mempercepat-navigasi-antar-halaman-web/images/3.png)

Response time di simulasi slow 3G dengan service worker



Membandingkan _response time_ tanpa service worker yaitu 2 seconds dan dengan service worker yaitu 10 milliseconds di kondisi simulasi _slow_ 3G menunjukkan perbedaan signifikan. Tapi memang kondisi tersebut hanya bisa kejadian bila halaman web diakses sekali agar service worker terpasang lalu kunjungan berikutnya akan jauh lebih cepat karena halaman dikembalikan dari cache, bukan dari server.

Lalu mungkin kalian bertanya, sama aja kalau butuh akses sekali dulu biar bisa service worker terpasang. Apa keuntungannya? Menurut saya ingin bergantung skenario kapan web kalian digunakan. Salah satunya adalah berpindah halaman lebih cepat karena semua sudah disimpan di cache pada saat kalian membuka halaman home. Sehingga kalian bisa berpindah ke halaman lain seperti about dan contact dengan cepat walaupun halaman tersebut belum pernah diakses, karena pada saat kalian mengakses home, halaman lainnya langsung disimpan di cache karena dideklarasikan di saat fase _install_ service worker seperti yang kalian bisa lihat di bawah ini.
`//service-worker.js``var CACHE_NAME = &#39;my-site-cache-v1&#39;;``var urlsToCache = [``&#39;/index.html&#39;,``&#39;/about.html&#39;,``&#39;/contact.html&#39;``];``self.addEventListener(&#39;install&#39;, function(event) {`` // Perform install steps`` event.waitUntil(``  caches.open(CACHE_NAME)``  .then(function(cache) {``   console.log(&#39;Opened cache&#39;);``   return cache.addAll(urlsToCache);``  })`` );``});`

Contoh service worker di atas adalah contoh sederhana bagaimana melakukan cache semua file yang kita inginkan. Tapi sangat disarankan walaupun kita bisa memasukkan banyak file, tapi sebaiknya digunakan dengan bijaksana dengan hanya memasukkan file statis seperti JavaScript file, CSS file, atau aset gambar dan font karena kita tidak tahu perangkat yang digunakan oleh pengunjung kita memiliki spesifikasi seperti apa. Mungkin saja kapasitas penyimpanan terbatas, sehingga sebaiknya website kita juga tidak mengkonsumsi cache space dengan file yang tidak terlalu sering diakses.

Hasil _experiment_ di atas menunjukkan bagaimana kalian bisa meningkatkan pengalaman pengguna di website kalian dimulai dengan kecepatan navigasi antar halaman. Dengan implementasi service worker, kalian bisa meningkatkan pengalaman secara progressive atau bertahap di kondisi jaringan yang lambat sekalipun. Lalu bagaimana bila jaringan sedang _offline_? Apakah _server rendered scripts_ website bisa tetap diakses? Nantikan di _experiment_ berikutnya._Source code experiment_ di atas bisa diakses di [https://github.com/tyohan/pwa-experiments/tree/master/nonspa-sw](https://github.com/tyohan/pwa-experiments/tree/master/nonspa-sw).
