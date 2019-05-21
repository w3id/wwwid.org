---
title: "Progressive Web App — Aplikasi Web Yang Bisa Di-Install — Bagian 2"
author: "Yohan Totting"
date: 2018-07-13T09:11:55.890Z
lastmod: 2019-05-20T16:27:23+07:00

description: ""

subtitle: "Melanjutkan tulisan sebelumnya terkait bagaimana sebuah Progressive Web App(PWA) bisa di-install, di tulisan ini kita ingin membahas…"
tags:
 - A2hs 
 - User Experience 
 - Web App Manifest 
 - Progressive Web App 

image: "/posts/2018-07-13_progressive-web-app-aplikasi-web-yang-bisa-diinstall-bagian-2/images/1.gif" 
images:
 - "/posts/2018-07-13_progressive-web-app-aplikasi-web-yang-bisa-diinstall-bagian-2/images/1.gif" 
 - "/posts/2018-07-13_progressive-web-app-aplikasi-web-yang-bisa-diinstall-bagian-2/images/2.png" 
 - "/posts/2018-07-13_progressive-web-app-aplikasi-web-yang-bisa-diinstall-bagian-2/images/3.png" 


aliases:
    - "/progressive-web-app-aplikasi-web-yang-bisa-di-install-bagian-2-c3839df40a8c"
---

