# **Bab 4 - Data Definition Language (DDL)**
#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Menggunakan DDL untuk membuat, mengubah, dan menghapus struktur tabel dan basis data.
- Menerapkan berbagai constraints (`PRIMARY KEY`, `FOREIGN KEY`, `NOT NULL`, `UNIQUE`, `CHECK`, `DEFAULT`) dalam desain tabel.
- Memahami konsep dan penerapan indeks (`INDEX`) untuk optimasi kinerja query dalam basis data.

#### **Materi Lengkap:**

1. **Pengertian Data Definition Language (DDL):**
   - **Apa itu DDL?**
     - Data Definition Language (DDL) adalah bagian dari SQL yang berfungsi untuk mendefinisikan dan mengelola struktur dari objek-objek dalam basis data seperti tabel, indeks, dan skema. Perintah-perintah DDL tidak hanya menentukan bagaimana data disimpan tetapi juga memastikan integritas data dan kinerja yang optimal melalui constraints dan indeks.

   - **Fungsi Utama DDL:**
     - **CREATE**: Digunakan untuk membuat objek baru dalam basis data seperti tabel, indeks, dan basis data itu sendiri.
     - **ALTER**: Digunakan untuk mengubah struktur objek yang sudah ada, seperti menambah atau menghapus kolom dalam tabel.
     - **DROP**: Digunakan untuk menghapus objek dari basis data, seperti tabel atau basis data itu sendiri.

   - **Mengapa DDL Penting?**
     - DDL memungkinkan desainer basis data untuk menentukan bagaimana data akan disusun, diakses, dan diatur. Tanpa DDL, basis data akan kehilangan struktur dan integritasnya, yang dapat menyebabkan kesalahan data dan performa yang buruk.

2. **Perintah Dasar DDL:**

   - **CREATE: Membuat Objek Basis Data**
     - **CREATE DATABASE**: Membuat basis data baru.
       ```sql
       CREATE DATABASE Sekolah;
       ```
     - **CREATE TABLE**: Membuat tabel baru dalam basis data dengan mendefinisikan kolom dan tipe datanya.
       ```sql
       CREATE TABLE Siswa (
           NIS INT PRIMARY KEY,
           Nama VARCHAR(100) NOT NULL,
           Kelas VARCHAR(10),
           Tahun_Masuk YEAR
       );
       ```
       - **Detail Kolom:**
         - `NIS`: Nomor Induk Siswa, tipe data `INT`, ditetapkan sebagai `PRIMARY KEY` yang berarti setiap nilai harus unik dan tidak boleh kosong.
         - `Nama`: Nama siswa, tipe data `VARCHAR(100)` yang artinya string dengan panjang maksimal 100 karakter, dan tidak boleh kosong (`NOT NULL`).
         - `Kelas`: Kelas siswa, tipe data `VARCHAR(10)` untuk menyimpan nama kelas.
         - `Tahun_Masuk`: Tahun masuk siswa, tipe data `YEAR`.

   - **ALTER: Mengubah Struktur Tabel**
     - **Menambahkan Kolom Baru:**
       - Kadang-kadang, setelah tabel dibuat, kita perlu menambahkan kolom baru. Ini bisa dilakukan dengan perintah `ALTER`.
       ```sql
       ALTER TABLE Siswa ADD Alamat VARCHAR(255);
       ```
     - **Mengubah Tipe Data Kolom:**
       - Jika tipe data dari kolom perlu diubah, kita bisa menggunakan `ALTER` dengan `MODIFY`.
       ```sql
       ALTER TABLE Siswa MODIFY Kelas VARCHAR(15);
       ```
     - **Menghapus Kolom:**
       - Untuk menghapus kolom yang tidak lagi diperlukan.
       ```sql
       ALTER TABLE Siswa DROP COLUMN Alamat;
       ```

   - **DROP: Menghapus Objek Basis Data**
     - **Menghapus Tabel:**
       - Menghapus tabel dari basis data secara permanen.
       ```sql
       DROP TABLE Siswa;
       ```
     - **Menghapus Basis Data:**
       - Menghapus seluruh basis data, beserta semua tabel dan data yang ada di dalamnya.
       ```sql
       DROP DATABASE Sekolah;
       ```

