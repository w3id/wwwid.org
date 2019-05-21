---
title: "Studi Kasus Accessibility — Web Form"
author: "Satya Kresna Adi Pratama"
date: 2018-01-24T14:57:26.204Z
lastmod: 2019-05-20T16:26:55+07:00

description: ""

subtitle: "Di artikel sebelumnya, kita telah belajar bahwa Accessibility adalah sebuah hal yang wajib ada dan memudahkan para pengguna disabilitas…"
tags:
 - Accessibility 
 - A11y 
 - Forms 
 - Web Development 
 - Web 

image: "/posts/2018-01-24_studi-kasus-accessibility-web-form/images/5.png" 
images:
 - "/posts/2018-01-24_studi-kasus-accessibility-web-form/images/1.png" 
 - "/posts/2018-01-24_studi-kasus-accessibility-web-form/images/2.png" 
 - "/posts/2018-01-24_studi-kasus-accessibility-web-form/images/3.png" 
 - "/posts/2018-01-24_studi-kasus-accessibility-web-form/images/4.png" 
 - "/posts/2018-01-24_studi-kasus-accessibility-web-form/images/5.png" 
 - "/posts/2018-01-24_studi-kasus-accessibility-web-form/images/6.png" 


aliases:
    - "/studi-kasus-accessibility-web-form-cd20369c475b"
---

![image](/posts/2018-01-24_studi-kasus-accessibility-web-form/images/1.png)



