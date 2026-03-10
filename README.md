# Deskripsi Website

Website ini memiliki **dua jenis role akses**, yaitu:

- **Viewer**, yang hanya dapat melihat data.
- **Admin**, yang dapat mengakses dan mengelola seluruh fitur dalam sistem.

Terdapat **9 jenis data/file Excel** yang akan dimasukkan ke dalam website, dan daftar file tersebut dapat dilihat pada bagian **Manajemen Data**.

Sistem juga menyediakan **template Excel** yang wajib digunakan saat mengunggah file, agar format data sesuai dengan struktur database dan dapat diproses tanpa kendala.

**Primary key** pada data menggunakan **NIK karyawan**, karena **ID karyawan berubah setiap 1 tahun sekali**.

Setiap file Excel yang diunggah diperkirakan dapat berisi **lebih dari 15.000 data karyawan**.

Untuk alasan keamanan dan privasi, **NIK tidak boleh ditampilkan pada frontend**.

Khusus untuk **file Excel tenaga kerja (TK)** yang diunggah per kuartal, sistem harus dapat melakukan **perbandingan data antar kuartal** untuk mengetahui tenaga kerja yang masih aktif dan yang sudah tidak ada di perusahaan.

Contoh:
- Pada **Q1 2025**, file yang diunggah berisi **15.000 data tenaga kerja**.
- Pada **Q2 2025**, file yang diunggah berisi **14.000 data tenaga kerja**.

Maka data pada **Q1 2025** akan digunakan sebagai pembanding terhadap data **Q2 2025**, dengan fokus utama pada data terbaru. Jika ada karyawan yang terdapat pada **Q1** namun sudah tidak ada pada **Q2**, maka data tersebut **tidak ditampilkan**. Sebaliknya, jika ada tenaga kerja yang **tidak ada di Q1 tetapi muncul di Q2**, maka data tersebut **tetap ditampilkan**.

---

# Istilah yang Digunakan

Berikut beberapa istilah yang digunakan dalam sistem:

- **PG** = *Plantation Group*  
  Terdiri dari: **PG1, PG2, PG3, dan PG4**
- **HKO** = *Hari Kerja*
- **Berita Acara** = izin atau kendala absensi
- **Pelanggaran** = tindakan yang melanggar aturan contohnya tidak masuk kerja tanpa keterangan

Dalam 1 tahun terdapat **4 kuartal**, dengan rincian:

- **Q1** = Januari, Februari, Maret
- **Q2** = April, Mei, Juni
- **Q3** = Juli, Agustus, September
- **Q4** = Oktober, November, Desember

Setiap **1 kuartal terdiri dari 3 bulan**.

---

# Halaman Website

## 1. Halaman Login

Halaman ini ditampilkan sebelum pengguna dapat mengakses dashboard. Jika pengguna berhasil login, maka pengguna akan diizinkan masuk ke halaman dashboard.

## 2. Halaman Dashboard (Utama)

Saat pengguna mengetikkan domain website, sistem akan mengarahkan ke halaman ini. Namun, jika pengguna belum login, maka pengguna akan diarahkan terlebih dahulu ke halaman login.

Pada halaman ini terdapat **4 grafik batang**, yang masing-masing menampilkan data **HKO, berita acara, dan pelanggaran per kuartal**. Data tersebut berasal dari file Excel yang diunggah setiap **3 bulan sekali** melalui halaman **Kelola Data Rekap Raport TK**.

Grafik disajikan **per kuartal** pada masing-masing **PG**, dengan pembagian warna sebagai berikut:

- **Hijau** untuk HKO
- **Kuning** untuk berita acara
- **Merah** untuk pelanggaran

Pengguna juga dapat melakukan **filter berdasarkan bulan dan tahun** untuk melihat grafik batang sesuai kebutuhan.

Selain grafik, pada halaman ini juga terdapat ringkasan jumlah atau persentase **HKO, berita acara, dan pelanggaran** berdasarkan filter yang dipilih. Dengan demikian, total terdapat **4 grafik** pada halaman dashboard utama.

## 3. Halaman Profil User

Halaman ini akan muncul ketika pengguna mengklik ikon akun di pojok kanan atas, lalu memilih menu **Pengaturan Akun**.

Halaman ini menampilkan detail akun yang sedang digunakan. Pengguna dapat mengubah beberapa data akun, seperti:

- email
- nama
- jenis kelamin
- password

Terdapat tombol **Simpan** dan **Kembali**.

Jika tidak ada perubahan data, maka tombol **Simpan** berada dalam keadaan **nonaktif (disabled)**. Jika ada data yang diubah, maka tombol **Simpan** akan menjadi **aktif (enabled)** dan dapat digunakan untuk menyimpan perubahan.

