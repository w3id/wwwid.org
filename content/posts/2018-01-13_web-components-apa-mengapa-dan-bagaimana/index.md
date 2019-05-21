---
title: "Web Components — Apa, Mengapa dan Bagaimana"
author: "Satya Kresna Adi Pratama"
date: 2018-01-13T00:38:26.546Z
lastmod: 2019-05-20T16:26:47+07:00

description: ""

subtitle: "Pendahuluan"
tags:
 - Webcomponents 
 - Web 
 - Shadow Dom 
 - Custom Elements 
 - Html Templates 

image: "/posts/2018-01-13_web-components-apa-mengapa-dan-bagaimana/images/1.png" 
images:
 - "/posts/2018-01-13_web-components-apa-mengapa-dan-bagaimana/images/1.png" 
 - "/posts/2018-01-13_web-components-apa-mengapa-dan-bagaimana/images/2.png" 
 - "/posts/2018-01-13_web-components-apa-mengapa-dan-bagaimana/images/3.png" 
 - "/posts/2018-01-13_web-components-apa-mengapa-dan-bagaimana/images/4.png" 
 - "/posts/2018-01-13_web-components-apa-mengapa-dan-bagaimana/images/5.png" 
 - "/posts/2018-01-13_web-components-apa-mengapa-dan-bagaimana/images/6.png" 
 - "/posts/2018-01-13_web-components-apa-mengapa-dan-bagaimana/images/7.png" 


aliases:
    - "/web-components-apa-mengapa-dan-bagaimana-d23f60951dfa"
---

![image](/posts/2018-01-13_web-components-apa-mengapa-dan-bagaimana/images/1.png)

Web Components — Apa, Mengapa dan Bagaimana?



### Pendahuluan

