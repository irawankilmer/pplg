# **Bab 5 - Data Manipulation Language (DML)**
#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Menggunakan DML untuk menambah, mengubah, menghapus, dan menampilkan data dalam basis data.
- Memahami penggunaan operator logika (`AND`, `OR`, `NOT`), pencarian pola (`LIKE`), dan pengurutan data (`ORDER BY`).
- Melakukan manipulasi data dengan kondisi kompleks menggunakan `IN`, `BETWEEN`, dan subqueries (`SUBQUERIES`).

#### **Materi Lengkap:**

1. **Pengertian Data Manipulation Language (DML):**
   - **Apa itu DML?**
     - Data Manipulation Language (DML) adalah bagian dari SQL yang digunakan untuk memanipulasi data dalam tabel basis data. DML memungkinkan kalian untuk melakukan operasi seperti menambah, memperbarui, menghapus, dan menampilkan data. Perintah DML sering digunakan dalam aplikasi yang memerlukan interaksi dinamis dengan basis data, seperti sistem manajemen informasi, e-commerce, dan aplikasi berbasis web lainnya.

   - **Fungsi Utama DML:**
     - **INSERT**: Menambahkan baris data baru ke dalam tabel.
     - **UPDATE**: Mengubah data yang sudah ada dalam tabel.
     - **DELETE**: Menghapus data dari tabel.
     - **SELECT**: Mengambil dan menampilkan data dari tabel.

   - **Mengapa DML Penting?**
     - DML merupakan dasar dari interaksi sehari-hari dengan basis data. Tanpa DML, kita tidak bisa memanipulasi data dalam basis data secara efisien. Operasi seperti menambah pelanggan baru ke dalam sistem, memperbarui informasi produk, atau menghapus data yang sudah tidak relevan adalah semua contoh penggunaan DML.

2. **Perintah Dasar DML:**

   - **INSERT: Menambah Data ke dalam Tabel**
     - **Menggunakan INSERT untuk Menambahkan Baris Baru:**
       - Perintah `INSERT` digunakan untuk menambahkan satu atau lebih baris data ke dalam tabel.
       ```sql
       INSERT INTO Siswa (NIS, Nama, Kelas, Tahun_Masuk)
       VALUES (12345, 'Ahmad Zaky', 'XI-RPL1', 2023);
       ```
       - **Detail Perintah:**
         - `Siswa`: Nama tabel tempat data akan ditambahkan.
         - `NIS, Nama, Kelas, Tahun_Masuk`: Kolom-kolom dalam tabel di mana data baru akan dimasukkan.
         - `VALUES`: Menyediakan nilai-nilai yang akan dimasukkan ke dalam kolom yang disebutkan.

     - **Menambahkan Beberapa Baris Sekaligus:**
       - Kalian juga bisa menambahkan beberapa baris data sekaligus dengan satu perintah `INSERT`.
       ```sql
       INSERT INTO Siswa (NIS, Nama, Kelas, Tahun_Masuk)
       VALUES 
       (12346, 'Suci Aulia Agniani', 'XI-RPL1', 2023),
       (12347, 'Amanda', 'XI-RPL2', 2023);
       ```

   - **UPDATE: Mengubah Data yang Ada**
     - **Menggunakan UPDATE untuk Memperbarui Data:**
       - Perintah `UPDATE` digunakan untuk mengubah data dalam tabel. Kalian bisa memperbarui satu atau lebih kolom dalam satu atau lebih baris data.
       ```sql
       UPDATE Siswa
       SET Nama = 'Ahmad Zaky Alfarizi', Kelas = 'XI-RPL2'
       WHERE NIS = 12345;
       ```
       - **Detail Perintah:**
         - `SET`: Menentukan kolom mana yang akan diubah dan nilai baru apa yang akan diberikan.
         - `WHERE`: Menentukan kondisi untuk memilih baris yang akan diubah. Jika `WHERE` tidak disertakan, semua baris dalam tabel akan diperbarui.

   - **DELETE: Menghapus Data dari Tabel**
     - **Menggunakan DELETE untuk Menghapus Baris:**
       - Perintah `DELETE` digunakan untuk menghapus satu atau lebih baris data dari tabel.
       ```sql
       DELETE FROM Siswa
       WHERE NIS = 12345;
       ```
       - **Detail Perintah:**
         - `FROM`: Menentukan tabel mana yang akan dihapus datanya.
         - `WHERE`: Menentukan kondisi untuk memilih baris yang akan dihapus. Jika `WHERE` tidak disertakan, semua baris dalam tabel akan dihapus.

   - **SELECT: Menampilkan Data dari Tabel**
     - **Menggunakan SELECT untuk Mengambil Data:**
       - Perintah `SELECT` digunakan untuk mengambil data dari satu atau lebih tabel dan menampilkannya.
       ```sql
       SELECT * FROM Siswa;
       ```
       - **Detail Perintah:**
         - `*`: Mengambil semua kolom dari tabel. Kalian juga bisa menentukan kolom spesifik untuk diambil.
         - `FROM`: Menentukan tabel mana yang akan diambil datanya.

