---
author: Agasi Gilang Persada
categories:
  - development
  - web
cover:
  alt: Logo Hugo.io
  image: https://gohugo.io/images/hugo-logo-wide.svg
date: "2025-01-26T09:18:25+00:00"
tag:
  - web
title: Migrasi Wordpress Ke Hugo
url: /2025/01/26/migrasi-wordpress-ke-hugo
draft: false

---
# Ringkasan
Tulisan ini berisi cara migrasi dari wordpress ke hugo yang terdiri dari dua bagian :
- [Bagian 1: cara migrasi wordpress ke hugo](/2025/01/26/migrasi-wordpress-ke-hugo)
- Bagian 2: cara deploy hugo ke hosting (segera)

# Alasan migrasi ke hugo
Setelah sekian lama terbengkalai, akhirnya web saya kembali terurus kembali😅 Karena kesibukan, web saya tidak sempat saya urus. [Konten terakhir](/2016/11/21/seminar-workshop-tanda-tangan-digital) saja dibuat 8 tahun yang lalu😯. Uang saya serasa terbuang percuma karena saya setiap tahun membayar biaya domain & hosting, tapi web tidak pernah diurus😢. Untung web cuma benda mati. Kalau dia benda hidup, mungkin sudah mati karena tidak pernah diurus.

Supaya uang saya tidak terbuang sia-sia lagi, akhirnya saya memutuskan untuk mulai mengisi konten web/blog ini lagi. Selain itu, saya juga memindahkan/migrasi konten blog ini yang semula menggunakan wordpress ke static content generator <a href="https://gohugo.io" target="_blank">Hugo</a>. Berikut ini beberapa alasan kenapa saya migrasi dari wordpress ke hugo :

1. Dengan menggunakan hugo, saya hanya perlu mengeluarkan uang tiap tahun untuk biaya perpanjangan domain saja. Saya tidak perlu lagi menggunakan hosting sebagai tempat/wadah untuk menyimpan konten web saya.
2. Web saya lebih cepat untuk diakses karena konten web saya statis alias hanya html,css, & js saja. Tidak ada koneksi lagi ke basisdata/database ketika menggunakan wordpress.
3. Web saya lebih aman karena tidak ada inputan dari pengguna sama sekali & juga tidak ada koneksi dengan basisdata/database.

# Alternatif selain hugo
Sebenarnya ada banyak staic content generator selain hugo, seperti <a href="https://jekyllrb.com/" target="_blank">Jekyll</a>, <a href="https://vitepress.dev/" target="_blank">Vitepress</a>, <a href="https://hexo.io/" target="_blank">Hexo</a>, <a href="https://astro.build/" target="_blank">Astro</a>, <a href="(https://github.com/myles/awesome-static-generators/" target="_blank">dll</a>. Kenapa saya memilih hugo? Sederhana, karena hugo merupakan static content generator yang sederhana & cepat. [Proses instalasi](https://gohugo.io/installation/) nya sederhana, tidak ribet. Generate content juga cukup cepat karena hugo menggunakan <a href="https://go.dev/" target="_blank">Golang</a>,. Beberapa blog yang sering saya kunjungi juga menggunakan hugo, antara lain blog <a href="https://blog.nafies.id" target="_blank">Mas Nafies</a> & <a href="https://software.endy.muhardin.com/" target="_blank">Pak Endy</a>.

# Proses Migrasi
Untuk proses migrasi nya, saya menggunakan <a href="https://github.com/ashishb/wp2hugo" target="_blank">wp2hugo</a>. Petunjuk instalasi bisa ikuti petunjuk yang ada. Berikut ini adalah langkah migrasi yang saya lakukan :
- Install `hugo`
- Install `wp2hugo`
- Unduh data/konten web wordpress via menu `Tools -> Export` di dashboard admin wordpress. File/berkas dalam bentuk `xml`
- Asumsi file `xml` saya berada di `/home/agasigp/Downloads/agasigpblog.WordPress.2024-12-22.xml` & hasil migrasi ingin saya letakkan di `/home/agasigp/`, maka jalankan perintah berikut untuk mengkonversi/migrasi data dari wordpress ke hugo : `wp2hugo --source /home/agasigp/Downloads/agasigpblog.WordPress.2024-12-22.xml --download-media -continue-on-media-download-error --output /home/agasigp/`.
- Setelah proses migrasi selesai, maka didalam folder `/home/agasigp` akan muncul folder baru yang isinya merupakan hasil migrasi dari `wordpress` ke `hugo` menggunakan `wp2hugo`.

Proses migrasi selesai. Konten wordpress telah selesai dimigrasi ke hugo. Sangat mudah bukan? saya pun tidak menyangka akan semudah itu😀.

Untuk tema bawaan yang digunakan oleh `wp2hugo` adalah <a href="https://github.com/adityatelange/hugo-PaperMod" target="_blank">Hugo Papermod</a>. Silahkan baca dokumentasi yang ada untuk referensi lebih lanjut jika web anda ingin dikustomisasi sesuai kebutuhan & keinginan.

Oke, cukup sekian tutorial yang saya bisa saya berikan. Semoga bermanfaat bagi teman-teman yang ingin migrasi dari wordpress ke hugo seperti saya. Untuk proses deployment akan dbuat di konten selanjutnya supaya tulisan tidak terlalu panjang. Selamat mencoba!
