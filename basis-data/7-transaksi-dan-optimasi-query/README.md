# **Bab 7 - Transaksi dan Optimasi Query**
#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Memahami konsep dasar transaksi dalam basis data dan pentingnya prinsip ACID.
- Menggunakan perintah SQL untuk mengelola transaksi, termasuk `COMMIT` dan `ROLLBACK`.
- Menerapkan teknik optimasi query untuk meningkatkan performa basis data.
- Menggunakan fungsi agregat (`COUNT`, `SUM`, `AVG`, `MIN`, `MAX`) dan `GROUP BY` untuk analisis data.
- Memanfaatkan indeks untuk optimasi query dan menganalisis performa query menggunakan `EXPLAIN`.

#### **Materi yang Akan Dibahas**

1. **Pengertian Transaksi dan Prinsip ACID**
   - **Apa itu Transaksi?**
     - Transaksi adalah satu unit pekerjaan yang dilakukan secara lengkap atau tidak sama sekali. Misalnya, dalam aplikasi perbankan, transfer dana antara dua akun harus dilakukan sebagai satu transaksi.
   - **Prinsip ACID:**
     - **Atomicity**: Transaksi harus dieksekusi sepenuhnya atau tidak sama sekali.
     - **Consistency**: Transaksi harus membawa basis data dari satu kondisi valid ke kondisi valid lainnya.
     - **Isolation**: Transaksi yang berjalan bersamaan tidak boleh saling mengganggu.
     - **Durability**: Setelah transaksi selesai, perubahan yang terjadi harus disimpan secara permanen.

2. **Perintah `COMMIT` dan `ROLLBACK` untuk Mengelola Transaksi**
   - **COMMIT:**
     - Mengakhiri transaksi dan menyimpan semua perubahan secara permanen.
     - **Contoh:**
       ```sql
       START TRANSACTION;
       INSERT INTO Siswa (NIS, Nama, Kelas) VALUES (12345, 'Ahmad Zaky', 'XI-IPA1');
       COMMIT;
       ```
   - **ROLLBACK:**
     - Membatalkan transaksi dan mengembalikan basis data ke kondisi sebelum transaksi dimulai.
     - **Contoh:**
       ```sql
       START TRANSACTION;
       INSERT INTO Siswa (NIS, Nama, Kelas) VALUES (12345, 'Ahmad Zaky', 'XI-IPA1');
       ROLLBACK;
       ```

3. **Pengenalan Optimasi Query**
   - **Mengapa Optimasi Query Penting?**
     - Optimasi query penting untuk memastikan query berjalan dengan efisien, terutama pada basis data yang besar.
   - **Teknik Dasar Optimasi:**
     - **Gunakan Indeks:** Membuat indeks pada kolom yang sering digunakan dalam `WHERE`, `JOIN`, dan `ORDER BY`.
     - **Pilih Kolom yang Spesifik:** Gunakan `SELECT` untuk memilih kolom yang diperlukan, hindari penggunaan `SELECT *`.

4. **Fungsi Agregat dalam SQL**
   - **Pengertian Fungsi Agregat:**
     - Fungsi agregat digunakan untuk meringkas data. Misalnya, menghitung jumlah baris, menghitung rata-rata, dan mencari nilai maksimum atau minimum.
   - **Contoh Fungsi Agregat:**
     - **COUNT:** Menghitung jumlah baris.
       ```sql
       SELECT COUNT(*) FROM Siswa WHERE Kelas = 'XI-IPA1';
       ```
     - **SUM:** Menjumlahkan nilai dalam kolom.
       ```sql
       SELECT SUM(Gaji) FROM Pegawai WHERE Jabatan = 'Manager';
       ```
     - **AVG:** Menghitung rata-rata nilai.
       ```sql
       SELECT AVG(Nilai) FROM Nilai_Siswa WHERE Mata_Pelajaran = 'Matematika';
       ```
     - **MIN:** Mencari nilai minimum.
       ```sql
       SELECT MIN(Gaji) FROM Pegawai WHERE Jabatan = 'Karyawan';
       ```
     - **MAX:** Mencari nilai maksimum.
       ```sql
       SELECT MAX(Gaji) FROM Pegawai WHERE Jabatan = 'Manager';
       ```

