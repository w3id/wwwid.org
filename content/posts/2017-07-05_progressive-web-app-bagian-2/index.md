---
title: "Progressive Web App — Bagian 2"
author: "Putu Alfred Crosby"
date: 2017-07-05T17:15:44.962Z
lastmod: 2019-05-20T16:26:13+07:00

description: ""

subtitle: "Hijack Request, Cache Storage, App Manifest, App Shell, Notify Updates"
tags:
 - Pwa 
 - JavaScript 

image: "/posts/2017-07-05_progressive-web-app-bagian-2/images/1.png" 
images:
 - "/posts/2017-07-05_progressive-web-app-bagian-2/images/1.png" 
 - "/posts/2017-07-05_progressive-web-app-bagian-2/images/2.png" 
 - "/posts/2017-07-05_progressive-web-app-bagian-2/images/3.png" 
 - "/posts/2017-07-05_progressive-web-app-bagian-2/images/4.png" 
 - "/posts/2017-07-05_progressive-web-app-bagian-2/images/5.png" 
 - "/posts/2017-07-05_progressive-web-app-bagian-2/images/6.png" 
 - "/posts/2017-07-05_progressive-web-app-bagian-2/images/7.png" 
 - "/posts/2017-07-05_progressive-web-app-bagian-2/images/8.png" 
 - "/posts/2017-07-05_progressive-web-app-bagian-2/images/9.png" 
 - "/posts/2017-07-05_progressive-web-app-bagian-2/images/10.png" 


aliases:
    - "/tutorial-pwa-progressive-web-app-bahasa-indonesia-627e1f6810d2"
---

#### Hijack Request, Cache Storage, App Manifest, App Shell, Notify Updates

