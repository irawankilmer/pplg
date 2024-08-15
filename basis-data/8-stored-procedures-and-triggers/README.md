# **Bab 8 - Pemrograman SQL (Stored Procedures, Triggers dan Subqueries)**
#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Memahami dan membuat stored procedures untuk menjalankan sekumpulan perintah SQL secara otomatis.
- Menggunakan triggers untuk menjalankan aksi otomatis sebagai respons terhadap perubahan data.
- Menggunakan subqueries untuk melakukan query di dalam query lain untuk operasi yang lebih kompleks.

#### **Materi yang Akan Dibahas**

1. **Pengenalan Stored Procedures**
   - **Apa itu Stored Procedure?**
     - Stored Procedure adalah sekumpulan perintah SQL yang disimpan di dalam basis data dan dapat dipanggil untuk dieksekusi. Stored procedures memungkinkan kalian untuk menjalankan operasi yang berulang secara otomatis, mengurangi duplikasi kode, dan meningkatkan efisiensi pemrograman.
   - **Mengapa Menggunakan Stored Procedures?**
     - Dengan stored procedures, kalian bisa mengelompokkan beberapa operasi SQL yang sering digunakan ke dalam satu unit yang dapat dipanggil kapan saja. Ini juga meningkatkan keamanan karena parameter input dapat divalidasi di sisi server.
   - **Membuat Stored Procedure:**
     - **Contoh:**
       ```sql
       CREATE PROCEDURE TambahSiswa(
           IN NIS INT,
           IN Nama VARCHAR(100),
           IN Kelas VARCHAR(10)
       )
       BEGIN
           INSERT INTO Siswa (NIS, Nama, Kelas) VALUES (NIS, Nama, Kelas);
       END;
       ```
     - **Penjelasan:**
       - Stored procedure ini menerima tiga parameter (`NIS`, `Nama`, `Kelas`) dan menggunakan mereka untuk menambahkan data ke dalam tabel `Siswa`.
   - **Memanggil Stored Procedure:**
     - **Contoh:**
       ```sql
       CALL TambahSiswa(12349, 'John Doe', 'XI-IPA3');
       ```

2. **Pengenalan Triggers**
   - **Apa itu Trigger?**
     - Trigger adalah perintah SQL yang secara otomatis dieksekusi sebagai respons terhadap peristiwa tertentu pada tabel, seperti `INSERT`, `UPDATE`, atau `DELETE`. Triggers sering digunakan untuk menjaga integritas data atau untuk mencatat perubahan dalam basis data.
   - **Mengapa Menggunakan Triggers?**
     - Triggers memungkinkan kalian untuk mengotomatisasi tugas-tugas yang harus dilakukan setiap kali terjadi perubahan data, misalnya, mencatat waktu terakhir suatu data diubah atau memvalidasi data sebelum disimpan.
   - **Membuat Trigger:**
     - **Contoh:**
       ```sql
       CREATE TRIGGER BeforeInsertSiswa
       BEFORE INSERT ON Siswa
       FOR EACH ROW
       BEGIN
           IF NEW.Kelas IS NULL THEN
               SET NEW.Kelas = 'Belum ditentukan';
           END IF;
       END;
       ```
     - **Penjelasan:**
       - Trigger ini secara otomatis memeriksa apakah kolom `Kelas` memiliki nilai saat ada `INSERT` baru. Jika tidak ada, trigger menetapkan nilai default `'Belum ditentukan'`.

3. **Menggunakan Subqueries untuk Operasi Kompleks**
   - **Apa itu Subquery?**
     - Subquery adalah query di dalam query lain. Subquery dapat digunakan dalam klausa `SELECT`, `FROM`, `WHERE`, atau `HAVING` untuk melakukan operasi yang lebih kompleks atau untuk mengolah hasil query lain.
   - **Mengapa Menggunakan Subquery?**
     - Subqueries memungkinkan kalian untuk melakukan operasi lebih kompleks, seperti menghitung agregat pada subset data atau memilih data berdasarkan hasil dari query lain.
   - **Contoh Subquery:**
     - **Subquery di dalam `WHERE`:**
       - Mencari siswa yang berada di kelas dengan lebih dari 20 siswa:
       ```sql
       SELECT Nama FROM Siswa
       WHERE Kode_Kelas IN (
           SELECT Kode_Kelas FROM Siswa
           GROUP BY Kode_Kelas
           HAVING COUNT(*) > 20
       );
       ```
     - **Subquery di dalam `SELECT`:**
       - Menampilkan nama siswa dan jumlah siswa di kelas mereka:
       ```sql
       SELECT Nama, (SELECT COUNT(*) FROM Siswa B WHERE B.Kode_Kelas = A.Kode_Kelas) AS Jumlah_Siswa
       FROM Siswa A;
       ```