3. **Operator Logika dalam DML:**

   - **AND, OR, NOT:**
     - Operator logika digunakan untuk membuat kondisi `WHERE` yang lebih kompleks.
     - **AND**: Menggabungkan dua atau lebih kondisi, di mana semua kondisi harus benar.
       ```sql
       SELECT * FROM Siswa
       WHERE Kelas = 'XI-RPL1' AND Tahun_Masuk = 2023;
       ```
     - **OR**: Menggabungkan dua atau lebih kondisi, di mana salah satu kondisi harus benar.
       ```sql
       SELECT * FROM Siswa
       WHERE Kelas = 'XI-RPL1' OR Kelas = 'XI-RPL2';
       ```
     - **NOT**: Digunakan untuk menegasikan kondisi.
       ```sql
       SELECT * FROM Siswa
       WHERE NOT Kelas = 'XI-RPL1';
       ```

4. **Penggunaan `LIKE` dalam DML:**

   - **LIKE untuk Pencarian Pola:**
     - Operator `LIKE` digunakan untuk mencari pola dalam teks. Biasanya digunakan dengan karakter `%` untuk mencocokkan bagian dari string.
     - **Contoh:**
       - Mencari semua siswa yang namanya dimulai dengan 'A':
       ```sql
       SELECT * FROM Siswa
       WHERE Nama LIKE 'A%';
       ```
       - Mencari semua siswa yang namanya berisi 'art':
       ```sql
       SELECT * FROM Siswa
       WHERE Nama LIKE '%art%';
       ```

5. **Pengurutan Data dengan `ORDER BY`:**

   - **ORDER BY untuk Mengurutkan Hasil:**
     - Perintah `ORDER BY` digunakan untuk mengurutkan hasil query berdasarkan satu atau lebih kolom dalam urutan menaik (`ASC`) atau menurun (`DESC`).
     - **Contoh:**
       - Mengurutkan siswa berdasarkan `Nama` dalam urutan abjad:
       ```sql
       SELECT * FROM Siswa
       ORDER BY Nama ASC;
       ```
       - Mengurutkan siswa berdasarkan `Tahun_Masuk` dari yang terbaru:
       ```sql
       SELECT * FROM Siswa
       ORDER BY Tahun_Masuk DESC;
       ```

6. **Penggunaan `IN` dan `BETWEEN`:**

   - **IN untuk Kondisi dalam Daftar:**
     - Operator `IN` digunakan untuk memeriksa apakah nilai dalam kolom sesuai dengan salah satu nilai dalam daftar.
     - **Contoh:**
       - Mencari siswa yang berada di kelas `XI-RPL1` atau `XI-RPL2`:
       ```sql
       SELECT * FROM Siswa
       WHERE Kelas IN ('XI-RPL1', 'XI-RPL2');
       ```

   - **BETWEEN untuk Rentang Nilai:**
     - Operator `BETWEEN` digunakan untuk memilih nilai dalam rentang tertentu.
     - **Contoh:**
       - Mencari siswa yang masuk antara tahun 2020 dan 2023:
       ```sql
       SELECT * FROM Siswa
       WHERE Tahun_Masuk BETWEEN 2020 AND 2023;
       ```

