<div align="center">
  <img src="https://readme-typing-svg.herokuapp.com?size=33&color=FFAE42&center=true&vCenter=true&width=600&lines=Installasi+𝘱𝘩𝘱𝘔𝘺𝘈𝘥𝘮𝘪𝘯+Di+Debian">
</div>

## Apa Itu 𝘱𝘩𝘱𝘔𝘺𝘈𝘥𝘮𝘪𝘯?

phpMyAdmin merupakan aplikasi berbasis PHP yang memudahkan kita dalam mengelola MySQL maupun MariaDB melalui tampilan web. Dengan antarmuka yang sederhana, kita bisa melakukan berbagai tugas seperti membuat atau mengatur database, tabel, kolom, relasi, hingga mengelola pengguna dan izin akses. Selain itu, phpMyAdmin juga menyediakan fitur untuk menjalankan perintah SQL secara langsung, sehingga tetap fleksibel untuk kebutuhan administrasi yang lebih teknis. Deskripsi ini diadaptasi dari dokumentasi resmi phpMyAdmin yang tersedia di https://www.phpmyadmin.net/.

## langkah-langkah Instalasi

Sebelum memulai pemasangan phpMyAdmin di Debian, pastikan kalian sudah menginstal LAMP terlebih dahulu. Untuk panduan lengkapnya, kalian bisa melihat dokumentasinya di repositori GitHub saya: [Instalasi_LAMP](https://github.com/Kaguai10/Instalasi_LAMP). Jika LAMP sudah terpasang, kita bisa langsung melanjutkan ke tahap instalasi phpMyAdmin.

1. Untuk menginstal phpMyAdmin sangat lah mudah. Untuk mengawali kalian dapat mengetik command ini:
```bash
sudo apt install phpmyadmin
```
2. Pilih Web Server, Pada proses Instalasi ada beberapa hal yang harus kita set terlebih dahulu. Salah satunya pemilihan Web Server. Disini kalian dapat menyesuaikan atau dapat memilih Apache2 jika kalian telah memasang saat penginstallan LAMP.

```txt
Web server to reconfigure automatically:
[*] apache2
[ ] lighthttpd
```
3. Setelah itu kalian bakal diminta untuk mengkonfigurasi database secara otomatis menggunakan dbconfig-common, nah disini kalian pilih 'Yes'. Kenapa kita pilih yes? karena agar pembuatan database bisa dilakukan dengan cara otomatis. dbconfig-common adalah sebuah framework otomatis di Debian/Ubuntu yang digunakan untuk mengelola konfigurasi database aplikasi ketika aplikasi tersebut diinstall menggunakan APT.
```txt
Configure database for phpmyadmin with dbconfig-common: 

[YES]
```

4. Mengatur Password dan Krendensial untuk phpMyAdmin. Setelah kalian memilih Yes pada konfigurasi otomatis menggunakan dbconfig-common, sistem akan langsung meminta kalian untuk membuat password khusus untuk user phpMyAdmin. Password ini akan digunakan sebagai kredensial agar phpMyAdmin dapat terhubung dengan database secara aman. Pada tahap ini, dbconfig-common akan: Membuat user database untuk phpMyAdmin. Menyimpan password yang kalian buat Mengatur koneksi dan konfigurasi secara otomatis Dengan begitu, phpMyAdmin dapat berjalan dan mengakses database tanpa perlu konfigurasi manual tambahan, sekaligus tetap menjaga aspek keamanan.
```txt
MySQL application password for phpmyadmin:

#*masukan_password_untuk_phpmyadmin*
```

sampai disini Penginstallan telah selesai selanjutnya kalian bisa mencoba membuka-nya di browser kalian dengan mengunjungi \<Ip Address>\/phpmyadmin. Kalian dapat melihat username dan password untuk masuk phpmyadmin dengan cara
```bash
cat /etc/phpmyadmin/config-db.php
```
saat kalian mengetik itu dan enter maka kalian akan melihat username di $dbuser dan password di $dbpass.
```php
<?php                                                                                                                      ##
## database access settings in php format   
## automatically generated from /etc/dbconfig-common/phpmyadmin.conf 
## by /usr/sbin/dbconfig-generate-include  
## 
## by default this file is managed via ucf, so you shouldn't have to 
## worry about manual changes being silently discarded.  *however*,  
## you'll probably also want to edit the configuration file mentioned
## above too. 
##                                                                                                                
$dbuser='phpmyadmin'; ## <= ini adalah username-nya                              
$dbpass='@pA5ssW0rd#';  ## <= ini adalah passwordnya                   
$basepath='';                                                                                                           
$dbname='phpmyadmin';                                                                                                   
$dbserver='localhost';                                                                                                  
$dbport='3306';                                                                                                         
$dbtype='mysql';   
```
**Setelah itu kalian dapat masuk ke halaman phpmyadmin.**<br>

![Login Page](https://raw.githubusercontent.com/Kaguai10/Instalasi_PHPMYADMIN/refs/heads/main/login_page_phpmyadmin.png "Login Page")
![Login Page](https://raw.githubusercontent.com/Kaguai10/Instalasi_PHPMYADMIN/refs/heads/main/index_page.png "Login Page")
