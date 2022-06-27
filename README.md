Praktikum 11: PHP Framework (Codeigniter)

Step 1
Buat folder baru lab11_php_ci lalu Jalankan XAMPP Ubah file php.ini seperti berikut 
![pemrograman2](https://user-images.githubusercontent.com/73973590/173235986-caa230d6-e252-4203-a64a-6ffd55f5f112.png)

Step2
Pada bagian extention, hilangkan tanda ; (titik koma) pada ekstensi yang akan diaktifkan. Kemudian simpan kembali filenya dan restart Apache web server
![Pemrograman1](https://user-images.githubusercontent.com/73973590/173236030-c331fa97-feab-4741-ab73-39a7478a534c.png)

Step 3
Instalasi Codeigniter 4
Untuk melakukan instalasi Codeigniter 4 dapat dilakukan dengan dua cara, yaitu cara manual dan menggunakan composer. Pada praktikum ini kita menggunakan cara manual.
Unduh Codeigniter dari website https://codeigniter.com/download • Extrak file zip Codeigniter ke direktori htdocs/lab11_ci. • Ubah nama direktory framework-4.x.xx menjadi ci4. • Buka browser dengan alamat http://localhost/lab11_ci/ci4/public/
![pemrograman3](https://user-images.githubusercontent.com/73973590/173236076-d38ff867-ceba-43da-9235-d6023d228a08.png)

Step 4
Buka cmd pada XAMPP Shell lalu buka php spark, untuk menjalankan server ketik "php spark serve" :
![Pemrograman4](https://user-images.githubusercontent.com/73973590/173236101-8f11552a-d695-41c6-8dcb-7905635382a4.png)

Step 5 
Mengaktifkan Mode Debugging
Codeigniter 4 menyediakan fitur debugging untuk memudahkan developer untuk mengetahui pesan error apabila terjadi kesalahan dalam membuat kode program.

Secara default fitur ini belum aktif. Ketika terjadi error pada aplikasi akan ditampilkan pesan kesalahan seperti berikut.
![Screenshot 2022-06-12 204301](https://user-images.githubusercontent.com/73973590/173236140-5fed9e00-9f34-4162-9eb5-d8478c14a5f8.png)

Step 6
Mengaktifkan mode Debugging dengan mengubah file .env menjadi = development, seperti berikut 
![pemrograman5](https://user-images.githubusercontent.com/73973590/173236167-b05c6a58-76f1-4f2c-9cf4-f44d872154fd.png)
Untuk mencoba Error hilangkan tanda ; (titik koma) pada Home.php, seperti berikut :
![Pemrograman6](https://user-images.githubusercontent.com/73973590/173236185-b0a9f197-f801-4df4-987b-d0c35c4dd556.png)
Contoh error/kesalahan akan ditampilkan secara detail
![Pemrograman7](https://user-images.githubusercontent.com/73973590/173236200-8ff83067-cbe7-4955-8e11-61449a064454.png)


Step 7
Mengarahkan router pada controller, kemudian Membuat Route Baru Tambahkan kode berikut pada Route.php :
![Screenshot 2022-06-12 204632](https://user-images.githubusercontent.com/73973590/173236297-06f98323-522e-4938-9f36-38d638edc767.png)
Cek pada CMD dengan memasukan "php spark routes", Akses route yang telah dibuat dengan http://localhost:8080/about, hasilnya :
![Pemrograman8](https://user-images.githubusercontent.com/73973590/173236241-1fa6a9eb-5d58-48db-8b9e-a0acfcb4817f.png)
Ketika diakses akan mucul tampilan error 404 file not found, itu artinya file/page tersebut tidak ada. Untuk dapat mengakses halaman tersebut, harus dibuat terlebih dahulu Contoller yang sesuai dengan routing yang dibuat yaitu Contoller Page.
![Pemrograman9](https://user-images.githubusercontent.com/73973590/173236357-a8ca7922-5807-4063-a0cc-15e9a9f1c64d.png)

Step 8
Membuat Controller
Selanjutnya adalah membuat Controller Page. Buat file baru dengan nama page.php pada direktori Controller kemudian isi kodenya seperti berikut.
![Pemrograman10](https://user-images.githubusercontent.com/73973590/173236372-bb9d28d0-0bd2-4501-a90c-17df77295ea1.png)
Hasilnya :
![Pemrograman11](https://user-images.githubusercontent.com/73973590/173236380-a952006c-73a1-43fe-9342-e073b0f29af2.png)

Step 9
Auto Routing
Mengaktifkan AutoRouting dengan men set nilai true/false, jika true maka fungsi akan aktif
![Screenshot 2022-06-12 204919](https://user-images.githubusercontent.com/73973590/173236431-e9e1db5f-7e32-4348-a91b-d9eef5c04e26.png)
Tambahkan method baru pada Controller Page seperti berikut untuk page Term of Services
![Pemrograman13](https://user-images.githubusercontent.com/73973590/173236472-7bf1fb2b-0b9e-4f33-b896-4c2fa989b0e7.png)
Akses http://localhost:8080/page/tos hasilnya :
![Pemrograman12](https://user-images.githubusercontent.com/73973590/173236463-8967b86c-a606-495d-91c0-d13b9b36c8d9.png)


Step 10
Membuat View
Selanjutnya adalam membuat view untuk tampilan web agar lebih menarik. Buat file baru dengan nama about.php pada direktori view (app/view/about.php) kemudian isi kodenya seperti berikut.
![Screenshot 2022-06-12 205239](https://user-images.githubusercontent.com/73973590/173236557-609a472d-41e2-4b5a-a523-0b6babe2e24f.png)
ubah method about pada class Controller Page menjadi seperti berikut:
![Screenshot 2022-06-12 151344](https://user-images.githubusercontent.com/73973590/173236514-7fa225e1-951d-4bb6-b899-c996672dd482.png)
Kemudian lakukan refresh pada halaman tersebut. hasilnya
![Screenshot 2022-06-12 151403](https://user-images.githubusercontent.com/73973590/173236575-39d2cb89-4c68-4e00-8640-e4487cdcc4c7.png)

Step 11
Membuat Layout Web dengan CSS
Pada dasarnya layout web dengan css dapat diimplamentasikan dengan mudah pada codeigniter. Yang perlu diketahui adalah, pada Codeigniter 4 file yang menyimpan asset css dan javascript terletak pada direktori public.

Buat file css pada direktori public dengan nama style.css
![Screenshot 2022-06-12 151818](https://user-images.githubusercontent.com/73973590/173236606-28ab82f8-5f3e-47c6-a149-2e304ffa1124.png)
Kemudian buat folder template pada direktori view kemudian buat file header.php dan footer.php

header.php
![Screenshot 2022-06-12 152351](https://user-images.githubusercontent.com/73973590/173236619-a031ff31-ff29-4189-a82f-3d1691b09e4e.png)
footer.php
![Screenshot 2022-06-12 152413](https://user-images.githubusercontent.com/73973590/173236633-e6344848-aacb-4ccc-93b0-c63d3e9f74f3.png)
Kemudian ubah file app/view/about.php seperti berikut
![Screenshot 2022-06-12 152556](https://user-images.githubusercontent.com/73973590/173236658-80a39b03-b63a-4fb5-89ec-ecc17581c88d.png)
Selanjutnya refresh tampilan pada alamat http://localhost:8080/about
![Screenshot 2022-06-12 153057](https://user-images.githubusercontent.com/73973590/173236671-63052d88-eeb1-4af8-aadd-b8cb4813ae97.png)


Pertanyaan dan Tugas
Lengkapi kode program untuk menu lainnya yang ada pada Controller Page, sehingga semua link pada navigasi header dapat menampilkan tampilan dengan layout yang sama

Tambahkan kode berikut di dalam Routes.php
![Screenshot 2022-06-12 154653](https://user-images.githubusercontent.com/73973590/173236688-2d93d159-100e-439f-9d7b-30cf4395f2a8.png)
edit page control pada page.php
![Screenshot 2022-06-12 154707](https://user-images.githubusercontent.com/73973590/173236705-3b866d55-22a2-4e24-86f4-244880173d08.png)
Buat file artikel.php dan contact.php pada direktori app/view/
![Screenshot 2022-06-12 154707](https://user-images.githubusercontent.com/73973590/173236733-05fd1fe7-42d9-4afc-8dc1-e1697ee60294.png)
![Screenshot 2022-06-12 154723](https://user-images.githubusercontent.com/73973590/173236761-90fbdf9c-495e-4109-9168-607ce3bb1fca.png)
saat kita membuka halaman artikel dan kontak maka tampilan akan menuju page artikel,about dan kontak

artikel
![Screenshot 2022-06-12 154419](https://user-images.githubusercontent.com/73973590/173236775-650ffbef-a1ad-432b-aa49-7b3c77496c91.png)
about
![Screenshot 2022-06-12 154436](https://user-images.githubusercontent.com/73973590/173236786-689dd255-f126-4c2b-b583-5e3dfd5ce499.png)
kontak
![Screenshot 2022-06-12 154453](https://user-images.githubusercontent.com/73973590/173236816-69b7c595-ae6c-4585-9a29-2192c93bc546.png)


Praktikum 12: Framework Lanjutan (CRUD)
Membuat Database

Step 1
CREATE DATABASE lab_ci4; Membuat Tabel seperti gambar berikut
![Screenshot 2022-06-27 214302](https://user-images.githubusercontent.com/73973590/175968340-f1732731-0957-4e9b-b953-7faf92d2d1d3.png)
Step 2
Jalankan MySQL pada program XAMPP berjalan dan buat database seperti berikut :
![Screenshot 2022-06-27 214431](https://user-images.githubusercontent.com/73973590/175968605-8bec2ad6-8821-4125-9b91-656ca377747d.png)
Konfigurasi koneksi database
