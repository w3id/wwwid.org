---
title: "Visualisasi Arsitektur Aplikasi Dengan Madge"
author: "R AdySurya A"
date: 2019-02-01T01:58:04.580Z
lastmod: 2019-05-20T16:27:57+07:00

description: ""

subtitle: "Madge merupakan Applikasi pengembang yang menghasilkan Grafik Visual mengenai struktur sebuah applikasi, modul-modul yang digunakan…"
tags:
 - JavaScript 
 - Architecture 
 - Software Development 
 - Dependencies 
 - Tools 

image: "/posts/2019-02-01_visualisasi-arsitektur-aplikasi-dengan-madge/images/1.png" 
images:
 - "/posts/2019-02-01_visualisasi-arsitektur-aplikasi-dengan-madge/images/1.png" 
 - "/posts/2019-02-01_visualisasi-arsitektur-aplikasi-dengan-madge/images/2.png" 


aliases:
    - "/visualisasi-arsitektur-applikasi-dengan-madge-ea5da2f5b9ce"
---

Madge merupakan Aplikasi pengembang yang menghasilkan Grafik Visual mengenai struktur sebuah aplikasi, modul-modul yang digunakan (dependencies Modul), &amp; Lingkaran Dependensi atau “Keterkaitan” satu atau lebih penggunaan sebuah modul (Circular Dependency).

[Circular dependency - Wikipedia](https://en.wikipedia.org/wiki/Circular_dependency)


Sebelumnya, saya sedang mempelajari **Lighthouse**, tepatnya Arsitektur dari **Lighthouse** kemudian mendapatkan sebuah informasi menarik “yah , tentang Madge ini” dari **** [**tautan ini**](https://github.com/GoogleChrome/lighthouse/blob/master/docs/architecture.md).

[GoogleChrome/lighthouse](https://github.com/GoogleChrome/lighthouse/blob/master/docs/architecture.md)


Pada tautan tersebut saya menemukan gambar atau visual grafik dari arsitektur lighthouse.



![image](/posts/2019-02-01_visualisasi-arsitektur-aplikasi-dengan-madge/images/1.png)

Lighthouse Architecture: Read More -[https://github.com/GoogleChrome/lighthouse/blob/master/docs/architecture.md](https://github.com/GoogleChrome/lighthouse/blob/master/docs/architecture.md)

Kemudian, menemukan perintah (command) yang digunakan lighthouse untuk menghasilkan grafik visual diatas yakni
`$ madge lighthouse-core/index.js --image arch.png --layout dot --backgroundColor &#34;#fafafa&#34; --nodeColor &#34;#4d4afc&#34; --noDependencyColor &#34;#48ad00&#34;``# madge &lt;directory&gt;or&lt;file&gt; [options]`

*   **madge** : bin file dari madge jika sudah di install
*   **lighthouse-core/index.js** : file index.js dari lighthouse didalam folder lighthouse-core
*   **image** : opsi untuk nama file gambar “output” setelah madge dijalankan
*   **layout** : opsi untuk mengatur layout dari “output”
*   untuk opsi lainnya bisa dilihat [**disini.**](https://www.npmjs.com/package/madge)

setelah menjalankan perintah seperti gambar diatas, silahkan buka “directory” atau “folder” tepat dimana kamu menjalankan perintah tersebut.
> Catatan: Madge membutuhkan sebuah dependensi juga, yakni **graphvis (required)** dan menggunakan [**node-dependency-tree**](https://github.com/dependents/node-dependency-tree) **** (tak perlu install karena sudah jadi bagian utama dari madge)
[Graphviz - Graph Visualization Software](https://www.graphviz.org/)


Jadi, harus menginstall **graphvis** agar **madge** dapat berjalan.

contoh instalasi dan penggunaan:
`// Install graphvis using brew for mac user  
$ **brew install -v graphviz**``// Install graphvis using apt-port for ubuntu  
$ **sudo apt-get install graphviz**``// Install madge using yarn  
$ **yarn global add madge**``// goto project directory  
$ **cd your_project**``// generate app architecture using madge  
$ **madge index.js --image your_project_arc.png** `

Contoh hasil generate pada project Simple Todo yang saya buat menggunakan ReactJs (create-react-app)



![image](/posts/2019-02-01_visualisasi-arsitektur-aplikasi-dengan-madge/images/2.png)

MedicineTodo — [https://github.com/ri7nz/medicine](https://github.com/ri7nz/medicine)

### Kesimpulan

Dengan menggunakan **Madge** atau tepatnya dengan mendapatkan informasi mengenai rancangan, arsitektur, dan dependesi yang digunakan pada sebuah project atau aplikasi kita dapat jadi lebih mudah untuk meningkatkan kualitas atau performa, Contohnya pada pengembangan **web jaman now** yang memiliki bundle file yang harus dijaga, dengan mengetahui apa yg tidak digunakan maka kita dapat menghapus atau tidak menggunakannya, serta untuk kebutuhan analisa.

Sekian, dan terima kasih semoga bermanfaat. 😀 (Mohon maaf jika ada yang salah).

[R AdySurya A](https://medium.com/u/4bafb556834e)

Follow Me On

*   Github : [https://github.com/ri7nz](https://github.com/ri7nz)
*   Twitter : [https://twitter.com/ri7nz](https://twitter.com/ri7nz)
