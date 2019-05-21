---
title: "Cara Mengecek dan Mengatur Versi Browser untuk Pengguna"
author: "Satya Kresna Adi Pratama"
date: 2019-03-06T00:13:10.000Z
lastmod: 2019-05-21T17:57:10+08:00

description: ""

subtitle: "User Agent berisikan informasi tentang nama browser, versi browser, sistem operasi, tipe perangkat dan banyak informasi yang berguna untuk…"
tags:
 - User Agent 
 - Browsers 
 - Browser Standard 

image: "/posts/2019-03-06_cara-mengecek-dan-mengatur-versi-browser-untuk-pengguna/images/1.jpeg" 
images:
 - "/posts/2019-03-06_cara-mengecek-dan-mengatur-versi-browser-untuk-pengguna/images/1.jpeg" 


aliases:
    - "/cara-mengecek-dan-mengatur-versi-browser-untuk-pengguna-1b3bb6e301be"
---

User Agent berisikan informasi tentang nama browser, versi browser, sistem operasi, tipe perangkat dan banyak informasi yang berguna untuk dipakai. Dalam pekerjaan, saya menggunakan informasi berupa nama browser dan versinya untuk mengendalikan browser dan versi yang digunakan oleh pengguna ketika mengakses ke sistem saya.
> _Daripada membuat sebuah library untuk menampung user-agent dari awal lebih baik saya menggunakan yang sudah ada dan banyak penggunanya. Terima kasih Github. :)_

Saya mengandalkan ua-parser-js untuk mengecek dan mengendalikan browser dan versi dari browser tersebut. Berikut kepingan kode terlampir di bawah:




Pertama, saya menambahkan ua-parser-js CDN ke dalam tag script. Kedua, saya melakukan instansiasi UAParser class. Ketiga, saya melakukan pengecekan untuk mengendalikan versi dari setiap browser.

Salah satu alasan mengapa saya melakukan hal ini adalah karena saya menggunakan ES6 (modern JavaScript) dalam mengembangkan sistem yang saya buat. Fitur-fitur ES6 yang saya gunakan antara lain `const`, `let`, `fetch` (XHR replacement), `template string literals`, `includes()`.

Kalangan pengguna sistem saya beragam umurnya dan tidak semua dari mereka melek dengan teknologi dan pernah beberapa kali mereka membuka website saya di ponsel pintar mereka namun data tidak tampil karena saya menggunakan ES6 dan yang bersangkutan tidak melakukan pembaharuan browser.
> _Daripada saya melakukan transpile ke ES5 atau menggunakan bantuan polyfill lebih baik saya mengecek browser mereka dan memaksa mereka untuk melakukan pembaharuan browser. ✌️_

Menurut saya, semenjak kehadiran ES6 dan dorongan dari tim TC39, ketergantungan dengan JQuery sebagai pihak ketiga dapat kita kurangi. Sekarang saya lebih sering menggunakan `getElementById`, `getElementsByClassName`, `querySelector`, `querySelectorAll`, `addEventListener` dan perintah lainnya untuk memilih elemen yang saya butuhkan yang mana sudah disediakan oleh browser secara alami.
> _Jika anda tertarik untuk berpindah dari JQuery ke JavaScript, silahkan Anda baca “You Might Don’t Need JQuery”. Hal ini akan membuat web Anda (sedikit) lebih cepat tanpa bantuan pihak ketiga._

Dari kode di atas pula saya menetapkan versi standar browser yang harus user gunakan ketika berinteraksi di sistem yang saya buat dan jika user tidak menggunakan lima browser di atas maka saya akan meminta mereka untuk menginstall salah satu dari lima browser tersebut.




![image](/posts/2019-03-06_cara-mengecek-dan-mengatur-versi-browser-untuk-pengguna/images/1.jpeg)

Menentukan versi standar setiap browser.



Mengapa cuma lima? Karena menurut pengamatan saya pribadi rata-rata user browsing menggunakan browser berdasarkan sistem operasi yang mereka pakai:

*   Windows: Chrome, Firefox, Opera, Edge
*   MacOS: Chrome, Firefox, Opera, Safari
*   Linux: Chrome, Firefox, Opera
*   Android: Chrome
*   iOS: Safari

Terima kasih telah membaca tulisan ini dan semoga bermanfaat.

#### Referensi

*   [UA Parser JS](https://github.com/faisalman/ua-parser-js)
*   [You Might Don’t Need JQuery](https://github.com/nefe/You-Dont-Need-jQuery)
*   [Can I Use ES6?](https://caniuse.com/#search=es6)
*   [TC39](https://github.com/tc39)_Originally published at_ [_www.satyakresna.io_](https://www.satyakresna.io/posts/cara-mengecek-dan-mengatur-versi-browser-untuk-pengguna/) _on March 6, 2019._
