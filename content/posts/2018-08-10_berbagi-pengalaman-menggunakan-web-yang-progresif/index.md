---
title: "Berbagi Pengalaman menggunakan Web yang Progresif"
author: "Satya Kresna Adi Pratama"
date: 2018-08-10T13:28:02.330Z
lastmod: 2019-05-20T16:27:33+07:00

description: ""

subtitle: "Jika pengembang mobile harus mengupload ke Google Play / App Store (belum ditambah dengan pengujian atau persetujuan aplikasi dari mereka)…"
tags:
 - Web Yang Progresif 
 - Pwa 
 - Push Notification 
 - Web Share 
 - Extra Feature On Web 

image: "/posts/2018-08-10_berbagi-pengalaman-menggunakan-web-yang-progresif/images/17.png" 
images:
 - "/posts/2018-08-10_berbagi-pengalaman-menggunakan-web-yang-progresif/images/1.png" 
 - "/posts/2018-08-10_berbagi-pengalaman-menggunakan-web-yang-progresif/images/2.png" 
 - "/posts/2018-08-10_berbagi-pengalaman-menggunakan-web-yang-progresif/images/3.png" 
 - "/posts/2018-08-10_berbagi-pengalaman-menggunakan-web-yang-progresif/images/4.png" 
 - "/posts/2018-08-10_berbagi-pengalaman-menggunakan-web-yang-progresif/images/5.png" 
 - "/posts/2018-08-10_berbagi-pengalaman-menggunakan-web-yang-progresif/images/6.png" 
 - "/posts/2018-08-10_berbagi-pengalaman-menggunakan-web-yang-progresif/images/7.png" 
 - "/posts/2018-08-10_berbagi-pengalaman-menggunakan-web-yang-progresif/images/8.png" 
 - "/posts/2018-08-10_berbagi-pengalaman-menggunakan-web-yang-progresif/images/9.png" 
 - "/posts/2018-08-10_berbagi-pengalaman-menggunakan-web-yang-progresif/images/10.png" 
 - "/posts/2018-08-10_berbagi-pengalaman-menggunakan-web-yang-progresif/images/11.png" 
 - "/posts/2018-08-10_berbagi-pengalaman-menggunakan-web-yang-progresif/images/12.png" 
 - "/posts/2018-08-10_berbagi-pengalaman-menggunakan-web-yang-progresif/images/13.png" 
 - "/posts/2018-08-10_berbagi-pengalaman-menggunakan-web-yang-progresif/images/14.png" 
 - "/posts/2018-08-10_berbagi-pengalaman-menggunakan-web-yang-progresif/images/15.png" 
 - "/posts/2018-08-10_berbagi-pengalaman-menggunakan-web-yang-progresif/images/16.png" 
 - "/posts/2018-08-10_berbagi-pengalaman-menggunakan-web-yang-progresif/images/17.png" 


aliases:
    - "/berbagi-pengalaman-menggunakan-web-yang-progresif-3d8682001343"
---

Jika pengembang mobile harus mengupload ke Google Play / App Store (belum ditambah dengan pengujian atau persetujuan aplikasi dari mereka), pengembang web cukup memiliki yang namanya URL a.k.a link situs website kita dan kirimkan ke penggunanya. Bahkan jika ada pembaharuan mulai dari interface dan fungsionalitas maka web adalah pemenangnya dibandingkan mobile (native). Mungkin ini yang bisa katakan “Kekuatan URL yang sesungguhnya”.