4. **Mengelola Performa dengan Stored Procedures dan Triggers**
   - **Keuntungan Menggunakan Stored Procedures:**
     - Stored procedures mengurangi lalu lintas jaringan karena hanya nama prosedur dan parameternya yang dikirim, bukan seluruh perintah SQL. Mereka juga meningkatkan keamanan karena validasi input dilakukan di server.
   - **Manfaat Triggers dalam Basis Data:**
     - Triggers membantu menjaga integritas data dan memungkinkan otomatisasi tugas yang terjadi saat data berubah, seperti mencatat log perubahan atau mengirim notifikasi.

#### **Praktikum Lengkap**

1. **Latihan 1: Membuat dan Menggunakan Stored Procedures**
   - **Membuat Stored Procedure**:
     - Buat sebuah stored procedure untuk menambahkan data siswa baru ke dalam tabel `Siswa`.
     ```sql
     CREATE PROCEDURE TambahSiswa(
         IN NIS INT,
         IN Nama VARCHAR(100),
         IN Kelas VARCHAR(10)
     )
     BEGIN
         INSERT INTO Siswa (NIS, Nama, Kelas) VALUES (NIS, Nama, Kelas);
     END;
     ```
     - **Penjelasan**: Stored procedure ini menerima tiga parameter (`NIS`, `Nama`, dan `Kelas`) dan menggunakannya untuk menambahkan baris baru ke tabel `Siswa`.

   - **Memanggil Stored Procedure**:
     - Setelah membuat stored procedure, panggil prosedur tersebut untuk menambahkan data siswa baru.
     ```sql
     CALL TambahSiswa(12350, 'Siti Nurhaliza', 'XI-IPA2');
     ```

2. **Latihan 2: Membuat dan Menggunakan Triggers**
   - **Membuat Trigger**:
     - Buat trigger yang secara otomatis mengisi kolom `Kelas` dengan nilai default `'Belum ditentukan'` jika tidak ada nilai yang dimasukkan saat data baru ditambahkan ke tabel `Siswa`.
     ```sql
     CREATE TRIGGER BeforeInsertSiswa
     BEFORE INSERT ON Siswa
     FOR EACH ROW
     BEGIN
         IF NEW.Kelas IS NULL THEN
             SET NEW.Kelas = 'Belum ditentukan';
         END IF;
     END;
     ```

   - **Menggunakan Trigger**:
     - Tambahkan data siswa tanpa mengisi kolom `Kelas` dan lihat bagaimana trigger otomatis mengisi nilai tersebut.
     ```sql
     INSERT INTO Siswa (NIS, Nama) VALUES (12351, 'Budi Santoso');
     ```

3. **Latihan 3: Menggunakan Subqueries untuk Operasi Kompleks**
   - **Subquery di dalam `WHERE`**:
     - Temukan nama-nama siswa yang berada di kelas dengan lebih dari 20 siswa.
     ```sql
     SELECT Nama FROM Siswa
     WHERE Kode_Kelas IN (
         SELECT Kode_Kelas FROM Siswa
         GROUP BY Kode_Kelas
         HAVING COUNT(*) > 20
     );
     ```

   - **Subquery di dalam `SELECT`**:
     - Tampilkan nama siswa dan jumlah siswa di kelas mereka.
     ```sql
     SELECT Nama, (SELECT COUNT(*) FROM Siswa B WHERE B.Kode_Kelas = A.Kode_Kelas) AS Jumlah_Siswa
     FROM Siswa A;
     ```

#### **Diskusi dan Review**

- **Mengapa Stored Procedures dan Triggers Penting?**
  - **Diskusi:** Stored procedures memungkinkan eksekusi otomatis dari sekumpulan perintah SQL yang sering digunakan, meningkatkan efisiensi dan keamanan. Triggers, di sisi lain, memungkinkan otomatisasi tugas yang terjadi saat data diubah, memastikan konsistensi dan keandalan data.
  
- **Bagaimana Subqueries Membantu dalam Operasi Kompleks?**
  - **Diskusi:** Subqueries memungkinkan kalian untuk melakukan query di dalam query, memungkinkan operasi yang lebih kompleks seperti pengelompokan dan penyaringan data berdasarkan hasil query lain. Ini adalah alat yang sangat berguna ketika kalian membutuhkan fleksibilitas dalam pengolahan data.

---
[⏮ Transaksi dan Optimasi Query](../7-transaksi-dan-optimasi-query/README.md) || [Home 🏘](../README.md) || [Case dan NoSQL ⏭](../9-case-dan-nosql/README.md)