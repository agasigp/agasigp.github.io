---
author: agasigp
categories:
  - development
  - php
  - web
date: "2013-05-08T01:11:52+00:00"
guid: http://agasigp.wordpress.com/?p=96
tag:
  - codeigniter
  - netbeans
  - php
title: Integrasi Codeigniter dan Netbeans Dengan NbPHPCI
url: /2013/05/08/integrasi-codeigniter-dan-netbeans-dengan-nbphpci/

---
Sebagai seorang pengembang aplikasi web,selama ini saya menggunakan framework [Codeigniter](http://codeigniter.com "Codeigniter") (biasa disingkat CI) dan IDE [Netbeans](http://netbeans.org "Netbeans") untuk mempermudah coding. Netbeans sendiri tidak terintegrasi dengan CI,sehingga fitur autocomplete untuk CI di Netbeans tidak semuanya muncul. Misal,jika ketik $this-> maka tidak ada opsi yang ditampilkan. Setelah bertanya dengan Google,akhirnya ketemu cara untuk mengintegrasikan CI dan Netbeans agar fitur autocompletenya bisa berjalan.

[NbPHPCI](https://kenai.com/projects/nbphpci/pages/Home "NbPHPCI"),itulah nama plugin Netbeans untuk mengintegrasikan CI dengan Netbeans. Dengan NbPHPCI,kita bisa membuat proyek web baru di Netbeans langsung dengan CI didalamnya. Selain itu,fitur autocomplete CI di Netbeans juga berjalan,sehingga mempermudah dan membantu kita untuk mempercepat kita dalam coding.

Instalasi nbphpci pun juga sangat gampang. Caranya adalah :

1. Versi Netbeans yang digunakan versi 7.2, 7.2.1, 7.3. Selain versi tersebut,plugin nbphpci tidak bisa diinstal
1. Masuk ke menu Tool - Plugin,pilih tab Setting
   ![](https://kenai.com/attachments/wiki_images/nbphpci/nbphpci.tools.png)
1. Klik tombol Add,isikan nama dengan nbphpci dan url dengan daftar yang tertera dibawah ini. Klik tombol OK
   - Untuk NetBeans 7.2 gunakan [https://kenai.com/downloads/nbphpci/Latest\_NetBeans720/updates.xml](https://kenai.com/downloads/nbphpci/Latest_NetBeans720/updates.xml)
   - Untuk NetBeans 7.2.1 gunakan [https://kenai.com/downloads/nbphpci/Latest\_NetBeans721/updates.xml](https://kenai.com/downloads/nbphpci/Latest_NetBeans721/updates.xml)
   - Untuk NetBeans 7.3 gunakan [https://kenai.com/downloads/nbphpci/Latest\_NetBeans730/updates.xml\
     ![](https://kenai.com/attachments/wiki_images/nbphpci/nbphpci.plugins.settings.uc.png)](https://kenai.com/downloads/nbphpci/Latest_NetBeans730/updates.xml)
1. Pindah ke Tab Available plugin,cari dengan kata kunci codeigniter. Pilih modul nbphpci yang akan diinstal dengan mencentang kedua pilihan (CI Framework dan CI Framework Repository). Klik tombol install
   ![](https://kenai.com/attachments/wiki_images/nbphpci/nbphpci.plugins.available.png)
1. Plugin nbphpci pun berhasil diinstal.

Selanjutnya adalah konfigurasi plugin nbphpci. Langkah ini opsional,karena hanya mengintegrasikan CI yang kita punya dengan nbphpci,sehingga ketika membuat proyek php baru kita bisa langsung menggunakan CI tanpa harus memasukkan manual CI kedalam proyek php kita. Langkahnya sebagai berikut :

1. Masuk ke menu Tool-Options,pilih PHP,pilih tab Codeigniter,pilih base file.
   ![](https://kenai.com/attachments/wiki_images/nbphpci/nbphpci.options.basefiles.png)
1. Klik tombol Add zip. Isikan name dengan versi CI yang kita miliki,misal CI\_2.1.3. Klik tombol browse untuk memilih file CI yang kita miliki,yang sudah dikompres kedalam zip. Klik tombol Ok
1. Integrasi selesai. Sekarang kita bisa membuat proyek php baru di Netbeans dengan Ci didalamnya,serta fitur automplete
   ![](https://kenai.com/attachments/wiki_images/nbphpci/nbphpci.newproject.png)![](https://kenai.com/attachments/wiki_images/nbphpci/nbphpci.project.png)

Instalasi dan integrasi sudah selesai. Selamat coding teman!

Referensi : [https://kenai.com/projects/nbphpci/pages/Home](https://kenai.com/projects/nbphpci/pages/Home)
