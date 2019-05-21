---
title: "Pembelajaran yang saya dapatkan dari Chrome Dev Summit untuk Indonesia"
author: "Yohan Totting"
date: 2017-10-30T02:26:01.616Z
lastmod: 2019-05-20T16:26:21+07:00

description: ""

subtitle: "Saya baru balik dari Chrome Dev Summit dan tulisan ini ingin merangkum beberapa hal yang saya dapatkan dari event tahunan team Chrome untuk…"
tags:
 - Web Development 
 - Chrome Dev Summit 
 - Progressive Web App 

image: "/posts/2017-10-30_pembelajaran-yang-saya-dapatkan-dari-chrome-dev-summit-untuk-indonesia/images/4.png" 
images:
 - "/posts/2017-10-30_pembelajaran-yang-saya-dapatkan-dari-chrome-dev-summit-untuk-indonesia/images/1.png" 
 - "/posts/2017-10-30_pembelajaran-yang-saya-dapatkan-dari-chrome-dev-summit-untuk-indonesia/images/2.png" 
 - "/posts/2017-10-30_pembelajaran-yang-saya-dapatkan-dari-chrome-dev-summit-untuk-indonesia/images/3.png" 
 - "/posts/2017-10-30_pembelajaran-yang-saya-dapatkan-dari-chrome-dev-summit-untuk-indonesia/images/4.png" 
 - "/posts/2017-10-30_pembelajaran-yang-saya-dapatkan-dari-chrome-dev-summit-untuk-indonesia/images/5.png" 


aliases:
    - "/pembelajaran-yang-saya-dapatkan-dari-chrome-dev-summit-untuk-indonesia-95adb25aad56"
---

![image](/posts/2017-10-30_pembelajaran-yang-saya-dapatkan-dari-chrome-dev-summit-untuk-indonesia/images/1.png)

