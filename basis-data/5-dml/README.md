# **Bab 5 - Data Manipulation Language (DML)**

## **Tujuan Pembelajaran**
Setelah pertemuan ini, kalian diharapkan:
- Memahami fungsi dan penggunaan DML dalam SQL untuk mengelola data dalam tabel.
- Mampu melakukan operasi dasar seperti SELECT, INSERT, UPDATE, dan DELETE.
- Memahami cara menghubungkan tabel menggunakan JOIN dan memanipulasi data secara efisien.

## **Materi yang Akan Dibahas**
1. Pengenalan Data Manipulation Language (DML)
2. Perintah SELECT untuk Mengambil Data
3. Perintah INSERT untuk Menambahkan Data
4. Perintah UPDATE untuk Mengubah Data
5. Perintah DELETE untuk Menghapus Data
6. Penggunaan JOIN untuk Menghubungkan Tabel

---

## **1. Pengenalan Data Manipulation Language (DML)**

### **Apa Itu DML?**
DML, atau **Data Manipulation Language**, adalah bagian dari SQL yang digunakan untuk memanipulasi data di dalam tabel. Jika DDL digunakan untuk mendefinisikan struktur basis data, DML digunakan untuk bekerja dengan data di dalam struktur tersebut.

### **Fungsi Utama DML:**
- **Mengambil Data:** Kalian bisa mencari dan menampilkan data yang ada dalam tabel.
- **Menambah Data:** Menambahkan data baru ke dalam tabel.
- **Mengubah Data:** Mengupdate atau mengedit data yang sudah ada.
- **Menghapus Data:** Menghapus data yang sudah tidak diperlukan lagi.

**Contoh DML dalam Kehidupan Sehari-hari:**
Bayangkan kalian bekerja di sebuah perpustakaan digital. DML adalah alat yang kalian gunakan untuk mencari buku, menambahkan buku baru, mengedit detail buku, atau menghapus buku yang sudah tidak relevan.

## **2. Perintah SELECT untuk Mengambil Data**

### **Perintah SELECT:**
Perintah `SELECT` adalah perintah yang paling sering digunakan dalam SQL. Perintah ini digunakan untuk mengambil data dari satu atau lebih tabel.

**Contoh Dasar:**
```sql
SELECT * FROM Pelanggan;
```
- `*` berarti kita ingin mengambil semua kolom dari tabel `Pelanggan`.

### **Menggunakan WHERE untuk Memfilter Data:**
Untuk mengambil data yang lebih spesifik, kalian bisa menggunakan klausa `WHERE`.

**Contoh:**
```sql
SELECT Nama, Alamat FROM Pelanggan WHERE Kota = 'Jakarta';
```
- Ini akan menampilkan nama dan alamat pelanggan yang berada di Jakarta.

### **Menggunakan Fungsi Agregat:**
SQL memiliki fungsi agregat yang bisa digunakan untuk menghitung nilai, seperti `COUNT`, `SUM`, `AVG`, `MAX`, dan `MIN`.

**Contoh:**
```sql
SELECT COUNT(*) FROM Pelanggan WHERE Kota = 'Jakarta';
```
- Ini akan menghitung jumlah pelanggan yang berada di Jakarta.

### **Mengurutkan dan Mengelompokkan Data:**
- **ORDER BY:** Untuk mengurutkan data.
  ```sql
  SELECT * FROM Pelanggan ORDER BY Nama ASC;
  ```
- **GROUP BY:** Untuk mengelompokkan data.
  ```sql
  SELECT Kota, COUNT(*) FROM Pelanggan GROUP BY Kota;
  ```

## **3. Perintah INSERT untuk Menambahkan Data**

### **Perintah INSERT:**
Perintah `INSERT` digunakan untuk menambahkan data baru ke dalam tabel.

**Contoh Dasar:**
```sql
INSERT INTO Pelanggan (Nama, Alamat, Kota) VALUES ('Andi', 'Jl. Merdeka', 'Jakarta');
```
- Ini menambahkan data baru ke dalam tabel `Pelanggan`.

### **Menambahkan Beberapa Baris Sekaligus:**
Kalian juga bisa menambahkan beberapa baris data sekaligus.

**Contoh:**
```sql
INSERT INTO Pelanggan (Nama, Alamat, Kota) VALUES 
('Budi', 'Jl. Sudirman', 'Bandung'),
('Citra', 'Jl. Thamrin', 'Surabaya');
```

## **4. Perintah UPDATE untuk Mengubah Data**