Sebagai web developer, wajib hukumnya untuk up to date terhadap teknologi web mulai dari dengerin podcast, lihat forum, follow para developer dan engineer di Twitter dan baca artikel di [WWWID](https://medium.com/wwwid) tentunya. 😉

Pernahkah anda membuka sebuah website dan iseng meng-inspect elemen atau view page source dan menemukan tag HTML yang tak lazim (contoh: `&lt;foo-bar&gt;` atau `&lt;custom-tag&gt;`)? Mungkin anda akan berpikir jika tag HTML tersebut tidak tersedia [di tag HTML](https://developer.mozilla.org/en-US/docs/Web/HTML/Element) pada umumnya. Jika anda menemukannya, selamat anda telah menemukan sebagian kepingan dunia web modern jaman now. Perkenalkan Web Components, sebuah fitur bagi anda untuk menciptakan tag HTML milik anda sendiri.

### TL;DR

#### Apa itu Web Components?

Secara singkat, Web Components adalah set plaform web API untuk membuat custom tag HTML yang reusable (bisa digunakan kembali) dan dienkapsulasi (child-tag dibungkus oleh parents-tag) di halaman atau aplikasi web yang kita miliki.

#### Mengapa dia lahir?

Web developer mengalami ketergantungan beragam framework dan library dalam membangun dan memelihara aplikasi. Ketergantungan yang saya maksud adalah membangun tag HTML element yang diberi CSS dan JS. Jika anda menggunakan sebuah framework seperti Bootstrap untuk membangun sebuah tag button, navs dan pagination kurang lebih sintaksnya seperti ini:

**Bootstrap button**




**Bootstrap nav**




**Bootstrap pagination**




Jika menggunakan Web Components, anda dapat mendefinisikan nya dengan tag — tag di atas seperti source code di bawah.

**Custom button**




**Custom nav**




**Custom pagination**




Bagaimana? Tidak ada “div” dan anda menciptakan tag html buatan anda. Masih ingat dengan pasal mutlak “Programmer itu pemalas”? ❤️ Web Components.

Web components lahir dari konsep desain yg modular (standar) dengan tujuan memudahkan para developer untuk menciptakan komponen atau elemen web yg dapat diperpanjang (extensible), digunakan kembali (reusable), mudah dipelihara (maintainable). Selain itu dengan dapat memudahkan kita melakukan pemisahan konsentrasi terhadap komponen kita (separation of concern) mulai dari scoping style CSS hingga DOM di JavaScript.

#### Bagaimana proses lahirnya Web Components?

Semula, istilah “web components” digunakan oleh Microsoft untuk menggambarkan add-ons mereka ke Office. Kemudian Sun, sekarang yang dikenal sebagai Oracle, digunakan untuk menggambarkan Java servlets. Kata “component” juga bukanlah hal yang baru ketika membahas CBSE (Component Based Software Engineering), yang didasarkan pada pendekatan pengembangan sistem perangkat lunak dengan memilih komponen yang sudah ada dan kemudian merakitnya menggunakan arsitektur perangkat lunak yang terdefinisi dengan baik. Sejak awal tahun 2011 dan juga sekarang, istilah “Web Components” telah digunakan merujuk pada standar W3C yang baru.

Pengembangan “Web Components” yang modern dapat ditelusuri kembali di tahun 2005, dengan dimulainya revolusi “AJAX” dan server side framework RAD (Rapid Application Development) seperti Ruby on Rails, CakePHP dan Django. Teknologi ini membantu pengembangan front-end dengan memberikan konten secara asynchronous sambil mempertahankan kinerja dan memungkinkan situs web dibangun dalam beberapa minggu daripada beberapa bulan. Selain itu, pada tahun 2005, toolkit DOJO diluncurkan, memungkinkan pengembang menambahkan widget ke situs web mereka hanya dengan beberapa baris kode. Hal ini semakin menggarisbawahi keuntungan pembuatan modul yang dapat digunakan kembali (reusable modules).

Pada tahun 2006, library JavaScript, jQuery dirilis. Library ini memungkinkan developer untuk menulis program JavaScript memanfaatkan API yang disederhanakan untuk interaksi DOM di berbagai macam web browser. Ini membantu memulai era “single page apps”. Mendampingi kesuksesan jQuery, banyak sekali library front-end, toolkit dan framework lainnya termasuk YUI, Prototype dan Extjs — masing-masing berisi stok widget library mereka sendiri. Sekitar tahun 2010 terlihat kemajuan besar dalam pengembangan sisi klien dan popularitas aplikasi satu halaman, yang mengarah ke implementasi sisi klien dari pola MV* (Model View Whatever). Di sini, pentingnya komponen UI yang dapat digunakan kembali dan dienkapsulasi menjadi semakin relevan karena kode yang menggelembung dalam single web apps berskala besar dan front-end framework.

Saat ini library, toolkit dan framework semua tampaknya memiliki keterbatasan besar — keduanya tidak berinteraksi dengan baik, developer juga tidak bisa dengan mudah mencampur dan mencocokkan komponen dari framework atau library yang berbeda. Keterbatasan utama lainnya saat bekerja dengan komponen berbasis library adalah platform browser itu sendiri.
> Jika vendor browser berhasil membangun kemampuan untuk mengenkapsulasi, mengemas, dan menggunakan kembali kode HTML dan DOM API sebelum revolusi AJAX, perkembangan web modern mungkin akan sangat berbeda hari ini. Inilah yang ditawarkan oleh Web Components — dukungan native browser untuk memperluas, mengemas, mengenkapsulasi, dan mengimpor UI.

Google telah menjadi advokat terdepan untuk Web Components sejak draf W3C pertama di bulan Mei 2012, yang dipimpin oleh dua Googler yakni [Dimitri Glazkov](https://github.com/dglazkov) dan [Hayato Ito](https://twitter.com/hayatoito). Investasi Google dalam Web Components terbukti pada tahun 2013 Google I/O di mana mereka mengumumkan Polymer, library ciptaan mereka untuk membangun komponen. Sejak itu, banyak sumber daya website seperti [webcomponents.org](http://webcomponents.org) dan customelements.io dan framework seperti [X-tag](https://x-tag.github.io/) dan [Bosonic](http://bosonic.github.io/), memungkinkan penerapan komponen web secara modern dengan dukungan browser yang lebih baik.

#### Apa spesifikasi dari web components?

Web Components memiliki empat spesifikasi meliputi:

**A. Custom Elements**  
 Salah satu yang bisa saya katakan menonjol dari Web Components adalah Custom Elements. Ia adalah sebuah spesifikasi atau syarat yang memperbolehkan developer untuk membuat tag HTML baru, mengextend tag HTML yang sudah ada atau mengextend komponen yang telah dibuat oleh developer lain. Custom Elements menyediakan sebuah jalan secara native untuk membuat komponen yang dapat digunakan kembali (re-usable components). Spesifikasi ini harus didefinisikan dalam JavaScript dan memiliki beberapa siklus kehidupan (lifecycle) seperti kode di bawah.




Jika anda ingin menambahkan DOM ke dalam elemen dapat dilakukan dengan menambahkan markup ke dalam  
 `this.innerHTML`:




Hal — hal yang harus diperhatikan:

*   Nama harus terdiri dari minimal dua kata dan berisi tanda strip (-) untuk memisahkan setiap kata (contoh: `&lt;foo-bar&gt;`). Kita sebut ini dengan istilah **_kebab-case._**
*   Nama harus unik.
*   Custom Elements harus disertai dengan closing tag (contoh: `&lt;foo-bar&gt;&lt;/foo-bar&gt;`) dan tidak bisa melakukan self closing tag (contoh: `&lt;foo-bar&gt;` tidak bisa).
*   Berdasarkan spesifikasi custom elements, kita bisa meng-extend tag HTML element native yang sudah ada (contoh: `HTMLButtonElement`). Jika anda melakukannya maka, elemen kustom yang kita buat akan mewarisi langsung semua fungsionalitas yang ada di `HTMLButtonElement`. Sayangnya, hal ini belum diimplementasikan di browser manapun. 😭
*   HTML template adalah tempat yang ideal untuk markup (shadow) DOM sebuah custom elements.
*   Selalu tambahkan method getter dan setter untuk semua dan setiap jenis atribut yang anda gunakan.

**HTML Templates**  
 HTML templates adalah spesifikasi atau syarat yang memberikan memperbolehkan developer untuk mendeklarasikan fragment (potongan) markup yang mana diurai sebagai HTML, tidak dipakai saat loading halaman, tetapi dapat diinstansiasi nanti saat dijalankan (runtime).

Membuat template semudah seperti membuat elemen DOM pada umumnya.




Hal — hal yang harus diperhatikan:

*   Isi dari template tidak aktif sampai diaktifkan.
*   Tidak ada efek samping sampai template digunakan.
*   Konten dianggap tidak berada di DOM.
*   Template dapat ditempatkan di manapun.
*   Tidak ada bentuk native data-binding. Jadi, anda masih memerlukan sebuah library untuk mengatasinya atau menulis beberapa logika bisnis sendiri untuk benar-benar mengisi template dengan konten yang bermanfaat.

**Shadow DOM**  
 Shadow DOM hanyalah sebuah DOM yang normal dengan dua perbedaan: 1) bagaimana dia dibuat/digunakan dan 2) bagaimana berperilaku dalam kaitannya dengan sisa halaman. Biasanya, anda membuat sebuah DOM nodes dan menambahkan mereka sebagai anak di elemen lain. Dengan shadow DOM, anda dapat membuat sebuah ruang lingkup (scoped) DOM tree yang disisipkan ke dalam sebuah elemen, tetapi terpisah dari anak yang sebenarnya. Ruang lingkup subtree ini disebut dengan shadow tree. Elemen yang disisipkan disebut dengan shadow host. Semua yang anda tambahkan ke dalam shadow menjadi lokal ke elemen yang dihost, termasuk `&lt;style&gt;`. Seperti inilah bagaimana shadow DOM mencapai ruang lingkup style CSS.

Anda mungkin telah menggunakan shadow DOM sebelumnya, bahkan ketika anda tidak menyadarinya. Browser menggunakan shadow DOM untuk beragam elemen HTML native seperti range input:




![image](/posts/2018-01-13_web-components-apa-mengapa-dan-bagaimana/images/2.png)

shadow-root user agent pada input type=”range”



Anda belum bisa melihat shadow-root (user-agent) pada elemen HTML native. Yang perlu anda lakukan adalah klik kanan `inspect element` &gt; pilih opsi `Settings` &gt; pilih sesi `Elements` &gt; centang `Show user agent shadow DOM`. Jika anda mengalami kesulitan, anda bisa melihatnya di [video ini](https://www.youtube.com/watch?v=7gDvFlvoZKQ).
> Jika anda membuat style CSS dengan `id=&#34;track&#34;` atau `id=&#34;thumb&#34;` apakah akan berpengaruh terhadap shadow root di input type=&#34;range&#34;?

API shadow DOM mengijinkan developer untuk membuat dan menyisipkan shadow DOM ke dalam elemen, yang mana sangat bagus jika digabungkan dengan Custom Elements.

Hal — hal yang harus diperhatikan:

*   Style yang menggunakan shadow DOM hanya akan berpengaruh pada ruang lingkup (scoped) elemen itu saja.
*   Gunakan `:host` selector untuk style parent container.
*   `position: fixed` and posisi CSS lainnya digunakan untuk membatasi komponen sebagai &#34;viewport&#34;.
*   Style CSS dari elemen di dalam shadow-root dapat ditimpa dari light-dom (“regular” / “parent” -dom).

**HTML Imports**  
 Biasanya kita dapat mengimpor aset seperti CSS dengan tag `&lt;link rel=&#34;stylesheet&#34;&gt;` dan JavaScript dengan tag `&lt;script src=&#34;foobar.js&#34;&gt;` file ke dalam markup HTML. Pernahkah anda mencoba mengimpor sebuah dokumen HTML? Jika iya, maka HTML import sudah tidak asing bagi anda. Dengan HTML imports, anda dapat menyisipkan dokumen HTML. Anda bisa mengimpor satu dokumen yang isinya HTML, CSS dan JavaScript sesuai dengan kebutuhan anda.

Mengimpor dokumen HTML sangat mirip dengan impor sebuah style CSS:

`&lt;link rel=&#34;import&#34; href=&#34;foobar.html&#34; /&gt;`

Dengan segera file yang dimpor akan diload, script yang disematkan akan berjalan dan kontennya dapat digunakan dengan mereferensikan properti `import` dari elemen:
``const content = document.querySelector(&#39;link[rel=&#34;import&#34;]&#39;).import;``

API ini akan berguna ketika mengimpor custom elements lainnya.
> _Salah satu catatan utama tentang dukungan browser terhadap HTML Import: Chrome telah menerapkan (implement) dan mengirimkannya (shipped), namun WebKit dan Firefox tidak akan menerapkannya sama sekali. WebKit menetapkan bahwa mereka ingin menyelidiki kombinasi dengan modul ES6._

Hal — hal yang perlu diperhatikan:

*   `link rel=import` de-duplikat semua permintaan secara otomatis
*   Dokumen yang diimpor tidak ditempatkan di DOM manapun, hanya dibuat tersedia untuk gunakan.
*   Tag `&lt;script&gt;` di dalam dokumen impor akan berjalan pada HTML import.
*   Statement import dibloking secara default, tetapi menerima atribut `async`.
*   Ketika mengakses `document` dari dalam dokumen yang akan diimpor, sebenarnya anda mengakses parent document. `document.currentScript.ownerDocument` merujuk kepada &#34;child&#34;-document.
*   HTML import yang bersarang akan mengencangkan (screw) dengan `document.currentScript.ownerDocument`. Untuk mencegah hal tersebut, bungkus script bersarang tersebut di dalam [IIFE](https://developer.mozilla.org/en-US/docs/Glossary/IIFE) dengan `document.currentScript.ownerDocument` sebagai parameter.

#### Bagaimana cara membuat vanilla web components?

Sejauh ini, saya menemukan dua contoh yang bagus dan baik untuk membuat vanilla web components (tanpa framework dan library). Silahkan anda membaca di link [codementor.io (studi kasus user card)](https://www.codementor.io/ayushgupta/vanilla-js-web-components-chguq8goz) dan [github.com milik Rijk van Zanten (studi kasus NASA Apod)](https://github.com/rijkvanzanten/nasa-apod). Jika anda menemukan contoh bagus lainnya silahkan beri komentar di artikel ini. 😉

#### Bagaimana status web components saat ini?

Berdasarkan situs caniuse.com, status web components sebagai gambar di bawah dan saya mengaksesnya pada tanggal 12 Januari 2018. Jadi, akan ada perubahan di waktu yang tidak ditentukan.




![image](/posts/2018-01-13_web-components-apa-mengapa-dan-bagaimana/images/3.png)

Dukungan Custom Elements via caniuse





![image](/posts/2018-01-13_web-components-apa-mengapa-dan-bagaimana/images/4.png)

Dukungan shadow DOM via caniuse





![image](/posts/2018-01-13_web-components-apa-mengapa-dan-bagaimana/images/5.png)

Dukungan HTML templates via caniuse





![image](/posts/2018-01-13_web-components-apa-mengapa-dan-bagaimana/images/6.png)

Dukungan HTML imports via caniuse



Hal — hal yang perlu diperhatikan:

*   Kita masih belum bisa mengextend elemen native HTML a.k.a. customized built-in elements (contoh: `HTMLButtonElement`) untuk membuat Custom Elements seperti yang dijelaskan pada gambar Custom Elements via caniuse.
*   Firefox, WebKit tidak mempertimbangkan untuk membuat spesifikasi HTML Imports di browser mereka. Info terakhir yang saya dapatkan bahwa [Chrome juga akan menghapus HTML Imports di browser mereka segera sekitar bulan Maret tahun 2018](https://github.com/TakayoshiKochi/deprecate-style-in-html-imports). Sebagai gantinya para browser vendor akan menggantinya dengan HTML Module a.k.a. ES6 modules.
*   [Custom Elements versi 1 telah dirilis pada Firefox Nightly](https://twitter.com/FirefoxNightly/status/951009715584225280). 🎉

**Mengapa belum disupport secara menyeluruh?**

Perlu kita ketahui bahwa pekerjaan browser vendor tidak hanya mengurusi Web Components saja. Banyak fitur lain yang harus mereka prioritaskan sesuai dengan kebijakan para browser vendor. Contoh [Safari](https://webkit.org/blog/8042/release-notes-for-safari-technology-preview-46/) dan [Ms. Edge](https://twitter.com/MSEdgeDev/status/943181166554705920) meluncurkan Service Worker secara default di browser Tech Preview di bulan Desember 2017. Kemudian, kali ini Safari sedang mengembangkan web manifest, salah satu syarat untuk PWA berdasarkan [tweet Maximiliano Firtman](https://twitter.com/firt/status/951216290991104000). Lalu bagaimana solusi agar bisa disupport secara menyeluruh? Web Components telah menyediakan sebuah [polyfills](https://www.webcomponents.org/polyfills/) untuk menanggulangi hal tersebut. Menurut perspektif saya, polyfill bersifat sementara hingga semua browser vendor mendukung Web Components dan para pengguna tidak menggunakan Internet Explorer seperti gambar yang saya dapatkan di situs [w3schools.com (Browser Statistics)](https://www.w3schools.com/browsers/).




![image](/posts/2018-01-13_web-components-apa-mengapa-dan-bagaimana/images/7.png)

browser statistics via w3schools



**Apa yang harus saya lakukan selanjutnya?**

Artikel ini hanyalah sebagian kecil dari dunia Web Components, berikut referensi dari saya jika anda ingin mengenal lebih dekat dengan Web Components:

Indonesia

*   [Podcast Web Components bersama Developer Muslim](https://devmuslim.id/post/034-web-components-dengan-satya-kresna/?utm_campaign=crowdfire&amp;utm_content=crowdfire&amp;utm_medium=social&amp;utm_source=twitter#904897702894362625-tw#1515558989470)
*   [Try Web Components](https://github.com/satyakresna/try-web-components)

Inggris

*   [Web Components specification](https://github.com/w3c/webcomponents)
*   [Web Components website](http://webcomponents.org)
*   [Brief history of Web Components](https://www.slideshare.net/YevgeniyValeyev/brief-history-of-web-components-72452483)
*   [Web Components -Kaitlin Rathwell](http://kaytcat.github.io/web-components/)
*   [An intro to web components with otters](https://meowni.ca/posts/web-components-with-otters/)
*   [Modular web design web components](http://infoq.com/presentations/modular-design-web-components)
*   [Wonderful of Web Components](https://hackernoon.com/the-wonderful-world-of-web-components-e4c1675c6901)
*   [A Practical Guide to Vanilla Web Components](https://app.pluralsight.com/library/courses/vanilla-web-components-practical-guide/table-of-contents)
*   [Why I’m Betting on Web Components (and You Should Think About Using Them Too)](https://medium.com/@gilfink/why-im-betting-on-web-components-and-you-should-think-about-using-them-too-8629396e27a)
*   [Building Components](https://developers.google.com/web/fundamentals/web-components/)
*   [How to components](https://github.com/GoogleChromeLabs/howto-components)

Terima kasih kepada anda yang telah membaca artikel saya tentang web components, semoga bermanfaat. Jika ada yang ingin disampaikan berupa kritik, saran dan pertanyaan silahkan berkomentar di artikel ini.