Saya baru balik dari [Chrome Dev Summit](https://developer.chrome.com/devsummit/) dan tulisan ini ingin merangkum beberapa hal yang saya dapatkan dari event tahunan team Chrome untuk para pengembang web. Dari semua yang disampaikan di-event ini, ada beberapa hal yang saya rasa sangat berguna bagi pengembang web Indonesia terutama dalam meningkatkan standar pengalaman web yang dikembangkan.

#### Bagaimana Pengguna Mengakses Web

Untuk membuka tulisan ini saya rasa yang menarik untuk disimak adalah _The Web for the Entire World_ oleh Tal Oppenheimer ini.




The Web for The Entire World — Tal Oppenheimer



Di presentasi ini Tal menunjukkan bagaimana kondisi sebenarnya pengguna mobile phone dalam mengakses web. Saya yakin sebagian besar pembaca tulisan ini berada dalam kondisi ideal dalam mengakses web. Yaitu mobile phone dengan ruang penyimpanan dan memori yang cukup besar, serta di jaringan yang cukup cepat. Tapi berbeda dengan kenyataan sebagian besar pengguna web di Indonesia yang menggunakan mobile phone dengan ruang penyimpanan dan memori terbatas, serta jaringan yang tidak stabil ataupun paket data yang cukup mahal buat mereka.




![image](/posts/2017-10-30_pembelajaran-yang-saya-dapatkan-dari-chrome-dev-summit-untuk-indonesia/images/2.png)

Kondisi jaringan Indonesia yang sebagian besar masih 2G di 2016



Di presentasi tersebut dijelaskan bahwa bukan cuma kondisi jaringan yang tidak reliable, tapi sebagian pengguna handphone juga kehabisan ruang penyimpanan, dan sebagian besar masih menganggap bahwa paket data yang ada masih sangat mahal, sehingga dalam mengakses internet mereka sangat peduli dengan jumlah data yang mereka konsumsi.

Presentasi Tal tersebut memberikan alasan baik bagi pengembang untuk bisa mengembangkan aplikasi web mereka yang cukup memberi perhatian pada hal-hal di bawah ini.




![image](/posts/2017-10-30_pembelajaran-yang-saya-dapatkan-dari-chrome-dev-summit-untuk-indonesia/images/3.png)

Hal-hal yang perlu diperhatikan oleh pengembang web



#### Pengalaman Yang Baik Bagi Pengguna

Dan untuk bisa merancang aplikasi yang memperhatikan hal di atas, saya rasa yang cocok untuk dilihat adalah presentasi dari Addy Osmani yang akan memberikan informasi bagaimana best practice dalam mengembangkan web yang bisa loading dengan cepat dan instant.






Salah satu yang menarik adalah bagaimana resep sebuah aplikasi web modern yang baik adalah aplikasi yang memiliki 3 kriteria berikut




![image](/posts/2017-10-30_pembelajaran-yang-saya-dapatkan-dari-chrome-dev-summit-untuk-indonesia/images/4.png)

Recipe for building good web sites



Dalam membangun sebuah website dengan performance yang baik, salah satu komponen di web yang sangat penting adalah [service workers](https://developers.google.com/web/fundamentals/getting-started/primers/service-workers). Di mana service workers bisa memberikan pengembang kontrol terhadap caches dan jaringan. Sehingga pengembang bisa memberikan pengalaman akses cepat dalam kondisi jaringan apapun.

Karena pentingnya [service workers](https://developers.google.com/web/fundamentals/getting-started/primers/service-workers), Google mengembangkan [Workbox](https://workboxjs.org/), sebuah tool yang memudahkan pengembang untuk menggunakan [service workers](https://developers.google.com/web/fundamentals/getting-started/primers/service-workers) dalam aplikasi mereka. Jeff Posnick berbagi di presentasi berikut bagaimana [Workbox](https://workboxjs.org/) bisa digunakan.






Dan tentunya performance cuma salah satu dari experiences yang diharapkan oleh user dari sebuah aplikasi. Experiences yang sebelumnya mereka rasakan di aplikasi native, saat ini sudah bisa juga dinikmati di web. [Progressive Web Apps](https://developers.google.com/web/progressive-web-apps/) adalah aplikasi web yang bisa ditingkatkan secara progressive dengan memberikan experiences yang sama dengan aplikasi native.

Salah satu experiences yang cukup penting juga adalah integrasi dengan sistem operasi. Hal ini yang selama ini dimiliki oleh aplikasi native yang memberikan kemudahan bagi pengguna dalam mengakses konten, atau berinteraksi dengan aplikasi. Owen menceritakan bagaimana aplikasi web bisa memberikan integrasi yang sama seperti aplikasi native.




Integration web and operating systems



#### WordPress, CMS Yang Paling Populer

[WordPress](https://wordpress.org/) memegang peran penting dalam publikasi konten di web. Bisa dibilang 28% web dibuat menggunakan CMS [WordPress](https://wordpress.org/). Angka ini bahkan bisa lebih besar lagi di Indonesia. Di event terakhir AMP Roadshow di Jakarta, lebih dari 50% publishers yang hadir menggunakan [WordPress](https://wordpress.org/). Sehingga bisa dibayangkan dengan membuat WordPress bisa memberikan pengalaman yang baik seperti diceritakan di atas maka impact-nya bisa dirasakan oleh sebagian besar pengakses web.




![image](/posts/2017-10-30_pembelajaran-yang-saya-dapatkan-dari-chrome-dev-summit-untuk-indonesia/images/5.png)

WordPress adalah CMS terpopuler di dunia



Surma dari Google bekerja sama dengan team [Automattic](https://automattic.com/), pengembang dibalik [WordPress](https://wordpress.org/) untuk memberikan dukungan [Progressive Web Apps] (https://developers.google.com/web/progressive-web-apps/)di WordPress. Dukungan tersebut berupa [plugin](https://github.com/Automattic/jetpack/pull/7963) yang akan bisa digunakan oleh semua pemilik [WordPress](https://wordpress.org/) sites, dan [theme PWA](https://github.com/GoogleChromeLabs/ProgressiveWordPress) sebagai referensi untuk pengembang themes [WordPress](https://wordpress.org/).




WordPress &amp; PWA



#### Web Dengan Standar Yang Lebih Baik

Merangkum tulisan ini, semua konten yang saya bahas diatas pada dasarnya untuk memberikan pengguna web sebuah pengalaman yang lebih baik. Dan dari sisi pengembang web juga bisa menaikkan standar pengembanganya sehingga web yang dikembangkan memiliki kualitas pengalaman yang sama dengan aplikasi native. Untuk memberikan gambaran bagaimana seharusnya standar web yang lebih baik, mungkin kalian bisa menonton video presentasi dari Thao Tran dan Chris Wilson ini yang menceritakan best practice dalam pengembangan web untuk standar yang lebih baik.






Rekapan di atas hanya sebagian dari konten yang ada di Chrome Dev Summit. Ada banyak konten lainnya yang patut disimak seperti Polymer, LitHTML, tooling, framworks panels, dan lainnya. Silakan cek di [Youtube channel Chrome Developers](https://www.youtube.com/playlist?list=PLNYkxOF6rcICUD5nBfRdAR6Fveosnqa5m) untuk keseluruhan konten. Dan semoga kalian bisa ikut menaikkan standar kualitas pengalaman web Indonesia.
