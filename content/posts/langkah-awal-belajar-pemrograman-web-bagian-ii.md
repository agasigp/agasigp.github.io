---
author: agasigp
categories:
  - php
  - web
cover:
  alt: Buku Programming
  image: /wp-content/uploads/2015/11/1409261660001.jpg
date: "2016-05-07T14:59:39+00:00"
guid: https://www.agasigp.web.id/?p=351
tag:
  - html
  - php
  - web
title: Langkah Awal Belajar Pemrograman Web Bagian II
url: /2016/05/07/langkah-awal-belajar-pemrograman-web-bagian-ii/

---
Pada tulisan sebelumnya, saya telah membahas tentang [konsep dasar dalam pemrograman web](/2016/04/30/langkah-awal-belajar-pemrograman-web-bagian-i/). Setelah paham akan konsep dasar, selanjutnya adalah belajar tentang bahasa pemrograman web itu sendiri. Berikut adalah tahapan belajar bahasa pemrogramannya.

### Client Side Programming

Langkah awal untuk belajar bahasa pemrograman adalah belajar client side programming. Bahasa yang harus dipelajari adalah html,css, & javascript. Khusus untuk javascript, untuk awal belajar, kita tidak perlu sampai paham detail karena banyak sekali yang harus dipelajari. Belajar client side programming tidak membutuhkan tool/software yang ribet,berat, & mahal seperti dreamweaver. Cukup berbekal sebuah web browser dan teks editor seperti [sublime text](https://www.sublimetext.com/) atau [notepad++](https://notepad-plus-plus.org/) kita sudah bisa belajar untuk membuat sebuah halaman web sederhana.

Untuk referensi belajar, saya menyarankan untuk belajar dari w3schools. Selain mudah dipahami oleh pemula, materinya pun cukup lengkap. Saya pun masih sering menggunakan [w3schools](http://www.w3schools.com/php/default.asp) untuk mencari referensi.

Jika sudah paham akan dasar html, css, kita bisa mencoba untuk membuat sebuah halaman web sederhana. Kita bisa ambil contoh atau studi kasus untuk web yang akan kita buat, seperti online shop, perpustakaan, atau rental mobil. Bikin semampu kita saja, tidak perlu dipaksakan untuk jadi sebuah halaman web yang keren & menarik. Kita masih dalam tahap belajar, jadi wajar kalau halaman web yang kita bikin masih sederhana sekali & mungkin kurang menarik atau keren.

Setelah berhasil membuat halaman web sederhana, publikasikan atau sebarkanlah hasil buatan kita. Taruh hasil karya kita di web hosting supaya hasil karya kita bisa diakses oleh semua orang. Kita bisa gunakan penyedia jasa web hosting gratisan seperti idhostinger untuk menaruh hasil karya kita. Minta saran dari teman-teman kita atau rekan-rekan di grup [PHP Indonesia](https://www.facebook.com/groups/35688476100/) tentang karya yang sudah kita buat. Dari saran yang masuk pasti kita akan banyak mendapat hal baru.

### Database (MySql)

Setelah paham dasar-dasar client side programming, selanjutnya adalah belajar tentang database. Ada banyak jenis database yang bisa kita gunakan untuk belajar, tapi yang biasa digunakan adalah MySQL karena instalasi & penggunaannya ang mudah. Selain itu, sebagian besar web hosting menggunakan MySql, sehingga aplikasi yang nanti kita buat bisa kita unggah/upload ke hosting.

Materi yang harus dipelajari dalam database adalah tentang konsep dari database itu sendiri, mulai dari tabel, field/kolom, record, SQL, hingga relasi antar tabel. Referensi yang bisa digunakan adalah [w3schools](http://www.w3schools.com/sql/default.asp) dan [manual/dokumentasi MySql](http://dev.mysql.com/doc/).

Kalau di bagian client side programming kita dilatih untuk melatih bagaimana membuat tampilan dari aplikasi web, maka di bagian database kita dilatih untuk membuat bagaimana kira-kira nanti data-data dari web yang akan kita buat akan disimpan. Disini kita lebih mengandalkan analisis, kira-kira bagaimana struktur tabelnya, terus relasi antar tabel nya seperti apa.

Untuk tool/aplikasi yang digunakan, tentu saja kita butuh MySql. Kita bisa gunakan aplikasi paketan seperti [xampp](https://www.apachefriends.org/download.html) untuk mempermudah kita, karena sudah ada web server (apache), MySQL, PHP, sehingga kita tidak perlu instalasi manual satu per satu. Phpmyadmin dapat kita gunakan untuk membantu, mempermudah kita dalam belajar MySQL. Phpmyadmin sudah tersedia dalam xampp. Selain phpmyadmin, kita juga bisa menggunakan aplikasi lain yang sejenis seperti [heidisql](http://www.heidisql.com/) atau [MySQL Workbench](https://www.mysql.com/products/workbench/).

Jika sudah paham konsep dasar, selanjutnya adalah membuat database dari aplikasi yang akan kita buat. Untuk menentukan struktur database aplikasi, kita bisa menggunakan desain dari tampilan yang sudah kita buat sebelumnya. Karena masih tahap belajar, tidak perlu kita membuat database yang rumit. Cukup 4-6 tabel saja itu sudah cukup untuk tahap belajar. Setelah berhasil, tunjukkan kepada teman atau rekan di grup/komunitas, minta saran dari mereka.

### Server Side Programming

Setelah paham dasar database, selanjutnya adalah belajar tentang server side programming. Ada banyak pilihan untuk belajar server side programming, mulai dari Java dengan jsp nya, asp dengan .net nya, python, ruby, go, php, dll. Karena tulisan ini adalah tentang php, maka tentu saja kita memilih php.

Untuk referensi belajar, saya lagi-lagi menyarankan w3schools karena kemudahannya. Selain w3schools, tentu saja dokumentasi resmi php juga menjadi referensi wajib. Situs [http://www.phptherightway.com/](http://www.phptherightway.com/) juga bisa menjadi rujukan bagaimana cara coding php dengan baik dan benar. Jika ada dana, bisa membeli buku tentang pemrograman web dengan php yang banyak beredar di toko buku. Materi yang dibahas didalam buku biasanya sudah mencakup tentang client side, database, dan server side.

Untuk tools/aplikasi, cukup hanya sekedar xampp dan sejenisnya serta teks editor favorit. Ingat, kita ini masih tahap belajar, jadi pakailah aplikasi yang sederhana dulu, jangan langsung menggunakan IDE seperti Netbeans, phpstorm, eclipse karena malah nanti akan membingungkan.

Untuk tahap awal, tidak perlu sampai paham akan konsep OOP. Cukup sudah paham bagaimana menggunakan php secara struktural, bisa membuat crud sederhana (1-2 tabel), autentikasi (login) itu sudah cukup.

### Gabungkan Client Side, Database, & Server Side

Dari belajar client side programming, kita sudah punya desain/tampilan aplikasi. Dari belajar database, kita sudah punya database untuk menyimpan data pada aplikasi. Dari belajar sever side, kita sudah bisa untuk membuat sebuah crud sederhana. Dari ketiga hasil belajar tersebut, kita tinggal gabungkan saja sehingga menjadi sebuah aplikasi web sederhana. Pasang di hosting, tunjukkan hasilnya ke komunitas, minta kritik dan saran dari aplikasi yang telah dibuat. Kalau perlu, sekalian saja berikan source code nya. Lakukan apa yang saya tulis disini, saya jamin kita akan belajar lebih cepat dibanding karena ada masukan dan saran dari teman-teman atau komunitas.

### Penutup

Ternyata belajar web programming itu tidak sesulit yang dibayangkan,asalkan kita mau belajar dan berlatih dengan sungguh serta paham akan konsep. Mungkin kita beranggapan membuat aplikasi web itu sulit karena kita langsung membayangkan aplikasi web yang rumit seperti gmail, google, wordpress, sisten infomasi. Padahal, untuk belajar itu tidak perlu langsung bisa membuat aplikasi yang keren. Cukup bisa membuat aplikasi sederhana saja dulu saja itu sudah cukup. Toh lama-lama nanti kita juga bisa dengan sendirinya membuat aplikasi keren seiring dengan meningkatnya skill/kemampuan kita. Jadi, selamat belajar web programming & happy coding! Jika ada yang ingin ditanyakan, bisa melalui kolom komentar yang telah disediakan.