7. **Penggunaan Subqueries (`SUBQUERIES`):**

   - **Apa itu Subqueries?**
     - Subqueries adalah query di dalam query lain. Mereka digunakan untuk melakukan operasi kompleks, seperti mengambil data dari satu tabel berdasarkan hasil dari query lain.
     - **Contoh:**
       - Mencari siswa yang berada di kelas yang memiliki lebih dari 10 siswa:
       ```sql
       SELECT Nama FROM Siswa
       WHERE Kode_Kelas IN (
           SELECT Kode_Kelas FROM Siswa
           GROUP BY Kode_Kelas
           HAVING COUNT(*) > 10
       );
       ```
     - Dalam contoh ini, subquery pertama kali menghitung jumlah siswa di setiap kelas, dan kemudian query utama menggunakan hasil ini untuk mencari siswa yang berada di kelas yang memiliki lebih dari 10 siswa.

#### **Praktikum Lengkap:**

1. **Latihan 1: Menambah Data ke Tabel**
   - Tambahkan data baru ke dalam tabel `Siswa` dengan beberapa baris siswa baru. Gunakan perintah `INSERT` dan tambahkan minimal 3 siswa.

   **SQL Query:**
```sql
   INSERT INTO Siswa (NIS, Nama, Kelas, Tahun_Masuk)
   VALUES 
   (12346, 'Suci Aulia Agniani', 'XI-RPL1', 2023),
   (12347, 'Amanda', 'XI-RPL2', 2023),
   (12348, 'Lisnawati', 'XI-IPA3', 2023);
```

- **Penjelasan:**
  - Latihan ini melibatkan penambahan beberapa baris data ke dalam tabel `Siswa`. Tujuannya adalah agar kalian terbiasa dengan perintah `INSERT` dan memahami bagaimana data ditambahkan ke dalam basis data dengan beberapa baris sekaligus.

2. **Latihan 2: Memperbarui Data yang Ada**
   - Ubah data siswa dengan NIS 12346, misalnya mengubah `Kelas` dari 'XI-RPL1' menjadi 'XI-RPL2'.

   **SQL Query:**
   ```sql
   UPDATE Siswa
   SET Kelas = 'XI-RPL2'
   WHERE NIS = 12346;
   ```

- **Penjelasan:**
  - Dalam latihan ini, kalian akan belajar bagaimana menggunakan perintah `UPDATE` untuk memperbarui data yang sudah ada. Perintah ini sangat berguna ketika kalian perlu mengoreksi data atau memindahkan data dari satu kategori ke kategori lainnya dalam tabel.

3. **Latihan 3: Menghapus Data dari Tabel**
   - Hapus data siswa dengan NIS 12347 dari tabel `Siswa`.

   **SQL Query:**
   ```sql
   DELETE FROM Siswa
   WHERE NIS = 12347;
   ```

- **Penjelasan:**
  - Latihan ini akan mengajarkan kalian bagaimana menghapus data dari tabel. Perintah `DELETE` sangat penting ketika kalian perlu menghapus data yang tidak lagi diperlukan atau ketika ada kesalahan yang perlu diperbaiki.

4. **Latihan 4: Menggunakan Operator Logika dan `LIKE`**
   - Temukan semua siswa yang berada di kelas 'XI-RPL2' dan yang namanya dimulai dengan 'D'.

   **SQL Query:**
   ```sql
   SELECT * FROM Siswa
   WHERE Kelas = 'XI-RPL2' AND Nama LIKE 'D%';
   ```