Melanjutkan [tulisan sebelumnya](https://medium.com/wwwid/progressive-web-app-aplikasi-web-yang-bisa-di-install-bagian-1-9a1a7e22fff3) terkait bagaimana sebuah _Progressive Web App_(PWA) bisa di-_install_, di tulisan ini kita ingin membahas bagaimana sebenarnya untuk implementasi di aplikasi web kita dan kira-kira hal seperti apa saja yang bisa kita lakukan.

Sebelum implementasi kita harus memastikan terlebih dahulu apakah memang kita membutuhkan implementasi A2HS(_Add To Home Screen_) ini. Beberapa pertanyaan yang mungkin perlu kita jawab adalah:

### Native atau PWA?

Bila kita sudah memiliki aplikasi _native_ di platform yang sama, baik Android atau iOS, apakah kita lebih ingin pengguna memasang PWA kita atau aplikasi _native_ kita? Beberapa aplikasi seperti [Twitter](https://mobile.twitter.com) dan [Instagram](https://instagram.com) menggunakan PWA untuk mengakomodasi pengguna dengan perangkat berspesifikasi rendah yang memiliki kapasitas penyimpanan dan memori yang rendah. Sehingga memasang aplikasi _native_ adalah sesuatu yang membuat pengguna beripikir beberapa kali sebelum memutuskannya. Karena terkadang untuk memasang aplikasi mereka harus menghapus foto atau aplikasi lainnya.

Bila kita sudah memiliki aplikasi _native_, sesederhana mencantumkannya di [_web app manifest_](https://developers.google.com/web/fundamentals/web-app-manifest/) kita maka bila kondisi A2HS terpenuhi, dia akan menawarkan aplikasi native kita dibanding PWA kita. Berikut di bawah adalah deklarasi aplikasi _native_ kita di web app manifest.
``&#34;prefer_related_applications&#34;: true,  
&#34;related_applications&#34;: [  
  {  
    &#34;platform&#34;: &#34;play&#34;,  
    &#34;id&#34;: &#34;com.google.samples.apps.iosched&#34;  
  }  
]``

Bila kita tidak mencamtumkan `prefer_related_applications` sebagai `true` maka browser akan menawarkan PWA kita dibanding aplikasi native kita. Bila kondisi A2HS terpenuhi, maka browser akan menawarkan aplikasi native kita seperti di bawah ini.




![image](/posts/2018-07-13_progressive-web-app-aplikasi-web-yang-bisa-diinstall-bagian-2/images/1.gif)

Browser menawarkan aplikasi native bukan PWA



### Apakah memang pengguna perlu memasang PWA?

Terkadang memiliki icon di homescreen menjadi keinginan subyektif para pemiliki aplikasi web dengan alasan wajib, atau keren. Padahal harusnya keputusan ini berdasarkan aktivitas pengguna. Data yang bisa kita gunakan adalah:

1.  Perbandingan pengguna baru dan pengguna lama yang sudah mengakses web kita sebelumnya. Bila lebih besar pengguna lama maka mungkin kita bisa menawarkan A2HS.
2.  Seberapa sering pengguna kita mengakses aplikasi web kita. Apakah setiap hari atau cuma sekali seminggu?
3.  Aktivitas pengguna, apakah mereka datang dan pergi? Atau mengakses banyak halaman sebelum pergi? Karena dengan PWA, tampilan _standalone_ atau _fullscreen_ akan membuat pengguna bernavigasi antar halaman. Sehingga perlu PWA untuk pengalaman lebih baik dalam mengakses tiap halaman dengan tampilan lebih luas tanpa _location bar browser_.

Sebagai contoh, media online saat ini sudah sangat menjamur. Para pembaca berita tidak lagi mengkonsumsi media hanya dari satu sumber saja. Bahkan beberapa pengguna lebih memilih menggunakan _news aggregator_ untuk membaca berita dari beragam sumber. Dengan kondisi seperti ini, harusnya A2HS tidak menjadi prioritas kecuali kita memiliki data pendukung bahwa pengguna kita rutin mengakses aplikasi web kita setiap hari.

### Memberikan pengalaman lebih baik dalam A2HS

Nah bila berdasarkan dua pertanyaan di atas kita memutuskan untuk implementasi A2HS maka yang lebih penting lagi adalah **pada saat momen seperti apa kita menjembatani pengguna kita dari web ke aplikasi yang terpasang pada perangkat?**

Kenapa ini penting? Karena akan meyakinkan mereka dengan memberikan alasan lebih baik bagi pengguna kita untuk memasang PWA kita di perangkat mereka. Saya akan mencoba menunjukkan untuk dua vertical yang populer di Indonesia.

### Online media atau publisher

Seperti sudah saya jelaskan di atas, saat ini pengguna sebagian besar tidak mengkonsumsi berita cuma dari satu sumber. Bahkan pengguna beberapa memilih menggunakan _aggregator_ untuk membaca berita dari berbagai sumber di satu aplikasi saja. Lalu apa yang bisa kita tawarkan?

Kalau saya jadi pengembang aplikasi media, saya akan melihat media saya dari perspektif _aggregator_ berita. Bahwa pengguna belum tentu ingin membaca semua topik di media saya. Maka yang akan saya tawarkan di PWA saya adalah pengguna bisa memilih topik atau kategori mana saja yang ingin saya ikuti dan PWA saya yang terpasang bukan menampilkan halaman utama, tapi hanya menampilkan berita hanya berita yang saya ikuti.




![image](/posts/2018-07-13_progressive-web-app-aplikasi-web-yang-bisa-diinstall-bagian-2/images/2.png)

Kumparan memberikan opsi untuk mengikuti topik pilihan



Kemudian PWA saya bukan secara _default_ membuka halaman depan tapi akan langsung membuka berita pilihan yang sudah difilter berdasarkan topik yang sudah saya pilih. Lalu untuk pengalaman lebih baik, saya akan membuat aplikasi PWA ini untuk memberikan opsi sikronisasi berita setiap pagi menggunakan kombinasi [_budget API_](https://developers.google.com/web/updates/2017/06/budget-api), [_push API_](https://developers.google.com/web/fundamentals/push-notifications/), dan [_background fetch_](https://github.com/WICG/background-fetch). Atau kalau [_periodicsync API_](https://github.com/WICG/BackgroundSync/blob/master/explainer.md) __ udah diadopsi luas, kita bisa menggunakan API _service worker_ ini untuk sinkronisasi rutin. Dan lebih baik lagi, berita yang sudah tersinkronisasi akan tersimpan di cache dan bisa diakses tanpa jaringan.

Nah yang jadi pertanyaan berikutnya kapan kita perlu menanyakan untuk mengikuti pilihan topik tertentu? Mungkin ada beberapa pilihan, misalnya pada saat pengguna membaca topik yang lagi tren seperti [#ThaiCaveRescue](https://mobile.twitter.com/hashtag/ThaiCaveRescue) maka di akhir berita kita akan menawarkan seperti “Klik di sini untuk mengikuti topik pilihan ini”. Atau mungkin mempromosikan di halaman utama seperti “pilih topik bacaan harian anda anda di sini” dan diarahkan ke aplikasi aggregator topik pilihan. Nanti di aplikasi aggregator pilihan baru kita menawarkan A2HS dengan membuat tombol install dengan cara sebagai berikut:

Pertama kita perlu menangkap event `beforeinstallprompt` yang akan di-_trigger_ bila browser sudah menganggap website kita [memenuhi kriteria](https://developers.google.com/web/fundamentals/app-install-banners/).
``window.addEventListener(&#39;beforeinstallprompt&#39;, (e) =&gt; {  
  // Prevent Chrome 67 and earlier from automatically showing the prompt  
  e.preventDefault();  
  //store event atlocal storage  
  `window.localStorage.setItem(&#39;a2hs&#39;,`e);  
  `**document.querySelector(&#39;btninstall&#39;).style.display = &#39;block&#39;;**```});``

Baris tebal di atas menunjukkan bagaimana kita menampilkan tombol install setelah seebelumnya kita sembunyikan. Hasil event tangkapan tersebut bisa kita gunakan untuk memunculkan kembali event tersebut.
``btninstall.addEventListener(&#39;click&#39;, (e) =&gt; {  
  // hide our user interface that shows our A2HS button  
  btninstall.style.display = &#39;none&#39;;  
  const deferredPrompt=window.localStorage.getItem(&#39;a2hs&#39;);  
  // Show the prompt  
  deferredPrompt.prompt();  
  // Wait for the user to respond to the prompt  
  deferredPrompt.userChoice  
    .then((choiceResult) =&gt; {  
      if (choiceResult.outcome === &#39;accepted&#39;) {  
        console.log(&#39;User accepted the A2HS prompt&#39;);  
      } else {  
        console.log(&#39;User dismissed the A2HS prompt&#39;);  
      }  
      deferredPrompt = null;  
    });  
});``

Namun bila kita ingin membuat dialog lebih informatif lagi, maka kita bisa membuat c_ustom dialog_ seperti Instagram.




![image](/posts/2018-07-13_progressive-web-app-aplikasi-web-yang-bisa-diinstall-bagian-2/images/3.png)

Custom dialog A2HS di Instagram



Untuk _custom dialog_ di atas, _event_ yang kita tangkap bisa kita gunakan pada button “Add to Home Screen” seperti contoh sebelumnya. Sehingga saat button itu di-tap, maka kita tinggal memanggil `deferredPrompt.prompt()` untuk memunculkan A2HS.

### E-Commerce dan Marketplace

Untuk industri _e-commerce_ juga sebagian besar pemain besar tentu sudah memiliki aplikasi _native_. Tapi mungkin yang menjadi pilihan adalah PWA bisa mengakomodasi pengguna dengan perangkat berspesifikasi rendah. Dalam hal berbelanja, saya rasa penggunaan aplikasi _native_ bagi orang yang jarang berbelanja dan perangkat berspesifikasi rendah akan menjadikan pemasangan aplikasi _native_ sebagai prioritas rendah. Karena belum tentu dalam sebulan kita pasti akan berbelanja kecuali memang kita adalah penjual yang akan rajin memeriksa apakah ada order atau tidak.

Dalam konteks _e-commerce_, saya mungkin akan mencoba mencari ide berdasarkan aktivitas yang paling sering pengguna lakukan. Asumsi saya, berdasarkan aktivitas yang saya lakukan di _e-commerce_ atau _marketplace_ adalah pengguna bolak-balik melakukan pengecekan pada status order aplikasi mereka bila membeli sebuah barang. Terkadang selalu harus mengetikkan URL di _browser_ lalu memilih menu halaman order. Dua langkah ini bisa diminimalisasi dengan membuat PWA yang langsung membuka halaman order.

Lebih baik lagi, mungkin untuk di _e-commerce_ harusnya permintaan notifikasi _push_ diminta di halaman ini. Kita bisa menanyakan seperti “Apakah kalian ingin diberitahu bila status ordermu berubah?” sehingga kita hanya mengirimkan notifikasi hanya bila order pengguna sudah berubah. Sehingga mereka tidak perlu bolak balik mengecek status order.

Bagaimana untuk implementasinya untuk membuat _custom_ URL pada A2HS? Caranya dimulai dari membuat _web app manifest_ dengan `start_url` ke halaman order. Kalian bisa membuat _web app manifest_ lebih dari satu, asalkan halaman HTML memberikan URL yang tepat pada halaman tersebut.
``{  
  &#34;short_name&#34;: &#34;IDShop Orders&#34;,  
  &#34;name&#34;: &#34;IDShop&#34;,  
  &#34;icons&#34;: [  
    {  
      &#34;src&#34;: &#34;/images/icons-192.png&#34;,  
      &#34;type&#34;: &#34;image/png&#34;,  
      &#34;sizes&#34;: &#34;192x192&#34;  
    },  
    {  
      &#34;src&#34;: &#34;/images/icons-512.png&#34;,  
      &#34;type&#34;: &#34;image/png&#34;,  
      &#34;sizes&#34;: &#34;512x512&#34;  
    }  
  ],  
  **&#34;start_url&#34;: &#34;/orders/?source=pwa&#34;,**  
  &#34;background_color&#34;: &#34;#3367D6&#34;,  
  &#34;display&#34;: &#34;standalone&#34;,  
  &#34;scope&#34;: &#34;/orders/&#34;,  
  &#34;theme_color&#34;: &#34;#3367D6&#34;  
}``

Pastikan _file web app manifest_ tercantum pada header file HTML halaman web seperti berikut   
`&lt;link rel=&#34;manifest&#34; href=&#34;/manifest-order.json&#34;&gt;`

Bila kalian menggunakan arsitektur _Single Page Application (SPA)_ maka kalian harus memastikan _link_ _manifest_ tersebut berbeda bila kalian dengan halaman home. Untuk memodifikasi halaman yang dibuka pada saat kita mengakses dari _icon_ di _home screen_, maka pastikan kalian mengubah start_url di _web app manifest_.

`&#34;start_url&#34;: &#34;/orders/?source=pwa&#34;`

Dan parameter `source=pwa` di URL tersebut itu untuk memudahkan kita mengetahui di _analytics_ berapa banyak akses lewat PWA kita, dan mana yang lewat _browser_.

### Kesimpulan

Poin utama dari Progressive Web App adalah memberikan pengalaman lebih baik bagi pengguna secara bertahap dalam mengakses layanan atau informasi kita melalui web. Namun banyak yang mengimplementasikan fitur baru di web tanpa peduli konteks dan kenyamanan pengguna.

Jadi, pastikan sebelum kita mengimplementasikan sebuah fitur baru. Tanyakan kepada pengguna apakah mereka butuh, pada saat kapan mereka butuh, dan bagaimana idealnya kita melayani mereka.

### Referensi

[Add to Home Screen | Web Fundamentals | Google Developers](https://developers.google.com/web/fundamentals/app-install-banners/)

[Changes to Add to Home Screen Behavior | Web | Google Developers](https://developers.google.com/web/updates/2018/06/a2hs-updates)

[WICG/BackgroundSync](https://github.com/WICG/BackgroundSync/blob/master/explainer.md)
