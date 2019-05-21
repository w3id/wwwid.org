---
title: "Web Payment Request API dan Kemungkinan Adopsinya di Indonesia"
author: "Yohan Totting"
date: 2017-10-09T06:42:43.578Z
lastmod: 2019-05-20T16:26:17+07:00

description: "Apa itu Web Payment Request API, kenapa perlu adanya API khusus untuk pembayaran online dan bagaimana adopsinya di Indonesia? Bagaimana cara menggunakan Payment Request API."

subtitle: "Apa itu Web Payment Request API, kenapa perlu adanya API khusus untuk pembayaran online dan bagaimana adopsinya di Indonesia?"
tags:
 - E-commerce 
 - Progressive Web App 
 - Fintech 
 - Payment Request Api 

image: "/posts/2017-10-09_web-payment-request-api-dan-kemungkinan-adopsinya-di-indonesia/images/1.png" 
images:
 - "/posts/2017-10-09_web-payment-request-api-dan-kemungkinan-adopsinya-di-indonesia/images/1.png" 
 - "/posts/2017-10-09_web-payment-request-api-dan-kemungkinan-adopsinya-di-indonesia/images/2.png" 
 - "/posts/2017-10-09_web-payment-request-api-dan-kemungkinan-adopsinya-di-indonesia/images/3.gif" 


aliases:
    - "/web-payment-request-api-dan-kemungkinan-adopsinya-di-indonesia-7cda8aee7a57"
---

Lanjutan dari tulisan sebelumnya terkait topik yang dibahas di _Progressive Web App Roadshow_ Indonesia tentang _service workers_, kali ini saya ingin menulis salah satu topik yang dipresentasikan di sesi _integration_, yaitu _Payment Request API_.

### Kenapa perlu adanya Payment Request API?

Seperti yang kalian tahu kalau melihat ekosistem startup Indonesia, _e-commerce_ merupakan salah satu area yang mendominasi. Dan di e-commerce, pembayaran adalah metrics yang paling penting. _Sales conversion_ menjadi goal utama dari startup _e-commerce_. Dan Indonesia adalah _mobile first country_ di mana penggunaan mobile mendominasi dalam hal mengakses internet.




![image](/posts/2017-10-09_web-payment-request-api-dan-kemungkinan-adopsinya-di-indonesia/images/1.png)

Persentase pembelian di mobile 66% terjadi di web.



Menurut data global 66% transaksi _e-commerce_ di _mobile_ itu terjadi di web. Tapi sayangnya walaupun angka tersebut cukup besar, tapi kegagalan pembayaran cukup besar terjadi di mobile kalau dibandingkan dengan desktop. Angkanya cukup besar, hingga 66% lebih kecil dibandingkan di desktop.




![image](/posts/2017-10-09_web-payment-request-api-dan-kemungkinan-adopsinya-di-indonesia/images/2.png)

Transaksi pembayaran di mobile 66% lebih sedikit dibandingkan di desktop



Belajar dari angka di atas, maka tantangan buat para pelaku _e-commerce_ adalah bagaimana untuk memperbaiki pengalaman dalam transaksi _e-commerce_.