5. **Menggunakan `GROUP BY` dan `HAVING` untuk Analisis Data**
   - **`GROUP BY`:**
     - Mengelompokkan data berdasarkan satu atau lebih kolom.
     - **Contoh:**
       ```sql
       SELECT Kelas, COUNT(*) AS Jumlah_Siswa FROM Siswa GROUP BY Kelas;
       ```
   - **`HAVING`:**
     - Menyaring hasil agregat setelah `GROUP BY`.
     - **Contoh:**
       ```sql
       SELECT Kelas, COUNT(*) AS Jumlah_Siswa FROM Siswa GROUP BY Kelas HAVING COUNT(*) > 20;
       ```

6. **Penggunaan Indeks untuk Meningkatkan Performa**
   - **Apa itu Indeks?**
     - Indeks adalah struktur data yang digunakan untuk mempercepat pencarian dan pengurutan data.
   - **Membuat Indeks:**
     - **Contoh:**
       ```sql
       CREATE INDEX idx_nama ON Siswa(Nama);
       ```
     - Indeks ini membantu mempercepat pencarian nama siswa dalam tabel besar.

7. **Menganalisis Performa Query dengan `EXPLAIN`**
   - **Apa itu `EXPLAIN`?**
     - `EXPLAIN` adalah perintah SQL yang digunakan untuk menganalisis bagaimana query akan dieksekusi oleh server basis data.
   - **Menggunakan `EXPLAIN`:**
     - **Contoh:**
       ```sql
       EXPLAIN SELECT * FROM Siswa WHERE Nama LIKE 'A%';
       ```
     - `EXPLAIN` akan memberikan detail tentang bagaimana SQL Server berencana untuk menjalankan query, membantu mengidentifikasi potensi bottleneck.

#### **Praktikum Lengkap:**

1. **Latihan 1: Mengelola Transaksi dengan `COMMIT` dan `ROLLBACK`**
   - Lakukan transaksi yang melibatkan beberapa operasi SQL dan gunakan `COMMIT` untuk menyimpan atau `ROLLBACK` untuk membatalkan perubahan.
   ```sql
   START TRANSACTION;
   INSERT INTO Siswa (NIS, Nama, Kelas) VALUES (12346, 'Dewi Sartika', 'XI-IPA1');
   UPDATE Siswa SET Kelas = 'XI-IPA2' WHERE NIS = 12345;
   COMMIT;
   ```

2. **Latihan 2: Menggunakan Fungsi Agregat dan `GROUP BY`**
   - Hitung jumlah siswa di setiap kelas dan tampilkan hanya kelas yang memiliki lebih dari 20 siswa.
   ```sql
   SELECT Kelas, COUNT(*) AS Jumlah_Siswa FROM Siswa GROUP BY Kelas HAVING COUNT(*) > 20;
   ```

3. **Latihan 3: Membuat dan Menggunakan Indeks**
   - Buat indeks pada kolom `Nama` dan lihat bagaimana ini mempengaruhi kecepatan query.
   ```sql
   CREATE INDEX idx_nama ON Siswa(Nama);
   ```

4. **Latihan 4: Menganalisis Performa Query dengan `EXPLAIN`**
   - Gunakan `EXPLAIN` untuk menganalisis performa query yang melibatkan pengurutan data dan penggunaan indeks.
   ```sql
   EXPLAIN SELECT * FROM Siswa WHERE Nama LIKE 'A%';
   ```

#### **Diskusi dan Review:**

- **Mengapa Optimasi Query Penting?**
  - **Diskusi:** Optimasi query membantu meningkatkan performa basis data, mengurangi waktu eksekusi query, dan mencegah beban berlebih pada sistem, terutama ketika bekerja dengan basis data yang besar.

- **Bagaimana Fungsi Agregat dan `GROUP BY` Membantu dalam Analisis Data?**
  - **Diskusi:** Fungsi agregat dan `GROUP BY` memungkinkan analisis data yang lebih mendalam, seperti menghitung total, rata-rata, atau mengelompokkan data untuk mendapatkan wawasan yang lebih baik.

- **Kapan dan Bagaimana Menggunakan `COMMIT` dan `ROLLBACK`?**
  - **Diskusi:** `COMMIT` digunakan untuk menyimpan semua perubahan yang dilakukan dalam transaksi, sementara `ROLLBACK` digunakan untuk membatalkan perubahan jika terjadi kesalahan atau jika perubahan tersebut tidak lagi diperlukan.

---
[⏮ DCL](../6-dcl/README.md) || [Home 🏘](../README.md) || [Stored Procedures dan Triggers ⏭](../8-stored-procedures-and-triggers/README.md)