## 4. Halaman Overtime / Lembur

Halaman ini menampilkan data dalam bentuk grafik yang berasal dari file Excel yang diunggah melalui halaman **Kelola Data Overtime**.

Selain grafik, pengguna juga dapat melihat data dalam bentuk **tabel**. Pada setiap baris data terdapat tombol **Edit** dan **Hapus** di bagian kanan.

Halaman ini juga menyediakan filter berdasarkan:

- bulanan
- kuartalan
- tahunan

Data yang ditampilkan akan menyesuaikan dengan filter yang digunakan.

## 5. Halaman TK Overtime

Halaman ini menampilkan data dari file Excel yang diunggah melalui halaman **Kelola Data Overtime**.

Data ditampilkan dalam bentuk **tabel**, dan pada setiap baris terdapat tombol **Edit** dan **Hapus** di bagian kanan.

Selain itu, tersedia juga filter berdasarkan:

- bulanan
- kuartalan
- tahunan

Data yang tampil akan mengikuti filter yang dipilih pengguna.

## 6. Halaman Raport Bulanan TK

Halaman ini menampilkan data yang berasal dari:

- Kelola Data HKO
- Kelola Data Berita Acara
- Kelola Data Pelanggaran

Data disajikan dalam bentuk **grafik garis** berdasarkan file Excel yang diunggah setiap bulan, dan ditampilkan **per bulan**.

Halaman ini menyediakan filter berdasarkan:

- tahun
- jenis rekap, seperti:
  - HKO
  - berita acara
  - pelanggaran

---

# Dropdown: Daftar PG

## 7. Halaman PG1–PG4

Halaman ini menampilkan data dari file yang diunggah melalui halaman **Kelola Data HKO, Berita Acara, dan Pelanggaran** dalam bentuk **grafik garis**.

Pada halaman ini terdapat **3 grafik**. Di atas grafik terdapat **3 section box** yang menampilkan persentase dari:

- HKO
- berita acara
- pelanggaran

## 8. Halaman TK PG1–PG4

Halaman ini menampilkan data dari file yang diunggah melalui halaman **Kelola Data TK PG1–PG4** dalam bentuk **tabel daftar tenaga kerja**.

Contohnya, jika file Excel yang diunggah adalah **file TK PG1**, maka data tersebut akan muncul di halaman ini.

Data yang ditampilkan hanya meliputi beberapa kolom berikut:

- Pers. No
- Nama
- Group Directorate Text
- Directorate Text
- Division Text
- Sub Division Text
- Department Text
- Sub Department Text
- Bagian Text
- Section Text

Pada setiap baris data terdapat tombol:

- **Detail**, untuk melihat detail tenaga kerja
- **Hapus**, untuk menghapus data karyawan

Jumlah data yang ditampilkan secara default adalah **50 orang**, dan dapat ditambah menjadi:

- 100
- 150
- 200

---

## 9. Halaman Detail Raport TK

Halaman ini akan tampil ketika pengguna mengklik tombol **Detail** pada halaman **TK PG1–PG4**.

Halaman ini menampilkan detail data tenaga kerja sesuai dengan **PG** yang sedang dipilih. Pada data ini, ada beberapa kolom yang dapat kosong karena memang terdapat data yang sejak awal tidak terisi, dan hal tersebut tidak menjadi masalah.

Pada halaman ini terdapat 3 tombol, yaitu:

- **Kembali**, untuk kembali ke halaman sebelumnya
- **Hapus**, untuk menghapus data tenaga kerja yang sedang dilihat
- **Download**, untuk mengunduh data tenaga kerja tersebut dalam format **PDF**

## 10. Halaman Detail Raport TK Rekap

Halaman ini menampilkan data dari file yang diunggah melalui halaman **Rekap Raport TK**.

Data tenaga kerja yang ditampilkan meliputi:

- No. Pers / ID karyawan
- Full Name
- Department
- Sub Department
- Mandor
- HKO per kuartal
- Berita acara per kuartal
- Pelanggaran per kuartal

Di bagian atas halaman terdapat fitur:

- **checkbox filter kuartal**, misalnya jika pengguna hanya mencentang **Q1**, maka yang ditampilkan hanya data **Q1** untuk HKO, berita acara, dan pelanggaran
- **dropdown filter PG / Plantation Group**

Selain itu, terdapat filter raport dengan 3 warna indikator, yaitu:

- hijau
- kuning
- merah

---

# Dropdown: Manajemen Data

## 11. Kelola Data TK PG1

Halaman ini memiliki satu grid di bagian tengah yang berisi pemberitahuan kepada pengguna untuk mengunduh template yang telah disediakan, agar database dapat memproses file tanpa masalah.

Selain itu, tersedia fitur untuk mengunggah file Excel data tenaga kerja ke website berdasarkan:

