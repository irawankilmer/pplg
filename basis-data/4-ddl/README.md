# **Bab 4 - Data Definition Language (DDL)**

## **Tujuan Pembelajaran**
Setelah pertemuan ini, kalian diharapkan:
- Memahami fungsi dan penggunaan DDL dalam SQL untuk mengelola struktur basis data.
- Mampu membuat, mengubah, dan menghapus tabel serta menerapkan constraint seperti primary key dan foreign key.
- Familiar dengan bagaimana DDL digunakan untuk membangun fondasi basis data yang kuat dan terstruktur.

## **Materi yang Akan Dibahas**
1. Pengenalan Data Definition Language (DDL)
2. Perintah CREATE untuk Membuat Tabel dan Menentukan Tipe Data
3. Perintah ALTER untuk Mengubah Struktur Tabel
4. Perintah DROP untuk Menghapus Tabel
5. Penerapan Constraint: PRIMARY KEY, FOREIGN KEY, UNIQUE, CHECK

---

## **1. Pengenalan Data Definition Language (DDL)**

### **Apa Itu DDL?**
DDL, atau **Data Definition Language**, adalah bagian dari SQL yang digunakan untuk mendefinisikan dan mengelola struktur basis data. DDL mencakup perintah-perintah untuk membuat, mengubah, dan menghapus objek dalam basis data seperti tabel, indeks, dan views.

### **Fungsi Utama DDL:**
- **Membangun Struktur:** DDL digunakan untuk menciptakan tabel-tabel yang akan menyimpan data kalian.
- **Menyesuaikan Struktur:** Mengubah struktur tabel jika ada kebutuhan untuk menambah atau mengubah kolom.
- **Menghapus Struktur:** Menghapus tabel atau objek lain yang sudah tidak diperlukan.

### **Contoh DDL dalam Kehidupan Sehari-hari:**
Bayangkan kalian sedang membangun sebuah rumah. DDL ini seperti peta dan alat yang kalian gunakan untuk menentukan di mana dinding, pintu, dan jendela akan ditempatkan. Kalian membuat struktur dasar dari sesuatu yang nantinya akan diisi dengan data, sama seperti kalian mengisi rumah dengan furnitur setelah bangunan selesai.

## **2. Perintah CREATE untuk Membuat Tabel dan Menentukan Tipe Data**

### **Perintah CREATE:**
Perintah `CREATE` digunakan untuk membuat objek baru dalam basis data. Objek yang paling umum dibuat dengan DDL adalah tabel.

**Contoh Membuat Tabel:**
```sql
CREATE TABLE Pelanggan (
    ID_Pelanggan INT PRIMARY KEY,
    Nama VARCHAR(100),
    Alamat TEXT,
    Tanggal_Lahir DATE
);
```
- **ID_Pelanggan:** Ini adalah kolom yang akan menjadi Primary Key, artinya setiap pelanggan akan memiliki ID unik.
- **Nama:** Tipe data VARCHAR digunakan untuk menyimpan teks yang panjangnya bisa bervariasi.
- **Alamat:** Tipe data TEXT digunakan untuk menyimpan teks yang lebih panjang.
- **Tanggal_Lahir:** Tipe data DATE digunakan untuk menyimpan informasi tanggal.

### **Tipe Data Umum dalam SQL:**
- **INT:** Angka bulat.
- **VARCHAR(n):** Teks dengan panjang maksimal n karakter.
- **TEXT:** Teks dengan panjang yang tidak ditentukan.
- **DATE:** Tanggal (tahun, bulan, hari).
- **BOOLEAN:** Nilai benar atau salah.

**Contoh Kasus:**
Misalnya, kalian ingin menyimpan data produk di toko online:
```sql
CREATE TABLE Produk (
    ID_Produk INT PRIMARY KEY,
    Nama_Produk VARCHAR(255),
    Harga DECIMAL(10, 2),
    Stok INT,
    Tanggal_Ditambahkan DATE
);
```

## **3. Perintah ALTER untuk Mengubah Struktur Tabel**

### **Perintah ALTER:**
Ketika tabel sudah dibuat, mungkin suatu saat kalian butuh menambahkan kolom baru, mengubah tipe data kolom yang ada, atau bahkan menghapus kolom. Untuk itulah perintah `ALTER` digunakan.

