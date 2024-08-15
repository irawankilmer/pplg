### **Materi DML Lanjutan: Memahami `JOIN` dalam SQL**

#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Memahami konsep dasar `JOIN` dalam SQL.
- Menggunakan berbagai jenis `JOIN` (`INNER JOIN`, `LEFT JOIN`, `RIGHT JOIN`, dan `FULL JOIN`) untuk menggabungkan data dari beberapa tabel.
- Memahami kapan dan bagaimana menggunakan setiap jenis `JOIN` dalam skenario nyata.

#### **Materi Lengkap:**

1. **Pengertian `JOIN` dalam SQL:**
   - **Apa itu `JOIN`?**
     - `JOIN` adalah perintah SQL yang digunakan untuk menggabungkan baris dari dua atau lebih tabel berdasarkan kondisi terkait antar kolom. `JOIN` memungkinkan kalian untuk menghubungkan data yang tersebar di beberapa tabel, sehingga kalian bisa melihat informasi yang saling berkaitan dalam satu hasil query.

   - **Mengapa `JOIN` Penting?**
     - Dalam basis data relasional, data seringkali dibagi ke dalam tabel-tabel yang berbeda untuk menghindari redundansi dan menjaga integritas. `JOIN` memungkinkan kalian untuk menggabungkan data dari tabel-tabel tersebut agar bisa dianalisis bersama-sama. Misalnya, menghubungkan data siswa dengan data kelas untuk melihat nama siswa bersama dengan nama kelas mereka.

2. **Jenis-jenis `JOIN`:**

   - **`INNER JOIN`:**
     - **Pengertian:**
       - `INNER JOIN` mengembalikan hanya baris-baris yang memiliki pasangan di kedua tabel. Jika ada baris di salah satu tabel yang tidak memiliki pasangan di tabel lain, baris tersebut tidak akan ditampilkan dalam hasil.
     - **Contoh:**
       - Gabungkan tabel `Siswa` dengan tabel `Kelas` untuk menampilkan nama siswa dan nama kelasnya:
       ```sql
       SELECT Siswa.Nama, Kelas.Nama_Kelas
       FROM Siswa
       INNER JOIN Kelas ON Siswa.Kode_Kelas = Kelas.Kode_Kelas;
       ```
     - **Kapan Menggunakan `INNER JOIN`:**
       - Gunakan `INNER JOIN` ketika kalian hanya ingin menampilkan data yang memiliki pasangan di kedua tabel.

   - **`LEFT JOIN` (atau `LEFT OUTER JOIN`):**
     - **Pengertian:**
       - `LEFT JOIN` mengembalikan semua baris dari tabel kiri (tabel pertama yang disebutkan), dan baris yang cocok dari tabel kanan. Jika tidak ada pasangan yang cocok di tabel kanan, maka kolom-kolom dari tabel kanan akan berisi `NULL`.
     - **Contoh:**
       - Gabungkan tabel `Siswa` dengan tabel `Kelas`, termasuk siswa yang belum terdaftar di kelas mana pun:
       ```sql
       SELECT Siswa.Nama, Kelas.Nama_Kelas
       FROM Siswa
       LEFT JOIN Kelas ON Siswa.Kode_Kelas = Kelas.Kode_Kelas;
       ```
     - **Kapan Menggunakan `LEFT JOIN`:**
       - Gunakan `LEFT JOIN` ketika kalian ingin menampilkan semua data dari tabel kiri, bahkan jika tidak ada pasangan yang cocok di tabel kanan.

   - **`RIGHT JOIN` (atau `RIGHT OUTER JOIN`):**
     - **Pengertian:**
       - `RIGHT JOIN` adalah kebalikan dari `LEFT JOIN`; ia mengembalikan semua baris dari tabel kanan, dan baris yang cocok dari tabel kiri. Jika tidak ada pasangan yang cocok di tabel kiri, kolom-kolom dari tabel kiri akan berisi `NULL`.
     - **Contoh:**
       - Gabungkan tabel `Kelas` dengan tabel `Siswa`, termasuk kelas yang belum memiliki siswa:
       ```sql
       SELECT Siswa.Nama, Kelas.Nama_Kelas
       FROM Siswa
       RIGHT JOIN Kelas ON Siswa.Kode_Kelas = Kelas.Kode_Kelas;
       ```
     - **Kapan Menggunakan `RIGHT JOIN`:**
       - Gunakan `RIGHT JOIN` ketika kalian ingin menampilkan semua data dari tabel kanan, bahkan jika tidak ada pasangan yang cocok di tabel kiri.

   - **`FULL JOIN` (atau `FULL OUTER JOIN`):**
     - **Pengertian:**
       - `FULL JOIN` mengembalikan semua baris dari kedua tabel. Jika tidak ada pasangan yang cocok, maka kolom-kolom yang tidak memiliki pasangan akan berisi `NULL`.
     - **Contoh:**
       - Gabungkan tabel `Siswa` dengan tabel `Kelas`, menampilkan semua siswa dan semua kelas, termasuk yang tidak memiliki pasangan:
       ```sql
       SELECT Siswa.Nama, Kelas.Nama_Kelas
       FROM Siswa
       FULL JOIN Kelas ON Siswa.Kode_Kelas = Kelas.Kode_Kelas;
       ```
     - **Kapan Menggunakan `FULL JOIN`:**
       - Gunakan `FULL JOIN` ketika kalian ingin menampilkan semua data dari kedua tabel, terlepas dari apakah ada pasangan yang cocok atau tidak.

   - **`SELF JOIN`:**
     - **Pengertian:**
       - `SELF JOIN` adalah `JOIN` dari tabel itu sendiri. Ini berguna ketika kalian ingin membandingkan baris dalam tabel yang sama.
     - **Contoh:**
       - Misalkan kalian ingin mencari pasangan siswa yang ada di kelas yang sama:
       ```sql
       SELECT A.Nama AS Siswa1, B.Nama AS Siswa2
       FROM Siswa A, Siswa B
       WHERE A.Kode_Kelas = B.Kode_Kelas AND A.NIS < B.NIS;
       ```
     - **Kapan Menggunakan `SELF JOIN`:**
       - Gunakan `SELF JOIN` ketika kalian perlu membandingkan baris di dalam tabel yang sama.

