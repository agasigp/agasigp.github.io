---
author: agasigp
categories:
  - development
cover:
  alt: MySQL Logo
  image: /wp-content/uploads/2016/02/MySQL.svg_.png
date: "2016-02-03T13:57:36+00:00"
guid: https://www.agasigp.web.id/?p=318
tags:
  - mysql
  - sql
title: Variabel di MySQL
url: /2016/02/03/variabel-di-mysql/

---
Kemarin di grup [FB PHP Indonesia](https://www.facebook.com/groups/35688476100/permalink/10153820428641101/), ada yang bertanya tentang masalah query di MySQL. Dari data di tabel1, dia ingin menghasilkan data seperti tabel2, seperti gambar dibawah ini.

[![](/wp-content/uploads/2016/02/12644791_1730139003886459_3804882412041477661_n.jpg)](/wp-content/uploads/2016/02/12644791_1730139003886459_3804882412041477661_n.jpg)

Query untuk menghasilkan data diatas sebetulnya cukup mudah yaitu seperti berikut :

\[code language="sql"\]
SELECT
@cat\_id:=category\_id,
category\_id,
count(category\_id) as count\_cat,
(SELECT count(category\_id) FROM table1 WHERE status = 'Y' AND category\_id = @cat\_id) as count\_y,
(SELECT count(category\_id) FROM table1 WHERE status = 'N' AND category\_id = @cat\_id) as count\_y
FROM table1
group by category\_id\[/code\]

Perhatikan bahwa pada query diatas, ada sesuatu yang agak berbeda, yaitu kita menggunakan simbol @, yaitu sebuah variabel, dalam hal ini variabel @cat\_id. Nilai dari kolom category\_id dimasukan ke variabel @cat\_id, kemudian nilai variabel @cat\_id nanti dipakai di tempat lain, dalam hal ini di subquery, bagian

\[code language="sql"\]
SELECT count(category\_id) FROM table1 WHERE status = 'Y' AND category\_id = @cat\_id) as count\_y.
\[/code\]

Jadi, penggunaan variabel pun tidak hanya untuk bahasa pemrograman saja, namun di MySQL pun juga terdapat variabel untuk menyimpan data. Referensi lebih lanjut tentang penggunaan variabel di MySQL bisa dilihat [disini](http://dev.mysql.com/doc/refman/5.7/en/user-variables.html).

Oke,sekian dulu tulisan dari saya. Semoga bermanfaat dan berguna. Selamat coding!
