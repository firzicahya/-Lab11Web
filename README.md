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
Step 3
Konfigurasi koneksi database
Mengkonfigurasi koneksi database pada file .env seperti berikut :
![Screenshot 2022-06-28 223304](https://user-images.githubusercontent.com/73973590/176220388-9877a811-97d5-4958-8d12-45be650cae97.png)
Step 4
Membuat Model
Membuat file Model pada direktori app/Models dengan nama ArtikelModel.php seperti berikut :
![Screenshot 2022-06-28 223437](https://user-images.githubusercontent.com/73973590/176220680-9e2186e9-c348-4980-89cd-4287f2075da7.png)
Step 5
Membuat Controller
Membuat file Controller baru dengan nama Artikel.php pada direktori app/Controllers. seperti berikut :
![Screenshot 2022-06-28 223610](https://user-images.githubusercontent.com/73973590/176221042-05c3f6ed-f7d1-4f80-91cd-4f367484e69c.png)
Step 6
Membuat View
Membuat file Views baru dengan nama artikel pada direktori app/views, kemudian buat filebaru dengan nama index.php, seperti berikut
![Screenshot 2022-06-28 223724](https://user-images.githubusercontent.com/73973590/176221354-3830489a-677d-4fb7-bb59-508a566de020.png)
Jalankan server dan akses link : http://localhost:8080/artikel
![Screenshot 2022-06-27 213410](https://user-images.githubusercontent.com/73973590/176221494-f0a7a070-fb49-43fc-9ddd-c8d7de094afb.png)
Step 7
Masukan data berikut pada database :
![Screenshot 2022-06-28 223917](https://user-images.githubusercontent.com/73973590/176221735-a697d3cb-f458-41d5-b095-7ba732abd3e8.png)
Refresh kembali browser, sehingga akan ditampilkan hasilnya.
![Screenshot 2022-06-27 213506](https://user-images.githubusercontent.com/73973590/176221860-1884b557-5e67-4db5-a5b5-b6a974f320fa.png)
Step 8
Membuat Tampilan Detail Artikel
Menambahkan Detail pada Artikel.php seperti berikut :
![Screenshot 2022-06-28 224249](https://user-images.githubusercontent.com/73973590/176222508-99465cf6-d3f7-43af-9d90-5565ee08a647.png)
Step 9
Membuat View Detail
Membuat file baru baru untuk halaman detail dengan nama app/views/artikel/detail.php. seperti berikut :
![Screenshot 2022-06-28 224357](https://user-images.githubusercontent.com/73973590/176222770-cce2e96c-ef57-47d9-a770-3842e5396c15.png)
Step 10
Tambahkan rute baru pada Routes.php :
![Screenshot 2022-06-28 224450](https://user-images.githubusercontent.com/73973590/176222963-ce785e88-6d54-42eb-8816-76a3f2c564ae.png)
Tampilan Artikel setelah di Klik :
![Screenshot 2022-06-27 213542](https://user-images.githubusercontent.com/73973590/176223058-411f9fc4-8cc4-43ee-8622-8c93ea0ed8de.png)
Step 11
Membuat Menu Admin
Buat method baru pada Controller Artikel dengan nama admin_index() :
![Screenshot 2022-06-28 224623](https://user-images.githubusercontent.com/73973590/176223343-99a367f5-81c1-4104-94f5-7adb42ae0b68.png)
Step 12
Buat file baru dengan nama admin_index.php pada folder artikel :
![Screenshot 2022-06-28 224722](https://user-images.githubusercontent.com/73973590/176223533-75b818da-660f-45ae-b26b-9800a0acdc71.png)
![Screenshot 2022-06-28 224800](https://user-images.githubusercontent.com/73973590/176223676-8e2b5777-833d-482e-b9a4-e36eb3c38f57.png)
Step 13
Tambahkan Routing baru pada Routes.php seperti berikut :
![Screenshot 2022-06-28 224858](https://user-images.githubusercontent.com/73973590/176223895-389a2dee-3f0d-42bf-b5b1-be63c0979acd.png)
Akses menu admin dengan url http://localhost:8080/admin/artikel :
![Screenshot 2022-06-27 213619](https://user-images.githubusercontent.com/73973590/176224028-0cd0124e-878e-4199-9237-01a0b781cc6d.png)
Step 14
Menambah Data Artikel
Tambahkan fungsi/method baru pada Controller Artikel dengan nama add() :
![Screenshot 2022-06-28 225032](https://user-images.githubusercontent.com/73973590/176224257-bc66c716-e4db-4ca5-8d7b-716dd53f29a3.png)
Step 15
Lalu buat file baru dengan nama form_add.php pada folder artikel :
![Screenshot 2022-06-28 225133](https://user-images.githubusercontent.com/73973590/176224488-c379acb9-d522-4dd8-baf2-ab5d1af5a49a.png)
tampilan saat klik artikel :
![Screenshot 2022-06-27 213651](https://user-images.githubusercontent.com/73973590/176224582-af821c64-dd4e-4b23-a56e-6ceabf386895.png)
Step 16
Mengubah Data artikel
Tambahkan fungsi/method baru pada Controller Artikel dengan nama edit() :
![Screenshot 2022-06-28 225318](https://user-images.githubusercontent.com/73973590/176224863-55b3e04a-a38d-4670-b534-49166ddb84c6.png)
Step 17
Lalu buat file baru dengan nama edit_add.php pada folder artikel :
![Screenshot 2022-06-28 225412](https://user-images.githubusercontent.com/73973590/176225093-9ad1a1bb-ebea-427e-baa1-a7c93c1c8ffd.png)
Tampilan saat mengubah artikel :
![Screenshot 2022-06-28 225457](https://user-images.githubusercontent.com/73973590/176225298-c80575ac-7343-4265-b4dc-ead925045744.png)
Step 18
Menghapus Data
Tambahkan fungsi/method baru pada Controller Artikel dengan nama delete()
![Screenshot 2022-06-28 225606](https://user-images.githubusercontent.com/73973590/176225554-8ce8d413-96a8-4e1e-8abb-1931f415a64a.png)



Praktikum 13: Framework Lanjutan (Modul Login)
Step 1
Membuat Tabel User
Membuat Tabel: User Login
![Screenshot 2022-06-28 230503](https://user-images.githubusercontent.com/73973590/176227377-6af0b50a-3900-40a5-a0a9-b2609b7ab139.png)
![Screenshot 2022-06-28 230647](https://user-images.githubusercontent.com/73973590/176227714-0fc157a2-675f-457c-b695-0b1b91a8815c.png)
Step 2
Membuat Model User
Selanjutnya adalah membuat Model untuk memproses data Login. Buat file baru pada direktori app/Models dengan nama UserModel.php
![Screenshot 2022-06-28 230752](https://user-images.githubusercontent.com/73973590/176227956-5e05f88b-25df-418e-91e0-41e70f9120a6.png)
Step 3
Membuat Controller User
Buat Controller baru dengan nama User.php pada direktori app/Controllers. kemudian tambahkan fungsi index() sebagai berikut :
![Screenshot 2022-06-28 230859](https://user-images.githubusercontent.com/73973590/176228173-d4c73cc2-43ed-4b30-a3d8-e475800d27e1.png)
![Screenshot 2022-06-28 230932](https://user-images.githubusercontent.com/73973590/176228285-636dbc47-af7d-4b6c-a3dd-a6028130c18d.png)
Step 4
Membuat View Login
Buat direktori baru dengan nama user pada direktori app/views, kemudian buat file baru dengan nama login.php. Dengan kode berikut
![Screenshot 2022-06-28 231031](https://user-images.githubusercontent.com/73973590/176228474-ce399a6d-262c-4db8-92db-387c3129b2c8.png)
Step 5
Membuat Database Seeder
Buka CLI dan masukan kode "php spark make:seeder UserSeeder", Hasilnya :
![Screenshot 2022-06-28 231426](https://user-images.githubusercontent.com/73973590/176229249-f3248d05-99ff-4528-a989-6a21d354cf6e.png)
Lalu buka file UserSeeder.php yang berada di lokasi direktori /app/Database/Seeds/UserSeeder.php kemudian isi dengan kode berikut
![Screenshot 2022-06-28 231518](https://user-images.githubusercontent.com/73973590/176229419-fbf8e059-c373-480d-8b4b-5d3cdae7e3c1.png)
Selanjutnya buka kembali CLI dan ketik perintah "php spark db:seed UserSeeder" , Hasilnya :
![Screenshot 2022-06-28 231617](https://user-images.githubusercontent.com/73973590/176229622-48bf0b3d-300c-45d5-897f-64bad88795c3.png)
Selanjutnya buka url http://localhost:8080/user/login seperti berikut Hasilnya


Step 6
Menambahkan Auth Filter
Selanjutnya membuat filer untuk halaman admin. Buat file baru dengan nama Auth.php pada direktori app/Filters. berikut :
![Screenshot 2022-06-28 231728](https://user-images.githubusercontent.com/73973590/176229885-18638126-79a5-486e-9ce5-380357c99d9c.png)
Selanjutnya buka file app/Config/Filters.php tambahkan kode berikut:
![Screenshot 2022-06-28 231811](https://user-images.githubusercontent.com/73973590/176230041-70115ca8-979a-458f-91d6-5d451267e384.png)
Selanjutnya buka file app/Config/Routes.php dan sesuaikan kode berikut :
![Screenshot 2022-06-28 231908](https://user-images.githubusercontent.com/73973590/176230207-a0f90801-0700-41fe-acbf-f5b25042db51.png)
Step 7
Percobaan Akses Menu Admin
Percobaan menu akses LOGIN

Buka url dengan alamat http://localhost:8080/admin/artikel ketika alamat tersebut diakses maka akan ditarik ke halaman login berikut :

Step 8
Membuat Fungsi LOGOUT
![Screenshot 2022-06-28 232050](https://user-images.githubusercontent.com/73973590/176230555-101fa98a-bf5f-4d7d-91ca-29ff85c83b42.png)


Tambahkan method logout pada Controller User seperti berikut :