3. **Constraints dalam DDL:**

   Constraints adalah aturan yang diterapkan pada kolom untuk memastikan integritas dan validitas data dalam basis data. Berikut adalah beberapa constraints penting yang sering digunakan:

   - **PRIMARY KEY:**
     - Kombinasi unik dari kolom yang mengidentifikasi setiap baris dalam tabel secara unik.
     - **Contoh:**
       ```sql
       CREATE TABLE Siswa (
           NIS INT PRIMARY KEY,
           Nama VARCHAR(100)
       );
       ```
     - Sebuah tabel hanya bisa memiliki satu `PRIMARY KEY`, dan kolom yang ditetapkan sebagai `PRIMARY KEY` tidak boleh mengandung nilai duplikat atau kosong.

   - **FOREIGN KEY:**
     - Menghubungkan dua tabel dengan menjadikan satu kolom sebagai referensi terhadap `PRIMARY KEY` di tabel lain. Ini menjaga konsistensi antar tabel.
     - **Contoh:**
       ```sql
       CREATE TABLE Kelas (
           Kode_Kelas VARCHAR(10) PRIMARY KEY,
           Nama_Kelas VARCHAR(50)
       );

       CREATE TABLE Siswa (
           NIS INT PRIMARY KEY,
           Nama VARCHAR(100),
           Kode_Kelas VARCHAR(10),
           FOREIGN KEY (Kode_Kelas) REFERENCES Kelas(Kode_Kelas)
       );
       ```
     - `FOREIGN KEY` memastikan bahwa nilai dalam kolom tertentu harus sesuai dengan nilai yang ada di kolom `PRIMARY KEY` tabel lain, menjaga integritas relasi antar tabel.

   - **NOT NULL:**
     - Mencegah kolom menerima nilai `NULL`, memastikan bahwa setiap baris memiliki nilai untuk kolom tersebut.
     - **Contoh:**
       ```sql
       ALTER TABLE Siswa MODIFY Nama VARCHAR(100) NOT NULL;
       ```

   - **UNIQUE:**
     - Memastikan bahwa semua nilai dalam kolom tertentu harus unik, tidak boleh ada duplikasi.
     - **Contoh:**
       ```sql
       CREATE TABLE Buku (
           ISBN VARCHAR(13) UNIQUE,
           Judul VARCHAR(255)
       );
       ```

   - **CHECK:**
     - Menetapkan kondisi yang harus dipenuhi oleh nilai dalam kolom tertentu.
     - **Contoh:**
       ```sql
       CREATE TABLE Pegawai (
           ID INT PRIMARY KEY,
           Nama VARCHAR(100),
           Umur INT CHECK (Umur >= 18)
       );
       ```
     - Dalam contoh ini, `CHECK` memastikan bahwa nilai `Umur` harus minimal 18.

   - **DEFAULT:**
     - Menentukan nilai default untuk kolom jika tidak ada nilai yang diberikan saat baris baru ditambahkan.
     - **Contoh:**
       ```sql
       CREATE TABLE Produk (
           ID INT PRIMARY KEY,
           Nama VARCHAR(100),
           Stok INT DEFAULT 0
       );
       ```
     - `DEFAULT` menetapkan bahwa jika `Stok` tidak diisi saat menambah baris baru, maka secara otomatis akan diberi nilai 0.

4. **Penggunaan Indeks (`INDEX`):**

   Indeks adalah struktur data yang meningkatkan kecepatan pengambilan data dalam tabel besar. Tanpa indeks, basis data harus melakukan pencarian sekuensial (memeriksa satu per satu) untuk menemukan data, yang bisa sangat lambat.

   - **Mengapa Indeks Penting?**
     - Pada tabel dengan jutaan baris, pencarian tanpa indeks bisa sangat lambat. Indeks bekerja seperti indeks di buku, membantu basis data menemukan baris tertentu tanpa harus memeriksa setiap baris.

   - **Jenis-jenis Indeks:**
     - **B-TREE Index**: Paling umum digunakan, mendukung pencarian rentang.
     - **Hash Index**: Hanya mendukung pencarian `=` (sama dengan), lebih cepat untuk pencarian sederhana tapi tidak mendukung rentang.
     - **Bitmap Index**: Efisien untuk kolom dengan jumlah nilai unik yang sangat sedikit.

   - **Membuat Indeks:**
     - **Contoh:**
       ```sql
       CREATE INDEX idx_nama ON Siswa(Nama);
       ```
     - Indeks ini akan membuat pencarian berdasarkan `Nama` lebih cepat.

   - **Menghapus Indeks:**
     - Jika indeks tidak lagi diperlukan atau jika kinerjanya menurun, kita bisa menghapusnya.
       ```sql
       DROP INDEX idx_nama ON Siswa;
       ```

