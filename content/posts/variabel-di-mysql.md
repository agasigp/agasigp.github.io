---
author: Agasi Gilang Persada
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
```sql
SELECT
@cat_id:=category_id,
category_id,
count(category_id) as count_cat,
(SELECT count(category_id) FROM table1 WHERE status = 'Y' AND category_id = @cat_id) as count_y,
(SELECT count(category_id) FROM table1 WHERE status = 'N' AND category_id = @cat_id) as count_y
FROM table1
group by category_id
```

Perhatikan bahwa pada query diatas, ada sesuatu yang agak berbeda, yaitu kita menggunakan simbol `@`, yaitu sebuah variabel, dalam hal ini variabel `@cat_id`. Nilai dari kolom `category_id` dimasukan ke variabel `@cat_id`, kemudian nilai variabel `@cat_id` nanti dipakai di tempat lain, dalam hal ini di subquery, seperti pada query dibawah ini :

```sql
SELECT (count(category_id) FROM table1 WHERE status = 'Y' AND category_id = @cat_id) as count_y
```

Jadi, penggunaan variabel pun tidak hanya untuk bahasa pemrograman saja, namun di MySQL pun juga terdapat variabel untuk menyimpan data. Referensi lebih lanjut tentang penggunaan variabel di MySQL bisa dilihat [disini](http://dev.mysql.com/doc/refman/5.7/en/user-variables.html).

Oke,sekian dulu tulisan dari saya. Semoga bermanfaat dan berguna. Selamat coding!