Saat ini, Progressive Web Apps (PWA) atau web yang progresif telah menjadi primadona bagi para web developer untuk menciptakan pengalaman web yang lebih baik kepada penggunanya sehingga bisa meminimalisir pembuatan aplikasi berbasis mobile (Android dan iOS). Jika Anda ingin tahu darimana harus memulai PWA bisa merujuk di artikel ini “[PWA, mulai dari mana?](https://medium.com/wwwid/progressive-web-apps-mulai-dari-mana-bd223a941782)” dan studi kasus yang layak dijadikan sebuah web yang progresif di artikel “[Progressive Web App For Startups — User Acquisition](https://medium.com/@tyohan/progressive-web-app-for-startups-user-acquisition-e1f9ec05afe6)” yang telah saya beri tanda highlight.

Kali ini saya akan berbagi pengalaman saya sebagai pengguna menggunakan web progresif. Studi kasus yang saya ambil adalah bagian notifikasi dan fitur ekstra yang disediakan oleh web progresif tersebut.

Adapun spesifikasi yang saya gunakan untuk menguji web progresif ini:

1.  Smartphone Xiaomi A1 sesuai [GSM Arena](https://www.gsmarena.com/xiaomi_mi_a1_%28mi_5x%29-8776.php).
2.  Chrome browser versi 68.0.3440.85.
3.  Operating System: Android 8.1.0; Mi A1 Build/OPM1.171019.026.
4.  Waktu pengujian berkisar di bulan awal Agustus sampai 10 Agustus 2018.

### Notifikasi

Manusia tidak ingin ketinggalan dengan informasi atau isu yang mengaitkan dirinya atau yang ingin dicari. Kadang kala manusia juga bisa lupa terhadap suatu hal karena kesibukan dan lain sebagainya. Karena itu, fitur notifikasi menjadi kunci utama. Hanya saja jika notifikasi tidak diiringi dengan teknik yang benar hal ini akan berdampak fatal bagi Anda sebagai developer dan user.

Di JSConf 2018, Phil Nash menjelaskan terdapat 3 esensi notifikasi:

1.  Timely (tepat waktu).
2.  Actionable (dapat ditindaklanjuti).
3.  Personal (pribadi).

Untuk detailnya silahkan Anda tonton di video yang berjudul “[Agressive Web Apps](https://www.youtube.com/watch?v=uo-UOvq3-0Y)”. Jika Anda membutuhkan referensi tambahan tentang tips dan trik menampilkan push notification, Anda bisa membaca artikel yang berjudul “[Web Push Checklist](https://medium.com/@senthil_hi/the-web-push-checklist-3d7ee1225901)”.

Jika saya sebagai user, saat mengakses web untuk pertama kalinya maka saya hanya ingin mencari informasi yang ada di dalam web tersebut bukannya mendapatkan notifikasi. Jika web tersebut bernilai penting bagi saya maka saya akan meminta notifikasi dari web tersebut.

Berikut adalah contoh notifikasi baik dan kurang baik berdasarkan pengalaman saya sebagai user.

### Notifikasi yang baik

#### Twitter Lite (PWA)

Twitter layak memenuhi kriteria dalam urusan menampilkan notifikasi di mata saya sebagai user. Notifikasi yang ditampilkan adalah (sejauh yang saya alami):

1.  Mention.
2.  Direct Message.
3.  Tweet yang dilike atau diretweet oleh orang yang saya follow.



![image](/posts/2018-08-10_berbagi-pengalaman-menggunakan-web-yang-progresif/images/1.png)





![image](/posts/2018-08-10_berbagi-pengalaman-menggunakan-web-yang-progresif/images/2.png)

Notifikasi mention, like dan DM di Twitter yang melibatkan diri saya.





![image](/posts/2018-08-10_berbagi-pengalaman-menggunakan-web-yang-progresif/images/3.png)





![image](/posts/2018-08-10_berbagi-pengalaman-menggunakan-web-yang-progresif/images/4.png)

Notifikasi dari Twitter berdasarkan orang yang kita follow.

Bahkan saat pertama kali saya membuka web mereka lewat mobile, tampilan notifikasi nya bukanlah modal pop up melainkan sebuah card yang menjadi satu dengan timeline saya di Twitter. Itupun muncul saat saya scroll ke bawah sedikit.




![image](/posts/2018-08-10_berbagi-pengalaman-menggunakan-web-yang-progresif/images/5.png)

Notifikasi muncul pertama kali saat membuka Twitter PWA



Update per tanggal 11 Agustus 2018: Seingat saya Twitter Lite memiliki fitur push notification yang ditaruh di menu settings. Setelah saya mencobanya, ternyata old pop-up dialog milik browser dibungkus dengan UI notification milik mereka.






Sisi bagusnya adalah Twitter mengemas push notification dengan baik di dalam menu settings (Good UX) dan sisi buruknya adalah saat saya menekan tombol “Turn on” saya dihadapkan pada old pop-up notification milik browser sehingga saya membuang waktu satu langkah saya untuk mengaktifkan notifikasi. **Update 22 September 2018:** Namun, setelah diselidiki ternyata memang di desain seperti itu dan merupakan hal default di browser. Hal ini juga bertujuan agar developer tidak usil mengaktifkan permission tanpa ijin pengguna browser.

#### Instagram (PWA)

Instagram sedang berinovasi membuat pengalaman web yang lebih baik melalui web yang progresif. Saat [di Chrome Dev. Summit 2017](https://www.youtube.com/watch?v=UTZVXlcUK1w&amp;t=420s), mereka mengklaim bahwa playing video di Instagram di web lebih cepat dibandingkan mobile berkat [Shaka Player](https://github.com/google/shaka-player).

Untuk urusan notifikasi, Instagram memiliki cara tersendiri. Mereka memilih menggunakan pop up namun dipoles dengan tampilan yang ciamik dan menawan.




![image](/posts/2018-08-10_berbagi-pengalaman-menggunakan-web-yang-progresif/images/6.png)

Notikasi muncul saat pertama kali membuka Instagram web dan disertai dengan A2HS.



#### Linkedin (PWA)

Meskipun Linkedin sudah berhasil memikat hati saya tentang notifikasi yang actionable, tetapi tampilan notifikasinya dibungkus berlapis saat saya mengakses hal web mereka pertama kali. Hal ini wajar karena hal tersebut merupakan ijin standar yang ditetapkan oleh browser agar developer tidak jahil melakukan trigger langsung ke default permission browser.



![image](/posts/2018-08-10_berbagi-pengalaman-menggunakan-web-yang-progresif/images/7.png)





![image](/posts/2018-08-10_berbagi-pengalaman-menggunakan-web-yang-progresif/images/8.png)

Kiri — Kanan: Tampilan pertama saat membuka web linkedin pertama kali dan tampilan kedua muncul setelah saya menekan tombol “YES” di toast Linkedin.

#### Linkedin (PWA)

Meskipun Linkedin belum mengimplementasikan A2HS, langkah mereka membuat notifikasi yang dapat ditindaklanjuti (actionable) patut diapresiasi. Salah satunya ketika seseorang ingin terhubung dengan kita di Linkedin.



![image](/posts/2018-08-10_berbagi-pengalaman-menggunakan-web-yang-progresif/images/9.png)





![image](/posts/2018-08-10_berbagi-pengalaman-menggunakan-web-yang-progresif/images/10.png)

Linkedin mengirimkan notifikasi ada seseorang yang ingin terhubung dengan kita dan Notifikasi Linkedin terkait dengan postingan kita.

Berikut saya berikan contoh video saya memperagakan notifikasi dari Linkedin dengan studi kasus orang ingin terhubung dengan saya.




Demo video menekan tombol accept di Linkedin (PWA)





Demo video menekan tombol setting di Linkedin (PWA)



#### Tech In Asia Indonesia (PWA)

TIA Indonesia berinovasi membuat pengalaman web yang baik dengan fitur notifikasi.



![image](/posts/2018-08-10_berbagi-pengalaman-menggunakan-web-yang-progresif/images/11.png)





![image](/posts/2018-08-10_berbagi-pengalaman-menggunakan-web-yang-progresif/images/12.png)

Kiri — Kanan: Tampilan pertama saat membuka web TIA ID pertama kali dan tampilan kedua muncul setelah saya menekan tombol “ALLOW” di toast TIA ID.

### Notifikasi kurang baik

#### Bukalapak (PWA)

Situs e-commerce besar di Indonesia, Bukalapak saat ini menggunakan A2HS dan push notification untuk meningkatkan keterlibatan pengguna (user engagement) lewat web mereka. Hanya saja notifikasi yang ditampilkan tidak relevan menurut saya salah satunya adalah notifikasi website mereka diupdate dibalik layar.




![image](/posts/2018-08-10_berbagi-pengalaman-menggunakan-web-yang-progresif/images/13.png)

Notifikasi dari Bukalapak yang tidak penting



#### Tokopedia (PWA)

Situs e-commerce besar selanjutnya di Indonesia, Tokopedia juga membuat fitur A2HS dan push notification seperti Bukalapak dengan tujuan yang sama. Hanya saja notifikasi muncul saat pertama kali membuka web mereka di mobile browser dan tampilannya pun tidak dipoles dengan baik (hanya pop-up biasa).




![image](/posts/2018-08-10_berbagi-pengalaman-menggunakan-web-yang-progresif/images/14.png)

Notifikasi muncul saat pertama kali membuka web Tokopedia

> Catatan untuk Bukalapak dan Tokopedia: Jika saya adalah user, yang saya inginkan adalah notifikasi tracking barang yang sudah saya kirim sudah sampai mana dan kapan kira-kira akan sampai.

**Facebook (PWA)**

Saat ini Facebook sedang [gencar-gencarnya menguji PWA mereka](https://www.androidpolice.com/2018/07/26/facebook-testing-proper-progressive-web-app-mobile-website/). Tinggal menunggu waktu kapan PWA mereka akan meluncur. Seperti biasa, saat saya mengakses Facebook di mobile web pertama kali, tampilan notifikasi tidak jauh berbeda dengan Tokopedia.




![image](/posts/2018-08-10_berbagi-pengalaman-menggunakan-web-yang-progresif/images/15.png)

Notifikasi muncul saat pertama kali membuka Facebook web



**Kompas dan Detik (PWA)**

Kompas dan Detik yang merupakan situs berita yang sering diakses oleh netizen Indonesia, menampilkan notifikasi tidak jauh berbeda dengan dengan Facebook dan Tokopedia.



![image](/posts/2018-08-10_berbagi-pengalaman-menggunakan-web-yang-progresif/images/16.png)

### Fitur Ekstra

#### Another Tweet (Twitter Lite PWA)

Twitter Lite membuat sebuah fitur baru (yang saya akses 10 Agustus 2018) yakni “another tweet”. Dengan adanya fitur ini memudahkan kita untuk membuat tweet berantai seperti gambar di bawah.




![image](/posts/2018-08-10_berbagi-pengalaman-menggunakan-web-yang-progresif/images/17.png)

Another Tweet di Twitter Lite



#### Web Share (Twitter Lite PWA)

Inovasi Twitter Lite membuat sebuah tweet dapat di share ke beberapa aplikasi native di mobile kita patut diacungi jempol. Dengan hal ini, kita tidak perlu screenshot tweet seseorang dan langsung bagikan ke rekan atau kita. Untuk mempelajari fitur Web Share, bisa dilihat pada artikel yang berjudul “[Introducing the Web Share API](https://developers.google.com/web/updates/2016/09/navigator-share)”. Berikut contoh demo video dari web share Twitter Lite PWA




Fitur Web Share Twitter Lite PWA



#### Night Mode (Twitter PWA)

Twitter memiliki fitur mengubah tampilan menjadi hitam a.k.a night mode. Sehingga hal ini membuat mata kita nyaman membaca timeline di Twitter.




Night mode in Twitter Lite



#### Data Saver (Twitter PWA)

Jika kuota internet Anda terbatas dan tidak ingin menampilkan gambar, Twitter telah menyediakan fitur data saver sebagai penyelamat Anda.




Data saver in Twitter Lite



Dari hal yang saya paparkan di atas, saya berharap ini akan menjadi pembelajaran bagi kita selaku developer, inspirasi bagi stakeholder web di Indonesia untuk menciptakan pengalaman web yang lebih baik dan tepat sasaran bagi pengguna.

**Catatan:**

1.  Artikel ini akan saya perbaharui (diusahakan) jika terdapat fitur menarik dan berguna yang disediakan oleh situs-situs web yang progresif.
2.  Gambar dan video murni saya buat sendiri. Semua ini demi pembelajaran yang lebih baik.

Terima kasih sudah membaca artikel ini, semoga bermanfaat dan jangan ragu berkomentar atau berbagi jika ada fitur web progresif yang menarik di artikel ini atau lewat grup [WWWIDPWA via telegram](https://t.me/wwwid_pwa).
