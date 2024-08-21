# **Bab 12 - Database Driver: PDO**

## **Tujuan Pembelajaran**
Pada akhir pertemuan ini, kalian diharapkan mampu:
- Memahami fungsi-fungsi dasar PDO yang sering digunakan.
- Menggunakan PDO untuk mengelola koneksi ke database, menjalankan query, dan menangani error.
- Memahami dan memilih metode pengambilan data (`fetch_assoc()`, `fetch_row()`, `fetch_array()`, `fetch_object()`, `fetch_all()`) yang paling sesuai berdasarkan kebutuhan.
- Mengimplementasikan fungsi-fungsi PDO dalam skenario CRUD (Create, Read, Update, Delete).

## **Materi yang Akan Dibahas**
1. Pengantar PDO
2. Fungsi-Fungsi Dasar PDO
   - `PDO::__construct()`
   - `PDO::setAttribute()`
   - **`PDO::prepare()` dan `PDOStatement::execute()`** (Penjelasan Lengkap)
   - **Metode Pengambilan Data PDO:**
     - `PDO::fetch()`
     - `PDO::fetchAll()`
     - **`PDO::fetch_assoc()`**
     - **`PDO::fetch_row()`**
     - **`PDO::fetch_array()`**
     - **`PDO::fetch_object()`**
3. Implementasi CRUD dengan PDO
   - Create (Membuat Data)
   - Read (Membaca Data)
   - Update (Memperbarui Data)
   - Delete (Menghapus Data)
4. Studi Kasus: Implementasi PDO dalam Aplikasi Sederhana

---

## **1. Pengantar PDO**

### **Apa Itu PDO?**
PDO (PHP Data Objects) adalah sebuah interface di PHP yang menyediakan cara konsisten untuk mengakses berbagai jenis database. PDO mendukung banyak database, termasuk MySQL, PostgreSQL, SQLite, dan banyak lagi. Selain itu, PDO menawarkan berbagai fitur canggih seperti prepared statements, transaksi, dan penanganan error.

## **2. Fungsi-Fungsi Dasar PDO**

### **1. `PDO::__construct()`**
Ini adalah konstruktor yang digunakan untuk membuat objek PDO baru dan menghubungkan aplikasi kalian ke database.

**Sintaks:**
```php
$pdo = new PDO('dsn', 'username', 'password');
```

### **2. `PDO::setAttribute()`**
Fungsi ini digunakan untuk mengatur atribut tertentu pada objek PDO, seperti mode penanganan error.

**Sintaks:**
```php
$pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
```

### **3. **`PDO::prepare()` dan `PDOStatement::execute()` (Penjelasan Lengkap)****

Prepared statements adalah fitur yang sangat penting dalam PDO karena memberikan dua keuntungan utama: meningkatkan keamanan aplikasi kalian terhadap serangan SQL Injection dan meningkatkan performa query yang sering dijalankan.

**Jenis Placeholder:**
1. **Positional Placeholder (`?`)**
2. **Named Placeholder (`:name`)**

#### **`PDOStatement::execute()`**
`PDOStatement::execute()` digunakan untuk mengeksekusi query yang telah dipersiapkan dengan `PDO::prepare()`. 

**Return Values:**
- `execute()` mengembalikan nilai `true` jika query berhasil dieksekusi, dan `false` jika gagal.

### **Metode Pengambilan Data PDO:**

Ketika kalian mengeksekusi query SELECT dengan PDO, kalian perlu mengambil hasilnya. PDO menyediakan berbagai metode untuk melakukan ini, masing-masing dengan kelebihan tersendiri tergantung pada skenario penggunaan.

### **1. `PDO::fetch()`**
`PDO::fetch()` digunakan untuk mengambil satu baris hasil query. Ini berguna jika kalian hanya mengharapkan satu hasil dari query atau ingin mengiterasi hasil satu per satu.

**Sintaks:**
```php
$row = $stmt->fetch(PDO::FETCH_ASSOC);
```

**Opsi Mode Fetch:**
- **`PDO::FETCH_ASSOC`**: Mengembalikan hasil sebagai array asosiatif, di mana nama kolom menjadi kunci.
- **`PDO::FETCH_NUM`**: Mengembalikan hasil sebagai array numerik, di mana indeks adalah urutan kolom.
- **`PDO::FETCH_BOTH`**: Mengembalikan hasil sebagai array dengan kunci asosiatif dan numerik.
- **`PDO::FETCH_OBJ`**: Mengembalikan hasil sebagai objek, di mana nama kolom menjadi properti objek.

**Kapan Menggunakan?**
- Gunakan `PDO::fetch()` ketika kalian hanya membutuhkan satu baris data atau ingin mengambil data baris demi baris, misalnya dalam loop.

### **2. `PDO::fetchAll()`**
`PDO::fetchAll()` digunakan untuk mengambil semua baris dari hasil query sekaligus.

**Sintaks:**
```php
$rows = $stmt->fetchAll(PDO::FETCH_ASSOC);
```

**Kapan Menggunakan?**
- Gunakan `PDO::fetchAll()` ketika kalian membutuhkan semua hasil query sekaligus, misalnya untuk menampilkan seluruh daftar produk di halaman.

