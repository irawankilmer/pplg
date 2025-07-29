# **Bab 13 - Database Driver: PDO (PHP 8.3+)**

## **Tujuan Pembelajaran**

Pada akhir pertemuan ini, kalian diharapkan mampu:

* Memahami konsep PDO dan keunggulannya dibandingkan ekstensi lain.
* Menguasai cara koneksi ke database menggunakan PDO.
* Menggunakan fitur prepared statements untuk mencegah SQL injection.
* Menerapkan mode fetch data (`FETCH_ASSOC`, `FETCH_OBJ`, dll.) sesuai kebutuhan.
* Melaksanakan operasi CRUD menggunakan PDO.
* Menangani error dan debugging saat bekerja dengan PDO.
* Memahami praktik terbaik penggunaan PDO pada aplikasi skala kecil hingga menengah.

---

## **1. Pengantar PDO**

### Apa Itu PDO?

PDO (PHP Data Objects) adalah antarmuka berbasis objek di PHP untuk mengakses berbagai jenis database secara konsisten. PDO mendukung lebih dari 12 jenis database seperti MySQL, PostgreSQL, SQLite, Oracle, SQL Server, dll.

### Mengapa Menggunakan PDO?

* ✅ *Keamanan*: Mendukung **prepared statements** untuk mencegah SQL Injection.
* ✅ *Portabilitas*: Kode dapat dipindahkan ke DBMS lain tanpa banyak perubahan.
* ✅ *Fleksibilitas*: Mendukung berbagai mode pengambilan data.
* ✅ *Fitur Modern*: Mendukung exception handling, transaksi, dan fetch style.

---

## **2. Membuat Koneksi PDO**

### Sintaks Umum:

```php
$pdo = new PDO("mysql:host=localhost;dbname=sekolah", "root", "");
$pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
```

### Parameter:

* **DSN (Data Source Name)**: Format `driver:host=...;dbname=...`
* **Username dan Password**
* **Opsi Atribut PDO**:

  ```php
  $pdo->setAttribute(PDO::ATTR_DEFAULT_FETCH_MODE, PDO::FETCH_ASSOC);
  ```

---

## **3. Prepared Statements**

### Kenapa Penting?

Prepared statement mencegah SQL injection dengan cara memisahkan struktur query dan data.

### Sintaks:

```php
$stmt = $pdo->prepare("SELECT * FROM siswa WHERE id = :id");
$stmt->execute(["id" => 1]);
$row = $stmt->fetch();
```

### Jenis Placeholder:

* `?` (Posisi) → `$stmt->execute([1]);`
* `:nama` (Named) → `$stmt->execute(['nama' => 'Alya']);`

---

## **4. Mode Pengambilan Data (Fetch Mode)**

| Mode               | Deskripsi                              |
| ------------------ | -------------------------------------- |
| `PDO::FETCH_ASSOC` | Array asosiatif dengan nama kolom      |
| `PDO::FETCH_NUM`   | Array numerik berdasarkan indeks kolom |
| `PDO::FETCH_BOTH`  | Kombinasi keduanya (default lama)      |
| `PDO::FETCH_OBJ`   | Objek PHP standar (akses via properti) |
| `PDO::FETCH_CLASS` | Objek dari class tertentu              |

### Contoh:

```php
$stmt = $pdo->query("SELECT * FROM siswa");
$data = $stmt->fetchAll(PDO::FETCH_OBJ);
echo $data[0]->nama;
```

---

## **5. CRUD Menggunakan PDO**

### a. Create

```php
$sql = "INSERT INTO siswa (nama, email) VALUES (:nama, :email)";
$stmt = $pdo->prepare($sql);
$stmt->execute(['nama' => 'Rani', 'email' => 'rani@example.com']);
```

### b. Read

```php
$sql = "SELECT * FROM siswa WHERE id = :id";
$stmt = $pdo->prepare($sql);
$stmt->execute(['id' => 1]);
$siswa = $stmt->fetch(PDO::FETCH_ASSOC);
```

### c. Update

```php
$sql = "UPDATE siswa SET nama = :nama WHERE id = :id";
$stmt = $pdo->prepare($sql);
$stmt->execute(['nama' => 'Rani Baru', 'id' => 1]);
```

### d. Delete

```php
$sql = "DELETE FROM siswa WHERE id = :id";
$stmt = $pdo->prepare($sql);
$stmt->execute(['id' => 1]);
```

---

## **6. Penanganan Error dan Debugging**

### Try...Catch Block

```php
try {
    $pdo = new PDO($dsn, $user, $pass);
    $pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
} catch (PDOException $e) {
    echo "Koneksi gagal: " . $e->getMessage();
}
```

### Debug Mode:

```php
$pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_WARNING);
```

---

## **7. Studi Kasus: Aplikasi Data Siswa**

### Fitur:

* Form input siswa (nama & email)
* Tampilkan daftar siswa
* Edit dan hapus data siswa

### Struktur File:

```
📁 siswa_app/
 ├── index.php
 ├── tambah.php
 ├── edit.php
 ├── hapus.php
 └── koneksi.php
```

### Koneksi (koneksi.php):

```php
<?php
$pdo = new PDO("mysql:host=localhost;dbname=sekolah", "root", "");
$pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
?>
```

---

## **8. Tips dan Best Practice**

* Selalu gunakan **prepared statement** — tidak ada alasan menggunakan query mentah.
* Gunakan `try...catch` di semua operasi database.
* Atur `PDO::ATTR_DEFAULT_FETCH_MODE` ke `PDO::FETCH_ASSOC` agar lebih ringkas.
* Gunakan transaksi (`beginTransaction()`, `commit()`, `rollBack()`) untuk operasi kompleks.
* Pisahkan koneksi ke file sendiri agar mudah digunakan ulang.

---

## **9. Aktivitas Siswa**

### 🔍 Diskusi:

* Apa perbedaan utama antara PDO dan MySQLi?
* Dalam kondisi apa `FETCH_OBJ` lebih baik daripada `FETCH_ASSOC`?

### 🧠 Latihan:

1. Buat form tambah data siswa (PDO + validasi dasar).
2. Tampilkan data dalam tabel.
3. Buat fitur edit dan hapus siswa.
4. Bonus: Tambahkan fitur pencarian nama siswa.

---

## **10. Referensi Resmi**

* [PHP Manual: PDO](https://www.php.net/manual/en/book.pdo.php)
* [PHP.net - PDOStatement](https://www.php.net/manual/en/class.pdostatement.php)
* [PHP 8.3 Docs](https://www.php.net/releases/8.3/en.php)

---
### Navigasi
[⏮ Database Driver Intro](../11-database-driver-intro/README.md) || [Home 🏘](../README.md) || [Database Driver MySqli Prosedural ⏭](../13-database-driver-mysqli-prosedural/README.md)