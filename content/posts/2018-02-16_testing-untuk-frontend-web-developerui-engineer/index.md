---
title: "Testing untuk Frontend Web Developer/UI Engineer"
author: "Fariz Rizaldy"
date: 2018-02-16T00:28:22.740Z
lastmod: 2019-05-20T16:27:09+07:00

description: ""

subtitle: "Karena Frontend Developer tidak hanya mengconvert design menjadi halaman"

image: "/posts/2018-02-16_testing-untuk-frontend-web-developerui-engineer/images/1." 
images:
 - "/posts/2018-02-16_testing-untuk-frontend-web-developerui-engineer/images/1." 
 - "/posts/2018-02-16_testing-untuk-frontend-web-developerui-engineer/images/2.png" 
 - "/posts/2018-02-16_testing-untuk-frontend-web-developerui-engineer/images/3.png" 
 - "/posts/2018-02-16_testing-untuk-frontend-web-developerui-engineer/images/4.png" 
 - "/posts/2018-02-16_testing-untuk-frontend-web-developerui-engineer/images/5.png" 
 - "/posts/2018-02-16_testing-untuk-frontend-web-developerui-engineer/images/6.png" 


aliases:
    - "/testing-untuk-frontend-web-developer-ui-engineer-c1e27e7e2742"
---

![image](/posts/2018-02-16_testing-untuk-frontend-web-developerui-engineer/images/1.)