- **Penjelasan:**
  - Dalam latihan ini, kalian akan menggunakan operator logika `AND` dan operator `LIKE` untuk mencari data yang memenuhi beberapa kriteria. Ini membantu mempersempit hasil pencarian dan menemukan data yang lebih spesifik.

5. **Latihan 5: Mengurutkan Data dengan `ORDER BY`**
   - Urutkan siswa berdasarkan `Nama` secara alfabetis dalam urutan menaik.

   **SQL Query:**
   ```sql
   SELECT * FROM Siswa
   ORDER BY Nama ASC;
   ```

- **Penjelasan:**
  - Latihan ini mengajarkan cara mengurutkan hasil query menggunakan `ORDER BY`. Ini sangat berguna ketika kalian perlu menampilkan data dalam urutan tertentu, misalnya alfabetis atau berdasarkan nilai numerik.

6. **Latihan 6: Menggunakan `IN` dan `BETWEEN` untuk Kondisi Khusus**
   - Cari semua siswa yang berada di kelas 'XI-RPL1' atau 'XI-RPL2' dan yang masuk antara tahun 2021 hingga 2023.

   **SQL Query:**
   ```sql
   SELECT * FROM Siswa
   WHERE Kelas IN ('XI-RPL1', 'XI-RPL2') AND Tahun_Masuk BETWEEN 2021 AND 2023;
   ```

- **Penjelasan:**
  - Latihan ini melibatkan penggunaan `IN` dan `BETWEEN` untuk memilih data berdasarkan beberapa kondisi sekaligus. Ini membantu dalam pencarian data yang lebih spesifik dan sesuai dengan kriteria yang lebih kompleks.

7. **Latihan 7: Menggunakan Subqueries (`SUBQUERIES`)**
   - Temukan nama siswa yang berada di kelas dengan lebih dari 10 siswa.

   **SQL Query:**
   ```sql
   SELECT Nama FROM Siswa
   WHERE Kode_Kelas IN (
       SELECT Kode_Kelas FROM Siswa
       GROUP BY Kode_Kelas
       HAVING COUNT(*) > 10
   );
   ```

- **Penjelasan:**
  - Dalam latihan ini, kalian akan belajar menggunakan subqueries untuk melakukan operasi yang lebih kompleks. Subqueries memungkinkan kalian melakukan query dalam query, yang berguna untuk menyaring data berdasarkan hasil query lain.

#### **Diskusi dan Review:**

- **Mengapa DML Penting?**
  - **Diskusi:** DML memungkinkan kita untuk berinteraksi secara langsung dengan data dalam basis data. Operasi seperti menambah, memperbarui, dan menghapus data sangat penting dalam aplikasi yang dinamis. Tanpa DML, kita tidak bisa mengubah data sesuai kebutuhan atau kondisi saat ini.

- **Kapan Menggunakan Operator Logika?**
  - **Diskusi:** Operator logika seperti `AND`, `OR`, dan `NOT` memungkinkan kita membuat kondisi yang lebih kompleks dalam query. Ini sangat berguna ketika kita perlu menyaring data dengan kriteria yang lebih dari satu. Misalnya, kalian bisa mencari semua siswa yang berada di kelas tertentu dan yang namanya dimulai dengan huruf tertentu.

- **Pentingnya Pengurutan Data dengan `ORDER BY`:**
  - **Diskusi:** Mengurutkan data membantu kita untuk menampilkan informasi dalam urutan yang lebih logis atau sesuai kebutuhan pengguna. Misalnya, mengurutkan daftar siswa berdasarkan nama atau tahun masuk.

- **Subqueries untuk Operasi Kompleks:**
  - **Diskusi:** Subqueries sangat berguna ketika kalian perlu melakukan query yang lebih kompleks. Misalnya, mencari siswa yang berada di kelas dengan jumlah siswa tertentu atau berdasarkan hasil dari tabel lain.

---
[⏮ DDL](../4-ddl/README.md) || [Home 🏘](../README.md) || [DML Lanjutan(JOIN) ⏭](../5-dml-lanjutan-join/README.md)