---
title: "5 kelemahan web apps yang sering hacker abuse"
author: "Yahya Fadhlulloh Al-Fatih"
date: 2018-09-23T16:03:34.917Z
lastmod: 2019-05-20T16:27:40+07:00

description: ""

subtitle: "Sering kali web developer baru menyadari betapa pentingnya keamanan setelah web atau aplikasinya sudah diretas atau mendapat ancaman dari…"

image: "/posts/2018-09-23_5-kelemahan-web-apps-yang-sering-hacker-abuse/images/1.jpg" 
images:
 - "/posts/2018-09-23_5-kelemahan-web-apps-yang-sering-hacker-abuse/images/1.jpg" 
 - "/posts/2018-09-23_5-kelemahan-web-apps-yang-sering-hacker-abuse/images/2.png" 
 - "/posts/2018-09-23_5-kelemahan-web-apps-yang-sering-hacker-abuse/images/3.png" 
 - "/posts/2018-09-23_5-kelemahan-web-apps-yang-sering-hacker-abuse/images/4.png" 
 - "/posts/2018-09-23_5-kelemahan-web-apps-yang-sering-hacker-abuse/images/5.png" 
 - "/posts/2018-09-23_5-kelemahan-web-apps-yang-sering-hacker-abuse/images/6.png" 
 - "/posts/2018-09-23_5-kelemahan-web-apps-yang-sering-hacker-abuse/images/7.png" 
 - "/posts/2018-09-23_5-kelemahan-web-apps-yang-sering-hacker-abuse/images/8.png" 
 - "/posts/2018-09-23_5-kelemahan-web-apps-yang-sering-hacker-abuse/images/9.png" 
 - "/posts/2018-09-23_5-kelemahan-web-apps-yang-sering-hacker-abuse/images/10.png" 
 - "/posts/2018-09-23_5-kelemahan-web-apps-yang-sering-hacker-abuse/images/11.png" 
 - "/posts/2018-09-23_5-kelemahan-web-apps-yang-sering-hacker-abuse/images/12.png" 
 - "/posts/2018-09-23_5-kelemahan-web-apps-yang-sering-hacker-abuse/images/13.png" 
 - "/posts/2018-09-23_5-kelemahan-web-apps-yang-sering-hacker-abuse/images/14.png" 
 - "/posts/2018-09-23_5-kelemahan-web-apps-yang-sering-hacker-abuse/images/15.png" 
 - "/posts/2018-09-23_5-kelemahan-web-apps-yang-sering-hacker-abuse/images/16.png" 
 - "/posts/2018-09-23_5-kelemahan-web-apps-yang-sering-hacker-abuse/images/17.png" 
 - "/posts/2018-09-23_5-kelemahan-web-apps-yang-sering-hacker-abuse/images/18.png" 
 - "/posts/2018-09-23_5-kelemahan-web-apps-yang-sering-hacker-abuse/images/19.png" 


aliases:
    - "/5-kelemahan-web-apps-yang-sering-hacker-abuse-34dd9e66546d"
---

S
ering kali web developer baru menyadari betapa pentingnya keamanan setelah web atau aplikasinya sudah diretas atau mendapat ancaman dari hacker berupa email. Kesulitan dari pengembangan pun mulai meningkat karena yang harus di tangkis adalah lubang keamanan, dua hal yang berbeda antara **lubang** yang biasa disebut bug **** dimana sebuah kesalahan teknikal ataupun bisnis yang menyebabkan munculnya error pada aplikasi yang biasanya muncul dengan ukuran seperti High, Medium, Low dan **keamanan** yang diukur dari tingkat resiko yang muncul dibagi seperti Confidential (kerahasiaan), Integrity(keutuhan) dan Availability (ketersediaan).




![image](/posts/2018-09-23_5-kelemahan-web-apps-yang-sering-hacker-abuse/images/1.jpg)

hacker sexually attracted to your vulnerable app



Penulis ingin membagikan beberapa pro tips untuk para web developer dalam mengamankan web aplikasi kalian supaya kelemahan kelemahan yang biasa hacker manfaatkan bisa terlebih dahulu ditemukan, dan di atasi lebih awal. Terdapat 5 kelemahan umum yang biasa hacker manfaatkan diantaranya :