Salah satu alasan akan konversi dari pengunjung menjadi pembeli adalah setiap langkah yang harus dilakukan tersebut berpotensi membuat pengunjung tidak melanjutkan. Bahkan data riset yang ada menunjukkan bahwa [**setiap langkah yang harus dilakukan pengunjung berpotensi menghilangkan 20% dari pengunjung tersebut**.] (http://blog.gaborcselle.com/2012/10/every-step-costs-you-20-of-users.html)Dan alasan inilah kenapa kita membutuhkan cara pembayaran yang lebih mudah di web untuk mengurangi jumlah kehilangan user yang berlanjut ke penyelesaian transaksi.




![image](/posts/2017-10-09_web-payment-request-api-dan-kemungkinan-adopsinya-di-indonesia/images/3.gif)

Payment Request API



Kalau ingin mendeskripsikan apa fungsi dari _Payment Request API_ ini, maka **_Payment Request API_ ini adalah cara _browsers_ untuk bisa mengumpulkan data pembayaran seperti data pembeli, alamat pengiriman, dan data pembayaran di mana semua input data ini bisa dibilang membutuhkan 3 langkah.** Sehingga data tersebut bisa diproses lebih lanjut di _payment gateway_.

Bayangkan bila semua data transaksi sudah terekam di _browsers_, maka pengguna tidak perlu lagi memasukkan semua data tersebut. Dengan demikian 3 langkah bisa dikurangi, dan pembeli bisa membayar hanya dengan mengkonfirmasi data saja.

Setelah mencoba bereksperimen dengan _Payment Request API_ ini, saya berkesimpulan bahwa API ini memang bisa mengurangi hambatan _user experiences(UX)_ yang buruk dalam proses transaksi pembayaran. UX yang buruk tentu berpotensi membuat calon pembeli tidak melanjutkan pembayaran karena bingung, kesulitan, atau tidak punya waktu.

Bahkan salah satu _e-commerce startup_ yang sempat saya bimbing di [Google Launchpad Accelerator](https://developers.google.com/startups/accelerator/) memiliki tantangan bagaimana mengurangi tingginya angka pengguna yang memasukkan barang ke keranjang belanja tapi tidak terkonversi menjadi pembeli. Dan sebagian pengguna yang tidak terkonversi itu ternyata bila di-_followup_ kembali, sekitar 50% akan melanjutkan pembayaran. Maka kesimpulannya setelah ditanya, sebagian besar mereka tidak berlanjut ke pembayaran karena terdistraksi. Distraksi yang mungkin bisa dihindari bila pembayaran bisa diselesaikan dalam waktu singkat.

### Kemungkinan adopsi Payment API Request di Indonesia

Namun salah satu yang menjadi kendala implementasi _Payment Request API_ ini di Indonesia dan sebagian besar _emerging market countries_ tentu adalah cara pembayaran. _Payment Request API_ hingga tulisan ini dibuat cuma mendukung 2 cara pembayaran, yaitu dengan kartu kredit/debit, dan aplikasi pembayaran seperti Paypal, Stripe, Android Pay, atau Apple Pay. Sedangkan negara-negara seperti Indonesia belum banyak menggunakan 2 media pembayaran tersebut. Sebenarnya saat ini sudah ada [r](http://w3c.github.io/webpayments-methods-credit-transfer-direct-debit/)ancangan spesifikasi untuk pembayaran transfer antar bank, namun hingga saat ini belum ada wacana untuk implementasinya di browser.

Namun seperti kita ketahui bahwa Indonesia sedang dalam masa transisi media pembayaran. Di mana pemerintah dan masyarakat mulai mengadopsi cashless society. Beberapa contohnya adalah maraknya transportasi _online_, pembayaran transport seperti Transjakarta, kereta api, dan tol dengan kartu e-money. Bahkannya maraknya _startups fintech_ yang bermunculan dalam setahun belakangan. Ini membuka peluang untuk integrasi aplikasi pembayaran online dengan _Payment Request API_.

### Integrasi _Payment Request API_ dengan aplikasi pembayaran online/perbankan

Intergrasi _Payment Request API_ dengan aplikasi pembayaran sendiri memang sudah tersedia. Untuk implementasi yang banyak saya lihat dari contoh-contoh yang ada sebagian besar adalah integrasi dengan Android Pay atau Apple Pay. Di Indonesia sendiri beberapa peluang yang memungkinkan untuk integrasi ini adalah integrasi dengan [Go-Pay](https://www.go-jek.com/go-pay/), [Kudo](https://kudo.co.id/), [Jenius](https://www.jenius.com/), [Digibank](https://www.dbs.com/digibank/id/id/index.html), [Mandiri Online](https://ibank.bankmandiri.co.id/retail3/), atau aplikasi online pembayaran atau perbankan lainnya.

Integrasi ini tidaklah instant, karena diperlukan implementasi di sisi aplikasi dan juga di merchant atau web si penjual. Di sisi aplikasi diperlukan intent untuk menerima request pembayaran dari aplikasi lain, dalam hal ini yaitu dari browsers. Lalu dari sisi web penjual atau merchant memerlukan implementasi _Payment Request API_ dan mendaftarkan aplikasi pembayaran yang ingin didukung di web tersebut.

Spesifikasi dukungan _Payment Request API_ dengan aplikasi pembayaran ini bisa dilihat [di halaman ini.](https://w3c.github.io/payment-method-manifest/) Dan bisa dilihat juga contoh implementasi menggunakan [Android Pay] (https://developers.google.com/web/fundamentals/payments/android-pay)dan [Apple Pay](https://github.com/GoogleChrome/appr-wrapper) sebagai referensi kalau kalian ingin melihat bagaimana untuk menintegrasikan dengan aplikasi pembayaran yang kalian punya.

Saat tulisan ini dibuat saya belum selesai dalam bereksperimen dengan _Payment Request API_. Dan ingin mencoba apakah mungkin kita mengintegrasikan _Payment Request API_ dengan aplikasi pembayaran seperti [Go-Pay](https://www.go-jek.com/go-pay/), [Kudo](https://kudo.co.id/), atau lainnya? Akan saya _update_ di tulisan berikutnya bagaimana hasil dari eksperimen integrasi _Payment Request API_ ini dengan aplikasi pembayaran online.
