---
title: "Berbagai best practice dalam memuat halaman website"
author: "Irfan Maulana"
date: 2018-07-09T08:45:57.875Z
lastmod: 2019-05-20T16:27:21+07:00

description: ""

subtitle: "Berbagai best practice yang bisa kita pelajari dan optimalkan dalam memuat halaman website."
tags:
 - Web Development 
 - Web Performance 
 - Best Practices 

image: "/posts/2018-07-09_berbagai-best-practice-dalam-memuat-halaman-website/images/1.png" 
images:
 - "/posts/2018-07-09_berbagai-best-practice-dalam-memuat-halaman-website/images/1.png" 
 - "/posts/2018-07-09_berbagai-best-practice-dalam-memuat-halaman-website/images/2.png" 
 - "/posts/2018-07-09_berbagai-best-practice-dalam-memuat-halaman-website/images/3.png" 
 - "/posts/2018-07-09_berbagai-best-practice-dalam-memuat-halaman-website/images/4.png" 


aliases:
    - "/berbagai-best-practice-dalam-memuat-halaman-website-20def6652adf"
---

Berbagai _best practice_ yang bisa kita pelajari dan optimalkan dalam memuat halaman website.




![image](/posts/2018-07-09_berbagai-best-practice-dalam-memuat-halaman-website/images/1.png)

