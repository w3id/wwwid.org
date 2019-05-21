---
title: "Progressive Web Apps, mulai dari mana?"
author: "Yohan Totting"
date: 2018-02-02T05:17:43.783Z
lastmod: 2019-05-20T16:26:56+07:00

description: ""

subtitle: "Banyak orang salah kaprah pada saat berbicara tentang Progressive Web App(PWA), bahwa untuk bisa memiliki PWA harus Single Page…"
tags:
 - Progressive Web App 
 - Web Development 
 - Product Development 

image: "/posts/2018-02-02_progressive-web-apps-mulai-dari-mana/images/1.png" 
images:
 - "/posts/2018-02-02_progressive-web-apps-mulai-dari-mana/images/1.png" 
 - "/posts/2018-02-02_progressive-web-apps-mulai-dari-mana/images/2.png" 
 - "/posts/2018-02-02_progressive-web-apps-mulai-dari-mana/images/3.png" 
 - "/posts/2018-02-02_progressive-web-apps-mulai-dari-mana/images/4.gif" 


aliases:
    - "/progressive-web-apps-mulai-dari-mana-bd223a941782"
---

Banyak orang salah kaprah pada saat berbicara tentang [_Progressive Web App_(PWA)](https://developers.google.com/web/progressive-web-apps/), bahwa untuk bisa memiliki PWA harus _Single Page Application_(SPA), atau harus menggunakan _framework_ modern seperti React, Angular, Polymer, dan lainnya. Sehingga banyak developer yang merasa bahwa mereka tidak bisa menerapkan PWA karena mereka masih menggunakan _server rendered framework_ seperti PHP atau Ruby Framework. Padahal berbicara PWA, tentunya yang utama adalah kata _progressive_ di mana maksud sebenarnya adalah peningkatan pengalaman user secara progresif atau bertahap. Nah pertanyaannya mulai dari mana sih kalau ingin membuat sebuah aplikasi PWA? Tulisan ini semoga bisa membantu kalian untuk menjawabnya.

### **Keamanan HTTPS Adalah Pondasi Dasar**

Keamanan di web merupakan isu yang cukup besar karena banyaknya _phising_, _content hijacking_, dan isu keamanan lainnya. Sebagian besar isu ini mengeksploitasi kemudahan web yang sangat mudah diakses. Hanya dengan URL, kita bisa mengakses tanpa perlu meng-_install_ apapun di perangkat kita. Dengan itu, [penggunaan HTTPS adalah wajib di sisi _web server_](https://developers.google.com/web/fundamentals/security/encrypt-in-transit/why-https), karena hampir semua fungsi dari PWA cuma bisa berjalan di HTTPS. Dan sekarang dengan adanya [_SSL certificate_ gratis](https://letsencrypt.org/), maka tidak ada alasan lagi untuk tidak menggunakan HTTPS di web kalian. Tentu ini juga panggilan buat para provider hosting untuk bisa menyediakan SSL gratis di semua server mereka. Tanpa dukungan pihak _hosting provider_ maka web yang aman akan tetap menjadi isu.

### Meningkatkan pengalaman pengguna secara bertahap

Setelah memiliki pondasi, baru kita bisa memulai untuk meningkatkan pengalaman pengguna web kita secara bertahap. Dan tentu tidak semua harus didukung, tapi kita perlu memilih berdasarkan jenis aplikasi web kita. PWA bukanlah teknologi yang semua komponen harus dibuat. Komponen PWA yang ada di bawah ini bersifat modular, jadi bisa saja beberapa komponen tidak digunakan, atau cuma mengimplementasi 2 atau 3 komponen saja. Dan berikut adalah tahapan yang kalian bisa coba.




![image](/posts/2018-02-02_progressive-web-apps-mulai-dari-mana/images/1.png)

Skema komponen fungsi PWA



### 1. Siap untuk PWA

Yang pertama adalah apakah website kalian sudah siap untuk PWA. Karena sebelum kita mencoba menerapkan fungsi PWA maka website kita harus siap untuk dioptimasi. Dua checklist yang saya rekomendasikan untuk memastikan website kalian siap untuk PWA adalah:

1.  [Menggunakan protokol HTTPS](https://developers.google.com/web/fundamentals/security/encrypt-in-transit/enable-https). Tanpa HTTPS maka hampir sebagian besar komponen PWA tidak akan bisa diimplementasikan.
2.  Menggunakan [_App Shell Architecture_](https://developers.google.com/web/fundamentals/architecture/app-shell), ini merupakan hal yang paling susah karena terkadang memerlukan penulisan ulang aplikasi. Tapi menurut saya, PWA tetap masih bisa diimplementasi walaupun ada beberapa hal yang terbatasi tanpa _App Shell Architecture_ ini.

### 2. Tingkatkan kecepatan loading dan respon

Kecepatan _loading_ dan respon menurut saya adalah yang paling penting dan harus menjadi langkah pertama untuk optimalisasi PWA. Tanpa kecepatan maka pengguna akan meninggalkan _website_ kalian tanpa mencoba pengalaman lainnya. Bahkan **data yang ada menyebutkan** [**3 detik website tidak tampil, 53% pengguna akan pergi**](https://www.doubleclickbygoogle.com/articles/mobile-speed-matters/). Buat apa membuat sesuatu sedemikian baik tapi akhirnya orang tidak memakai karena terlalu lambat.

Dengan _loading_ yang cepat maka pengguna akan dapat merasakan _value_ yang kalian coba tawarkan dan selanjutnya baru menentukan apakah kalian bisa membuat mereka tinggal atau pergi.




![image](/posts/2018-02-02_progressive-web-apps-mulai-dari-mana/images/2.png)

Source: DoubleClick — The need for mobile speed, September 2016



Untuk meningkatkan kecepatan _website_, kalian bisa melihat [beberapa petunjuk di sini](https://developers.google.com/web/fundamentals/performance/rail).

### 3. Memasang _service worker_ untuk dukungan _offline_ dan peningkatan kecepatan serta pengalaman extra

[_Service worker_](https://developers.google.com/web/fundamentals/primers/service-workers/) adalah komponen yang bisa diprogram dan berada di antara _browser_ dan _web server_. Dengan memasang _service worker_ maka kita bisa melakukan cache pada resources yang dibutuhkan dan juga memungkinkan aplikasi kita tetap bisa diakses dengan baik walaupun di jaringan yang tidak stabil atau [bahkan _offline_](https://developers.google.com/web/fundamentals/instant-and-offline/offline-cookbook/).

Tujuannya adalah untuk kondisi pengguna yang sudah merasakan _value_ yang kalian tawarkan dan mereka merasa ingin terus menggunakannya. Maka untuk pengguna seperti ini, mereka harus bisa merasakan pengalaman dari value yang ditawarkan lebih baik lagi. Seperti aplikasi tetap responsif di kondisi apapun.

_Service worker_ juga memungkinkan kita untuk melakukan fungsi ekstra seperti [_background sync_](https://developers.google.com/web/updates/2015/12/background-sync) __ di mana aplikasi bisa melakukan sinkronisasi data pada saat kondisi kembali online walaupun website tidak sedang dibuka, dan [_push notification_](https://developers.google.com/web/updates/2015/03/push-notifications-on-the-open-web) __ untuk mengirimkan notifikasi kepada pengguna atau menjalankan fungsi tertentu di aplikasi.

### 4. Push notification untuk mengingatkan value dan membawa pengguna kembali

Setelah pengguna betah dengan _value_ yang ditawarkan, maka selanjutnya adalah bagaimana untuk mengingatkan mereka akan _value_ kalian. Salah satu caranya tentu dengan mengingatkan mereka. Dan media yang bisa dicoba selain _email_ adalah dengan [_push notification_](https://developers.google.com/web/fundamentals/push-notifications/).

Tapi yang ini kalian harus berhati-hati jangan sampai terlalu sering mengingatkan dan akhirnya akan terganggu oleh notifikasi yang terlalu sering. Pastikan notifikasi yang kalian kirimkan memiliki kriteria agar pengguna tidak menganggap notifikasi kalian sebagai _spam_ pengganggu. Karena hasil riset yang ada menunjukkan notifikasi adalah salah satu alasan sebuah aplikasi dihapus. Dan di _web_, bila notifikasi kalian diblok maka kemungkinan besar kalian akan diblok selamanya hingga pengguna mengganti perangkat.




![image](/posts/2018-02-02_progressive-web-apps-mulai-dari-mana/images/3.png)

Source: [http://www.uxbooth.com/articles/rules-for-creating-perfect-push-notifications/](http://www.uxbooth.com/articles/rules-for-creating-perfect-push-notifications/)



### 5. Add to homescreen untuk kemudahan akses

Setelah secara kecepatan akses sudah baik dan value sudah diterima dengan baik, selanjutnya adalah memudahkan pengguna untuk mengakses aplikasi kita semudah memilih _icon_ aplikasi di layar _smart phone_. Untuk itu PWA sudah dilengkapi dengan komponen [_add to home screen_](https://developers.google.com/web/fundamentals/app-install-banners/) di mana aplikasi _web_ kalian akan menawarkan opsi untuk menyimpan icon aplikasi kalian di home screen perangkat mereka.




![image](/posts/2018-02-02_progressive-web-apps-mulai-dari-mana/images/4.gif)

Add to home screen



Cara agar tawaran ke pengguna bisa muncul adalah kalian harus melengkapi aplikasi kalian dengan [_file manifest_](https://developers.google.com/web/fundamentals/web-app-manifest/) lengkap dengan _icon_ dan _meta data_ lainnya. User yang merasakan value dan suka maka akan mencoba menggunakan aplikasi kalian lagi. Dengan memberikan kemudahan pada mereka untuk mengakses aplikasi kalian maka pengalaman pengguna akan lebih baik.

### 6. Memudahkan pengguna untuk registrasi dan masuk ke website kalian

Membuat user mendaftarkan diri mereka adalah salah satu bagian yang paling susah. Kendala pertama tentu memberikan alasan untuk mendaftarkan diri, kenapa mereka harus mendaftarkan diri mereka. Selanjutnya adalah adalah memudahkan usaha yang diperlukan untuk mendaftar atau masuk ke website kalian.

Dengan memudahkan pengguna mendaftar dan masuk ke website kalian maka kalian bisa lebih mudah dalam mempelajari tingkah laku mereka dan bisa mengetahui bagaimana kalian bisa memberikan value yang lebih baik lagi untuk pengguna kalian.

Beberapa cara untuk memudahkan pengguna untuk mendaftarkan diri dan masuk ke website kalian adalah [pengaturan _credentials_](https://developers.google.com/web/fundamentals/security/credential-management/), masuk dengan akun social media seperti Facebook atau Twitter, serta [_Google one-tap sign-up and auto sign-in_](https://developers.google.com/identity/one-tap/web/).

### 7. Memudahkan proses pembayaran

Bila kalian adalah startup atau layanan yang memerlukan proses pembayaran, salah satu isu terbesar di _mobile_ adalah kompleksitas pembayaran. Banyaknya informasi yang harus dimasukkan dengan layar dan papan ketik terbatas membuat orang kebanyakan jadi malas untuk melanjutkan.

Konversi pembayaran di _mobile_ masih di bawah _desktop_ padahal dari sisi trafik _mobile_ masih lebih besar dari _desktop_. Salah satu yang kalian bisa lakukan implementasi __ [_auto fill checkout form_](https://developers.google.com/web/updates/2015/06/checkout-faster-with-autofill) atau [_Payment Request API_](https://developers.google.com/web/fundamentals/payments/) untuk memudah pembayaran. Dua cara tersebut mampu mengurangi usaha yang diperlukan oleh pengguna untuk menyelesaikan proses pembayaran.

### Penutup

Itulah 7 langkah yang kalian bisa coba untuk memberikan pengalaman progresif atau bertahap kepada pengguna kalian di web. Dari 7 langkah tersebut, tahapan 1–3 merupakan yang paling prioritas karena bertujuan untuk memberikan kemudahan untuk pengguna bisa mengenal _value_ yang kalian tawarkan. Dan tidak harus sekaligus, kalian bisa mengimplementasikan komponen tersebut secara bertahap. Setelah itu kalian bisa melihat tergantung dari kebutuhan pengguna kalian.
