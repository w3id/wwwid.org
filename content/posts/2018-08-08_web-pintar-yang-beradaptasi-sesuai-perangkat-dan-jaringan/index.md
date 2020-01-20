---
title: "Web Pintar Yang Beradaptasi Sesuai Perangkat dan Jaringan"
author: "Yohan Totting"
date: 2018-08-08T06:35:21.908Z
lastmod: 2019-05-20T16:27:31+07:00

description: ""

subtitle: "Para pengguna internet mengakses web saat ini dengan perangkat yang beragam walaupun bisa dibilang bahwa perangkat tersebut didominasi oleh…"
tags:
 - Progressive Web App 
 - Front End Development 
 - Adaptive Streaming 
 - Network Information Api 

image: "/posts/2018-08-08_web-pintar-yang-beradaptasi-sesuai-perangkat-dan-jaringan/images/2.png" 
images:
 - "/posts/2018-08-08_web-pintar-yang-beradaptasi-sesuai-perangkat-dan-jaringan/images/1.png" 
 - "/posts/2018-08-08_web-pintar-yang-beradaptasi-sesuai-perangkat-dan-jaringan/images/2.png" 


aliases:
    - "/web-pintar-yang-beradaptasi-sesuai-perangkat-dan-jaringan-78f4496915a4"
---

Para pengguna internet mengakses web saat ini dengan perangkat yang beragam walaupun bisa dibilang bahwa perangkat tersebut didominasi oleh mobile. Namun ragam perangkat mobile ini sendiri sebenarnya cukup beragam dan bisa kita klasifikasikan dalam perangkat tingkat atas, seperti iPhone 8/X, Samsung S9, LG G6 dan lain-lain. Lalu perangkat tingkat menengah seperti Oppo, Xiaomi, dan Vivo. Serta perangkat low end di bawah 1 juta seperti Samsung seri J.

### Beradaptasi dengan perangkat

Dengan beragamnya perangkat dari pengakses web, maka sudah seharusnya kita sebagai pengembang wajib mengoptimalkan website kita untuk perangkat yang paling banyak mengakses website kita. Data perangkat ini sebenarnya bisa dilihat di Google Analytics, sehingga kita bisa memastikan web kita jalan dengan baik di perangkat populer tersebut. Cuma terkadang developer merasa bahwa kalau di perangkat milik dia jalan dengan baik, dia merasa bahwa web tersebut jalan dengan baik di semua perangkat, padahal setiap perangkat memiliki spesifikasi dan kemampuan pemrosesan yang berbeda.


![image](/posts/2018-08-08_web-pintar-yang-beradaptasi-sesuai-perangkat-dan-jaringan/images/1.png)