### **3. **`PDO::fetch_assoc()`**

`PDO::fetch_assoc()` tidak secara langsung tersedia dalam PDO, tetapi kalian bisa mencapainya menggunakan `PDO::FETCH_ASSOC` dalam `PDO::fetch()` atau `PDO::fetchAll()`.

### **4. **`PDO::fetch_row()`**

`PDO::fetch_row()` tidak secara langsung tersedia dalam PDO, tetapi kalian bisa mencapainya menggunakan `PDO::FETCH_NUM` dalam `PDO::fetch()` atau `PDO::fetchAll()`.

### **5. **`PDO::fetch_array()`**

`PDO::fetch_array()` tidak secara langsung tersedia dalam PDO, tetapi kalian bisa mencapainya menggunakan `PDO::FETCH_BOTH` dalam `PDO::fetch()` atau `PDO::fetchAll()`.

### **6. **`PDO::fetch_object()`**

`PDO::fetch_object()` tidak secara langsung tersedia dalam PDO, tetapi kalian bisa mencapainya menggunakan `PDO::FETCH_OBJ` dalam `PDO::fetch()` atau `PDO::fetchAll()`.

### **Kesimpulan Pemilihan:**
- **Gunakan `fetch_assoc()`** ketika kalian hanya membutuhkan data dengan nama kolom sebagai kunci.
- **Gunakan `fetch_row()`** ketika kalian lebih nyaman dengan indeks numerik.
- **Gunakan `fetch_array()`** ketika kalian membutuhkan keduanya.
- **Gunakan `fetch_object()`** ketika kalian lebih nyaman mengakses data sebagai properti objek, terutama jika bekerja dalam lingkungan OOP.

## **3. Implementasi CRUD dengan PDO**

### **Create (Membuat Data)**
```php
<?php
$sql = "INSERT INTO siswa (nama, email) VALUES (:nama, :email)";
$stmt = $pdo->prepare($sql);
$stmt->execute(['nama' => 'Alya', 'email' => 'alya@example.com']);

echo "Data berhasil ditambahkan! ID terakhir: " . $pdo->lastInsertId();
?>
```

### **Read (Membaca Data)**
```php
<?php
$sql = "SELECT * FROM siswa WHERE id = :id";
$stmt = $pdo->prepare($sql);
$stmt->execute(['id' => 1]);
$siswa = $stmt->fetch(PDO::FETCH_ASSOC);

echo "Nama: " . $siswa['nama'] . " - Email: " . $siswa['email'];
?>
```

### **Update (Memperbarui Data)**
```php
<?php
$sql = "UPDATE siswa SET email = :email WHERE id = :id";
$stmt = $pdo->prepare($sql);
$stmt->execute(['email' => 'alyabaru@example.com', 'id' => 1]);

echo "Data berhasil diperbarui!";
?>
```

### **Delete (Menghapus Data)**
```php
<?php
$sql = "DELETE FROM siswa WHERE id = :id";
$stmt = $pdo->prepare($sql);
$stmt->execute(['id' => 1]);

echo "Data berhasil dihapus!";
?>
```

## **4. Studi Kasus: Implementasi PDO dalam Aplikasi Sederhana**

### **Deskripsi Masalah**
Kita akan membuat aplikasi sederhana untuk mengelola data siswa menggunakan PDO. Aplikasi ini akan mencakup fitur untuk menambah, membaca, memperbarui, dan menghapus data siswa dari database.

### **Langkah-Langkah Implementasi:**

1. **Membuat Koneksi PDO ke Database:**
   - Gunakan contoh kode koneksi di atas untuk menghubungkan aplikasi ke database.

2. **Mengimplementasikan CRUD:**
   - Gunakan contoh kode CRUD untuk membuat, membaca, memperbarui, dan menghapus data siswa.

3. **Menambahkan Fitur Keamanan:**
   - Gunakan prepared statements untuk semua query.
   - Implementasikan transaksi jika ada lebih dari satu operasi yang harus dijalankan bersama.

### **Kesimpulan**
Dengan memahami dan menggunakan metode pengambilan data di PDO, kalian dapat menyesuaikan cara kalian mengambil hasil query sesuai kebutuhan aplikasi. Memilih metode yang tepat berdasarkan skenario dapat meningkatkan efisiensi dan kemudahan pemeliharaan aplikasi kalian.

---

### **Aktivitas**

1. **Diskusi Kelompok:**
   - **Topik:** Bagaimana memilih metode fetch yang tepat berdasarkan skenario yang kalian hadapi?
   - **Tujuan:** Memahami kapan menggunakan masing-masing metode fetch di PDO.

2. **Latihan:**
   - **Tugas:** Buatlah aplikasi PHP sederhana yang mengimplementasikan CRUD menggunakan PDO dengan berbagai metode fetch, dan tentukan kapan menggunakan masing-masing metode berdasarkan kebutuhan.

---
### Navigasi
[⏮ Database Driver Intro](../11-database-driver-intro/README.md) || [Home 🏘](../README.md) || [Database Driver MySqli Prosedural ⏭](../13-database-driver-mysqli-prosedural/README.md)