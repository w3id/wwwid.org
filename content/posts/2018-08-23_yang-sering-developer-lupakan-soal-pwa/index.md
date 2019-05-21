---
title: "Yang sering developer lupakan soal PWA"
author: "Irfan Maulana"
date: 2018-08-23T07:03:41.802Z
lastmod: 2019-05-20T16:27:36+07:00

description: ""

subtitle: "PWA (Progressive Web Apps) memang sepertinya menjadi satu hal yang sering terjadi simpang siur antar satu developer dengan developer lain…"
tags:
 - Progressive Web App 
 - Web Development 
 - Software Development 

image: "/posts/2018-08-23_yang-sering-developer-lupakan-soal-pwa/images/2.png" 
images:
 - "/posts/2018-08-23_yang-sering-developer-lupakan-soal-pwa/images/1.jpeg" 
 - "/posts/2018-08-23_yang-sering-developer-lupakan-soal-pwa/images/2.png" 


aliases:
    - "/yang-sering-developer-lupakan-soal-pwa-d26d3ee6a7ba"
---

PWA (_Progressive Web Apps_) memang sepertinya menjadi satu hal yang sering terjadi simpang siur antar satu developer dengan developer lain pun antar satu perusahaan dengan perusahaan lain baik dalam hal implementasi maupun dalam hal pemahamannya sendiri.




![image](/posts/2018-08-23_yang-sering-developer-lupakan-soal-pwa/images/1.jpeg)

Gambar dari motivasinews.com

> Disclaimer: saya pribadi menulis ini bukan berarti apa yang saya pahami adalah mutlak yang terbenar dan yang lain salah, melainkan mencoba menyampaikan apa yang saya pahami agar sama-sama berpikir ulang untuk memahami kembali apa yang selama ini sudah kita yakini benarnya.

Untuk mem-_break down_ lebih dalam, mari kita sama-sama mundur ke belakang dengan memahami kenapa PWA itu ada atau dibutuhkan.

Pada mulanya kita mesti tau bahwa pengguna internet semakin kesini memang semakin _mobile_, ini ditunjukkan dengan data bahwa pengguna yang menggunakan _mobile device_ semakin mendominasi diantara keseluruhan pengguna. Sayangnya pertumbuhan pengguna ini tidak dibarengi dengan baiknya kualitas yang harus pengguna dapatkan ketika mengakses internet lewat mobile, hal ini tentu berbanding lurus dengan _device_ yang digunakan dimana menjadi salah satu penentu baik tidaknya juga pengalaman yang akan mereka rasakan ketika mengakses internet. Keberagaman dan keterbatasan _mobile device_ diperparah dengan kondisi jaringan yang memang belum merata di beberapa negara termasuk di Indonesia. Sebagian pengguna _mobile device_ terutama di negara berkembang seperti Indonesia masih berkutat di jaringan _slow 3G_ yang tentunya masih terbatas soal kecepatan akses data.




![image](/posts/2018-08-23_yang-sering-developer-lupakan-soal-pwa/images/2.png)