Waktu yang diperlukan oleh perangkat untuk memproses JavaScript di CNN.com berdasarkan pengujian [WebPageTest](https://webpagetest.org) ([src](http://bit.ly/jscost-wpt)). Perangkat tingkat tinggi (iPhone 8) butuh ~4 detik, bandingkan dengan~13 detik di [perangkat menengah](https://infrequently.org/2017/10/can-you-afford-it-real-world-web-performance-budgets/) (Moto G4) bahkan butuh~36 detik pada parangkat tingkat rendah (Alcatel 1X).



Berdasarkan data di atas, kita bisa melihat kecepatan perangkat memproses JavaScript berbeda beda di setiap handphone. Bahkan ada perbedaan signifikan antara perangkat tingkat atas hingga 32 detik. Dengan demikian, diperlukan optimasi lebih lanjut di sisi pengembang web untuk membuat web bisa lebih pintar dalam beradaptasi dengan kondisi ini.

Untuk bisa optimal di semua perangkat, tentunya kita perlu akses ke spesifikasi perangkat tersebut. Dan di web, ada beberapa API yang bisa kita gunakan yaitu:

**Hardware concurrency**  
[API hardware concurrency](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorConcurrentHardware/hardwareConcurrency) ini untuk mengetahui berapa banyak core CPU yang dimiliki oleh perangkat.
```
const logicalProcessors = window.navigator.hardwareConcurrency
```

**Device memory**  
[API device memory](https://developers.google.com/web/updates/2017/12/device-memory) ini untuk mengetahui berapa besar jumlah memori (GiB) atau RAM dari perangkat.

```
const componentVersion = navigator.deviceMemory < 2? "lite" : "full";
```

Dari contoh di atas selanjutnya adalah menggunakan informasi jumlah _core_ CPU atau memori perangkat untuk mengoptimasi konten yang akan ditampilkan. Sebagai contoh:

```
const contentParams= {pageSize:0,showVideo:true,hiresImage:true};  
if(logicalProcessors < 3 && componentVersion ==="lite){  
  contentParams={pageSize:10,showVideo:false,hiresImage:false};  
}
```

Contoh di atas menggunakan informasi di _cpu cores_ dan _device memory_ untuk menampilkan konten versi _lite_ bila perangkat memiliki core kurang dari 3 cores dan RAM kurang dari 2 GiB. Konten versi _lite_ yang dimaksud adalah video diganti dengan gambar statis di-mana masih bisa diberikan _link_ untuk memutar video, jumlah konten yang ditampilkan hanya 10 atau setengah dari seharusnya, serta hanya menampilkan gambar dengan resolusi rendah.

**Kesimpulan untuk informasi perangkat** 
Yang perlu diperhatikan dari spesifikasi perangkat adalah kemampuan perangkat untuk memproses JavaScript serta memuat konten seperti gambar dan video. Sehingga bila spesifikasi perangkat cukup rendah sebaiknya ukuran JavaScript yang di-load juga lebih kecil, serta konten media yang ditampilkan sebaiknya tidak beresolusi tinggi atau menggunakan jenis file yang optimal.

### Beradaptasi dengan jaringan

Jaringan bersifat sangat dinamis, berbeda dengan perangkat yang bersifat tetap. Pada jaringan walaupun perangkat terhubung dengan wifi atau koneksi selular 4G, hal ini tidak menjamin kecepatan akses pada perangkat akan selalu cepat. Karena itu diperlukan cara untuk mengetahui kecepatan akses sebenarnya untuk melakukan sesuatu pada aplikasi web yang bergantung pada kondisi jaringan.

**Network Information API** Untuk mengetahui kondisi jaringan pada perangkat maka tersedia [Network Information API](https://developer.mozilla.org/en-US/docs/Web/API/NetworkInformation) yang bisa diakses seperti contoh berikut

```
const networkInformation = navigator.connection
```

Dan informasi yang dapat diakses dari API tersebut mencakup

*   downlink, kecepatan download sebenarnya dalam megabits per second (Mbps).
*   downlinkMax, kecepatan download maksimum bergantung pada jenis koneksi. Bila koneksinya adalah 4G maka akan tercantum kecepatan maksimum pada 4G.
*   rtt, _round trip time_ atau biasa disebut _ping_ dalam satuan _mili second(ms)_
*   effectiveType, tipe kecepatan sebenarnya (‘slow-2g’, ‘2g’, ‘3g’, atau ‘4g’) yang dikalkulasi berdasarkan downlink, rtt, dan lainnya.
*   type, tipe jaringan yang sedang terhubung di mana akan menampilkan nilai salah satu dari ‘_bluetooth’, ‘cellular’, ‘ethernet’,’none’,’wifi’,’wimax’,’other’,_ dan _’unknown’._

Nah bagaimana menggunakan informasi di atas untuk bisa membuat aplikasi web kita beradaptasi untuk kenyamanan pengguna. Yang utama dari informasi di atas menurut saya adalah _effectiveType_ dan _type_. Untuk effectiveType, kita bisa mengkondisikan jenis konten yang akan ditampilkan yang sesuai dengan kecepatan jaringan sebenarnya.

**Kesimpulan kecepatan jaringan** Kalau spesifikasi perangkat mempengaruhi kemampuan perangkat memproses JavaScript, dan menampilkan konten. Maka kecepatan jaringan mempengaruhi waktu yang diperlukan untuk memuat konten tersebut. Karena itu untuk kecepatan jaringan rendah, sebaiknya kita memuat konten dengan ukuran lebih kecil dari seharusnya. Lalu di kecepatan tinggi kita bisa memuat konten dengan ukuran yang sebenarnya.

### **Adaptive Streaming**

Salah satu fungsi yang digunakan dalam mengkonsumsi konten video adalah fungsi _streaming_. Permasalahannya kecepatan jaringan bersifat dinamis dan bisa berubah-ubah setiap waktu. Dengan menggunakan informasi _effectiveType_ yang diperiksa secara berkala pada saat sedang _streaming_, kita bisa mengganti _streaming_ kita ke _bitrate_ yang sesuai. Misalnya bila _effectiveType_ 4G maka kita akan memuat konten _bitrate_ resolusi tinggi. Namun bila pada 3G kita akan memuat konten beresolusi rendah.




![image](/posts/2018-08-08_web-pintar-yang-beradaptasi-sesuai-perangkat-dan-jaringan/images/2.png)

Contoh adaptive streaming yang mengecek effectiveType setiap 6 detik



Hal ini sudah diadaptasi oleh Instagram [di aplikasi web](https://www.instagram.com/) mereka menggunakan [Shaka Player](https://github.com/google/shaka-player) sehingga mereka bisa memutar video di web dengan lebih lancar tanpa _lagging_.

### Sinkronisasi data hanya di jaringan wifi

Salah satu yang bisa dilakukan juga dengan informasi _type_ adalah untuk keperluan upload atau download file berukuran besar atau sinkronisasi data berukuran besar. Hal ini diperlukan untuk mencegah pengguna kehabisan paket data karena proses sinkronisasi data berukuran besar.

```
if(navigator.connection.type==="wifi"){  
  //upload data langsung  
  uploadData();  
} else {  
  //jadwalkan upload nanti pada saat terhubung dengan wifi.  
  scheduleForUploadOnWifi();  
}
```

Sinkronisasi bahkan bisa lebih baik lagi bila menggunakan [_service workers_](https://developers.google.com/web/fundamentals/primers/service-workers/) yang sudah didukung oleh semua _browsers modern_. Pada _service worker_ ada [background sync](https://github.com/WICG/BackgroundSync/blob/master/explainer.md) API yang bisa digunakan untuk melakukan sinkronisasi data ini di background tanpa harus membuka aplikasi web. Dan _background sync_ API ini juga bisa diatur untuk hemat daya dan hanya jalan pada wifi saja.

```
navigator.serviceWorker.ready.then(function(registration) {  
  registration.periodicSync.register({  
    tag: "get-latest-news",         // default: ""  
    minPeriod: 12 * 60 * 60 * 1000, // default: 0  
    powerState: "avoid-draining",   // default: "auto"  
    networkState: "avoid-cellular"  // default: "online"  
  }).then(function(periodicSyncReg) {  
    // success  
  }, function() {  
    // failure  
  })  
});
```

### Kesimpulan

Web harusnya bisa diakses dengan nyaman tanpa peduli jenis perangkat atau kondisi jaringan yang ada. Dengan adanya akses pengembang ke informasi spesifikasi perangkat dan kecepatan jaringan memungkinkan pengembang web bisa membuat web yang lebih pintar beradaptasi dengan kondisi spesifikasi perangkat dan jaringan dalam memuat konten yang dapat dikonsumsi oleh pengguna dengan lebih cepat dan nyaman. Dan penggunaannya bahkan bisa lebih jauh lagi seperti untuk _adaptive streaming_ atau sinkronisasi data.

### Referensi

*   [Hardware concurrency API](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorConcurrentHardware/hardwareConcurrency)
*   [Device memory API](https://github.com/w3c/device-memory)
*   [Client Hint Header](http://httpwg.org/http-extensions/client-hints.html)
*   [Background Sync API](https://github.com/WICG/BackgroundSync/blob/master/explainer.md)
*   [Shaka Player](https://github.com/google/shaka-player)
