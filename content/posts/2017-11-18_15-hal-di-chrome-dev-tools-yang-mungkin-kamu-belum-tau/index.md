---
title: "15 Hal di Chrome Dev Tools yang Mungkin Kamu Belum Tau"
author: "Putu Alfred Crosby"
date: 2017-11-18T12:26:11.148Z
lastmod: 2019-05-20T16:26:32+07:00
featured: true
description: ""

subtitle: "No 8 bikin netizen geleng-geleng kepala."
tags:
 - Chrome 
 - Front End Development 
 - Frontend 

image: "/posts/2017-11-18_15-hal-di-chrome-dev-tools-yang-mungkin-kamu-belum-tau/images/4.png" 
images:
 - "/posts/2017-11-18_15-hal-di-chrome-dev-tools-yang-mungkin-kamu-belum-tau/images/1.png" 
 - "/posts/2017-11-18_15-hal-di-chrome-dev-tools-yang-mungkin-kamu-belum-tau/images/2.png" 
 - "/posts/2017-11-18_15-hal-di-chrome-dev-tools-yang-mungkin-kamu-belum-tau/images/3.png" 
 - "/posts/2017-11-18_15-hal-di-chrome-dev-tools-yang-mungkin-kamu-belum-tau/images/4.png" 
 - "/posts/2017-11-18_15-hal-di-chrome-dev-tools-yang-mungkin-kamu-belum-tau/images/5.png" 
 - "/posts/2017-11-18_15-hal-di-chrome-dev-tools-yang-mungkin-kamu-belum-tau/images/6.png" 
 - "/posts/2017-11-18_15-hal-di-chrome-dev-tools-yang-mungkin-kamu-belum-tau/images/7.png" 
 - "/posts/2017-11-18_15-hal-di-chrome-dev-tools-yang-mungkin-kamu-belum-tau/images/8.png" 
 - "/posts/2017-11-18_15-hal-di-chrome-dev-tools-yang-mungkin-kamu-belum-tau/images/9.png" 
 - "/posts/2017-11-18_15-hal-di-chrome-dev-tools-yang-mungkin-kamu-belum-tau/images/10.png" 
 - "/posts/2017-11-18_15-hal-di-chrome-dev-tools-yang-mungkin-kamu-belum-tau/images/11.png" 


aliases:
    - "/15-hal-di-chrome-dev-tools-yang-mungkin-kamu-belum-tau-1ca76a31305"
---

![image](/posts/2017-11-18_15-hal-di-chrome-dev-tools-yang-mungkin-kamu-belum-tau/images/1.png)

Chrome Developer Tools

#### No 8 bikin netizen geleng-geleng kepala.


K
etika mengembangkan sebuah aplikasi web, tentunya kita tak jauh dari yang namanya debugging. Chrome Dev Tools adalah salah satu tools debugging yang sering digunakan. Setelah sekian lama menggunakammya, akhirnya saya menemukan beberapa _hidden-gems_ yang ada di Chrome Dev Tools, dan beberapa saya selalu gunakan dalam kehidupan saya sebagai engineer sehari-hari. 😹

Berikut ini adalah list fitur dan tips nya:

#### 1. Throttle Network &amp; CPU




![image](/posts/2017-11-18_15-hal-di-chrome-dev-tools-yang-mungkin-kamu-belum-tau/images/2.png)

Throttling juga dapat diakses melalui **Tab** **Network**.



Dari namanya sudah lumayan intuitif, jadi fungsi dari throttling adalah _mencekik_ koneksi atau CPU. Dengan tools ini kita bisa mensimulasikan bagaimana webapp kita berjalan di koneksi atau _device_ yang lemot. Kalian bisa mengaktifkan fitur ini pada tab **Performance** lalu klik _icon gear_ yang terdapat di pojok kanan**.**

#### **2. Three-snapshots technique**

Merupakan sebuah teknik yang terkenal untuk mencari _memory-leak_ pada webapp kita, yaitu dengan cara mengambil 3 buah snapshot dan membandingkannya dengan tiap snapshot. Langkah simpelnya seperti ini:

1.  Mengambil snapshot #1 ketika webapp pertama kali di load
2.  Melakukan sesuatu (Contoh: klik pada suatu elemen yang kita curigai mengonsumsi memory terbanyak)
3.  Ambil snapshot #2
4.  Melakukan sesuatu yang sama dengan sebelumnya untuk memastikan lagi apakah benar elemen tersebut penyebab _memory-leak_
5.  Ambil snapshot #3
6.  Bandingkan antar snapshot.

Untuk mengambil snapshot dapat dilakukan pada **Tab Memory**




![image](/posts/2017-11-18_15-hal-di-chrome-dev-tools-yang-mungkin-kamu-belum-tau/images/3.png)

Tab Network pada Chrome Dev Tools