Image source: [https://developers.google.com/web/tools/chrome-devtools/network-performance/reference](https://developers.google.com/web/tools/chrome-devtools/network-performance/reference)



Pernahkah kita merasa frustasi dengan bagaimana browser memuat website yang sudah kita buat dengan susah payah? Pernahkah kita merasa sudah melakukan berbagai optimasi di website kita namun hasilnya tetap saja tidak memuaskan? Nah, untuk mengetahui apakah hal yang sudah kita lakukan berada pada jalan yang benar maka pada tulisan ini kita akan sama-sama belajar memahami bagaimana browser memuat sebuah halaman website serta berbagai hal yang bisa kita optimasi dari website kita untuk memperbaiki performa rendering website kita di browser.

Ada banyak hal tentunya dan juga ada banyak pendapat mengenai apa saja hal yang sebaiknya dan harus kita lakukan untuk memperbaiki performa website kita saat dimuat oleh browser. Kita akan coba pecahkan kedalam beberapa bagian agar lebih mudah bagi kita bersama memahami poin per poinnya.
> Disclaimer: beberapa hal pada tulisan ini didasarkan pada pengalaman yang dialami oleh penulis dan dibumbui berbagai pendapat pribadi. Silahkan dikoreksi kalau memang ada hal yang salah atau kurang tepat dan silahkan diikuti bila memang benar dan berguna bagi kalian.

### 🌏 Browser

Sebelum melakukan berbagai hal optimasi, kita perlu terlebih dahulu memahami bagaimana dasar-dasar browser bekerja agar nantinya lebih mudah bagi kita untuk mengaitkan pekerjaan yang akan dan telah kita lakukan.

Browser sendiri adalah alat yang digunakan pengguna untuk melihat website kita. Bila browser adalah milik pengguna, artinya kita sebagai penyedia website akan mengirimkan berbagai file dan assets kepada pengguna melalui network mereka. Dari sini kita mengetahui bahwa pengguna satu dan pengguna lain kemungkinan akan memiliki pengalaman yang berbeda dalam memuat website kita. Kesemuanya tergantung dari kondisi pengguna itu sendiri, mulai dari kondisi network pengguna, device yang digunakan oleh pengguna, sampai browser vendor dan versi yang digunakan oleh pengguna. Berbagai hal tersebut akan secara langsung mempengaruhi pengalaman pengguna dalam memuat website kita.

Selebihnya peran kita adalah memastikan bahwa semua file yang dibutuhkan oleh pengguna yang ingin melihat website kita dalam kondisi tersedia. Jadi kita harus bisa memastikan bahwa baik dalam keadaan _low traffic_ ataupun _high traffic_ pengguna kita tetap bisa mendapatkan file yang dibutuhkan. Karena bila kita sudah tidak bisa menyediakan, maka sebaik apapun kondisi pengguna tersebut tetap saja tidak akan bisa memuat halaman kita.### 📄 HTML

HTML merupakan bagian utama dari sebuah website. Saya sering menyebut kalau HTML ini ibarat kerangka di tubuh manusia, sesuatu yang membangun tubuh itu sendiri. HTML merupakan representasi struktur dari website yang kita buat. Semakin rumit dan kompleks website yang kita buat akan berimbas langsung pada struktur HTML dan berakibat pada ukuran file yang harus kita kirimkan ke pengguna.

Beberapa hal yang bisa kita optimalkan terhadap HTML antara lain:

**1.** **Compress dan optimize**

Ketika membuat HTML tentu kita akan membuat kode kita agar mudah dibaca oleh developer lain dan kita akan menambahkan banyak _white space_ agar kode kita lebih rapi. _White space_ ini tidak dibutuhkan ketika kita mengirimkan HTML ke browser, membuang hal yang tidak perlu artinya kita dalam proses memperkecil file yang dihasilkan.

Meskipun tidak semua penghilangan bagian yang tidak dibutuhkan itu selalu terlihat efeknya secara masif terhadap ukuran file, namun prakteknya merupakan hal yang baik untuk dilakukan. Seperti halnya saya yang selalu membenci bila ada developer yang meng-_comment_ code dibandingkan menghapusnya ketika sudah tidak digunakan.

**2. Memangkas waktu pembuatan**

Bila kita masih menggunakan SSR dimana kode HTML kita harus dibuat di server dengan data yang dinamis pada saat itu juga, maka kita harus memastikan waktu untuk membuat HTML tersebut bisa dipangkas sebisa mungkin. Gunakan **cache** baik pada data dinamis yang dibutuhkan ataupun pada HTML yang dihasilkan bila memang diperlukan.

**3. Utamakan konten _above the fold_**

Pengguna tidak akan melihat keseluruhan halaman website kita pada saat pertama kali halaman tersebut dimuat, melainkan hanya bagian teratas sebatas tinggi layar. Karena itu kita wajib memprioritaskan konten-konten yang berada pada wilayah tangkapan ini, sedangkan konten yang berada dibawahnya bisa dimuat belakangan. Hal ini termasuk juga dengan konten yang membutuhkan aksi dari pengguna untuk ditampilkan seperti komponen _popup modal._




![image](/posts/2018-07-09_berbagai-best-practice-dalam-memuat-halaman-website/images/2.png)

Image source: [https://neilpatel.com/blog/google-pagespeed-insights/](https://neilpatel.com/blog/google-pagespeed-insights/)

### 💅 CSS

CSS merupakan bagian yang tidak terpisahkan dari sebuah website. CSS sendiri bisa dimuat paling tidak dengan 3 cara yakni _inline style_, _internal style_, dan _external style_. Masing-masing cara yang kita gunakan memiliki kelebihan dan kekurangannya sendiri, penggunaannya tergantung pada kebutuhan kita.

_Inline style_ tidak akan menambah jumlah _roundtrip_ network kita namun susah untuk digunakan ulang dan akan menambah ukuran HTML kita. _Internal style_ bisa digunakan ulang selama berada di halaman tersebut dan tidak akan menambah jumlah _request_ namun juga akan menambah ukuran HTML kita. _External style_ bisa digunakan ulang dengan mudah dan tidak akan menambah ukuran HTML yang kita kirim namun akan menambah jumlah _request_ di _network_ kita.

Paling tidak berikut adalah beberapa cara yang bisa kita lakukan terhadap CSS kita:

1.  **Minify dan merge**

Seperti HTML, CSS pun akan membawa banyak _white space_ yang tidak diperlukan di lingkungan _production_ yang bisa kita hilangkan. Pengoptimalan CSS juga bisa dilakukan dengan menyatukan berbagai _class_ atau _selector_ lain di CSS yang memiliki _rule_ yang sama. Penggunaan berbagai _shorthand_ juga diperlukan untuk memberikan hasil file yang lebih ramping.

Artikel berikut akan membantu kalian agar lebih bijak dalam menulis CSS dan bisa menghasilkan file yang lebih bersahabat dengan browser:

[7 Principles Of Clean And Optimized CSS](https://www.smashingmagazine.com/2008/08/7-principles-of-clean-and-optimized-css-code/)


**2. Kurangi jumlah file**

Satu prinsip yang harus diketahui adalah bahwa semakin banyak kita memuat file maka semakin banyak waktu yang dibutuhkan untuk memuat website kita. Jadi bila kita bisa menyatukan file yang akan kita muat (selama memiliki ukuran yang masuk akal) maka menyatukannya adalah hal yang sebaiknya dilakukan.

**3. Kurangi _unused_ style**

Faktanya sebagian besar website memuat file CSS dengan isi yang sebenarnya hanya digunakan sebagian kecil dari keseluruhan isi yang ada. Menghilangkan _style_ di CSS yang tidak digunakan oleh suatu halaman website akan sangat membantu kita dalam mengurangi ukuran file CSS yang akan kita kirimkan ke browser pengguna.

Sedikit trik tambahan, kita bisa melihat _coverage_ dari _unused_ CSS dari suatu halaman website melalui menu _coverage_ yang terdapat pada _console drawer_ di ChromeDevTools.




![image](/posts/2018-07-09_berbagai-best-practice-dalam-memuat-halaman-website/images/3.png)

Screenshoot coverage di ChromeDevTools



**4. Utamakan critical CSS**

Critical CSS adalah sekumpulan _style_ CSS yang keberadaannya dirasa sangat penting bagi pengguna pada masa-masa awal halaman tersebut dimuat sehingga sangat tidak disarankan untuk menunda dalam pemuatan _style_ semacam ini. Perlu diketahui bahwa critical CSS harus sekecil mungkin dan menghasilkan tampilan yang minimal tidak menggangu bagi pengguna dan memenuhi berbagai tampilan minimal yang harus pengguna lihat pertama kali.

Beberapa pengembang web memutuskan untuk meletakan critical CSS ini ke dalam _internal style_ di dalam HTML dan di dalam tag head meraka.   
Artikel berikut ini membantu kita memahami apa itu critical CSS dan bagaimana cara mengindentifikasi _style_ mana yang critical:

[Understanding Critical CSS](https://www.smashingmagazine.com/2015/08/understanding-critical-css/)
### ⚙️ JS

JS merupakan penggerak dari berbagai website jaman sekarang, perannya kini kian vital seiring berkembangnya kemampuan dari bahasanya sendiri. Sayangnya JS masih menjadi momok sendiri bagi browser, selain karena biasanya memiliki ukuran file yang mendominasi bagian dari website kita, juga karena dibutuhkan proses _parsing_ maupun _compile_ agar bisa dipahami oleh browser itu sendiri. Proses _parsing_ ini sendiri bisa berbeda-beda setiap device dan browsernya, seperti terlihat pada gambar berikut:




![image](/posts/2018-07-09_berbagai-best-practice-dalam-memuat-halaman-website/images/4.png)

Image source: [https://medium.com/dev-channel/the-cost-of-javascript-84009f51e99e](https://medium.com/dev-channel/the-cost-of-javascript-84009f51e99e)



Untuk memahami lebih lanjut mengenai proses bagaimana JS dimuat dalam suatu browser, silahkan baca artikel dari [Addy Osmani](https://medium.com/u/2508e4c7a8ec) pada tautan berikut:

[The Cost Of JavaScript](https://medium.com/dev-channel/the-cost-of-javascript-84009f51e99e)


Beberapa hal yang bisa lakukan dengan JS diantaranya:

1.  **Kurangi ukuran file**> Semakin sedikit kode maka semakin sedikit yang harus di compile/parse, semakin sedikit yang harus di transfer lewat network, dan semakin sedikit juga yang harus di decompress. (diterjemahkan dari [@junwatu](http://twitter.com/junwatu) dari [https://medium.com/dev-channel/the-cost-of-javascript-84009f51e99e](https://medium.com/dev-channel/the-cost-of-javascript-84009f51e99e))

Dengan kemampuan JS yang sekarang bisa modular dan bisa menambahkan berbagai _dependencies_ ke dalam projek kita dengan lebih mudah seringkali justru di-_abuse_ oleh banyak pengembang web. Mereka tidak merasa ikut bertanggung jawab ketika hasil akhir dari file JavaScript yang harus dimuat menjadi terlalu besar. Setiap keputusan dalam menambahkan kode atau bahkan pustaka luar buatan orang lain akan secara langsung berakibat pada ukuran file kita, menjadi lebih bijak sebagai pengembang web adalah cara terbaik untuk mengurangi hal seperti ini terulang kembali. Selain kita juga bisa memasang berbagai _gate_ termasuk ukuran file pada saat melakukan _build_ pada projek kita.

**2. Lazy load chunk**

Untuk beberapa website yang memilih menggunakan _Single Page Application_, memisahkan script berdasarkan halaman yang dikunjungi adalah hal yang mutlak harus dilakukan karena ini bisa mengurangi jumlah kode yang tidak digunakan pada halaman tersebut.

**3. Uglify dan optimize**

Pastikan kita melakukan _uglify_ dan juga _optimize_ pada kode kita dan membuang berbagai _dead code_ yang mungkin ada pada kode kita. Untuk melakukan ini biasanya menggunakan tools yang sudah tersedia seperti [UglifyJS](https://github.com/mishoo/UglifyJS).

**4. Async dan Defer**

_Directive_ _async_ pada script eksternal bisa membuat _request_ suatu script dilakukan secara bersamaan dengan script yang lain. Hal ini bisa mengurangi waktu muat karena beberapa script dieksekusi atau diminta dalam waktu yang hampir sama. Sayangnya ketika menggunakan _directive_ ini kita jadi tidak bisa mengetahui urutan kapan selesai satu script dieksekusi atau diminta.

Seringkali kita harus menambahkan berbagai _third party_ script kedalam website kita seperti analytics, berbagai _tracker_, maupun _remarkerting_/_retargeting_ script. Hal ini tentu saja akan memperlambat waktu muat website kita, dan salah satu trik yang bisa kita lakukan adalah men-_defer_ script kita yang artinya menunda script ini di-_request_ ataupun dieksekusi sampai halaman terkait selesai di _parsing_.

Berbeda dengan _async_ yang tidak memperdulikan urutan, _defer_ akan tetap dieksekusi berdasarkan urutan dari script yang kita tulis di kode.

[Asynchronous vs Deferred JavaScript](https://bitsofco.de/async-vs-defer/)
### 🌇 IMAGE

1.  **Kompresi kualitas**

Pastikan melakukan kompresi terhadap gambar-gambar yang akan dimuat di website kita, tidak perlu menggunakan kualitas yang sangat tajam karena akan menghasilkan ukuran gambar yang besar pula. Sudah banyak _online_ _tools_ gratis yang bisa kita gunakan untuk melakukan kompresi gambar seperti melalui website [https://tinypng.com/](https://tinypng.com/) dan [https://tinyjpg.com/](https://tinyjpg.com/). Kita juga bisa meletakan proses kompresi ini kedalam build proses kita seperti salah satunya menggunakan [https://github.com/tcoopman/image-webpack-loader](https://github.com/tcoopman/image-webpack-loader).

**2. Kurangi jumlah request**

Mengurangi jumlah file gambar yang harus dimuat adalah hal utama selain melakukan optimasi pada file gambar itu sendiri. Untuk melakukan hal ini kita bisa melakukan beberapa trik seperti berikut:

**— Lazy load**

Gambar yang tidak sedang dilihat oleh pengguna tidaklah boleh kita muat pada saat pertama kali memuat website kita, gambar tersebut hanya boleh dimuat ketika pengguna memang sedang atau akan melihat gambar tersebut.

Cara paling _mainstream_ untuk menerapkan _lazy load_ gambar adalah dengan mendeteksi _scroll_ yang dilakukan oleh pengguna di website kita. Kabar baiknya lagi, belakangan kita malah dimudahkan untuk memuat gambar secara _lazy_ dengan adanya [_IntersectionObserver_](https://medium.com/mazipan-mind/intersection-observer-sebuah-pengantar-f996cf8ab27b)_._

**— Inline SVG kecil**

SVG merupakan gambar yang dibangun dari berbagai _path_ yang saling dihubungkan. SVG memiliki keunggulan yang bisa diperbesar tanpa mengalami pecah pada pixelnya. SVG seringkali digunakan untuk berbagai icon dalam website. Untuk memuat file ini sendiri paling mudah adalah dengan membuat tag `&lt;img src=&#34;path/file.svg&#34;/&gt;` namun cara ini tentu akan menambah jumlah request pada network kita karena akan dimuat layaknya gambar pada umumnya. Cara lain adalah dengan meyalin tag _markup_ yang ada di dalam file SVG tersebut dan menempatkannya langsung didalam HTML kita atau biasa dikenal dengan _inline SVG_. Cara ini bisa mengurangi jumlah request yang harus dilakukan namun akan menambah ukuran dari HTML kita.

Selain itu kita bisa juga melakukan optimasi pada file SVG menggunakan [SVGO](https://github.com/svg/svgo) yang telah dibuatkan juga versi websitenya di [https://jakearchibald.github.io/svgomg/](https://jakearchibald.github.io/svgomg/).

**— Gunakan Sprite**

_Sprite_ digunakan untuk memuat banyak gambar dalam sekali _request_ network sehingga tidak diperlukan banyak _request_ berulang pada prosesnya.

[CSS Sprites: What They Are, Why They&#39;re Cool, and How To Use Them | CSS-Tricks](https://css-tricks.com/css-sprites/)


**5. Utamakan ekstensi WebP**

Utamakan untuk menggunakan tipe gambar yang lebih baik seperti [_webp_](https://developers.google.com/speed/webp/) karena memiliki ukuran yang lebih kecil tanpa menurunkan kualitas masif.

—

Artikel berikut bisa jadi panduan kita dalam menyajikan dan mengoptimalkan gambar bagi website kita:

[summary_large_image](https://images.guide/)
### 🎁 OTHERS

1.  **Kompresi**

Pastikan semua file yang akan kita kirimkan ke browser dalam keadaan terkompresi dengan baik. Kompresi yang paling sering digunakan oleh pengembang adalah GZip yang bisa dengan mudah di set melalui webserver semacam Apache atau Nginx.

Artikel berikut akan membantu kita dalam mengaktifkan kompresi untuk website kita:

[Enable Compression | PageSpeed Insights | Google Developers](https://developers.google.com/speed/docs/insights/EnableCompression)


**2. Preload, prefetch dan dns-prefetch**

_Preload_ bisa digunakan untuk mendahulukan berbagai _resources_ yang kita yakini akan dipakai di halaman web tersebut seperti font, CSS maupun JavaScript dibandingkan _resources_ yang lain. Hanya gunakan _preload_ bila _resources_ tersebut benar-benar digunakan karena cara ini akan memberikan perintah ke browser untuk menetapkan _resources_ sebagai _high priorit_y dalam urutan _request_ yang akan dilakukan.

Berikut contoh menggunakan preload untuk memuat file CSS:

`&lt;link rel=&#34;preload&#34; href=&#34;path/file.css&#34; as=&#34;style&#34;&gt;`

_Prefecth_ hampir sama dengan _preload_ hanya saja memiliki prioritas dibawah _preload_. Gunakan _prefetch_ untuk memuat berbagai _resource_ yang kita yakini akan digunakan pada navigasi berikutnya setelah halaman terkait.

Artikel berikut akan membantu kita memahami preload dan prefetch:

[Preload, Prefetch And Priorities in Chrome](https://medium.com/reloading/preload-prefetch-and-priorities-in-chrome-776165961bbf)


_Dns-prefetch_ akan menjalankan DNS lookup untuk domain eksternal yang akan kita gunakan pada halaman website tersebut. _Dns-prefetch_ ini akan membawa _bandwith_ yang sangat kecil namun _latency_ yang cukup tinggi, karenanya hanya gunakan cara ini untuk domain eksternal yang memang benar-benar kita akan panggil pada halaman tersebut.
`&lt;!-- Prefetch DNS for external assets --&gt;  
&lt;link rel=&#34;dns-prefetch&#34; href=&#34;//fonts.googleapis.com&#34;&gt;`
[X-DNS-Prefetch-Control](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-DNS-Prefetch-Control)


**3. Browser Cache**

Browser pada dasarnya secara _default_ telah melakukan _cache_ pada semua _resources_ yang dia telah request agar pada request berikutnya tidak perlu meminta _resource_ yang sama kembali. Namun kita diharuskan untuk menyetel `max-age` atau `E-tag` di _header_ setiap _resource_ yang diminta agar browser bisa memahami kapan waktu yang tepat untuk meminta ulang resource tersebut. Hal ini sudah merupakan hal wajib yang harus dikerjakan oleh para pengembang web.

Bicara soal _cache_, hal yang paling menyulitkan adalah menentukan kapan waktu yang tepat untuk dilakukan _evict_ terhadap _cache_ tersebut. Pengembang web harus tau kapan waktu yang tepat untuk melakukan _evict_ atau memaksa browser meminta resource terbaru. Cara yang sering diterapkan oleh para pengembang web adalah dengan memberikan _signature/hash/finger print_ pada nama file dari _resource_ yang diminta. Sehingga bila dilakukan _deployment_ file terbaru maka _signature/hash/finger print_ tersebut akan berubah dan kita tidak perlu memusingkan lagi untuk meng-_evict_ _cache_ sebelumnya.

Artikel berikut membantu kita memahami bagaimana untuk memaksa browser melakukan _cache_ kepada file kita:

[Leverage Browser Caching | PageSpeed Insights | Google Developers](https://developers.google.com/speed/docs/insights/LeverageBrowserCaching)


**4. HTTP/2**

HTTP/2 merupakan generasi berikutnya dari HTTP/1 yang banyak digunakan oleh sebagian besar website. Bila di HTTP/1 kita susah untuk melakukan banyak round-trip request dalam waktu yang hampir bersamaan, di HTTP/2 ini kita bisa melakukan beberapa request dalam waktu yang hampir bersamaan sehingga latency bisa dikurangi.

Untuk memahami HTTP/2 silahkan baca artikel berikut ini:

[Introduction to HTTP/2 | Web Fundamentals | Google Developers](https://developers.google.com/web/fundamentals/performance/http2/)
Dan terakhir, silahkan tonton video menarik [Addy Osmani](https://medium.com/u/2508e4c7a8ec) mengenai bahasan kita kali ini. Jangan lupa aktifkan _subtitles_ kalau yang kurang baik pendengarannya kaya saya ini.




Modern Loading Best Practice by Addy Osmani in #ChromeDevSummit2017



### 📚 Referensi Artikel

1.  [https://developers.google.com/web/tools/chrome-devtools/network-performance/reference](https://developers.google.com/web/tools/chrome-devtools/network-performance/reference)
2.  [https://www.smashingmagazine.com/2008/08/7-principles-of-clean-and-optimized-css-code/](https://www.smashingmagazine.com/2008/08/7-principles-of-clean-and-optimized-css-code/)
3.  [https://www.smashingmagazine.com/2015/08/understanding-critical-css/](https://www.smashingmagazine.com/2015/08/understanding-critical-css/)
4.  [https://developers.google.com/speed/docs/insights/OptimizeCSSDelivery](https://developers.google.com/speed/docs/insights/OptimizeCSSDelivery)
5.  [https://medium.com/dev-channel/the-cost-of-javascript-84009f51e99e](https://medium.com/dev-channel/the-cost-of-javascript-84009f51e99e)
6.  [https://bitsofco.de/async-vs-defer/](https://bitsofco.de/async-vs-defer/)
7.  [https://images.guide/](https://images.guide/)
8.  [https://developers.google.com/speed/docs/insights/EnableCompression](https://developers.google.com/speed/docs/insights/EnableCompression)
9.  [https://medium.com/reloading/preload-prefetch-and-priorities-in-chrome-776165961bbf](https://medium.com/reloading/preload-prefetch-and-priorities-in-chrome-776165961bbf)
10.  [https://responsivedesign.is/articles/prefetch-preconnect-dns-priority/](https://responsivedesign.is/articles/prefetch-preconnect-dns-priority/)
11.  [https://developers.google.com/web/fundamentals/performance/http2/](https://developers.google.com/web/fundamentals/performance/http2/)

—

#### Log Update Artikel

*   09 juli 2018 — Menambahkan async dan defer di bagian JS.
*   10 juli 2018 — Fixing typo dan menambahkan referensi mengenai image spriteBila kamu suka dengan tulisan ini, silahkan tekan tombol 👏 sebanyak-banyaknya dan mohon bantuannya untuk share 📲 di sosial media kalian bila kalian rasa artikel ini akan bermanfaat bagi orang lain.

Saya [Irfan Maulana](https://medium.com/u/d09eac079a9c), kalian bisa ikuti tulisan-tulisan saya di berbagai publikasi Medium seperti [Vuejs-ID](https://medium.com/vuejs-id), [AngularID](https://medium.com/angularid), [WWWID](https://medium.com/wwwid/), dan [mazipan-mind](https://medium.com/mazipan-mind). Saya menulis berbagai hal teknikal maupun non-teknikal terkait dengan dunia programming terutama yang berkaitan dengan web programming dan sebagian besar saya tulis dalam bahasa Indonesia. Saya juga senang bereksplorasi dan membuat berbagai percobaan mengenai apa yang saya sudah atau sedang saya pelajari. Anda bisa ikuti dan lihat semuanya di Github saya di [🐙 mazipan](https://github.com/mazipan).
