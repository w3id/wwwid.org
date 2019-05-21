---
title: "Progressive Web-Application di AWS"
author: "Pradita Utama"
date: 2018-10-19T10:10:54.297Z
lastmod: 2019-05-20T16:27:41+07:00

description: ""

subtitle: "PWA+S3+Cloudfront = ❤️"
tags:
 - React 
 - S3 
 - Cloudfront 
 - Pwa 
 - Deployment 

image: "/posts/2018-10-19_progressive-webapplication-di-aws/images/1.jpeg" 
images:
 - "/posts/2018-10-19_progressive-webapplication-di-aws/images/1.jpeg" 
 - "/posts/2018-10-19_progressive-webapplication-di-aws/images/2.png" 
 - "/posts/2018-10-19_progressive-webapplication-di-aws/images/3.png" 
 - "/posts/2018-10-19_progressive-webapplication-di-aws/images/4.png" 
 - "/posts/2018-10-19_progressive-webapplication-di-aws/images/5.png" 
 - "/posts/2018-10-19_progressive-webapplication-di-aws/images/6.png" 
 - "/posts/2018-10-19_progressive-webapplication-di-aws/images/7.png" 
 - "/posts/2018-10-19_progressive-webapplication-di-aws/images/8.png" 
 - "/posts/2018-10-19_progressive-webapplication-di-aws/images/9.png" 
 - "/posts/2018-10-19_progressive-webapplication-di-aws/images/10.png" 
 - "/posts/2018-10-19_progressive-webapplication-di-aws/images/11.png" 
 - "/posts/2018-10-19_progressive-webapplication-di-aws/images/12.png" 
 - "/posts/2018-10-19_progressive-webapplication-di-aws/images/13.png" 
 - "/posts/2018-10-19_progressive-webapplication-di-aws/images/14.png" 
 - "/posts/2018-10-19_progressive-webapplication-di-aws/images/15.png" 


aliases:
    - "/progressive-web-application-di-aws-2c622b8ff434"
---

PWA+S3+Cloudfront = ❤️




![image](/posts/2018-10-19_progressive-webapplication-di-aws/images/1.jpeg)

Sumber: Pexels