Mungkin ada yang penasaran tentang cara menggunakan teknik three-snapshot teman-teman bisa baca lebih detailnya [disini](https://addyosmani.com/blog/taming-the-unicorn-easing-javascript-memory-profiling-in-devtools/).

#### 3. Audits

Bagi teman-teman yang sedang mengerjakan [PWA](https://medium.com/wwwid/pengenalan-progressive-web-app-pwa-bagian-1-cac0fadbe5f4), kalian tidak akan bisa jauh dari fitur ini. **Tab Audit** digunakan untuk menilai score [PWA](https://medium.com/wwwid/pengenalan-progressive-web-app-pwa-bagian-1-cac0fadbe5f4), Performance, Best Practice dan Accessbility webapp kita. Cara pakai nya sangat simpel. Tinggal klik tombol Perform an Audit dan tunggu hasilnya.




Audits PWA



#### 4. Network Filmstrip

Jika kalian perhatikan cover artikel ini, disana terdapat screenshot dari proses load webapp. Keren banget kan? Bagaimana cara menggunakan fitur ini?

Caranya dengan menuju **Tab** **Performance** kemudian centang **Screenshot** lalu klik Start Profiling yaitu icon refresh yang terdapat di pojok kiri.




![image](/posts/2017-11-18_15-hal-di-chrome-dev-tools-yang-mungkin-kamu-belum-tau/images/4.png)

Menampilkan filmstrip proses load sebuah webapp pada chrome dev tools



Fitur ini sangat bermanfaat jika dikombinasikan dengan fitur throttle network untuk memvisualisasikan bagaimana halaman ditampilkan pada koneksi slow 3g(misalkan) pada detik tertentu.

Pada **Tab Performance** juga kalian bisa melihat **Flame Graph** dari app kalian, seberapa lama sebuah fungsi dieksekusi atau seberapa dalam stack fungsi-fungsi tersebut. Jika kalian bingung membaca flame graph, kalian bisa belajar melalui [slide](https://speakerdeck.com/mrfoto/what-are-flame-graphs-and-how-to-read-them) ini atau dari artikel [ini](http://www.brendangregg.com/FlameGraphs/cpuflamegraphs.html).

#### 5. Paint flashing &amp; FPS meter

Fitur ini biasa digunakan untuk melihat element yang sedang di render oleh browser. Khususnya ketika mengembangkan sebuah SPA (Single Page Application) jika menggunakan virtual-dom (React, Preact, etc) kita tanpa sadar mengabaikan performa app kita dengan me-render ulang sebuah komponen yang datanya identik (m_engingat library seperti react akan melakukan render jika props yang baru di pass ke dalam sebuah komponen_).

Untuk mengetahui mana komponen yang melakukan _waste-render_, salah satu caranya adalah menggunakan _paint flashing_.

Untuk mengakses fitur ini bisa dari Tab manapun, tekan **Esc** akan menampilkan section baru di bawah Chrome dev tools. Sisanya kalian bisa lihat di video di bawah ini.




Melihat proses render pada Chrome



#### 6. Beautify Scripts

Pernahkah teman-teman menginspect sebuah scripts di web tertentu kemudian yang kita buka merupakan scripts yg sudah di _uglify?_

Di Chrome kita bisa buat script yg _uglified_ tadi jadi _human-readable._ Caranya dengan menekan tombol {} di Tab Source.




Mempercantik tampilan scripts pada Chrome dev tools



#### 7. XHR/Fetch information

Teman-teman juga bisa melihat data-data yang dikirim dan diterima oleh sebuah webapp. Untuk melihatnya kalian bisa pergi ke Tab Network dan klik pada sebuah request untuk melihat detail dan respon nya. (jangan digunakan untuk melakukan kejahatan ya guys 😿)






#### 9. Capture Screenshot

Kini untuk mengambil screenshot dari webapp kita tidak perlu lagi menginstall Chrome extension. Cukup mengaktifkan mobile-device mode kemudian klik ellipsis dan pilih Screenshot atau Full Screenshot.




Capture Screenshot di Chrome Dev Tools





![image](/posts/2017-11-18_15-hal-di-chrome-dev-tools-yang-mungkin-kamu-belum-tau/images/5.png)

Dark Theme FTW 😎



#### 10. Dark Theme

Fitur favorit saya dan menurut saya paling penting 😋 Bagaimana cara mengaktifkannya?

Teman-teman cukup tekan F1 kemudian pada section theme pilih Dark

#### 11. Devtools Docking Position

Mungkin teman-teman dari tadi kesel lihat kenapa devtools saya selalu di sebelah kanan. Kebetulan pekerjaan sehari-hari saya adalah seorang Mobile-Web Engineer jadi untuk kenyamanan mengembangkan aplikasi web, saya memindahkan posisi devtool ke sebelah kanan. Bagaimana caranya?

Teman-teman bisa menggunakan shortcut `CMD + Shift + D` untuk OSX, atau `Ctrl + Shift + D` untuk *nix &amp; Windows; atau bisa juga melalui menu yang tersedia di devtools seperti yang ditunjukan pada gambar dibawah ini.




![image](/posts/2017-11-18_15-hal-di-chrome-dev-tools-yang-mungkin-kamu-belum-tau/images/6.png)

Devtools docking position



#### 12. $0 in console

$0 adalah cara cepat dari `getElementBy*` untuk memilih sebuah element di console. Pertama kalian harus klik memilih element tersebut, kemudian ketik $0 pada console. Contohnya bisa dilihat pada gambar dibawah ini.



![image](/posts/2017-11-18_15-hal-di-chrome-dev-tools-yang-mungkin-kamu-belum-tau/images/7.png)

$0 pada Chrome Dev Tools

#### 13. Preserve Logs

Preserve log biasanya digunakan untuk tetap menyimpan log ketika halaman di refresh atau ketika alamat web berpindah. Secara default jika kita melakukan log pada web app kita, contoh jika menggunakan`console.log()`, dan jika kita refresh, maka log tersebut akan hilang. Tapi dengan mengaktifkan **preserve log** maka log kita akan tetap ada di **Tab Console.**

Untuk mengaktifkan fitur ini, teman-teman bisa pergi ke Tab Console lalu klik icon gear, kemudian centang **Preserve Logs.**




![image](/posts/2017-11-18_15-hal-di-chrome-dev-tools-yang-mungkin-kamu-belum-tau/images/8.png)

Log tetap ada walaupun halaman sudah di refresh.



#### 14. Check Rendered Fonts

Pernah penasaran dengan font yang digunakan oleh sebuah situs? Untuk mengetahuinya caranya gampang banget. Inspect text yang diinginkan kemudian pada **Tab** **Element** sebelah kanan terdapat beberapa tabs. Pilih tab **Computed**, dan lihat baris paling bawah 😎




Mencari tahu font yang digunakan oleh sebuah website



#### 15. Remote Debug UC Browser menggunakan Chrome Dev Tools

Ini adalah salah satu hal yang paling wajib diketahui. Kenapa? Karena pengguna mobile UC browser di Indonesia sangat banyak.




![image](/posts/2017-11-18_15-hal-di-chrome-dev-tools-yang-mungkin-kamu-belum-tau/images/9.png)

Sumber: [http://gs.statcounter.com/browser-market-share/mobile/indonesia](http://gs.statcounter.com/browser-market-share/mobile/indonesia)



Nah, ketika mengembangkan aplikasi, terkadang kita menemukan masalah cross-browser. Bagaimana cara debugging UC browser atau mobile browser lainnya melalui desktop/laptop?

Ada banyak cara untuk debugging mobile browser tergantung dari platform dan merk. Umumnya orang-orang menggunakan tools tambahan seperti [weinre](https://www.npmjs.com/package/weinre), namun disini saya akan menjelaskan langkah-langkahnya hanya dengan Android saja. (tanpa tools tambahan)

1.  Aktifkan mode developer. Bagi yang belum tahu caranya bisa dilihat [disini](http://blog.syncios.com/enable-developer-optionsusb-debugging-mode-on-devices-with-android-4-2-jelly-bean/).
2.  Download .apk [UC Browser Developer Edition](http://www.uc.cn/business/developer) (Bahasa Mandarin 😂)
3.  Masukkan alamat yang ingin di-inspect.
4.  Buka [chrome://inspect](about:invalid#zSoyz)
5.  Device dan browser akan muncul di list. Lalu klik inspect 👌🏻



![image](/posts/2017-11-18_15-hal-di-chrome-dev-tools-yang-mungkin-kamu-belum-tau/images/10.png)

Screenshot by @wayanjimmy



### Bonus:

#### 16. Show Redux State from React App

Biasanya kita akan men-disable redux dev tools di production. Namun kadang kita penasaran ingin melihat bagaimana bentuk redux state tersebut, atau juga kadang kita penasaran dengan redux state website orang lain 😂

Yang perlu disiapkan adalah:

1.  Install [React devtools](https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi?hl=en).
2.  Web yang akan kita inspect menggunakan react, dan masih mengaktifkan react-devtools. Contoh yang saya ambil disini adalah Twitter.
3.  Pergi ke Tab React, cari komponen yang mempunyai props store, lalu pilih komponen tersebut. (cukup 1x klik pada komponen tersebut)
4.  Pergi ke console lalu ketik. `$r.props.store.getState()`



![image](/posts/2017-11-18_15-hal-di-chrome-dev-tools-yang-mungkin-kamu-belum-tau/images/11.png)

Melihat redux state sebuah react website.

### Conclusion

Dari list di atas, fitur dan tips manakah yang akan kalian praktekan? 😂 atau fitur manakah yang membuat kalian penasaran?

Tentunya masih banyak fitur-fitur yang saya belum tahu, **jika kalian mempunyai beberapa jutsu atau tips menggunakan Chrome Developer Tools jangan ragu untuk beritahu saya dan akan saya tambahkan di artikel ini**. 👌🏻

Jika kalian anggap artikel ini bermanfaat, jangan lupa bagikan ke teman-teman yang lain. 😉