### Vulnerable Packages
> npm packages over 375000, 70000 publisher, ~14% carry known vulnerabilities — snyk.io

Kelemahan paling umum yang biasa hacker manfaatkan, _outdated_, _unsupported, vulnerable_ libraries/packages/dependencies…..

Jangan pernah menganggap remeh vulnerable packages ini karena komunitas hacker sendiri mereka mereka pasti akan merilis jika menemukan kelemahan, dan akan di sebar lewat komunitas.




![image](/posts/2018-09-23_5-kelemahan-web-apps-yang-sering-hacker-abuse/images/2.png)



Bahkan terdapat komunitas hacker sendiri yang menjual exclusive bug seperti bug nya twitter, facebook maupun instagram.




![image](/posts/2018-09-23_5-kelemahan-web-apps-yang-sering-hacker-abuse/images/3.png)



yang harus dilakukan web developer untuk mencegah ini adalah :

Gunakan package scanner untuk mengetahui kelemahan dari package, banyak sekali pilihan untuk package scanner salah satunya :

#### [npm audit](https://docs.npmjs.com/getting-started/running-a-security-audit)

Tools ini sangat membantu developer untuk mengetahui lebih awal jika ada library yang vulnerable, cukup dengan perintah biasa **npm install** nanti muncul peringatan kalau library tersebut terdapat kelemahan dan menyarankan menjalankan **npm audit** (jangan lupa ini menggunakan npm latest bisa langsung update menggunakan **npm install npm@latest -g** )




![image](/posts/2018-09-23_5-kelemahan-web-apps-yang-sering-hacker-abuse/images/4.png)



setelah menjalankan npm install, pasti disaraankan untuk menjalankan npm audit, nanti hasilnya seperti berikut




![image](/posts/2018-09-23_5-kelemahan-web-apps-yang-sering-hacker-abuse/images/5.png)



untuk fixing bisa update aja versi library nya atau menggunakan perintah **npm audit fix** buat auto fixing yang vulnerable, mungkin ada beberapa library yang ga bisa di fixing biasnaya dikarenakan library nya sudah tidak di kembangkan lagi, atau harus update manual library nya.

#### [snyk.io](https://snyk.io/)

Ini bukan tools melainkan Website yang menyediakan jasa untuk melakukan scanning library, menggunakan website ini dia cukup general karena dia bisa scanning untuk multi language. Cukup dengan menambahkan project yang ada di berbagai repository (github, gitlab, dll) nanti dia bakal scanning library sekarang yang dipakai. Kelebihannya untuk menggunakan snyk.io ini kita bisa melakukan daily scanning, bisa liat detail permasalahan dan rekomendasinya terutama gratis, penulis sangat menyarankan menggunakan ini 👍




![image](/posts/2018-09-23_5-kelemahan-web-apps-yang-sering-hacker-abuse/images/6.png)



#### [github security alert](https://blog.github.com/2017-11-16-introducing-security-alerts-on-github/)

Buat developer github mungkin ini sudah tidak asing lagi, untuk enable fitur ini bisa cek pada tab Insight, lalu bagian menu dependency graph ada fitur untuk memulai cek dependencies security. Biasanya setiap minggu jika ditemukan vulnerability pada dependencies langsung di peringatkan lewat email.




![image](/posts/2018-09-23_5-kelemahan-web-apps-yang-sering-hacker-abuse/images/7.png)

Github memberikan peringatan tentang dependencies yang lema