“Long colorful lines of code on a computer screen” by [Markus Spiske](https://unsplash.com/@markusspiske?utm_source=medium&amp;utm_medium=referral) on [Unsplash](https://unsplash.com?utm_source=medium&amp;utm_medium=referral)

#### Karena Frontend Developer tidak hanya mengconvert design menjadi halaman

### Latar Belakang

Sudah 9 bulan lebih saya bekerja menjadi seorang Frontend Developer di sebuah startup yang bergerak di bidang edukasi. Karena produk kami merupakan produk digital — salah satu nya berbentuk website — dan kebetulan saya merupakan penanggung jawab di hasil akhir untuk pengguna langsung di website.

Banyak yang saya pelajari dari menjadi seorang Frontend Developer untuk skala enterprise. Salah satu nya adalah tentang penting nya testing. Sebelum nya saya **tidak pernah** menulis testing sedikitpun di Frontend, karena memang saya belum menemukan penting nya testing di Frontend. Terlebih saya termasuk orang yang belajar [Just In Time](https://en.wikipedia.org/wiki/Just-in-time_teaching), mempelajari nya ketika memang butuh.

Dan karena dulu belum butuh-butuh banget sama testing, jadi belum dipelajari. Dan setelah ‘tau’ penting nya menulis test, baru saya pelajari perlahan.

### Kenapa menulis test?

Sebagai seorang Frontend Developer yang bekerja langsung dengan tampilan akhir, terkadang kita merasa _ngapain sih nulis testing segala, kan kita test nya bisa langsung di real browser?_

Itu enggak salah, setidaknya untuk saat ini. Apakah kalian pernah merasakan dikirim pesan di Telegram/Slack oleh seorang QA Tester atau siapapun tentang bug yang ada pada UI kita? Sebagai seorang Frontend Developer di era sekarang, kita tidak hanya mengubah desain menjadi suatu halaman. User Interface merupakan sebuah fungsi pada state di aplikasi kita.

Setiap state yang berubah pada aplikasi kita, kita ingin tampilan tersebut merefleksikan perubahan nya. State bila data tidak ada, maka tampilan nya seperti apa; State ketika user sedang menginput di searchbar, maka tampilan nya seperti apa. Dan lain-lain.

Agar semua nya _make sure works well,_ tentu kita perlu menulis test agar proses lebih efektif. Tentu testing secara automatis lebih efektif daripada manual, kan?

### Testing untuk Frontend Developer/UI Engineer

Sama seperti untuk developer apapun. Unit Testing, Integration Testing dan End-to-End Testing. Tapi untuk yang bekerja di Web, dua testing ekslusif: Visual Regression Testing &amp; Snapshot Testing.

Kita akan bahas satu-satu.

#### Unit Testing

Unit Testing merupakan proses testing dari hal-hal yang terkecil. Misal kita membuat sebuah component Search Bar dari component Navbar (saya ambil contoh dari KelasKita)




![image](/posts/2018-02-16_testing-untuk-frontend-web-developerui-engineer/images/2.png)

Navbar di KelasKita



Unit-unit yang akan kita test dari Search Bar tersebut adalah:

1.  Apakah component berhasil di mount?
2.  Kita mengetik: “Belajar Android”, apakah state nya sama dengan apa yang kita ketik (Belajar Android)?
3.  Apakah muncul hasil pencarian (dari data dummy), misal: “Belajar Android untuk pemula”, “Belajar Android selama 99 hari”, dan “Belajar Android dengan React Native”
4.  Membuat validasi, misal minimal kita input 3 karakter. Apakah fungsi di submit sukses/gagal apabila kata kunci kurang dari 3 karakter?
5.  Apakah icon search tersebut bisa diklik apabila kata kunci kurang dari 3 karakter?

Hal yang perlu diingat adalah jangan menulis test ketika proses development; Bila kamu menggunakan proses Test-driven Development, karena sudah jelas: TDD merupakan proses pengembangan yang di-stir oleh test.

Jadi sebelum kamu menulis kode ‘asli’, kamu harus menulis testing nya terlebih dahulu. Ini yang buat saya bingung waktu dulu.

Lanjut. Hasil dari testing hanya satu dari 2 pilihan: Sukses &amp; Gagal. Karena di TDD ini siklus nya seperti ini:




![image](/posts/2018-02-16_testing-untuk-frontend-web-developerui-engineer/images/3.png)

Red -&gt; Green -&gt; Refactor



Apa maksud dari siklus tersebut?

1.  Tulis test case tersebut (dan pasti gagal)
2.  Tulis kode yang membuat test case tersebut sukses
3.  Refactor code

Misal kita ambil contoh dari test case diatas, _Apakah component berhasil di mount?_ Kita gunakan pseudo-code terlebih dahulu untuk saat ini:
`&lt;!-- HTML --&gt;``&lt;body&gt;  
&lt;/body&gt;``// JavaScript``(function () {``  const searchBarComponent = document.querySelector(&#39;.c-searchbar.qa-searchbar&#39;)``  // Test 1``  console.log(searchBarComponent) // undefined!``}())`

Tentu gagal, karena `searchBarComponent` tidak ada. Mari kita buat test tersebut berhasil.
`&lt;!-- HTML --&gt;``&lt;body&gt;  
  &lt;input class=&#34;c-searchbar qa-searchbar&#34; /&gt;  
&lt;/body&gt;``// JavaScript``(function () {``  const searchBarComponent = document.querySelector(&#39;.c-searchbar.qa-searchbar&#39;)``  // Test 1``  console.log(searchBarComponent) // pass!``}())`

Sekarang test tersebut berhasil. Mari kita refactor kode nya.
`&lt;!-- HTML --&gt;``&lt;body&gt;  
  &lt;form&gt;  
    &lt;input  
      type=&#34;text&#34;  
      class=&#34;c-searchbar qa-searchbar&#34;  
      placeholder=&#34;Cari kelas atau keterampilan yang ingin kamu pelajari&#34;  
    /&gt;  
  &lt;/form&gt;  
&lt;/body&gt;``// JavaScript``(function () {``  const searchBarComponent = document.querySelector(&#39;.c-searchbar.qa-searchbar&#39;)``  // Test 1``  console.log(searchBarComponent) // pass!``}())`

Lalu testing lagi, apakah sukses/gagal? Jika sukses, buat test lain, jika gagal, lakukan perubahan agar test tersebut berhasil.
> Yaelaaa Riz, gitu doang mah masih bikin enggak ngerti sama Unit Testing. Contoh lagi, dong!

Test case kedua: Kita mengetik: “Belajar Android”, apakah state nya sama dengan apa yang kita ketik (Belajar Android)?
`&lt;!-- html --&gt;  
&lt;body&gt;  
  &lt;form&gt;  
    &lt;input  
      type=&#34;text&#34;  
      class=&#34;c-searchbar qa-searchbar&#34;  
      placeholder=&#34;Cari kelas atau keterampilan yang ingin kamu pelajari&#34;  
    /&gt;  
  &lt;/form&gt;  
&lt;/body&gt;``// JavaScript``(function () {``  const searchBarComponent = document.querySelector(&#39;.c-searchbar.qa-searchbar&#39;)``  const appState = { searchQuery: &#39;&#39; }``  searchBarComponent.value = &#34;Belajar Android&#34;``  // Okay this is weird, I&#39;m sorry.``  appState.searchQuery = searchBarComponent.value``  // Test 1``  console.log(searchBarComponent.length &gt; 0) // pass!``  // Test 2``  console.log(searchBarComponent.value === appState.searchQuery) // pass!``}())`

Okay ini berhasil. Meskipun sangat tidak disarankan (cuma buat contoh aja ya).

#### Integration Testing

Setelah kita melakukan proses development berdasarkan dari unit-unit kecil yang dibuat beserta fungsionalitas nya, sekarang kita akan mulai ke integration testing.

Agar tidak pusing tentang perbedaan Integration Testing dengan Unit Testing, Unit Testing adalah mentesting fungsionalitas dari unit-unit tersebut, sedangkan Integration Testing adalah mentesting dengan real data (integrasi)

Masih di Searchbar tadi, anggap semua testing tersebut sudah berhasil. Lalu kita integrasi dengan real data.

1.  Ketika user input dan lebih dari 3 karakter, maka request ke: [https://domain.com/api/v1/search/?q=kataKunci](https://domain.com/api/v1/search/?q=kataKunci)
2.  Apakah request berhasil?
3.  Apakah menampilkan hasil data berdasarkan kata kunci tersebut?



![image](/posts/2018-02-16_testing-untuk-frontend-web-developerui-engineer/images/4.png)

Dropdown hasil pencarian yang data nya diambil dari system. Mungkin search logic nya menggunakan fuzzy search

Make it fail:

❎ Not request to endpoint  
❎ Only type ≤ 2 characters

Make it pass:

✅ Request to endpoint  
✅ Input ≥ 3 characters

Make it better:

✅ Show warning message if user input ≤ 2 characters

Library yang biasa digunakan untuk Unit Testing &amp; Integration Testing: [Jest](https://facebook.github.io/jest/), [Ava](https://github.com/avajs/ava), [Chai](https://chaijs.com) dan [Tape](https://github.com/substack/tape).

#### End-to-End Testing

End-to-End testing merupakan testing yang benar-benar seperti bagaimana user menggunakan aplikasi kita. Ketika Unit Testing &amp; Integration Testing hanya melakukan berdasarkan skenario, end-to-end testing benar-benar berdasarkan interaksi user didunia nyata.

Masih mengambil contoh di searchbar.

User klik searchbar, lalu ketik “Be”. Kita buat delay selama 3 detik, karena searchbar harus diisi dengan 3 karakter lebih, maka akan menampilkan error message.

Dan kita bisa tau error message nya itu seperti apa tampilan nya. Lalu dilanjutkan dengan mengetik “Belajar Android…”. Lalu muncul hasil pencarian. Lalu user klik salah satu link nya. Case untuk “End-to-end testing searchbar pun selesai”.

Bedanya dengan tes langsung di browser adalah: Automatisasi. Ya, kita enggak usah capek-capek ngelakuin all possible action secara manual.

Library yang biasa digunakan untuk E2E Testing: [Selenium](http://www.seleniumhq.org/), [Protractor](http://www.protractortest.org/), dan [Cypress](https://www.cypress.io/) (Very looks promising!)

#### Snapshot Testing

Snapshot testing mungkin hanya berlaku di yang component-based, seperti React, Vue, dll. Snapshot Testing berguna untuk mencegah perubahan UI yang tidak sesuai espektasi kita.

Jadi pertama kita lakukan snapshot testing, dan ketika sukses akan menyimpan snapshot tersebut. Snapshot berbeda dengan screenshot, karena disini tidak menyimpan/membandingkan piksel sedikitpun.

Workflownya: Kamu bikin component, lalu buat snapshot testing. Bila belum memiliki snapshot sebelumnya yang disimpan, maka dibuat. Dan test pasti pass. Jika snapshot sebelumnya ternyata sudah ada, maka bandingkan. Jika beda, maka test fail.

Saya belum menemukan ‘manfaat’ dari snapshot testing ini, jadi belum tertarik untuk mempelajari nya lebih lanjut.

Berdasarkan dari dokumentasi nya tentang manfaat Snapshot Testing:
> Snapshot Testing berguna untuk mencegah perubahan UI yang tidak sesuai espektasi kita.

Terlihat sangat bermanfaat. Siapa sih yang enggak mau UI nya berubah dan ternyata perubahan nya tidak sesuai dengan espektasi kita? Jika menurut saya, snapshot testing ini bisa di case seperti ini:



![image](/posts/2018-02-16_testing-untuk-frontend-web-developerui-engineer/images/5.png)

Related category by topic di KelasKita

Related by Topic di KelasKita selalu berubah data nya (secara random) setiap top-level component dibuat (created, yeah we use Vue!). Lalu saya buat snapshot nya.

Lalu saya membuat perubahan. Misalnya data di random setiap ada perubahan di component. Ketika saya melakukan snapshot testing, pasti gagal. Karena beda dengan snapshot sebelumnya.

Jika ternyata perubahan tersebut sesuai espektasi kita, maka update snapshot. Jika tidak, maka kita perbaiki apa yang membuat UI tersebut berbeda.

Library yang biasa digunakan untuk Snapshot Testing: [Jest](https://facebook.github.io/jest/)

#### Visual Regression Testing

Ketika snapshot testing membandingkan snapshot (berbentuk text) yang dihasilkan dari hasil render, visual regression testing membandingkan berdasarkan screenshot (pixel).

Contoh Visual Regression Testing:




![image](/posts/2018-02-16_testing-untuk-frontend-web-developerui-engineer/images/6.png)

Contoh Visual Regression Testing diambil dari: [https://www.thecrumb.com/2016/05/01/wraith/](https://www.thecrumb.com/2016/05/01/wraith/)



Tentu visual regression testing berguna untuk mentrack perubahan pada UI kita secara visual. Sehingga kita tau element mana saja yang berubah. Tujuan nya sama saja dengan Snapshot testing: untuk mencegah perubahan UI yang tidak sesuai espektasi kita.

Library yang biasa digunakan untuk Visual Regression Testing: [PhantomJS](http://phantomjs.org/) (beserta plugin nya), [BackstopJS](https://garris.github.io/BackstopJS/), dan [Cypress](https://cypress.io).

### Testing apa saja yang harus saya pilih?

Jika kamu menggunakan metodologi TDD, maka Unit Testing &amp; Integration Testing. Karena Snapshot Testing, E2E Testing, dan Visual Regression Testing dilakukan ketika kita sudah membuat code yang sebenarnya (production code)

E2E Testing mungkin sangat recommended, daripada [‘QA Tester’, ‘Developer’, ‘Co-worker’], atau bahkan user mengetest dan menemukan bug pada aplikasi kamu secara manual. Meskipun _tracable_ menggunakan Error Logger (Sentry misalnya), tapi men-deliver aplikasi yang _stable_ dan _less bug_ ke pengguna akhir tentu lebih nyaman (karena sudah di test) dibanding kamu harus di japri pada waktu istirahat/nyantai/liburan ketika ada bug yang tak terduga di production

Jika kamu malas membuat test untuk snapshot testing &amp; visual regression testing, kamu bisa menggunakan layanan alternatif seperti [Saucelabs](https://saucelabs.com) dan [BrowserStack](https://www.browserstack.com) agar kamu bisa melihat hasil render langsung dari beberapa device, browser, dan beberapa sistem operasi.

Ya, kita Frontend Developer. Kita membuat UI yang nyaman dilihat di sistem operasi — Windows, Linux, Mac, iOS, Android, Windows Phone — di browser — Webkit family, Gecko Family, Firefox, Brave, Safari, Internet Explorer, Microsoft Edge, Google Chrome, Yandex, Opera, Opera Mini, Vivaldi, Dolphin Browser — di beberapa device (mobile, tablet, desktop) — di beberapa orientation — Landscape dan Potrait — dan lain-lain.

Kita pun harus membuat halaman memiliki performa yang cepat.

SEO yang bagus.

Interaksi yang responsif dan nyaman.

Basic Frontend Security.

Memiliki tampilan yang indah dilihat

Daaaan….

> [](https://mobile.twitter.com/wycats/status/930463710941872128)
Front end software development by Yehuda Katz



Sekian. Jika ada kesalahan, mohon diperbaiki.
