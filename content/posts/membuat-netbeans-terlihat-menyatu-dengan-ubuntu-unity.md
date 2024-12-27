---
author: agasigp
categories:
  - development
  - linux
date: "2013-06-04T05:41:20+00:00"
guid: http://agasigp.wordpress.com/?p=114
tag:
  - linux
  - netbeans
  - ubuntu
title: Membuat Netbeans Terlihat Menyatu Dengan Ubuntu Unity
url: /2013/06/04/membuat-netbeans-terlihat-menyatu-dengan-ubuntu-unity/

---
[Netbeans](http://netbeans.org "Netbeans") adalah [IDE](http://en.wikipedia.org/wiki/Integrated_development_environment "Integrated Development Environment") favorit saya untuk pengembangan aplikasi. Saya sendiri sudah menggunakan Netbeans sudah cukup lama,sekitar 3 tahun. Sekarang versi Netbeans terbaru adalah sudah mencapai versi 7.2. Saya sendiri menggunakan Netbeans untuk pengembangan aplikasi web dengan bahasa pemrograman PHP.

Netbeans bersifat multiplatform,jadi bisa berjalan di Windows,Linux,dan OSX. Nah,kebetulan saya menggunakan Netbeans di Ubuntu 12.04. Ubuntu sendiri menggunakan lingkungan desktop sendiri yang bernama Unity,menggantikan Gnome yang sudah lama digunakan. Di Unity,menu aplikasi semua berada taskbar atas,mirip dengan di OSX. Model menu seperti ini disebut global menu. Netbeans sendiri merupakan aplikasi java,sehingga menu nya belum terintegrasi dengan global menu unity. Supaya menu di netbeans terintegrasi dengan global menu unity,berikut langkah-langkah nya :

1. Buka Netbeans,masuk menu tool-plugin. Di tab setting,klik tombol add. Isikan name dengan Jaya Ayatana,url dengan **http://java-swing-ayatana.googlecode.com/files/netbeans-catalog.xml**
   **![](http://danjared.files.wordpress.com/2012/02/netbeans.png?w=650)![](http://danjared.files.wordpress.com/2012/02/java-ayatana-nbs-config.png?w=650)**
1. Di tab available plugin,cari kemudian instal plugin java ayatana. Setelah selesai,tutup netbeans.
   **![](http://danjared.files.wordpress.com/2011/05/install-java-ayatana.png?w=650)**
1. Tambahkan opsi berikut di file \[netbeans\_folder\]/etc/netbeans.conf : -J-Dswing.aatext=true -J-Dawt.useSystemAAFontSettings=lcd
   [![Screenshot from 2013-06-04 12:31:54](/wp-content/uploads/2013/06/screenshot-from-2013-06-04-123154.png)](/wp-content/uploads/2013/06/screenshot-from-2013-06-04-123154.png)
1. Buka kembali netbeans. Menu nya sekarang sudah terintergrasi dengan global menu unity

Sekian tutorial dari saya,semoga bermanfaat. Selamat coding!

Referensi :

1. [http://alvonsius.tumblr.com/post/50819847481/to-make-netbeans-more-blended-to-ubuntus-unity](http://alvonsius.tumblr.com/post/50819847481/to-make-netbeans-more-blended-to-ubuntus-unity)
1. [http://plugins.netbeans.org/plugin/41822](http://plugins.netbeans.org/plugin/41822)