3. **Praktikum Lengkap untuk `JOIN`:**

   - **Latihan 1: Menggunakan `INNER JOIN` untuk Menggabungkan Data**
     - Gabungkan tabel `Siswa` dengan tabel `Kelas` untuk menampilkan nama siswa beserta nama kelasnya.

     **SQL Query:**
     ```sql
     SELECT Siswa.Nama, Kelas.Nama_Kelas
     FROM Siswa
     INNER JOIN Kelas ON Siswa.Kode_Kelas = Kelas.Kode_Kelas;
     ```

   - **Latihan 2: Menggunakan `LEFT JOIN` untuk Menampilkan Data yang Tidak Cocok**
     - Tampilkan semua siswa, termasuk yang belum terdaftar di kelas mana pun.

     **SQL Query:**
     ```sql
     SELECT Siswa.Nama, Kelas.Nama_Kelas
     FROM Siswa
     LEFT JOIN Kelas ON Siswa.Kode_Kelas = Kelas.Kode_Kelas;
     ```

   - **Latihan 3: Menggunakan `RIGHT JOIN` untuk Menampilkan Data dari Tabel Kanan**
     - Tampilkan semua kelas, termasuk kelas yang belum memiliki siswa.

     **SQL Query:**
     ```sql
     SELECT Siswa.Nama, Kelas.Nama_Kelas
     FROM Siswa
     RIGHT JOIN Kelas ON Siswa.Kode_Kelas = Kelas.Kode_Kelas;
     ```

   - **Latihan 4: Menggunakan `FULL JOIN` untuk Menampilkan Semua Data**
     - Tampilkan semua siswa dan semua kelas, termasuk yang tidak memiliki pasangan.

     **SQL Query:**
     ```sql
     SELECT Siswa.Nama, Kelas.Nama_Kelas
     FROM Siswa
     FULL JOIN Kelas ON Siswa.Kode_Kelas = Kelas.Kode_Kelas;
     ```

   - **Latihan 5: Menggunakan `SELF JOIN` untuk Membandingkan Data dalam Tabel yang Sama**
     - Cari pasangan siswa yang berada di kelas yang sama.

     **SQL Query:**
     ```sql
     SELECT A.Nama AS Siswa1, B.Nama AS Siswa2
     FROM Siswa A, Siswa B
     WHERE A.Kode_Kelas = B.Kode_Kelas AND A.NIS < B.NIS;
     ```

#### **Diskusi dan Review:**

- **Mengapa `JOIN` Penting?**
  - **Diskusi:** `JOIN` adalah salah satu konsep paling penting dalam SQL karena memungkinkan penggabungan data dari beberapa tabel menjadi satu hasil query. Ini sangat penting dalam aplikasi di mana data terdistribusi di berbagai tabel untuk menghindari redundansi.
  
- **Kapan Menggunakan Setiap Jenis `JOIN`?**
  - **Diskusi:** Setiap jenis `JOIN` memiliki skenario penggunaannya sendiri. Misalnya, gunakan `INNER JOIN` ketika kalian hanya membutuhkan data yang memiliki pasangan di kedua tabel, dan gunakan `LEFT JOIN` ketika kalian ingin menampilkan semua data dari tabel kiri, meskipun tidak ada pasangan di tabel kanan.

---
[⏮ DML](../5-dml/README.md) || [Home 🏘](../README.md) || [DCL ⏭](../6-dcl/README.md)