[Di artikel sebelumnya](https://medium.com/wwwid/perkenalan-accessibility-c9d893318567), kita telah belajar bahwa Accessibility adalah sebuah hal yang wajib ada dan memudahkan para pengguna disabilitas untuk mengakses produk kita seperti website layaknya orang normal. Pada bagian ini, saya akan menjelaskan studi kasus Accesibility pada sebuah form website dan menggunakan Lighthouse pada browser Chrome versi 63.0.3239.132 sebagai audit.

Form web yang kita rancang sebagai berikut:

1.  **Nama dan username** menggunakan `&lt;input type=&#34;text&#34;&gt;`
2.  **Alamat** menggunakan `&lt;textarea&gt;`
3.  **Email** menggunakan `&lt;input type=&#34;email&#34;&gt;`
4.  **Password** menggunakan `&lt;input type=&#34;password&#34;&gt;` dan menambahkan atribut `**required**`
5.  **Jenis kelamin** menggunakan `&lt;input type=&#34;radio&#34;&gt;`
6.  **Hobi** menggunakan `&lt;input type=&#34;checkbox&#34;&gt;`
7.  **Asal kota** menggunakan `&lt;select&gt;`

Saya telah membuatkan file **no-a11y-form.html** dan sebagai developer yang baik cukup copy paste source code di bawah.




Selanjutnya, bukalah **no-a11y-form.html** di browser Chrome dan gunakan kursor anda untuk melakukan percobaan dengan meng-klik setiap label di form tersebut. Apakah kursor keyboard langsung mengarah pada setiap field? Jika tidak, maka hal ini perlu kita perbaiki bersama. Mengapa? **_Dalam dunia Accessibility, pengguna disabilitas sangat bergantung dengan interaksi keyboard, mouse dan screen reader._**

Kita akan gunakan salah satu screen reader bernama Voice Over yang tertanam dalam Mac OS untuk menguji **no-a11y-form.html**. Umumnya, ketika ingin berpindah dari satu tempat ke tempat lain dalam satu halaman, pengguna disabilitas menggunakan tombol **TAB** keyboard. Hasil pengujiannya seperti video di bawah ini.






Kita bisa lihat bahwa label **nama, email, username**, dsb tidak terbaca oleh screen reader dan hal tersebut akan membuat pengguna disabilitas bingung serta kemungkinan paling buruk adalah meninggalkan halaman web. Tentu hal tersebut tidak kita inginkan!

Sebelum kita mulai memperbaiki, kita lakukan audit Lighthouse pada browser Chrome. Lighthouse telah tertanam secara default di versi Chrome 60 ke atas dan jika browser anda berada di bawah versi tersebut, silahkan menggunakan extension Lighthouse yang disediakan oleh Chrome. Klik kanan pada halaman no-a11y-form.html =&gt; pilih inspect atau inspect element =&gt; pilih tab Audits =&gt; pilih perform an audit =&gt; centang Accessibility. Biarkan Lighthouse melakukan inspeksi dan hasilnya seperti di bawah.




![image](/posts/2018-01-24_studi-kasus-accessibility-web-form/images/2.png)





![image](/posts/2018-01-24_studi-kasus-accessibility-web-form/images/3.png)

Audit no-a11y form tanggal 24 Januari 2018



Dari hasil audit Accessibility pada form no-a11y sebesar 97/100. Dan jika anda perhatikan, ada satu isu yang perlu diperhatikan yakni **Form elements do not have associated labels.** Maksudnya adalah setiap elemen form yang kita buat harus berasosiasi atau terhubung dengan label yang kita buat agar dijabarkan dengan benar oleh teknologi pembantu seperti screen reader.

Terdapat dua cara untuk memperbaikinya. Cara pertama saya berikan nama **form-a11y-alternative-1.html**




Jika anda perhatikan source code di atas dengan seksama maka `**&lt;label&gt;**` telah berasosiasi dengan elemen form yang kita buat. Hal ini bisa ditunjukkan pada sintaks di bawah.




Kita hanya perlu menyisipkan atribut `**for**` pada label dan atribut `**id**` pada elemen form yang kita asosiasikan serta **value dari kedua atribut harus sama**.

Kita akan lakukan lagi pengujian menggunakan Voice Over dan hasilnya seperti video di bawah ini.






Kita bisa lihat bahwa label **nama, email, username**, dsb sudah terbaca oleh screen reader. Berikutnya kita audit **form-a11y-alternative-1.html** dengan Lighthouse.




![image](/posts/2018-01-24_studi-kasus-accessibility-web-form/images/4.png)





![image](/posts/2018-01-24_studi-kasus-accessibility-web-form/images/5.png)

Audit form-a11y-alternative-1.html tanggal 24 Januari 2018



Cara kedua saya berikan nama **form-a11y-alternative-2.html**




Jika anda perhatikan source code di atas dengan seksama pada field email, `**&lt;label&gt;**` membungkus elemen form email yang kita buat seperti sintaks di bawah.




Kita lakukan pengujian dengan Voice Over seperti video di bawah ini.






Jika anda menggunakan screen reader seperti [Voice Over](https://www.apple.com/voiceover/info/guide/_1121.html) (Mac) atau [NVDA](https://www.nvaccess.org/) (Windows) dan menggunakan tombol **TAB** di keyboard akan berbunyi “Hobi Ngoding”, “Hobi Tidur”, “Hobi Makan”, “Jenis kelamin Perempuan”, “Jenis kelamin laki-laki”. Berikutnya kita lakukan audit pada **form-a11y-alternative-2.html** menggunakan Lighthouse, hasilnya seperti sama seperti **form-a11y-alternative-1.html**.




![image](/posts/2018-01-24_studi-kasus-accessibility-web-form/images/6.png)

Audit form-a11y-alternative-2.html tanggal 24 Januari 2018



**Bonus**

Jika anda memperhatikan source code pada **form-a11y-alternative2.html** maka terdapat sebuah atribut bernama **aria-labelledby** pada field **Hobi dan Jenis kelamin**. **** Hal ini akan dibahas pada artikel selanjutnya.

**Kesimpulan**

1.  Setiap form elemen harus berasosiasi dengan label.
2.  Terdapat dua cara untuk melakukan hal tersebut. Pertama menambahkan atribut `**&lt;for&gt;**` pada label dan atribut `**&lt;id&gt;**` pada elemen form. Kedua, menambahkan membungkus form elemen dengan **** `**&lt;label&gt;**`. Kedua cara tersebut dapat digunakan sesuai dengan kenyamanan anda dalam menciptakan Accessibility yang baik bagi pengguna disabilitas.

Terima kasih telah membaca artikel ini, semoga bermanfaat, sebarkan dan jangan ragu bila ingin bertanya atau menyampaikan kritik dan saran di kolom komentar. 😉
