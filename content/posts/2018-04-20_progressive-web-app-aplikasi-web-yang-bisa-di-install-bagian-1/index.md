---
title: "Progressive Web App — Aplikasi Web Yang Bisa Di Install — Bagian 1"
author: "Yohan Totting"
date: 2018-04-20T08:49:47.307Z
lastmod: 2019-05-20T16:27:19+07:00

description: ""

subtitle: "Salah satu pengalaman yang sangat memudahkan pengguna aplikasi native dalam mengakses aplikasi yang mereka ingin gunakan adalah…"
tags:
 - Add To Homescreen 
 - Progressive Web App 
 - Front End Development 
 - Web App Manifest 

image: "/posts/2018-04-20_progressive-web-app-aplikasi-web-yang-bisa-di-install-bagian-1/images/1.png" 
images:
 - "/posts/2018-04-20_progressive-web-app-aplikasi-web-yang-bisa-di-install-bagian-1/images/1.png" 
 - "/posts/2018-04-20_progressive-web-app-aplikasi-web-yang-bisa-di-install-bagian-1/images/2.png" 
 - "/posts/2018-04-20_progressive-web-app-aplikasi-web-yang-bisa-di-install-bagian-1/images/3.png" 
 - "/posts/2018-04-20_progressive-web-app-aplikasi-web-yang-bisa-di-install-bagian-1/images/4.png" 
 - "/posts/2018-04-20_progressive-web-app-aplikasi-web-yang-bisa-di-install-bagian-1/images/5.png" 
 - "/posts/2018-04-20_progressive-web-app-aplikasi-web-yang-bisa-di-install-bagian-1/images/6.png" 
 - "/posts/2018-04-20_progressive-web-app-aplikasi-web-yang-bisa-di-install-bagian-1/images/7.png" 


aliases:
    - "/progressive-web-app-aplikasi-web-yang-bisa-di-install-bagian-1-9a1a7e22fff3"
---

Salah satu pengalaman yang sangat memudahkan pengguna aplikasi _native_ dalam mengakses aplikasi yang mereka ingin gunakan adalah kemudahannya dalam men-launch aplikasi tersebut dengan semudah men-tap _icon_ aplikasi di layar _home smart phone_ mereka dan aplikasi langsung siap digunakan. Bandingkan dengan aplikasi web yang harus melakukan tap beberapa kali karena selain men-tap _icon_ _browser_ di layar home, tentu juga harus mengetikkan alamat URL dari aplikasi web tersebut. Ini yang membuat _retention_ dan tingkat interaktifitas aplikasi web terkadang lebih kecil dibandingkan aplikasi native.

Berkaca dari contoh di atas, maka komunitas web mencoba mencari cara bagaimana memberikan pengalaman yang sama, di mana pengguna dapat dengan mudah mengakses aplikasi web semudah melakukan sekali tap di layar smartphone. Salah satu caranya adalah adanya tombol _add to home screen_ (A2HS) yang bila di-tap maka akan membuat icon launcher di layar smartphone pengguna. Ini tidak cuma ada di Android, tapi juga tersedia di iOS.




![image](/posts/2018-04-20_progressive-web-app-aplikasi-web-yang-bisa-di-install-bagian-1/images/1.png)

Tombol add to home screen di iOS



Tapi ternyata tidak semua pengguna bisa melihat adanya tombol tersebut sehingga pengguna _smartphone_ masih mengeluhkan repotnya harus mengetikkan alamat URL berulang kali setiap ingin mengakses aplikasi web yang mereka gunakan. Karena memang posisinya tidak langsung tampak di kalau di Android, atau icon di iOS masih kurang familiar buat pengguna. Dari situ mulailah dikembangkan semacam dialog yang akan menanyakan apakah ingin menambahkan akses langsung di layar _smartphone_ dengan _icon launcher_, bila pengguna mengakses suatu aplikasi web cukup sering dan memenuhi [kriteria tertentu](https://developers.google.com/web/fundamentals/app-install-banners/#what_are_the_criteria).

### Syarat Agar Bisa Menampilkan Add To Homescreen

Agar website tersebut bisa memunculkan dialog _add to homescreen_ maka diperlukan beberapa syarat yang harus dipenuhi:

1.  Memiliki _file web manifest_
2.  Memiliki _service worker_ teregisterasi
3.  Diakses di protokol aman HTTPS
4.  Memenuhi [tingkat interaktifitas tertentu dengan halaman web tersebut](https://www.chromium.org/developers/design-documents/site-engagement) (ini selalu berubah dan berbeda di tiap browser)

Bila syarat di atas terpenuhi maka kita bisa menempatkan icon launcher web tersebut di home screen kita baik melalui menu _add to homescreen_ di _browser_ atau muncul secara otomatis berdasarkan tingkat interaktifitas pengguna.




![image](/posts/2018-04-20_progressive-web-app-aplikasi-web-yang-bisa-di-install-bagian-1/images/2.png)

Dialog add to home screen di Android Chrome



Untuk menguji coba apakah website kalian sudah bisa menampilkan dialog _add to homescreen_, bisa menggunakan [ChomeDevTool](https://developers.google.com/web/tools/chrome-devtools/) dengan masuk ke _tab application_ dan mengklik tombol _add to homescreen_ seperti di gambar ini.




![image](/posts/2018-04-20_progressive-web-app-aplikasi-web-yang-bisa-di-install-bagian-1/images/3.png)

Mengaktifkan dialog add to homescreen secara manual



Setelah aplikasi dapat diakses langsung dari layar _smartphone_ langsung tanpa mengetikkan alamat URL, ternyata sebagian besar pengguna berekspektasi bahwa layar aplikas web yang dijalankan tersebut akan muncul tanpa _location bar_ selayaknya sebuah aplikasi _native_, bukan seperti _browser_.

### Web Application Manifest

Untuk menentukan apakah sebuah aplikasi web yang sudah terpasang di layar _smartphone_ bisa muncul _full screen_ tanpa _location bar_ maka diperlukan sebuah _manifest_ _file_ yang mendeskripsikan bagaimana aplikasi harus ditampilkan pada saat dijalankan dari _icon launcher_, bukan dari mengetikkan alamat di browser. _Manifest file_ ini dinamakan [_Application Manifest_](https://developer.mozilla.org/en-US/docs/Web/Manifest) dengan format JSON file yang isinya kurang lebih seperti di bawah ini.
``{  
  &#34;name&#34;: &#34;HackerWeb&#34;,  
  &#34;short_name&#34;: &#34;HackerWeb&#34;,  
  &#34;start_url&#34;: &#34;/app&#34;,  
  &#34;display&#34;: &#34;standalone&#34;,  
  &#34;background_color&#34;: &#34;#fff&#34;,  
  &#34;description&#34;: &#34;A simply readable Hacker News app.&#34;,  
  &#34;icons&#34;: [{  
    &#34;src&#34;: &#34;images/touch/homescreen144.png&#34;,  
    &#34;sizes&#34;: &#34;144x144&#34;,  
    &#34;type&#34;: &#34;image/png&#34;  
  }, {  
    &#34;src&#34;: &#34;images/touch/homescreen168.png&#34;,  
    &#34;sizes&#34;: &#34;168x168&#34;,  
    &#34;type&#34;: &#34;image/png&#34;  
  }, {  
    &#34;src&#34;: &#34;images/touch/homescreen192.png&#34;,  
    &#34;sizes&#34;: &#34;192x192&#34;,  
    &#34;type&#34;: &#34;image/png&#34;  
  }],  
  &#34;related_applications&#34;: [{  
    &#34;platform&#34;: &#34;web&#34;  
  }, {  
    &#34;platform&#34;: &#34;play&#34;,  
    &#34;url&#34;: &#34;https://play.google.com/store/apps/details?id=cheeaun.hackerweb&#34;  
  }]  
}``