**Contoh Menambah Kolom:**
```sql
ALTER TABLE Pelanggan ADD Email VARCHAR(100);
```

**Contoh Mengubah Tipe Data Kolom:**
```sql
ALTER TABLE Pelanggan MODIFY Nama VARCHAR(150);
```

**Contoh Menghapus Kolom:**
```sql
ALTER TABLE Pelanggan DROP COLUMN Alamat;
```

### **Kapan Menggunakan ALTER?**
Bayangkan kalian punya toko, dan seiring waktu kalian ingin menambahkan fitur baru seperti email notifikasi kepada pelanggan. Dengan `ALTER`, kalian bisa menambahkan kolom email ke dalam tabel tanpa harus membuat ulang tabel dari awal.

## **4. Perintah DROP untuk Menghapus Tabel**

### **Perintah DROP:**
Perintah `DROP` digunakan untuk menghapus objek dari basis data, seperti tabel atau indeks. Jika kalian tidak lagi membutuhkan tabel atau objek tertentu, kalian bisa menghapusnya secara permanen dengan `DROP`.

**Contoh Menghapus Tabel:**
```sql
DROP TABLE Produk;
```

### **Pentingnya Hati-hati dengan DROP:**
Perintah `DROP` ini sangat kuat, karena ketika kalian menghapus tabel, semua data yang ada di dalamnya juga akan hilang. Jadi, pastikan kalian benar-benar tidak memerlukan tabel tersebut sebelum menjalankan perintah ini.

## **5. Penerapan Constraint: PRIMARY KEY, FOREIGN KEY, UNIQUE, CHECK**

### **Apa Itu Constraint?**
Constraint adalah aturan yang diterapkan pada kolom dalam tabel untuk memastikan integritas data. Beberapa jenis constraint yang umum adalah:

- **PRIMARY KEY:** Menjamin bahwa setiap nilai dalam kolom unik dan tidak kosong. Contoh: `ID_Pelanggan`.
- **FOREIGN KEY:** Menghubungkan kolom di satu tabel dengan PRIMARY KEY di tabel lain. Contoh: `ID_Pelanggan` di tabel `Pesanan`.
- **UNIQUE:** Menjamin bahwa semua nilai dalam kolom adalah unik (tidak ada duplikat).
- **CHECK:** Memastikan bahwa nilai dalam kolom memenuhi kondisi tertentu.

### **Contoh Penerapan PRIMARY KEY dan FOREIGN KEY:**
```sql
CREATE TABLE Pesanan (
    ID_Pesanan INT PRIMARY KEY,
    Tanggal DATE,
    ID_Pelanggan INT,
    FOREIGN KEY (ID_Pelanggan) REFERENCES Pelanggan(ID_Pelanggan)
);
```

### **Contoh Penerapan UNIQUE dan CHECK:**
```sql
CREATE TABLE Karyawan (
    ID_Karyawan INT PRIMARY KEY,
    Nama VARCHAR(100),
    Email VARCHAR(100) UNIQUE,
    Gaji DECIMAL(10, 2),
    CHECK (Gaji > 0)
);
```

### **Mengapa Constraint Penting?**
Constraint ini seperti aturan main dalam basis data. Mereka memastikan bahwa data yang kalian masukkan benar dan sesuai dengan yang diharapkan. Misalnya, kalian tidak bisa menambahkan pesanan jika pelanggan tidak ada di dalam tabel `Pelanggan`, atau kalian tidak bisa memasukkan email yang sama untuk dua karyawan yang berbeda.

---

### **Aktivitas**

1. **Diskusi Kelompok:**
    - **Topik:** Mengapa penting untuk memastikan struktur tabel sudah benar sebelum menambahkan data?
    - **Tujuan:** Memahami peran penting DDL dan constraint dalam menjaga integritas data dalam basis data.

2. **Latihan:**
    - **Tugas:** Buat tabel baru untuk menyimpan data karyawan di perusahaan kalian, lengkap dengan constraint yang sesuai. Gunakan perintah `CREATE`, `ALTER`, dan `DROP` untuk memodifikasi tabel jika diperlukan.
    - **Output:** Kode SQL dan penjelasan singkat tentang apa yang dilakukan setiap bagian dari kode tersebut.