Untuk membuat Web App kita menjadi sebuah Progressive Web App ada beberapa checklist yang harus dipenuhi, teman-teman bisa melihat checklist nya pada link [ini](https://developers.google.com/web/progressive-web-apps/checklist).

Saatnya kita mulai dengan membuat project sederhana. Teman-teman bisa clone project ini dari github. Kita akan fokus pada service worker saja. Jadi kita tidak akan membahas hal diluar SW dulu ya.
`git clone [https://github.com/alfrcr/tutorial-pwa-bahasa-indonesia.git](https://github.com/alfrcr/tutorial-pwa-bahasa-indonesia.git)`

*   _catatan: teman-teman perlu menginstall NodeJS untuk menjalankan project diatas. Kalau ada yg belum memasang NodeJS silakan di-install dulu._
*   _link project_ [_disini_](https://github.com/alfrcr/tutorial-pwa-bahasa-indonesia)

Kalau sudah di-clone silakan install dulu dependency project tersebut dengan menjalankan perintah.

`npm install` atau `yarn install`

Setelah itu, silakan jalankan perintah `npm start` atau `yarn start`

Kemudian silakan buka browser dan masukkan alamat `http://localhost:5000`




![image](/posts/2017-07-05_progressive-web-app-bagian-2/images/1.png)

Akan muncul halaman list seperti di atas 😁



Kalau sudah muncul halamannya, sekarang saatnya kita mulai. Pertama-tama kita belajar untuk menambahkan SW ke dalam project.

### Menambahkan Service Worker ke dalam Project

Di dalam folder project, silakan teman-teman buka file `/js/sw-controller.js`. Disana kita akan menambahkan script untuk mendaftarkan SW kita. Silakan teman-teman tambahkan code dibawah ini. (Lihat comment di dalam file)




Yang kita lakukan barusan adalah:

1.  Pertama kita cek apakah browser support dengan SW. Jika tidak support kita akan lewati.
2.  Jika support maka kita akan register dengan menambahkan path file sw kita yaitu `/sw.js`

Kalau sudah coba di cek hasilnya, pada Console browser akan menampilkan pesan seperti ini.




![image](/posts/2017-07-05_progressive-web-app-bagian-2/images/2.png)

Muncul pesan registrasi SW berhasil pada browser console



### Hijack Request

Salah satu kekuatan utama SW yaitu bisa meng-hijack sebuah request. Bagaimana caranya menghijack sebuah request? Teman-teman silakan buka file **_sw.js_ **lalu tambahkan code dibawah ini:




_*tips: teman-teman bisa menggunakan_`console.log(event.request)` _untuk melihat semua request yang terjadi ketika halaman di-reload_

Jadi, pada kode diatas, pertama kita _mendengarkan(listen)_ event **_fetch._ **Lalu setiap request dari user akan kita merespon request tersebut dengan event.respondWith(). Perlu diingat `.respondWith()` tersebut membutuhkan sebuah argument berupa **Promise.** Dan pada kode diatas kita menggunakan new Response() untuk memberikan hasil request kepada client. Jika kita refresh(bukan hard-refresh), harusnya HALAMAN akan menampilkan **Hello Indonesia,** tapi kenapa halaman tetap seperti semula? Tidak itu saja tetapi ada hal lain yang terjadi…




![image](/posts/2017-07-05_progressive-web-app-bagian-2/images/3.png)

Service worker memiliki sebuah antrian



Kalau kita perhatikan gambar diatas, pada Tab Application pada Chrome Dev Tools dan pada bagian Service Workers, disana kita bisa lihat ada sebuah antrian. Apa artinya?

Ternyata perubahan pada SW tidak bisa langsung diaplikasikan ke halaman, disana SW akan mengantri seperti yang kita lihat, jadi browser benar-benar memastikan hanya ada _SATU_ _VERSI SW SAJA YANG BOLEH AKTIF_, sama seperti perilaku(cara kerja) Native Apps.

Untuk mengetahui kapan kita mendapatkan perubahan terbaru dari SW kita, maka pertama kita perlu membahas **LIFECYCLE** dari SW.

#### SW Lifecycle

Kenapa halaman tidak berubah? Ternyata perubahan yang kita lakukan masih dalam antrian. Lalu teman-teman mungkin bertanya lagi, “Bagaimana kita mendapatkan perubahan yang terbaru?”

Ada banyak cara untuk mendapatkan perubahan terbaru dari, jawabannya kita akan bahas sekaligus Lifecycle pada SW:

1.  Ketika kita mendaftarkan SW pertama kali, browser akan menyimpan dan menginstall versi pertama SW milik kita.
2.  Kemudian ketika kita melakukan perubahan, pada request berikutnya SW akan mengecek apakah ada perubahan, jika ada maka SW versi berikutnya akan masuk antrian terlebih dahulu sampai versi yang sedang aktif sekarang hilang atau tidak digunakan lagi.
3.  Service Worker akan digantikan ke versi baru ketika versi sekarang sudah tidak digunakan lagi oleh browser. Me-refresh halaman tidak akan mengubah SW ke versi yang terbaru. Jadi kapan SW tidak digunakan lagi? Yaitu ketika halaman ditutup, atau ketika user berpindah ke halaman yang tidak menggunakan SW tersebut.

Jadi untuk mendapatkan perubahan terbaru, teman-teman harus menutup window halaman kita terlebih dahulu kemudian kita membukanya lagi atau bisa dengan pergi ke halaman lain, contoh: URL sekarang adalah `[http://localhost:5000](http://localhost:5000)` kemudian kita pindah ke `https://www.google.com` setelah itu kembali lagi ke localhost. Maka SW secara otomatis akan menggunakan versi yang terbaru.

TAPI…

untuk development itu sangatlah merepotkan, syukurnya pada Chrome Dev Tools tersedia pilihan Update on Reload pada Tab Application.




![image](/posts/2017-07-05_progressive-web-app-bagian-2/images/4.png)

Cukup centang Update on reload maka SW akan selalu update ketika development



Mungkin untuk sekarang terdengar aneh user hanya akan mendapatkan updates ketika user berpindah halaman atau ketika user menutup window app kita. Nanti pada artikel ini kita akan gunakan pemberitahuan untuk memberitahu user ketika kita mempunyai perubahan pada app kita.

Kembali pada HIJACKING REQUEST

Pastikan teman-teman mendapatkan versi SW terbaru, kemudian coba refresh halaman. Dan….




![image](/posts/2017-07-05_progressive-web-app-bagian-2/images/5.png)

Browser sudah menggunakan SW versi terbaru!!



Apa yang dapat kita pelajari? Hijacking Request adalah fitur yang sangat powerful namun sangat berbahaya karena itu seperti yang sudah saya katakan pada artikel sebelumnya, SW hanya dapat digunakan pada protocol HTTPS dan pada localhost ketika development.

Lalu apa manfaat dari Hijacking Request?

Kita akan menggunakan fitur ini untuk mengecek semua request. Lalu setiap request kita cocokkan dengan semua file-file asset(HTML, CSS &amp; JS) yang sudah kita simpan di dalam Cache Storage.

Mari kembali ke text editor dan kita ubah file SW kita menjadi seperti ini:




Apa saja yang kita lakukan pada kode diatas?

Line 1: Penamaan cache di Cache Storage.

Line 3: List dari file yang akan kita cache. `/` merupakan `index.html` jadi disana kita juga meng-cache file index.html kita yang akan menjadi App Shell (kerangka halaman).

Line 20: Ketika SW diinstal, `waitUntil()` kita gunakan untuk menunggu proses populasi file di Cache Storage. `waitUntil()` berfungsi untuk menjalankan sebuah proses secara async, dan memberitahu browser untuk tidak memberhentikan proses install SW sampai proses yang kita kerjakan selesai. Dengan kata lain status SW tidak akan berubah menjadi **installed** sampai semua cache berhasil dikumpulkan pada Cache Storage.

Line 29: Ketika user mempunyai sebuah request (dalam arti simple user me-reload halaman), semua request akan di-cek terlebih dahulu pada Cache Storage (line 33) dan jika file yang di-request sudah tersedia pada Cache Storage, kita akan gunakan file tersebut. **TAPI** jika request tersebut tidak ada di dalam storage _(kita hanya meng-cache asset, jadi dengan kata lain adalah request selain asset)_, maka browser akan mendownloadnya dari server.

Ketika teman-teman me-refresh halaman, tidak ada banyak yang berubah bukan?

Tapi coba teman-teman centang Offline pada Tab Network atau Tab Application pada Chrome Dev Tools.

TADAAAA…




![image](/posts/2017-07-05_progressive-web-app-bagian-2/images/6.png)

Web App kita sudah berjalan Offline



Dan teman-teman bisa cek di Cache Storage pada Tab Application




![image](/posts/2017-07-05_progressive-web-app-bagian-2/images/7.png)

File-file yang berhasil kita cache



Keren banget kan? 😄

### Web App Manifest

Karena di dalam App kita sudah tersedia file `manifest.json` maka jika teman-teman buka melalui handphone teman-teman lalu Add to Homescreen (Android secara otomatis akan menampilkan popup jika `manifest.json` sudah ditambahkan), maka web app kita terasa seperti Native Apps, yaitu mempunyai icon dan dapat langsung diakses melalui Homescreen. Tidak hanya itu, app kita sudah bisa berjalan secara Offline. Itu berarti dengan PWA experience-nya sudah benar-benar mendekati Native Apps.

Untuk membuat Web App Manifest, teman-teman bisa generate dari web ini: [https://tomitm.github.io/appmanifest/](https://tomitm.github.io/appmanifest/) dan sisanya tinggal copy manifest dan meta tag dari halaman tersebut ke dalam project kita. (Project kita sudah ada semuanya jadi tidak perlu ditambahkan lagi 😉)

Tapi offline-mode ini belum bisa dinikmati oleh [pengguna iOS.](http://blog.ionic.io/what-is-a-progressive-web-app/)

### New updates available

Hal terakhir yang akan dibahas pada bagian 2 di series PWA adalah menambahkan pesan bahwa kita memiliki sebuah perubahan baru pada file web kita. Misalkan kita menambahkan sebuah fungsi baru yang berkilauan pada file JS kita atau merubah tampilan style kita menjadi warna lain atau bisa juga kita merubah ukuran font pada app kita.

User tidak akan mendapatkan semua perubahan itu sampai SW yang baru diaktifkan. Nah, kita sudah sampai sejauh ini, kita sudah siap mental untuk meninggalkan **Force on reload.** Sekarang kita akan buka file `styles.css` dan ubah pada `.custom-theme`




![image](/posts/2017-07-05_progressive-web-app-bagian-2/images/8.png)

Silakan pilih salah satu, dan comment yang lainnya



Pilih salah satu background-color lalu comment property css lainnya. Jika teman-teman refresh warna akan berubah seperti ekspektasi kita.






Nah, sekarang kita akan menonaktifkan “Force on reload” untuk mengetahui bagaimana user berinteraksi langsung dengan app kita.






Pada video kedua kita lihat Hard Reload bisa mem-bypass SW namun ketika kita coba Reload normal, tampilan kembali ke warna sebelumnya.

Dan jika kita perhatikan ketika kita mengubah file assets, **TIDAK ADA ANTRIAN** baru pada Service Worker. Itu artinya user tidak akan pernah mendapatkan perubahan terbaru walaupun user menutup dan membuka kembali window web app kita atau mengarahkan navigasi ke web lain seperti yang saya jelaskan pada lifecycle SW diatas, kecuali user melakukan **UNREGISTER SW**.

Cara yang akan kita gunakan untuk mendapatkan perubahan terbaru ketika kita mengubah file assets kita yaitu dengan memanfaatkan lifecycle dari SW itu sendiri. Namun harus kita pahami dulu bahwa ketika kita merubah file assets, kita juga perlu mengubah file SW supaya browser tahu bahwa ada kita memiliki versi terbaru dari app kita. Karena kita lihat tadi ketika kita mengubah warna header, SW baru tidak ada di dalam antrian.




![image](/posts/2017-07-05_progressive-web-app-bagian-2/images/9.png)

Mengubah nama cache untuk mendapatkan update terbaru



Sebenarnya bukan hanya mengubah nama cache, apapun bisa kita ubah agar browser tahu bahwa ada perubahan terbaru pada SW (termasuk memberikan /* comment */). Namun dalam kasus ini (project artikel ini) hal yang paling masuk akal untuk diubah menurut saya, karena tidak mengganggu fungsi lainnya. (opini pribadi)

Namun idealnya ketika kita sudah menggunakan asset bundler seperti Webpack, kita bisa mengkonfigurasi nama assets agar memiliki hash seperti `app.sd76sdf876a.js` jadi ketika kita memperbarui assets, mau tidak mau kita harus mengubah nama file yang akan di-cache. Jadi ada banyak alasan yang bisa kita gunakan untuk memperbarui SW.

Kembali ke file SW, sekarang kita tambahkan script pada bagian paling bawah:




Yang kita lakukan diatas adalah:

1.  `caches.keys()` mendapatkan semua cache pada Cache Storage. (Line 13)
2.  Setelah mendapatkan semua cache, kita akan hapus semua cache selain versi terbaru. Dalam kasus kita kali ini, kita akan hapus semua cache selain `v2-pwa-dasar`

Kemudian teman-teman bisa tutup window atau arahkan navigasi ke alamat lain kemudian buka kembali `http://localhost:5000` maka kita akan mendapatkan versi terbaru dari app kita.

#### Menambahkan UX untuk proses update SW

Idealnya kita perlu memberitahu user bahwa ada perubahan terbaru pada aplikasi tanpa mengganggu kegiatan user dan tentunya dengan cara yang lembut 😅 dan bukan cara yang terlalu teknis seperti cara diatas.

Di dalam file `/js/sw-controller.js` sudah saya siapkan beberapa method untuk memunculkan **Toast** pemberitahuan update yang imut 😄




![image](/posts/2017-07-05_progressive-web-app-bagian-2/images/10.png)

Pemberitahuan bahwa ada Service Worker versi terbaru.



#### Menampilkan Pemberitahuan Update

Seperti yang kita tahu, ketika kita membuat perubahan pada Service Worker, versi terbaru SW akan berada di dalam antrian. Simpelnya, kita akan mengecek jika ada antrian pada SW, dan jika ada maka akan kita tampilkan pemberitahuan.

Ada beberapa API yang bisa kita gunakan di dalam callback ketika kita mendaftarkan SW. Berikut adalah listnya:
`navigator.serviceWorker.register(&#39;/sw.js&#39;)  
  .then(function(reg) {  
    // reg.waiting;  
    // reg.installing;  
    // reg.active;  
    // reg.update();  
    // reg.unregister();``    // reg.addEventListener(&#39;updatefound&#39;, function() { ... });  
  })`

Kita akan memanfaatkan beberapa API tersebut untuk menampilkan pemberitahuan update. Silakan teman-teman perhatikan kode berikut:




Kita mengubah semua kode di dalam method `.registerSW()` . Berikut adalah penjelasannya:

1.  Line 8: Tidak perlu dijelaskan teman-teman harus sudah paham penggunaan keyword `this`
2.  Line 14: Kita menambahkan `if(!navigator.serviceWorker.controller)` fungsi kode ini adalah untuk mengecek apakah halaman kita diload menggunakan SW, karena ketika kita membuka halaman app kita pertama kali, SW controller masih `null` karena pada saat itu halaman masih di serve oleh server, bukan oleh SW. Jadi jika halaman bukan di serve oleh SW kita akan langsung _exit._
3.  Line 16: Disana kita melakukan cek jika sudah terdapat antrian dan sudah terinstall namun SW belum diaktifkan. Maka kita akan menampilkan pemberitahuan. Silakan lihat method `updateReady()` pada line 60.
4.  Line 21: Kita akan tracking aktifitas dari SW, ketika worker sedang di-install, kita bisa mengecek status dari worker tersebut. Ada beberapa status yang tersedia yaitu: `installing, installed, activating, activated, redundant` . Lengkapnya bisa dibaca [disini](https://developers.google.com/web/fundamentals/instant-and-offline/service-worker/lifecycle). Karena status `installing` maka ada kemungkinan akan terjadi error, karena itu kita akan mengecek apakah state dari sw, jika `installed` maka kita akan menampilkan pemberitahuan (lihat di dalam method `trackInstall()` pada line 53)
5.  Line 33: Karena proses SW berjalan di background, maka kita perlu tracking status dari SW. Karena itu kita memanggil kembali method `trackInstall()` lagi. Ketika SW terbaru sudah selesai terinstall maka, kita tidak perlu me-refresh halaman untuk mendapatkan pemberitahuan update. Apa yang terjadi jika kode dari line 33–35 dihilangkan? Jawabannya adalah kalian perlu me-refresh halaman untuk menampilkan pemberitahuan update, karena setelah me-refresh halaman baru kalian mendapatkan status `waiting` yang akan men-trigger method `updateReady()` .
6.  Line 38: Seperti yang saya sebut tadi, proses update SW berjalan di background, ketika SW yang baru sudah diaktifkan oleh user dengan cara mengklik tombol refresh pada toast, maka kita akan mendengarkan perubahan controller (SW) dengan memanfaatkan `controllerchange` . Setelah itu kita akan mereload halaman dengan cache yang baru dengan menggunakan `window.location.reload()`.
7.  Line 66: Akan kita bahas setelah ini.

Jadi sekarang ketika teman-teman merubah css, lalu memberikan perubahan pada file `sw.js` maka ketika teman-teman mereload halaman, secara otomatis akan menampilkan pemberitahuan. Keren bukan?






Tapi jangan buru-buru dulu, tombol REFRESH nya masih tidak berguna, sekarang saatnya kita membuatnya menjadi berguna. 😌

#### Trigger Updates

Seperti yang kita ketahui, bahwa Service Worker dan Javascript di halaman kita berjalan di thread yang berbeda. Service Worker tidak bisa mengakses DOM yang ada di dalam halaman kita. Lalu bagaimana kita berkomunikasi dengan SW?

SW mempunyai sebuah API untuk mengirim sinyal dari halaman ke SW, yaitu dengan menggunakan `reg.installing.postMessage({ foo: bar })`

Kembali ke code diatas pada **line 66** disana kita mengirimkan sinyal berupa object dengan property action dan dengan nilai `skipWaiting` . Code tersebut kita gunakan untuk mengirimkan sinyal ke SW. Lalu sekarang saatnya SW untuk mendengarkan sinyal tersebut.

Silakan tambahkan kode ini pada baris terakhir di dalam file `sw.js`




Kemudian ulangi langkah-langkah perubahan CSS seperti pada video sebelumnya, dan jangan lupa berikan perubahan juga pada file `sw.js`

Lihat hasilnya:






### Conclusion

Tidak terasa perjalanan kita jauh banget. Tidak perlu dijelaskan panjang lebar, intinya kalo kalian punya web dan sudah HTTPS wajib pasang SW ya!! 😆

Maaf cuma bercanda.

Setelah kita mengetahui fitur-fitur keren dari SW yang sudah kita pelajari tadi diatas, bagaimana menurut kalian? Jawaban silakan teman-teman renungkan sendiri ya.

Nah, sekarang apa selanjutnya?

Masih banyak yang perlu dibahas, pada artikel selanjutnya semoga saya dimampukan untuk membahas **Push Notification**. Doakan yah!!! 😆

### Reference

1.  [https://developers.google.com/web/fundamentals/instant-and-offline/service-worker/lifecycle](https://developers.google.com/web/fundamentals/instant-and-offline/service-worker/lifecycle)

#### Link bermanfaat

1.  [sw-precache-webpack-plugin](https://www.npmjs.com/package/sw-precache-webpack-plugin) atau [offline-plugin](https://www.npmjs.com/package/offline-plugin) buat kalian yang membangun SPA dengan webpack bisa menggunakan plugin tersebut.
2.  [Intercept, defer atau cancel add to homescreen](https://developers.google.com/web/fundamentals/engage-and-retain/app-install-banners/#deferring_or_cancelling_the_prompt)

### PWA — The Series Dalam Bahasa Indonesia

1.  [Bagian 1](https://medium.com/@alfrcr/pengenalan-progressive-web-app-pwa-bagian-1-cac0fadbe5f4)
2.  Kalian sedang disini

Jangan lupa jika artikel ini bermanfaat dibagikan ke teman-teman yang lain dan klik lambang hati ♥️
