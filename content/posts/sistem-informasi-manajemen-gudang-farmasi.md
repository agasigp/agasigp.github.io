---
author: Agasi Gilang Persada
categories:
  - php
  - web
cover:
  alt: Sistem Informasi gudang Farmasi
  image: /wp-content/uploads/2016/01/Screenshot-from-2016-01-11-153606.png
date: "2016-01-11T09:15:31+00:00"
guid: http://www.agasigp.web.id/?p=236
tag:
  - laravel
  - php
  - web
title: Sistem Informasi Manajemen Gudang Farmasi
url: /2016/01/11/sistem-informasi-manajemen-gudang-farmasi/
draft: true

---
Sesuai [janji saya kemarin](/2016/01/03/mengganti-login-laravel-dengan-username/), kali ini saya akan bercerita tentang aplikasi Gudang Farmasi. Jadi, akhir tahun kemarin, alhamdullilah saya mendapat kesempatan untuk berkunjung ke bumi Maluku Utara, tepatnya Kabupaten Halmahera Barat. Saya mendapat kerjaan dari teman sekelas kuliah dulu untuk mengerjakan aplikasi Sistem Informasi Gudang Farmasi di Dinas Pendapatan Pengelolaan Keuangan dan Aset Daerah Kabupaten Halmahera Barat. Kebetulan teman saya ini asli Maluku Utara, tepatnya kota Ternate. Saya mengerjakan aplikasi ini berdua dengan rekan saya Ariefan.

Sistem Informasi Manajemen Gudang Farmasi merupakan aplikasi yang berguna untuk membantu dalam pengelolaan stok obat dan distribusi di gudang farmasi. Aplikasi ini digunakan di dua instansi, yaitu di Dinas Kesehatan (UPTD Gudang Farmasi dan Puskesmas) serta RSUD Jailolo (Apotik dan Gudang Farmasi). Jadi, DPPKAD melakukan pengadaan aplikasi ini supaya mereka bisa mendata aset barang yang ada di Halbar setiap tahun dengan akurat. Obat dan alat kesehatan yang berada di Puskemas, UPTD Gudang Farmasi, dan RSUD termasuk barang/aset milik daerah, jadi harus didata dan dibuat laporannya setiap tahun untuk dilaporkan ke DPPKAD. Selama ini pengelolaan stok dan distribusi obat di UPTD Gudang Farmasi, Puskesmas, dan RSUD masih menggunakan cara manual. Segala pencatatan masih dilakukan secara manual, yaitu dicatat di selembar kertas, kemudia diinput kedalam file spreadsheet menggunakan MS Excel. Akibatnya, mereka kesusahan untuk merekap data, membuat laporan yang diperlukan, serta rentan terjadi kesalahan akibat _human error._ Oleh karena itu, DPPKAD berinisiatif untuk mengatasi permasalahan tersebut dengan pengadaan aplikasi Sistem Informasi Gudang Farmasi.

Sistem/aplikasi ini berbasis web, dibuat menggunakan [Laravel 5.1](/2014/11/07/mainan-baru-bernama-laravel/) dan _database_ MySQL. Fitur-fitur yang ada antara lain :

1. Modul Pengguna dan group, berisi grup dan daftar pengguna yang membatasi hak akses masing-masing pengguna.
1. Modul Data Referensi, berisi manajemen data master seperti master obat, golongan obat, satuan, supplier, customer, dan sumber dana.
1. Modul Order Pembelian (Purchase Order),berisi manajemen order pembelian barang kepada supplier.
1. Modul Penerimaan, berisi manajemen penerimaan barang dari supplier, penerimaan dibagi 2 yaitu peneriman dengan PO (Purchase Order) atau penerimaan non-PO misal dari dana hibah atau lain-lain.
1. Modul Order distribusi, berisi manajemen order distribusi dari customer.
1. Modul Distribusi, berisi manajemen pendistribusian atau pengeluaran barang ke customer.
1. Modul Retur, berisi manajemen pengembalian barang karena rusak atau expired.,terdiri dari retur penerimaan (pengembalian ke supplier) dan retur distribusi (pengembalian dari customer).
1. Modul manajemen barang rusak, berisi manajemen barang rusak di gudang, untuk memisahkan barang yang rusak atau expired di gudang dengan barang yang masih baik
1. Modul Resep, berisi manajemen resep pasien. Modul ini digunakan di Apotik dan Puskesmas yang khusus melayani pasien.
1. Modul pelaporan, berisi output laporan mutasi obat dalam bentuk file excel.

Contoh tampilan aplikasi :

\[caption id="attachment\_259" align="aligncenter" width="665"\] [![Halaman Manajemen Order Distrbusi](/wp-content/uploads/2016/01/10572223_10205364902707234_4584392795199189256_o-1024x640.jpg)](/wp-content/uploads/2016/01/10572223_10205364902707234_4584392795199189256_o.jpg) Halaman Manajemen Order Distrbusi\[/caption\]

{{< figure align=aligncenter width=665 src="/wp-content/uploads/2016/01/12513822%5F10205364902867238%5F5002269514184406326%5Fo-1024x640.jpg" alt="" >}}

{{< figure align=aligncenter width=665 src="/wp-content/uploads/2016/01/12469358%5F10205364903387251%5F847496710755988009%5Fo-1024x640.jpg" alt="" >}}

{{< figure align=aligncenter width=665 src="/wp-content/uploads/2016/01/12489397%5F10205364903667258%5F4928190170601645620%5Fo-1024x640.jpg" alt="" >}}

{{< figure align=aligncenter width=665 src="/wp-content/uploads/2016/01/Screenshot-from-2016-01-11-153606-1024x640.png" alt="" >}}

Untuk demo aplikasinya, bisa diakses di [https://sisfarm.agasigp.web.id](http://sisfarm.agasigp.web.id). Silahkan masuk dengan username: **admin** dan password: **administrator**.Jika pembaca atau rekan-rekan yang berminat terhadap aplikasi ini untuk diimplementasikan di tempat lain, bisa menghubungi saya via email di [mail@agasigp.web.id](mailto:mail@agasigp.web.id) atau [agasigp@live.com](mailto:agasigp@live.com).