Di contoh di atas ada bagian `start_url:&#34;/app&#34;` yang menjadi pembeda antara aplikasi yang dijalankan dari browser dengan aplikasi yang dijalankan dengan tap di icon di home screen smartphone. Dengan demikian kalian bisa mengkontrol dan mencatat setiap akses dari launcher misalnya untuk keperluan analytics.

### Hal Yang Perlu Diperhatikan Sebelum Implementasi Add To Homescreen

Kebanyakan developer akan mengeksploitasi fungsi dan menggunakan tanpa memikirkan bagaimana pengguna menggunakannya. Salah satu contohnya adalah _push notification_ yang diminta oleh hampir sebagian besar website modern.

Hal ini sangat mengganggu bila kita tidak ingin menerima _push notification_ tapi setiap website meminta secara otomatis pada saat website mereka dibuka pertama kali. Bahkan beberapa mulai mengakali agar tidak terblok dengan tetap memunculkan custom dialog pertanyaan apakah mau menerima push notification sebelum melakukan _trigger request push notification browser_. Hal ini karena di browser begitu pengguna melakukan _block_ pada website tersebut maka kecil kemungkinan dia akan di-_unblock_ lagi.




![image](/posts/2018-04-20_progressive-web-app-aplikasi-web-yang-bisa-di-install-bagian-1/images/4.png)

Custom dialog untuk menawarkan notifikasi di Detik.com



Dampak push notification inilah yang ingin dihindari oleh _add to homescreen,_ karena kita tidak ingin setiap kita membuka website langsung muncul tawaran install seperti iklan pop-up yang menjadi hal wajib di website berita Indonesia. Padahal harusnya setiap penawaran yang dilakukan oleh sebuah website harusnya berdasarkan konteks tertentu yang kemungkinan besar user memang perlu apa yang kita tawarkan.




![image](/posts/2018-04-20_progressive-web-app-aplikasi-web-yang-bisa-di-install-bagian-1/images/5.png)

Twitter Lite hanya menawarkan push notification bila kita membuka page notification.



Contoh yang baik misalnya Twitter Lite yang menawarkan untuk mengaktifkan _push notification_ hanya pada saat kita membuka halaman atau _tab notification_, bukan pada saat kita membuka Twitter lite. Selain itu memberikan konteks yang tepat kepada pengguna apa manfaat buat mereka bila mengaktifkan push notification.




![image](/posts/2018-04-20_progressive-web-app-aplikasi-web-yang-bisa-di-install-bagian-1/images/6.png)

Dialog _add to homescreen default_ tanpa konteks apapun



Bila melihat _dialog window add to homescreen default_ di atas, maka jelas bahwa _add to homescreen_ tidak memiliki konteks yang baik. Tidak ada alasan yang diberikan kenapa pengguna sebaiknya _add to homescreen_. Sehingga pengguna yang awam akan bingung apa yang ditawarkan. Berikut adalah bagaimana memberikan informasi konteks untuk pengguna.




![image](/posts/2018-04-20_progressive-web-app-aplikasi-web-yang-bisa-di-install-bagian-1/images/7.png)

Contoh dialog untuk menawarkan A2HS



Lalu bagaimana mengontrol flow dan memberikan konteks pada penawaran _add to homescreen_ ini? Sedangkan tidak ada API khusus untuk melakukan pemanggilan manual dialog _add to homescreen_. Tunggu di bagian 2 yang akan membahas cara implementasinya.