- kuartal yang dipilih
- tahun yang dipilih

Pilihan kuartal yang tersedia hanya:

- Kuartal 1
- Kuartal 2
- Kuartal 3
- Kuartal 4

Terdapat juga bagian **riwayat file upload** yang menampilkan informasi berikut:

- nama file
- format file
- tanggal dan jam upload
- nama akun pengguna yang mengunggah file

Pengguna juga dapat:

- menghapus file yang telah diunggah
- mengunduh kembali file yang telah diunggah selama file tersebut belum dihapus

Jika sebuah file dihapus, maka:

- seluruh data yang berasal dari file tersebut akan ikut terhapus
- seluruh data hasil edit yang berasal dari file tersebut juga akan ikut hilang

Data dari halaman ini akan ditampilkan pada halaman **PG1**.

## 12. Kelola Data TK PG2

Fungsinya sama seperti halaman **Kelola Data TK PG1**, namun data yang diunggah dan dikelola akan ditampilkan pada halaman **PG2**.

## 13. Kelola Data TK PG3

Fungsinya sama seperti halaman **Kelola Data TK PG1**, namun data yang diunggah dan dikelola akan ditampilkan pada halaman **PG3**.

## 14. Kelola Data TK PG4

Fungsinya sama seperti halaman **Kelola Data TK PG1**, namun data yang diunggah dan dikelola akan ditampilkan pada halaman **PG4**.

## 15. Kelola Data HKO

Halaman ini memiliki satu grid di bagian tengah yang berisi pemberitahuan untuk mengunduh template yang telah ditentukan agar database dapat memproses data tanpa kendala.

Tersedia fitur upload file Excel berdasarkan:

- bulan yang dipilih
- tahun yang dipilih

Pilihan bulan tersedia dari **bulan 1 sampai bulan 12**.

Halaman ini juga memiliki **riwayat file upload** yang menampilkan:

- nama file
- format file
- tanggal dan jam upload
- nama akun pengguna yang mengunggah file

Pengguna dapat menghapus file yang telah diunggah. Jika file dihapus, maka seluruh data yang berasal dari file tersebut, termasuk data yang telah diedit, juga akan ikut terhapus.

File yang belum dihapus masih dapat diunduh kembali.

Data dari halaman ini akan ditampilkan pada halaman **Rekap Raport Bulanan TK**.

## 16. Kelola Data Berita Acara

Struktur dan fungsi halaman ini sama seperti **Kelola Data HKO**, namun data yang dikelola adalah data **berita acara**. Data dari halaman ini akan ditampilkan pada halaman **Rekap Raport Bulanan TK**.

## 17. Kelola Data Pelanggaran

Struktur dan fungsi halaman ini sama seperti **Kelola Data HKO**, namun data yang dikelola adalah data **pelanggaran**. Data dari halaman ini akan ditampilkan pada halaman **Rekap Raport Bulanan TK**.

## 18. Kelola Data Rekap Raport TK

Halaman ini memiliki satu grid di bagian tengah yang berisi pemberitahuan kepada pengguna untuk mengunduh template yang telah ditentukan agar database dapat memproses data tanpa masalah.

Tersedia fitur untuk mengunggah file Excel berdasarkan:

- bulan yang dipilih
- tahun yang dipilih

Pilihan bulan tersedia dari **bulan 1 sampai bulan 12**.

Halaman ini juga menyediakan **riwayat file upload** yang menampilkan:

- nama file
- format file
- tanggal dan jam upload
- nama akun pengguna yang mengunggah file

Jika file dihapus, maka seluruh data yang berasal dari file tersebut akan ikut terhapus, termasuk data yang sebelumnya telah diedit.

File yang belum dihapus tetap dapat diunduh kembali.

Data dari halaman ini akan ditampilkan pada halaman **Dashboard (Utama)**.

## 19. Kelola Data Overtime

Halaman ini memiliki satu grid di bagian tengah yang menampilkan pemberitahuan kepada pengguna untuk mengunduh template yang telah ditentukan agar database dapat memproses data tanpa kendala.

Tersedia fitur upload file Excel berdasarkan:

- bulan yang dipilih
- tahun yang dipilih

Pilihan bulan tersedia dari **bulan 1 sampai bulan 12**.

Selain itu, terdapat **riwayat file upload** yang menampilkan:

- nama file
- format file
- tanggal dan jam upload
- nama akun pengguna yang mengunggah file

Jika file yang telah diunggah dihapus, maka seluruh data yang berasal dari file tersebut, termasuk data hasil edit, juga akan ikut terhapus.

File yang belum dihapus masih dapat diunduh kembali.

Data dari halaman ini akan ditampilkan pada halaman **Overtime**.