### **Perintah UPDATE:**
Perintah `UPDATE` digunakan untuk mengubah data yang sudah ada dalam tabel.

**Contoh Dasar:**
```sql
UPDATE Pelanggan SET Alamat = 'Jl. Baru' WHERE ID_Pelanggan = 1;
```
- Ini akan mengubah alamat pelanggan dengan ID 1 menjadi "Jl. Baru".

### **Mengubah Data Secara Massal:**
Kalian bisa mengubah data beberapa baris sekaligus dengan menggunakan klausa `WHERE` yang lebih umum.

**Contoh:**
```sql
UPDATE Pelanggan SET Kota = 'Bandung' WHERE Kota = 'Jakarta';
```

## **5. Perintah DELETE untuk Menghapus Data**

### **Perintah DELETE:**
Perintah `DELETE` digunakan untuk menghapus data dari tabel.

**Contoh Dasar:**
```sql
DELETE FROM Pelanggan WHERE ID_Pelanggan = 1;
```
- Ini akan menghapus pelanggan dengan ID 1 dari tabel `Pelanggan`.

### **Hati-Hati dengan DELETE:**
Jika kalian tidak menggunakan klausa `WHERE`, maka semua data dalam tabel bisa terhapus!

**Contoh Berbahaya:**
```sql
DELETE FROM Pelanggan;
```
- Ini akan menghapus semua data dalam tabel `Pelanggan`. Jadi, selalu hati-hati saat menggunakan DELETE!

## **6. Penggunaan JOIN untuk Menghubungkan Tabel**

### **Apa Itu JOIN?**
`JOIN` digunakan untuk menggabungkan baris dari dua atau lebih tabel berdasarkan kolom terkait di antara mereka. Ada beberapa jenis `JOIN` yang bisa kalian gunakan.

### **Jenis-Jenis JOIN:**

1. **INNER JOIN:** Menggabungkan baris yang memiliki kecocokan di kedua tabel.
   ```sql
   SELECT Pesanan.ID_Pesanan, Pelanggan.Nama FROM Pesanan 
   INNER JOIN Pelanggan ON Pesanan.ID_Pelanggan = Pelanggan.ID_Pelanggan;
   ```

2. **LEFT JOIN:** Menggabungkan semua baris dari tabel kiri, dan baris yang cocok dari tabel kanan.
   ```sql
   SELECT Pelanggan.Nama, Pesanan.ID_Pesanan FROM Pelanggan 
   LEFT JOIN Pesanan ON Pelanggan.ID_Pelanggan = Pesanan.ID_Pelanggan;
   ```

3. **RIGHT JOIN:** Kebalikan dari LEFT JOIN; menggabungkan semua baris dari tabel kanan.
   ```sql
   SELECT Pelanggan.Nama, Pesanan.ID_Pesanan FROM Pelanggan 
   RIGHT JOIN Pesanan ON Pelanggan.ID_Pelanggan = Pesanan.ID_Pelanggan;
   ```

4. **FULL JOIN:** Menggabungkan semua baris ketika ada kecocokan di salah satu tabel.
   ```sql
   SELECT Pelanggan.Nama, Pesanan.ID_Pesanan FROM Pelanggan 
   FULL OUTER JOIN Pesanan ON Pelanggan.ID_Pelanggan = Pesanan.ID_Pelanggan;
   ```

### **Contoh Skenario:**
Misalnya kalian punya dua tabel, `Pelanggan` dan `Pesanan`. Dengan `JOIN`, kalian bisa menggabungkan data untuk melihat siapa yang memesan apa:
```sql
SELECT Pelanggan.Nama, Pesanan.Tanggal FROM Pelanggan 
INNER JOIN Pesanan ON Pelanggan.ID_Pelanggan = Pesanan.ID_Pelanggan;
```

---

### **Aktivitas**

1. **Diskusi Kelompok:**
    - **Topik:** Bagaimana kalian bisa memastikan bahwa operasi DML tidak merusak integritas data dalam basis data?
    - **Tujuan:** Memahami pentingnya menggunakan perintah DML dengan benar untuk menjaga integritas dan konsistensi data.

2. **Latihan:**
    - **Tugas:** Gunakan DML untuk mengisi tabel dengan data, memperbarui beberapa record, menghapus record yang tidak diperlukan, dan menggabungkan tabel menggunakan JOIN.
    - **Output:** Kode SQL dan hasil query yang menunjukkan operasi DML yang kalian lakukan.
