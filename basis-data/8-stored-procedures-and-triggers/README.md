# **Bab 8 - Pemrograman SQL (Stored Procedures & Triggers)**

## **Tujuan Pembelajaran**
Setelah pertemuan ini, kalian diharapkan:
- Memahami konsep dasar stored procedures dan triggers dalam SQL.
- Mampu membuat dan menggunakan stored procedures untuk otomatisasi tugas-tugas di dalam basis data.
- Memahami fungsi triggers dan bagaimana mereka dapat digunakan untuk menangani kejadian otomatis dalam basis data.
- Mengerti bagaimana stored procedures dan triggers berkontribusi terhadap efisiensi dan konsistensi data dalam aplikasi basis data.

## **Materi yang Akan Dibahas**
1. Pengenalan Stored Procedures
2. Membuat dan Menggunakan Stored Procedures
3. Pengenalan Triggers
4. Membuat dan Menggunakan Triggers
5. Contoh Implementasi dalam Skenario Nyata

---

## **1. Pengenalan Stored Procedures**

### **Apa Itu Stored Procedure?**
Stored procedure adalah kumpulan perintah SQL yang disimpan dalam basis data dan dapat dijalankan kapan saja. Mereka sangat berguna untuk menyederhanakan dan mengotomatisasi tugas-tugas yang sering dilakukan.

### **Fungsi Utama Stored Procedures:**
- **Otomatisasi Tugas:** Mengurangi pengulangan perintah SQL dengan menyimpan logika di satu tempat.
- **Keamanan:** Menyembunyikan logika bisnis dari pengguna akhir, memberikan kontrol lebih besar atas apa yang dieksekusi.
- **Kinerja:** Stored procedures biasanya lebih cepat daripada menjalankan perintah SQL satu per satu, karena mereka dikompilasi sekali dan dapat digunakan berulang kali.

### **Mengapa Stored Procedures Penting?**
Bayangkan kalian sering perlu menghitung total penjualan mingguan. Alih-alih menulis query yang panjang setiap minggu, kalian bisa membuat stored procedure untuk melakukannya secara otomatis hanya dengan memanggilnya satu kali.

## **2. Membuat dan Menggunakan Stored Procedures**

### **Cara Membuat Stored Procedure:**
Untuk membuat stored procedure, kalian perlu menggunakan perintah `CREATE PROCEDURE` diikuti dengan logika SQL yang ingin kalian jalankan.

**Contoh Dasar:**
```sql
CREATE PROCEDURE HitungTotalPenjualanMingguan()
BEGIN
    SELECT SUM(Harga_Total) FROM Penjualan WHERE Tanggal_Penjualan >= CURDATE() - INTERVAL 7 DAY;
END;
```
- Stored procedure ini akan menghitung total penjualan selama seminggu terakhir.

### **Menjalankan Stored Procedure:**
Untuk menjalankan stored procedure yang sudah kalian buat, gunakan perintah `CALL`.

**Contoh:**
```sql
CALL HitungTotalPenjualanMingguan();
```

### **Menggunakan Parameter di Stored Procedures:**
Stored procedures bisa menerima input dalam bentuk parameter, memungkinkan fleksibilitas lebih dalam penggunaan.

**Contoh dengan Parameter:**
```sql
CREATE PROCEDURE CariPelanggan(IN namaPelanggan VARCHAR(100))
BEGIN
    SELECT * FROM Pelanggan WHERE Nama = namaPelanggan;
END;
```
- Stored procedure ini mencari pelanggan berdasarkan nama yang diberikan sebagai input.

## **3. Pengenalan Triggers**

### **Apa Itu Trigger?**
Trigger adalah perintah SQL yang dieksekusi secara otomatis ketika suatu kejadian tertentu terjadi dalam basis data, seperti INSERT, UPDATE, atau DELETE. Triggers sering digunakan untuk menjaga integritas data atau untuk melakukan tindakan otomatis.