Membangun PWA sepertinya sedang tren. Kita tidak akan membahas tips membangun PWA, jika ingin update tulisan yang berkaitan dengan pengembangan website di Indonesia bisa ikuti tautan ini [https://medium.com/wwwid](https://medium.com/wwwid)

### Create React App

Saya akan mencontohkan menggunakan React tapi sebenarnya seluruh website statis bisa juga (VueJS, Angular, Vanilla, dsb). Statis disini maksudnya adalah hanya HTML, JavaScript, dan CSS. Bukan server-side rendering.

CRA ini sudah PWA-enabled, jadi bisa kita jadikan contoh.

Supaya lebih cepat, saya menggunakan Create React App (CRA), ini semacam boilerplate tanpa harus coding dari awal.

[facebook/create-react-app](https://github.com/facebook/create-react-app)


Kita hanya tinggal lakukan perintah ini saja
`npm install -g create-react-app  
create-react-app my-app  
cd my-app  
npm run build`

Hasil build file statis akan ada di direktori `build`

### Amazon S3

Buat akun AWS jika belum punya, biasanya AWS ada limited trial selama 12 bulan untuk akun baru. Jika sudah ada, login dan masuk ke console Amazon S3




![image](/posts/2018-10-19_progressive-webapplication-di-aws/images/2.png)



#### Buat Bucket

Klik tombol `Create Bucket` dan isi sesuai yang kamu inginkan. Tips: gunakan nama yang mudah dibaca, misal diisi dengan nama website kamu, misal : **jsisforthe-you-name-it.com**




![image](/posts/2018-10-19_progressive-webapplication-di-aws/images/3.png)



#### Next… Next… dan Set Permissions

Karena S3 ini nantinya akan dipakai sebagai host website kamu, pilih _Grant public read access to this bucket_

dan lanjutkan pilih Next dan Create Bucket.




![image](/posts/2018-10-19_progressive-webapplication-di-aws/images/4.png)



#### Jadikan S3 Bucket Menjadi Web Hosting

Masuk ke bucket kamu buat tadi, pilih Properties dan klik Static website hosting. Isi sesuai gambar dibawah dan klik save.




![image](/posts/2018-10-19_progressive-webapplication-di-aws/images/5.png)





![image](/posts/2018-10-19_progressive-webapplication-di-aws/images/6.png)



Perhatikan teks Endpoint [http://test-langsung-hapus.s3-website-ap-southeast-1.amazonaws.com](http://test-langsung-hapus.s3-website-ap-southeast-1.amazonaws.com)

Itu adalah alamat website statis kamu, selanjutnya kamu tinggal upload ke bucket tadi dan kunjungi URL Endpoint di atas. Selamat! sampai sini kamu sudah punya website statis di S3.

Tapi, URL yang kamu dapatkan panjang sekali dan susah diingat. Termasuk bagaimana jika kamu ingin menggunakan HTTPS? atau bahkan domain sendiri? atau kamu ingin memanfaatkan CDN AWS supaya cepat?

Kita lanjutkan di bagian bawah.

### Amazon Cloudfront

Apa itu Cloudfront? Silakan klik tautan berikut.

[What Is Amazon CloudFront? - Amazon CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html)


Masuk ke console Cloudfront dan buat distribusi baru dengan delivery method adalah web dan isi bagian Origin Domain Name dengan nama Bucket S3 di atas dan Viewer Protocol Policy pilih Redirect HTTP to HTTPS




![image](/posts/2018-10-19_progressive-webapplication-di-aws/images/7.png)



Selanjutnya klik Create Distribution dan tunggu hingga selesai.

Kamu akan mendapatkan URL Cloudfront kamu dengan format **adfadf123adf.cloudfront.net**




![image](/posts/2018-10-19_progressive-webapplication-di-aws/images/8.png)



Sampai disini, website kamu sudah siap diakses menggunakan URL **https://adfadf123adf.cloudfront.net**

#### Optional: Menggunakan Domain Sendiri

Jika kamu menggunakan domain sendiri atau subdomain sendiri, masukkan domain atau subdomain kamu di bagian Alternate Domain Names.

Setelah itu kamu harus membuat CNAME dari Domain Control Panel kamu sendiri (tempat dimana kamu beli domain). Buat CNAME yang mengarah ke alamat distribusi Cloudfront yang nanti kamu dapatkan setelah kamu Click Distribution. Contoh di atas adalah **adfadf123adf.cloudfront.net**

Termasuk jika ingin menggunakan HTTPS, kamu harus memasukkan SSL certificate di ACM. Klik **_Request or Import a Certificate with ACM_** jika ingin memasukkan SSL certificate.




![image](/posts/2018-10-19_progressive-webapplication-di-aws/images/9.png)



### Cache Control?

Menurut Google, file `service-worker.js` jangan diberikan cache. Gunakan `Cache-Control: max-age=0`

[Fresher service workers, by default | Web | Google Developers](https://developers.google.com/web/updates/2018/06/fresher-sw)


Kembali ke Bucket S3 kamu, klik kanan di file `service-worker.js` dan pilih Change Metadata dan masukkan `Cache-Control: max-age=0`




![image](/posts/2018-10-19_progressive-webapplication-di-aws/images/10.png)





![image](/posts/2018-10-19_progressive-webapplication-di-aws/images/11.png)



PWA kamu sudah siap di [**https://adfadf123adf.cloudfront.net**](https://adfadf123adf.cloudfront.net)**!**

### Bonus: Deployment Pakai AWS CLI

Harus manual melakukan upload setiap selesai coding? gunakan AWS CLI, cara install bisa dibaca di link ini

[Installing the AWS Command Line Interface - AWS Command Line Interface](https://docs.aws.amazon.com/cli/latest/userguide/installing.html)


Sebelum menggunakan AWS CLI kamu harus punya `AWS_ACCESS_KEY` dan `AWS_SECRET_KEY` yang bisa kamu dapatkan di bagian IAM.




![image](/posts/2018-10-19_progressive-webapplication-di-aws/images/12.png)



Tulisan ini tidak membahas cara mendapatkan KEY tersebut, tapi saya menemukan artikel yang membahas ini

[Where&#39;s My Secret Access Key? | Amazon Web Services](https://aws.amazon.com/blogs/security/wheres-my-secret-access-key/)


Jika sudah mendapat KEYs dan install AWS CLI, lakukan perintah di bawah dan masukkan KEY yang kamu dapatkan.
`aws configure`

Sudah semua? mari kita lakukan upload menggunakan AWS CLI. Masuk ke dalam root project website kamu dan lakukan perintah berikut.
`aws s3 sync build/ s3://NAMA_BUCKET --delete --cache-control max-age=604800,public``aws s3 cp s3://NAMA_BUCKET/service-worker.js s3://NAMA_BUCKET/service-worker.js --metadata-directive REPLACE --cache-control max-age=0,no-cache,no-store,must-revalidate --content-type application/javascript --acl public-read``aws s3 cp s3://NAMA_BUCKET/index.html s3://NAMA_BUCKET/index.html --metadata-directive REPLACE --cache-control max-age=0,no-cache,no-store,must-revalidate --content-type text/html --acl public-read`

Kenapa harus 3 perintah? perintah yang pertama melakukan upload ke Bucket S3 kamu dari folder `build` dan membuat metadata `Cache-Control: max-age:604800` untuk semua file yang diupload. Oh iya, 604800 ini adalah dalam detik, yang sama dengan 7 hari. Jadi file yang diupload akan punya header yang memerintahkan browser untuk cache filenya selama 7 hari.

Tapi tadi katanya Google `service-worker.js` tidak boleh cache? itulah gunanya perintah ke-dua. Mirip dengan perintah pertama tapi ini hanya menyalin dari Bucket yang sama tapi membuat metadata`Cache-Control: max-age:0` dan beberapa metadata lainnya yang berguna untuk browser

Perintah ke-tiga sama dengan perintah ke-dua, tapi untuk file `index.html`

Secara general akan seperti ini:

*   index.html → tidak akan di-cache (karena setiap build bisa saja berubah)
*   service-worker.js → tidak akan di-cache
*   lainnya → cache

Selesai!

### Bonus: Gitlab CI Configuration

Jika kamu menggunakan Gitlab runner, kamu bisa menambahkan file `gitlab-ci.yml` agar semua proses deployment kamu dilakukan otomatis. Tapi sebelumnya kamu harus sudah setup runner yang akan kamu pakai dan tambahkan AWS KEYS sebagai VARIABLES di repository kamu. Masuk ke Repository → Settings → CI/CD dan bagian variables




![image](/posts/2018-10-19_progressive-webapplication-di-aws/images/13.png)



Tambahkan file `gitlab-ci.yml` seperti ini




Setiap kamu push ke Gitlab, maka hasil perubahan code kamu akan otomatis terdeploy di [**https://adfadf123adf.cloudfront.net**](https://adfadf123adf.cloudfront.net)

Happy coding!### **Troubleshoot #1: 403 (Forbidden) Ketika akses asset (CSS, JS) padahal sudah set public di S3**

Ini biasanya terjadi bila menggunakan routing di web SPA kamu, karena jika user masuk ke url [https://domain/product/123](https://domain/product/123) itu sebenarnya semua route dilempar ke /index.html.

Masuk ke CloudFront, edit Distribution kamu dan pilih Error Pages. Create Custom Responses dan masukkan seperti gambar di bawah ini.




![image](/posts/2018-10-19_progressive-webapplication-di-aws/images/14.png)



### Troubleshoot #2: 404 (Not Found) Ketika akses route / URL secara langsung tanpa lewat halaman depan

Ini biasanya terjadi bila menggunakan routing di web SPA kamu, karena jika user masuk ke url [https://domain/product/123](https://domain/product/123) itu sebenarnya semua route dilempar ke /index.html.

Masuk ke CloudFront, edit Distribution kamu dan pilih Error Pages. Create Custom Responses dan masukkan seperti gambar di bawah ini.




![image](/posts/2018-10-19_progressive-webapplication-di-aws/images/15.png)