#### **Praktikum Lengkap:**

1. **Latihan 1: Membuat Tabel dengan Constraints**
   - Buat tabel `Pegawai` dengan kolom `ID`, `Nama`, `Jabatan`, `Gaji`, dan `Umur`. Tetapkan `ID` sebagai `PRIMARY KEY`, `Nama` sebagai `NOT NULL`, `Gaji` dengan nilai `DEFAULT` 0, dan pastikan `Umur` minimal 18 tahun (`CHECK`).

   **SQL Query:**
   ```sql
   CREATE TABLE Pegawai (
       ID INT PRIMARY KEY,
       Nama VARCHAR(100) NOT NULL,
       Jabatan VARCHAR(50),
       Gaji INT DEFAULT 0,
       Umur INT CHECK (Umur >= 18)
   );
   ```

2. **Latihan 2: Menggunakan ALTER untuk Mengubah Tabel**
   - Tambahkan kolom `Alamat` ke tabel `Pegawai` dan tetapkan tipe data `VARCHAR(255)`. Pastikan `Alamat` tidak boleh kosong (`NOT NULL`).

   **SQL Query:**
```sql
ALTER TABLE Pegawai ADD Alamat VARCHAR(255) NOT NULL;
```

- **Penjelasan:**
  - Dalam latihan ini, kalian menambahkan kolom `Alamat` ke dalam tabel `Pegawai` yang sudah dibuat sebelumnya. Kolom `Alamat` diset untuk tidak boleh kosong (`NOT NULL`), yang berarti setiap baris di tabel harus memiliki nilai di kolom ini. Jika kalian menambahkan baris baru tanpa mengisi nilai `Alamat`, SQL akan menolak memasukkan data tersebut.

3. **Latihan 3: Membuat dan Menghapus Indeks**
   - **Membuat Indeks pada Kolom `Nama`:**
     - Tujuan dari indeks ini adalah untuk mempercepat pencarian atau pengurutan data berdasarkan `Nama`. Indeks sangat berguna ketika tabel memiliki banyak baris.
     ```sql
     CREATE INDEX idx_nama ON Pegawai(Nama);
     ```
   - **Menghapus Indeks:**
     - Jika setelah beberapa waktu kalian merasa indeks ini tidak lagi dibutuhkan (misalnya karena tabel `Pegawai` menjadi kecil sehingga pencarian sekuensial cukup cepat), kalian bisa menghapusnya.
     ```sql
     DROP INDEX idx_nama ON Pegawai;
     ```

- **Penjelasan:**
  - Latihan ini memberikan pengalaman langsung dalam membuat dan mengelola indeks di tabel. Ini akan membantu kalian memahami bagaimana indeks bekerja dan kapan perlu menggunakannya untuk meningkatkan performa query.

#### **Diskusi dan Review:**

- **Mengapa Constraints Penting?**
  - **Diskusi:** Constraints memastikan integritas dan konsistensi data. Misalnya, `PRIMARY KEY` memastikan bahwa setiap baris dapat diidentifikasi secara unik, sementara `FOREIGN KEY` menjaga hubungan antar tabel tetap konsisten. Constraints seperti `NOT NULL`, `CHECK`, dan `DEFAULT` juga memainkan peran penting dalam menjaga kualitas data.
  - **Contoh Praktis:** Jika kalian memiliki tabel `Siswa` dan `Kelas`, `FOREIGN KEY` membantu memastikan bahwa setiap siswa hanya bisa dihubungkan ke kelas yang benar-benar ada dalam tabel `Kelas`. Tanpa constraints, data bisa menjadi kacau, misalnya, siswa mungkin terdaftar di kelas yang tidak ada.

- **Peran Indeks dalam Optimasi Query:**
  - **Diskusi:** Indeks adalah alat yang sangat kuat untuk meningkatkan kinerja query, terutama pada tabel besar. Indeks bekerja seperti indeks dalam sebuah buku, memungkinkan basis data untuk menemukan data lebih cepat tanpa harus memeriksa setiap baris.
  - **Contoh Praktis:** Pertimbangkan tabel `Pegawai` dengan ribuan baris. Tanpa indeks, pencarian pegawai berdasarkan `Nama` akan memakan waktu lama karena SQL harus memeriksa setiap baris. Dengan indeks, SQL bisa langsung menuju ke baris yang relevan, mempercepat proses pencarian.

---
[⏮ Installasi](../3-installasi/README.md) || [Home 🏘](../README.md) || [DML ⏭](../5-dml/README.md)