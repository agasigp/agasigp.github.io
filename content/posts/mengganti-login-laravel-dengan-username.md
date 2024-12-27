---
author: agasigp
categories:
  - development
  - php
cover:
  alt: laravel logo
  image: /wp-content/uploads/2016/01/laravel-1.png
date: "2016-01-03T11:16:06+00:00"
guid: http://www.agasigp.web.id/?p=189
tag:
  - laravel
  - php
  - web
title: Mengganti Login Laravel Dengan Username
url: /2016/01/03/mengganti-login-laravel-dengan-username/

---
Jadi, ceritanya saya sedang membuat Sistem Informasi Gudang Farmasi di Kabupaten Halmahera Barat, Maluku Utara. Detail bagaimana saya mendapatkan kerjaan ini, akan saya tulis di tulisan selanjutnya. Aplikasi yang saya buat bersama teman saya, Ariefan, menggunakan [Laravel 5.1](/2014/11/07/mainan-baru-bernama-laravel/) dan database MySQL.

Masalah yang saya alami adalah fitur login (Auth) bawaan laravel menggunakan email untuk login. Sedangkan saya aplikasi yang saya buat tidak membutuhkan fitur email, karena aplikasi bersifat lokal, tidak terhubung internet. Saya ingin mengganti _default_ login email menjadi username.

Setelah saya googling, akhirnya saya menemukan caranya. Ternyata caranya sangat mudah. Tambahkan \[sourcecode language="php"\]
protected $username = 'username';
\[/sourcecode\] di **app/Http/ontrollers/Auth/AuthController.php.** Pastikan terdapat kolom/field username di tabel users atau tabel yang digunakan untuk login.

Beres! Sekarang kita bisa menggunakan username untuk login, tidak lagi menggunakan email. Kalau masih ada yang bingung atau mau ditanyakan, silahkan :)

Referensi : [http://stackoverflow.com/questions/31211153/modify-laravel-5-1-login-to-use-username-instead-of-email](http://stackoverflow.com/questions/31211153/modify-laravel-5-1-login-to-use-username-instead-of-email)