Statistik dari [https://www.statista.com/statistics/241462/global-mobile-phone-website-traffic-share/](https://www.statista.com/statistics/241462/global-mobile-phone-website-traffic-share/)



Teknologi web dibandingkan apps dalam hal menangani pengguna _mobile_ ini tentu berbeda jauh, bila pengguna tidak membutuhkan internet hanya untuk membuka apps maka untuk membuka web pengguna diharuskan mendownload setiap kepingan _byte_ dari file yang dibutuhkan oleh web tersebut. Apps jelas lebih _engage_ terhadap pengguna _mobile_ dibandingkan web apalagi dengan kemampuannya mengakses sistem dan hardware dari _device_ pengguna itu sendiri. Sayangnya untuk meng-_install_ suatu apps didalam _device_ masih dibutuhkan _effort_ yang lumayan karena mereka harus menyiapkan _storage_ yang mana jumlahnya juga seringkali terbatas.

Maka PWA hadir mencoba menjembatani dan mengurangi _gap_ antara teknologi web dengan teknologi apps. Tujuannya jelas memberikan pengalaman yang lebih baik terhadap pengguna _mobile device_ ketika mengakses web.

Setelah memahami kenapa harus ada PWA, maka berikutnya akan saya rangkumkan beberapa hal yang seringkali terjadi salah persepsi dan adopsi mengenai PWA:

#### Tidak melihat kebutuhan dan kondisi pengguna

Ya, PWA dibuat dengan fokus utama untuk menyajikan pengalaman yang _progressive_ kepada pengguna ketika mengakses sebuah website. Masalahnya ada banyak developer (termasuk saya) yang seringkali mencoba mengimplementasikan sesuatu tanpa melihat pada kebutuhan pengguna serta data yang kita miliki mengenai pengguna kita. Sebetulnya sebelum memutuskan untuk menggunakan PWA, terlebih dahulu sebaiknya kita memahami berbagai hal mengenai pengguna kita seperti menjawab beberapa pertanyaan seperti siapa mereka? _device_ apa yang mereka gunakan? bagaimana persebaran wilayah mereka? jaringan apa yang mereka gunakan? seberapa penting menghemat penggunaan _bandwidth data_ buat mereka? berapa besar persentase _bounce rate_ dari keseluruhan pengguna? konten apa yang benar-benar dibutuhkan oleh pengguna kita? serta banyak lagi pertanyaan yang akan membuat kita lebih paham dengan kondisi pengguna kita.

Setelah memahami kebutuhan dan kondisi pengguna, barulah kita bisa memutuskan PWA yang seperti apa yang ingin dan harus kita buat untuk membantu menyelesaikan masalah yang dihadapi pengguna. Cerita mengenai memahami kebutuhan pengguna sebelum membuat PWA bisa dibaca di artikel “[Bagaimana Kulina Bisa Mendapatkan 41.000 Lebih Pelanggan Melalui Web](https://medium.com/wwwid/bagaimana-kulina-bisa-mendapatkan-41-000-lebih-pelanggan-melalui-web-d00af6165880)” oleh [Yohan Totting](https://medium.com/u/19ca0cae7023).

#### Terlalu fokus pada fitur

PWA punya segudang fitur dan kemampuan, sayangnya banyak kita (developer) yang sering terkecoh dengan fitur-fitur ini. Seolah ingin agar semua fitur yang dimiliki PWA diadopsi kedalam website kita padahal sebenarnya sama sekali tidak dibutuhkan oleh pengguna. Masing-masing fitur memiliki fungsi dan konteks yang berbeda-beda. Lebih baik bagi kita jika mengadopsi sedikit fitur namun sesuai dengan kebutuhan daripada berusaha menumpuk semua fitur namun tidak tepat guna, tidak tepat konteks dan tidak pernah digunakan oleh pengguna.

Contoh dari beberapa kesalahan ini bisa ditemui dari tulisan [Satya Kresna Adi Pratama](https://medium.com/u/2645da69fbda) di “[Berbagi Pengalaman menggunakan Web yang Progresif](https://medium.com/wwwid/berbagi-pengalaman-menggunakan-web-yang-progresif-3d8682001343)”, dimana banyak website yang mencoba mengimplementasi _push notification_ dengan cara yang liar tanpa melihat konteks kapan waktu yang tepat bagi pengguna mendapatkan tawaran untuk berlangganan _push notification,_ kapan waktu yang pas untuk mengirimkan pesan notifikasi tersebut kepada pengguna, serta konten seperti apa yang cocok untuk pengguna dapatkan di _push notification_ itu.

#### Berpikir bahwa PWA hanya soal Service Worker

Salah satu _core_ PWA memang [_service worker_](https://developers.google.com/web/fundamentals/primers/service-workers/), tapi bila ingin memberikan pengalaman yang _progressive_ untuk pengguna kita maka saya jamin _service worker_ saja tidak akan cukup untuk memberikan perbedaan yang signifikan dari sebelumnya. PWA akan lebih optimal bila didukung dengan berbagai hal seperti diantaranya UX/UI yang mudah dan bersahabat, performa website yang baik (baca: “[Berbagai best practice dalam memuat halaman website](https://medium.com/wwwid/berbagai-best-practice-dalam-memuat-halaman-website-20def6652adf)”), mendukung _accessibility_ yang baik, kemampuan diakses _offline_, _caching_ yang tepat, beradaptasi sesuai kondisi jaringan (baca: “[Web Pintar Yang Beradaptasi Sesuai Perangkat dan Jaringan](https://medium.com/wwwid/web-pintar-yang-beradaptasi-sesuai-perangkat-dan-jaringan-78f4496915a4)”) dan banyak hal lainnya yang mendukung.

#### Berpikir bahwa PWA merupakan one hit and run task

PWA seringkali dikerjakan oleh para developer (termasuk saya) dengan _one-hit and run task_, yang artinya dikerjakan dalam satu waktu kemudian di _ship_ ke _production_ dan pekerjaan selesai, tanpa pernah dilihat lagi dan dikaji ulang setelahnya.

PWA sebenarnya membutuhkan perhatian lebih, setelah mengirimkan PWA ke _production_ sebaiknya kita juga memantau data yang bisa kita dapatkan seperti seberapa banyak pengguna yang terbantu dengan fitur PWA kita, berapa pengguna yang melakukan A2HS di _device_ mereka, seberapa besar _cache_ yang dilakukan s_ervice worker_ memakan memori pengguna, seberapa membantu _cache_ yang dilakukan s_ervice worker_ dan hal lainnya.

Setelah memantau berbagai data kita bisa memperbaiki PWA kita agar lebih sesuai dengan kondisi pengguna kita. Intinya membangun PWA adalah proses yang harus dilakukan secara berulang dari _analyze_, _build_, _ship_, _measure_, _fix_, _ship again_, and _repeat again_.Kita sebagai developer seringkali terjebak dengan banyak hal teknis dan lupa bahwa ada banyak hal yang mesti diperhatikan ketika membuat sebuah fitur untuk pengguna. Mari sama-sama belajar memahami pengguna kita dan _let’s be a better developer!!!_Bila kamu suka dengan tulisan ini, silahkan tekan tombol 👏 sebanyak-banyaknya dan mohon bantuannya untuk share 📲 di sosial media kalian bila kalian rasa artikel ini akan bermanfaat bagi orang lain.

Saya [Irfan Maulana](https://medium.com/u/d09eac079a9c), kalian bisa ikuti tulisan-tulisan saya di berbagai publikasi Medium seperti [Vuejs-ID](https://medium.com/vuejs-id), [AngularID](https://medium.com/angularid), [WWWID](https://medium.com/wwwid/), dan [mazipan-mind](https://medium.com/mazipan-mind). Saya menulis berbagai hal teknikal maupun non-teknikal terkait dengan dunia programming terutama yang berkaitan dengan web programming dan sebagian besar saya tulis dalam bahasa Indonesia. Saya juga senang bereksplorasi dan membuat berbagai percobaan mengenai apa yang saya sudah atau sedang saya pelajari. Anda bisa ikuti dan lihat semuanya di Github saya di [🐙 mazipan](https://github.com/mazipan).
