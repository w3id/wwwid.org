---
title: "LighthouseBOT Untuk Auto Audit Web di Github Repositori"
author: "R AdySurya A"
date: 2019-02-26T01:58:04.580Z
lastmod: 2019-05-22T16:27:57+07:00

description: ""

subtitle: "Madge merupakan Applikasi pengembang yang menghasilkan Grafik Visual mengenai struktur sebuah applikasi, modul-modul yang digunakan…"
tags:
 - JavaScript
 - Lighthouse
 - WebPerformance
 - WebAccessibility
 - WebTest
 - WebAudit
 - w3id

image: "/posts/2019-02-26_lighthousebot_untuk_auto_audit_web_di_github_repositori/images/1.png" 
images:
 - "/posts/2019-02-26_lighthousebot_untuk_auto_audit_web_di_github_repositori/images/1.png" 
 - "/posts/2019-02-26_lighthousebot_untuk_auto_audit_web_di_github_repositori/images/2.png"
 - "/posts/2019-02-26_lighthousebot_untuk_auto_audit_web_di_github_repositori/images/3.png"
 - "/posts/2019-02-26_lighthousebot_untuk_auto_audit_web_di_github_repositori/images/4.png"
 - "/posts/2019-02-26_lighthousebot_untuk_auto_audit_web_di_github_repositori/images/5.png"

aliases:
    - "/lighthousebot-untuk-auto-audit-web-b6058984a6c6"
---
![image](/posts/2019-02-26_lighthousebot_untuk_auto_audit_web_di_github_repositori/images/1.png)
LighthouseBOT — merupakan sebuah akun “bot” yang bekerja untuk “Audit Web” dengan menggunakan Lighthouse dan melaporkan hasil audit tersebut pada repositori kita di Github. Dengan menggunakan LighthouseBOT maka kita tidak perlu lagi untuk melakukan audit secara manual dengan menggunakan https://web.dev, Lighthouse pada Chrome DevTools, Lighthouse Extension pada browser, Lighthouse-cli, & cara-cara lain yang menggunakan Lighthouse.

Hal — hal yang bisa dilakukan LighthouseBOT hanyalah menampilkan laporan mengenai Performance, Accessibility, SEO, & Best Practices.

**Yang dibutuhkan**
- [Github](https://github.com)
- [Travis](https://travis.org) 

## Cara integrasi
- Menambahkan [LighthouseBOT](https://github.com/lighthousebot) sebagai kolaborator pada repositori di Github.
- Mengajukan permintaan `API_KEY` untuk Lighthouse CI.
- Menambahkan Script dan Konfigurasi Travis untuk Lighthouse CI.
- Tes dengan Pull-Request.
- Menambahkan LighthouseBOT sebagai kolaborator di Github Repository
- Menambahkan LighthouseBOT sebagai kolaborator pada repositori project kamu di Github.

### Menambahkan LighthouseBOT sebagai kolaborator di Github Repository
Menambahkan  `LighthouseBOT` sebagai kolaborator pada repositori project kamu di Github.
   
    
![image](/posts/2019-02-26_lighthousebot_untuk_auto_audit_web_di_github_repositori/images/2.png)
Silahkan follow https://github.com/lighthousebot 😇 .  
   
  
Setelah ditambah, status `LighthouseBOT` default-nya pending atau menunggu sampai permintaan teman-teman diterima. Sambil menunggu, silahkan isi formulir di bawah ini untuk mendapatkan `LIGHTHOUSE_API_KEY` yang digunakan (saya mendapatkan `LIGHTHOUSE_API_KEY` dalam waktu kurang lebih 1x24 jam).    `LIGHTHOUSE_API_KEY` nanti di tambahkan pada `environment variable` di Travis-ci.com.
### Mengajukan Permintaan API_KEY untuk Lighthouse CI
[Isi Formulir Disini](https://docs.google.com/forms/d/e/1FAIpQLSdIc3QNIMn7bBMgl2cfxmmo6wGBlUpdLGxjB_ml464t9eCg_A/viewform)
   
### Menambahkan Script dan Konfigurasi Travis untuk Lighthouse CI
Jika `LIGHTHOUSE_API_KEY` telah didapatkan melalui email yang kamu gunakan pada saat proses pengajuan maka yang kamu perlukan adalah menambahkan `LIGHTHOUSE_API_KEY` pada `Travis-ci` yang sudah integrasi dengan repositori di Github.

![image](/posts/2019-02-26_lighthousebot_untuk_auto_audit_web_di_github_repositori/images/3.png)

Jika telah mendapatkan Environment Variable, silahkan tambahkan package `LighthouseBot` pada project kamu.

`yarn add https://github.com/GoogleChromeLabs/lighthousebot --dev`
Perintahnya seperti ini,
```bash
// dasar | basic usage
lighthousebot <alamat_web>
// Perfomance budgeting
lighthousebot --perf=95 --seo=100 --pwa=100 --a11y=100 --bp=100 <alamat_web>
```  

- **perf** — Performance
- **seo** — Search Engine Optimization
- **pwa** — Progressive Web Application
- **a11y** — Accessibility
- **bp** — Best Practices

Jangan lupa tambahkan perintah lighthousebot pada `.travis.yml` dibagian `after_success`

after_success:  
  - `lighthousebot --perf=95 --seo=100 --pwa=100 --a11y=100 --bp=100 <alamat_web>` . 
  
## Kesimpulan
  
Jika menggunakan opsi seperti contoh perfomance budgeting, artinya kita telah mengatur minimum pencapaian setiap web kita di audit. Jika kurang dari nilai yang sudah di tentukan maka di anggap error atau gagal dalam tes audit.

![image](/posts/2019-02-26_lighthousebot_untuk_auto_audit_web_di_github_repositori/images/4.png)

Terakhir, kamu bisa tes dengan mengirimkan `commit` atau `pull-request` ke repository kamu.

![image](/posts/2019-02-26_lighthousebot_untuk_auto_audit_web_di_github_repositori/images/5.png)
    
Log Travis dan data tersebut akan di gunakan oleh LighthouseBOT sebagai komentar di Repository Github kamu.
Kesimpulan
Jika kamu memiliki project open source atau private project dan tetap peduli pada performa website, kamu bisa menggunakan LigthouseBOT, agar kamu dapat dibantu dan mengurangi hal — hal manual. Selain itu, kamu akan lebih peduli terhadap code yang kamu tulis dikarenakan ada pencapaian yang sudah di tetapkan.

Contoh project yang menerapkan LighthouseBOT.
