---
author: Agasi Gilang Persada
date: '2025-02-13T18:01:57+07:00'
draft: false
title: 'Jangan Sampai Terjebak! Karakter ‘#’ di .env Bisa Bikin Laravel Error – Ini Cara Memperbaikinya!'
cover:
  alt: Logo Laravel
  image: https://cdnlogo.com/logos/l/56/laravel-wordmark.svg
categories:
  - development
  - web
tag:
  - web
---

# Masalah
Kemarin ada salah satu anggota grup [grup telegram laravel Indonesia](https://t.me/laravelindonesia) yang [bertanya](https://t.me/laravelindonesia/835182), kok koneksi ke database selalu gagal? Padahal username,password, & nama database sudah sesuai🤔. Saya pun [mebalas](https://t.me/laravelindonesia/835188) jika semua kredensial sudah benar, berarti masalahnya ada pada hak akses ke database. Namnun masalahnya belum kunjung usai. Koneksi ke database masih tidak bisa.

# Solusi
Usut punya usut, setelah saya [cek kembali](https://t.me/laravelindonesia/835205), ternyata password database di file `.env` nya mengandung karakter hashtag `(#)`🤦🏻. Alhasil, password tidak terbaca dengan sempurna karena karakter `#` dianggap sebagai komentar di file `.env`. Komentar disini maksudnya karakter setelah `#` dianggap tidak ada alias tidak dibaca oleh laravel. String `agasigp123#` atau `agasi#123`, di `.env` hanya terbaca sebagai `agasigp123` dan `agasi`.

Solusi untuk menangani masalah ini sangat gampang sekali. Cukup ganti `agasigp123#` menjadi `'agasigp123#'`. Dengan mengapit string dengan `'`, karakter `#` tetap terbaca di oleh laravel. Koneksi ke database pun kembali normal👍.


Jadi, lain kali jika di `.env` teman-teman, ada konfigurasi yang berisi karakter `#`, apit dengan karakter `'` supaya konfigurasi terbaca dengan benar😉