Banyak sekali tools tools pendukung untuk cek dependencies dari lubang keamanan, contoh lainnya untuk composer libraries bisa di lakukan menggunakan tools [sensiolabs](https://security.sensiolabs.org/check) ([web] (https://security.sensiolabs.org/check)/ [github] (https://github.com/sensiolabs/security-checker)).

### Injeksi

OWASP Top 10 Vulnerability menyebutkan injeksi adalah serangan yang paling sering hacker manfaatkan, dalam arti lain serangan yang paling di favoritkan oleh hacker, disisi mudah di gunakan, tipe serangannya juga sangat banyak bahkan [varian] (https://www.netsparker.com/blog/web-security/sql-injection-cheat-sheet/)untuk setiap masing masing sql server (mysql, postgres, oracle). Penulis akan berbagi tips untuk handle jenis serangan Injection yang umum, salah satunya :

#### SQL Injection

Arti sederhananya adalah query dari data yang terstruktur dan dimanfaatkan hacker untuk mendapatkan informasi lebih, contohnya seperti pada query berikut
`select judul, highlight, deskripsi, tag from tbl_artikel where id = 1;`



![image](/posts/2018-09-23_5-kelemahan-web-apps-yang-sering-hacker-abuse/images/8.png)

hasilnya



sederhana ko, anggap saja 1 adalah variabel input, jadi kalau angka tersebut di ganti ganti artinya akan menampilkan data berita dengan spesifik id, simple kan. Nah jika “ 1 “ adalah inputan dari user, artinya user bisa menambahkan query kan, anggap lah jika user tersebut memasukkan query berikut setelah inputan.
`**union select 1,concat(table_name),3,4 from information_schema.tables where table_schema  
=&#34;CRACKING&#34;;**`

jika di gabungkan menjadi begini
`select   
 judul, highlight, deskripsi, tag   
from tbl_artikel   
where id = 1 **union select 1,concat(table_name),3,4 from information_schema.tables where table_schema  
=&#34;CRACKING&#34;;**`

maka hasilnya akan memberitahukan semua list tabel yang tersedia pada database “CRACKING” (contoh database yang dicoba)




![image](/posts/2018-09-23_5-kelemahan-web-apps-yang-sering-hacker-abuse/images/9.png)

hasilnya



artinya memungkinkan hacker melakukan ekstrak data lainnya pada query tersebut contoh lainnya pada query ini untuk menampilkan username dan password pada tabel
`select judul, highlight, deskripsi, tag from tbl_artikel where id = 1 union select 1,concat(username,0x3a,  
password),3,4 from tbl_user;`



![image](/posts/2018-09-23_5-kelemahan-web-apps-yang-sering-hacker-abuse/images/10.png)



Mungkin ribet ya, simple nya gini, kalo nyatanya bisa seperti ini.




![image](/posts/2018-09-23_5-kelemahan-web-apps-yang-sering-hacker-abuse/images/11.png)



Serangan SQL Injection ini paling umum, paling banyak varian nya, paling random banget muncul nya, bahkan banyak tools tools hacking yang sesimple masukkan URL dan langsung ekstrak database salah satunya Havij (one click hack, paling sering dipake noob hacker buat merasa lebih powerfull), BFSQL, paling the best itu [SQLMap](http://sqlmap.org/). Buat kawan kawan yang penasaran dan pengen coba sendiri, saya saranin menggunakan SQLMap

#_Attention disini penulis share tentang SQLMap khusus untuk testing aplikasi kalian sendiri buat kepentingan keamanan, kalo yang lain tanggung jawab masing masing_

#### Test kelemahan aplikasi menggunakan SQL Map

Bahan :

&gt; python 2.6.x atau 2.7.x

&gt; install library python [requests](http://docs.python-requests.org/en/master/)

&gt; clone dari project [https://github.com/sqlmapproject/sqlmap](https://github.com/sqlmapproject/sqlmap)

Kalau udah siap semua coba jalankan perintah **python sqlmap.py**




![image](/posts/2018-09-23_5-kelemahan-web-apps-yang-sering-hacker-abuse/images/12.png)



lalu ada beberapa cara untuk mendefinisikan fungsi/ URL yang lemah :

1.  berupa inputan dari user
2.  untuk method GET jika menggunakan petik satu ( ‘ ) akan muncul error mysql seperti **localhost/?parent_id=91&amp;v=portal&amp;page=&amp;id=93&#39;`** artinya fungsi ini ada potensi lemah



![image](/posts/2018-09-23_5-kelemahan-web-apps-yang-sering-hacker-abuse/images/13.png)

contoh jika menggunakan petik satu



3. untuk method POST masukkan variabel yang tidak sesuai dengan tipe data contoh memasukkan huruf pada nomor telepon

4. Jika muncul Error SQL Syntax artinya fungsi/ URL ini berpotensi lemah, save URL nya.

Jika sudah mempunyai URL lemah tersebut, selanjutnya adalah memasukkan URL lemah tersebut ke sqlmap tanpa petik dengan perintah
`python sqlmap.py -u &#34;**localhost/?parent_id=91&amp;v=portal&amp;page=&amp;id=93&#34;**`

Selanjutnya tools ini akan melakukan pengecekan tipe DBMS dan melakukan serangan serangan dari semua jenis sql injection, SQLMap akan melakukan beberapa pertanyaan simple dan selanjutnya jika berhasil maka akan muncul seperti berikut




![image](/posts/2018-09-23_5-kelemahan-web-apps-yang-sering-hacker-abuse/images/14.png)

Hasil jika berhasil terdapat informasi “injectable”



Kotak merah artinya fungsi/ URL tersebut jelas jelas lemah, dan kotak hijau adalah query yang digunakan untuk menemukan kelemahan. Simple ko!! silahkan dicoba,

#### Pencegahan SQL Injection

Paling efektif di antara pencegahan SQL Injection adalah menggunakan **prepared statement** untuk di setiap query yang akan di execute, karena setiap prepared statement query tidak akan langsung di eksekusi oleh database server dipisah antara variabel yang di input dan query yang akan di eksekute, menggunakan prepared statement akan mengecilkan kemungkinan hacker melakukan serangan sql injection.
``$stmt = $dbConnection-&gt;prepare(&#39;SELECT * FROM employees WHERE name = ?&#39;);  
$stmt-&gt;bind_param(&#39;s&#39;, $name); // &#39;s&#39; specifies the variable type =&gt; &#39;string&#39;  

$stmt-&gt;execute();  

$result = $stmt-&gt;get_result();  
while ($row = $result-&gt;fetch_assoc()) {  
    // do something with $row  
}``

Untungnya banyak framework developement semacam laravel, express dan sebagainya yang sudah menangkal basic SQL Injection, tapi masih banyak cara untuk pencegahan sql injection, ini hanyalah salah satu dari pencegahan, karena serangan belum tentu itu itu saja.

### Tidak menggunakan HTTPS

Sudah menjadi hal umum update terbesar chrome di tahun ini adalah menandakan website yang [tidak menggunakan HTTPS akan di anggap tidak aman](https://www.theregister.co.uk/2018/07/03/google_chrome_http/), hal ini menjelaskan bahwa HTTP bukanlah protokol yang aman lagi untuk melakukan transport data karena dengan menggunakan http data yang dikirimkan dapat di ekstrak dan di manipulasi oleh orang lain dalam satu jaringan.




![image](/posts/2018-09-23_5-kelemahan-web-apps-yang-sering-hacker-abuse/images/15.png)

HTTP ibarat website telanjang, dalam satu jaringan masih bisa di ambil datanya



HTTPS menyediakan user melakukan transportasi data melewati jalur yang aman, secara teknikal data yang dikirimkan ke HTTPS akan di encrypt supaya data tidak bisa di baca secara mentah mentah. Biarpun HTTPS itu banyak yang mahal, jangan minder bahkan masih banyak website pemerintah yang tidak menggunakan HTTPS, wajar website pemerintah lebih sering dijadikan bahan eksperimen hacker. Tidak telat buat kalian web developer untuk segera pasang HTTPS karena sudah banyak HTTPS gratis seperti letsencrypt ataupun cloudflare.

### Password

Paling sering hacker memanfaatkan password umum untuk meretas akun orang lain, karena password adalah hal sederhana yang pada dasarnya manusia sulit untuk diingat,

Kadang juga web developer lupa dengan menyimpan password sensitif ke dalam aplikasi, yang seharusnya tidak boleh contoh seperti di github jika mencari commit dengan keyword “hapus password” akan muncul banyak commit berupa credential database ataupun server




![image](/posts/2018-09-23_5-kelemahan-web-apps-yang-sering-hacker-abuse/images/16.png)

silly commit

> Cara paling aman menyimpan secret key ke dalam aplikasi adalah dengan tidak menyimpan secret key ke dalam aplikasi

Sebenarnya mudah, cukup jangan menyimpan secret key ke dalam aplikasi, bisa dipisahkan menggunakan variable enviroment atau di encrypt supaya membuat bingung orang usil.

### File Upload

Serangan terakhir yang biasanya hacker paling cari kalau sudah menemukan akses dari aplikasinya adalah file upload supaya hacker bisa menanam backdoor dan akses aplikasi/ server secara mudah. Nah sebelumnya kita cari tau dulu cara hacker hack file upload ini

**Manipulasi File Signature File Type**

Sudah umum buat di bagian file upload untuk mengkhususkan file yang akan diupload secara spesifik, khusus dokumen (pdf, doc,dll), khusus gambar (png, jpeg, svg) biasanya hacker akan melakukan manipulasi tipe data juga pada bagian header atau [file format structure](https://en.wikipedia.org/wiki/JPEG_File_Interchange_Format) . Setiap file terdapat format yang dibaca secara binary dan file format ini

Contohnya salah satunya file JPG dia pada header biasanya terdapat header ÿØÿà..JFIF.. dengan alamat `FF D8 FF E0 00 10 4A 46 49 46 00 01`




![image](/posts/2018-09-23_5-kelemahan-web-apps-yang-sering-hacker-abuse/images/17.png)



Untuk png dengan binary `.PNG...` dengan alamat`89 50 4E 47 0D 1A 0A`seperti berikut




![image](/posts/2018-09-23_5-kelemahan-web-apps-yang-sering-hacker-abuse/images/18.png)



Dengan cukup menambahkan header ke file php tersebut hacker secara mudah memanipulasi dan file tersebut akan terdeteksi sebagai JPG/ PNG




![image](/posts/2018-09-23_5-kelemahan-web-apps-yang-sering-hacker-abuse/images/19.png)



Oke dalam kasus ini biasanya hacker menggunakan File upload jenis Whitelist, artinya biasanya developer PHP menggunakan fungsi `get_mime_type($filename)` dengan mime yang dibutuhkan `image/jpeg` dengan fungsi tersebut file yang di manipulasi akan tetap muncul `image/jpeg`

#### Manipulasi EXIF key

Pada file gambar terdapat EXIF ( Exchangeable Image File Format ) untuk mendefinisikan file format pada gambar biasanya berupa lokasi file diambil, resolusi file dan sebagainya. Pada PHP disaat upload file dan filenya dibaca akan dibaca pada bagian EXIF nya juga, dan ada cara hacker menyisipkan php execution pada EXIF nya seperti berikut
``exiftool -Comment=&#39;&lt;?php echo &#34;&lt;pre&gt;&#34;; system($_GET[&#39;cmd&#39;]); ?&gt;&#39; lo.jpg``

Dengan EXIF ini code php tersebut akan dieksekusi

**Solusi File Upload**

Semua tujuan dari file upload itu semua adalah shell execution atau dalam artian lain melakukan eksekusi perintah pada operating sistem tersebut, sebenernya sesederhana disable eksekusi shell pada PHP atau engine web lainnya pada php bisa menggunakan [https://www.cyberciti.biz/faq/linux-unix-apache-lighttpd-phpini-disable-functions/](https://www.cyberciti.biz/faq/linux-unix-apache-lighttpd-phpini-disable-functions/)> Saya merasa kurang dan masih kena hacking :(

Banyak alternatif nya di internet, kalo saran saya sendiri bisa menggunakan web security checklist untuk developer, bisa cek disini

[Web developer security checklist](https://medium.com/@yahya.kimochi/web-developer-security-checklist-920ac4421589)
### Referensi

[https://www.netsparker.com/blog/web-security/sql-injection-cheat-sheet/](https://www.netsparker.com/blog/web-security/sql-injection-cheat-sheet/)

[List of file signatures - Wikipedia](https://en.wikipedia.org/wiki/List_of_file_signatures)


[http://exif.regex.info/exif.cgi](http://exif.regex.info/exif.cgi)

[Why HTTPS Matters | Web Fundamentals | Google Developers](https://developers.google.com/web/fundamentals/security/encrypt-in-transit/why-https)