### **Fungsi Utama Triggers:**
- **Otomatisasi Tugas:** Menjalankan logika tertentu secara otomatis saat data dimanipulasi.
- **Konsistensi Data:** Memastikan bahwa setiap perubahan data memenuhi aturan tertentu.
- **Keamanan:** Membatasi atau memantau perubahan yang dilakukan pada data sensitif.

### **Mengapa Triggers Penting?**
Triggers berguna untuk mengelola perubahan yang dilakukan pada data. Misalnya, setiap kali ada pesanan baru ditambahkan, trigger bisa otomatis memperbarui stok barang.

## **4. Membuat dan Menggunakan Triggers**

### **Cara Membuat Trigger:**
Untuk membuat trigger, gunakan perintah `CREATE TRIGGER` diikuti dengan logika SQL yang ingin dijalankan saat trigger tersebut dipicu.

**Contoh Dasar:**
```sql
CREATE TRIGGER UpdateStok
AFTER INSERT ON Pesanan
FOR EACH ROW
BEGIN
    UPDATE Produk SET Stok = Stok - NEW.Jumlah WHERE ID_Produk = NEW.ID_Produk;
END;
```
- Trigger ini akan mengurangi stok produk setiap kali pesanan baru ditambahkan.

### **Jenis-Jenis Triggers:**
- **BEFORE Trigger:** Dijalankan sebelum operasi INSERT, UPDATE, atau DELETE dilakukan.
- **AFTER Trigger:** Dijalankan setelah operasi INSERT, UPDATE, atau DELETE dilakukan.

### **Contoh Kasus Penggunaan Triggers:**
Misalnya, kalian ingin memastikan bahwa tidak ada pesanan yang bisa dibuat jika stok produk habis. Kalian bisa membuat `BEFORE INSERT` trigger yang mengecek stok sebelum pesanan diproses.

## **5. Contoh Implementasi dalam Skenario Nyata**

### **Skenario: Sistem Manajemen Gudang**

**Stored Procedure:**
Kalian memiliki stored procedure untuk memeriksa stok minimum produk setiap hari:
```sql
CREATE PROCEDURE CekStokMin()
BEGIN
    SELECT * FROM Produk WHERE Stok < 10;
END;
```
- Stored procedure ini membantu manajer gudang memastikan tidak ada produk yang hampir habis tanpa disadari.

**Trigger:**
Trigger yang otomatis mengurangi stok produk ketika pesanan ditambahkan:
```sql
CREATE TRIGGER KurangiStok
AFTER INSERT ON Pesanan
FOR EACH ROW
BEGIN
    UPDATE Produk SET Stok = Stok - NEW.Jumlah WHERE ID_Produk = NEW.ID_Produk;
END;
```
- Trigger ini memastikan stok selalu terupdate tanpa harus dilakukan manual oleh staf gudang.

### **Mengapa Implementasi Ini Penting?**
Dalam sistem manajemen gudang, otomatisasi seperti ini sangat penting untuk efisiensi dan mencegah kesalahan manusia, terutama ketika kalian berurusan dengan inventaris yang besar dan beragam.

---

### **Aktivitas**

1. **Diskusi Kelompok:**
    - **Topik:** Bagaimana kalian bisa menggunakan stored procedures dan triggers untuk mengotomatisasi tugas-tugas rutin dalam basis data kalian?
    - **Tujuan:** Memahami peran stored procedures dan triggers dalam meningkatkan efisiensi dan menjaga integritas data dalam basis data.

2. **Latihan:**
    - **Tugas:** Buat stored procedure untuk melakukan kalkulasi tertentu di basis data kalian dan buat trigger untuk menangani otomatisasi tugas yang sering terjadi. Uji coba dengan data nyata untuk melihat bagaimana keduanya bekerja.
    - **Output:** Kode SQL untuk stored procedures dan triggers, serta laporan singkat tentang bagaimana mereka mempengaruhi operasi basis data kalian.

---
[⏮ Transaksi dan Optimasi Query](../7-transaksi-dan-optimasi-query/README.md) || [Home 🏘](../README.md) || [Case dan NoSQL ⏭](../9-case-dan-nosql/README.md)