# Bab 12 - Pengenalan Database Driver dalam PHP

---

## Tujuan Pembelajaran

Setelah mempelajari bab ini, siswa diharapkan:

* Memahami konsep "Database Driver" dalam konteks pemrograman PHP.
* Mengetahui sejarah dan perkembangan driver database dalam PHP.
* Mengenal dan membedakan driver `mysql`, `mysqli`, dan `PDO` secara mendalam.
* Mengetahui keunggulan dan kekurangan masing-masing driver.
* Dapat menentukan driver yang paling sesuai dalam berbagai kebutuhan aplikasi.
* Mampu membuat koneksi dan menjalankan query sederhana menggunakan `MySQLi` dan `PDO`.
* Menyadari isu keamanan dan praktik terbaik dalam koneksi database.

---

## 1. Apa Itu Database Driver?

Database Driver adalah **komponen atau antarmuka (interface)** yang memungkinkan sebuah bahasa pemrograman (dalam hal ini PHP) untuk **terhubung dan berinteraksi** dengan database seperti MySQL, PostgreSQL, SQLite, Oracle, dsb.

Secara teknis, driver bertugas menghubungkan antara perintah PHP dengan sistem database agar:

* PHP dapat mengirim kueri SQL.
* PHP dapat menerima hasil dari database.
* PHP dapat mengelola error, transaksi, dan fitur lainnya.

Tanpa driver, PHP tidak bisa membaca atau memanipulasi data di dalam database.

---

## 2. Sejarah Driver Database di PHP

### 2.1 `mysql_*` Extension (Driver Lama, Deprecated)

* Diperkenalkan sejak PHP versi 2.x hingga 5.x.
* Fungsi umum: `mysql_connect()`, `mysql_query()`, `mysql_fetch_assoc()`, dll.
* Sifat: **Procedural** (bukan OOP).
* Kelemahan:

  * Tidak mendukung **prepared statement**.
  * Tidak mendukung **transaction**.
  * Tidak mendukung **stored procedure**.
  * **Rentan terhadap SQL Injection**.
  * Tidak konsisten dalam penanganan error.

> Deprecated sejak PHP 5.5 (2013), dan dihapus permanen di PHP 7.0 (2015).

### 2.2 `mysqli` (MySQL Improved)

* Diperkenalkan di PHP 5 untuk menggantikan `mysql_*`.
* Dukungan untuk **MySQL 4.1+**.
* Bisa digunakan dalam dua gaya:

  * Procedural: `mysqli_connect()`, `mysqli_query()`
  * Object-Oriented: `$conn = new mysqli(...)`
* Fitur penting:

  * **Prepared Statement**
  * **Transaction support**
  * **Multiple Statements**
  * **Stored Procedures**
  * **Binding Result / Input Parameter**

### 2.3 PDO (PHP Data Objects)

* Diperkenalkan sejak PHP 5.1 sebagai interface universal database.
* Berbasis **Object-Oriented**.
* Mendukung banyak database:

  * MySQL, PostgreSQL, SQLite, Oracle, IBM, Firebird, dll.
* Fitur:

  * Prepared Statement
  * Error Handling dengan Exception
  * Flexibilitas Query
  * Transaksi

---

## 3. Jenis Driver Database di PHP

| Driver    | Mendukung Database            | Mode             | Fitur Modern | Keterangan                       |
| --------- | ----------------------------- | ---------------- | ------------ | -------------------------------- |
| `mysql`   | MySQL                         | Procedural       | ❌            | Usang, tidak aman, sudah dihapus |
| `mysqli`  | MySQL                         | Procedural + OOP | ✅            | Direkomendasikan untuk MySQL     |
| `PDO`     | Multi DB (MySQL, SQLite, dsb) | OOP              | ✅            | Aman, fleksibel, modern          |
| `ODBC`    | Umum (via driver OS)          | Procedural       | ⚠️ Terbatas  | Butuh konfigurasi tambahan       |
| `SQLite3` | SQLite                        | OOP              | ✅            | Untuk aplikasi ringan            |

---

## 4. Perbandingan `mysql` vs `mysqli` vs `PDO`

### 4.1 `mysql` (Usang)

* Sangat terbatas dan tidak aman.
* Tidak bisa menangani parameter input.
* Contoh:

```php
$conn = mysql_connect("localhost", "root", "");
mysql_select_db("dbku", $conn);
$result = mysql_query("SELECT * FROM siswa");
```

* Status: ❌ Tidak boleh digunakan lagi.

### 4.2 `mysqli`

* Modern, cepat, aman.
* Support banyak fitur terbaru MySQL.
* Bisa digunakan dengan gaya procedural atau OOP.
* Contoh koneksi:

```php
$conn = new mysqli("localhost", "root", "", "dbku");
$result = $conn->query("SELECT * FROM siswa");
```

### 4.3 `PDO`

* Modern, fleksibel, aman.
* Bisa dipakai untuk banyak jenis database.
* Hanya mendukung gaya Object-Oriented.
* Contoh koneksi:

```php
$dsn = "mysql:host=localhost;dbname=dbku";
$conn = new PDO($dsn, "root", "");
$stmt = $conn->query("SELECT * FROM siswa");
```

---

## 5. Kelebihan dan Kekurangan

| Aspek              | `mysqli`                 | `PDO`                           |
| ------------------ | ------------------------ | ------------------------------- |
| Dukungan DB        | Hanya MySQL              | Banyak (MySQL, PostgreSQL, dll) |
| Mode               | Procedural + OOP         | Hanya OOP                       |
| Prepared Statement | ✅ Ya                     | ✅ Ya                            |
| Portabilitas       | ❌ Rendah                 | ✅ Tinggi                        |
| Kinerja            | Optimal untuk MySQL      | Sedikit lebih lambat            |
| Keamanan           | ✅ Aman (prepared)        | ✅ Aman (prepared)               |
| Learning Curve     | Mudah untuk pemula MySQL | Sedikit lebih kompleks          |

---

## 6. Praktik Terbaik

* Selalu gunakan **Prepared Statement** untuk mencegah SQL Injection.
* Gunakan `PDO` jika proyek bersifat portabel atau ingin mendukung banyak database.
* Gunakan `MySQLi` jika hanya menggunakan MySQL dan ingin memanfaatkan fitur spesifiknya.
* Hindari menggunakan fungsi `mysql_*`.
* Selalu validasi hasil koneksi.
* Tangani error dengan try-catch (`PDO`) atau pengecekan error (`MySQLi`).

---

## 7. Aktivitas & Tugas

### Aktivitas Diskusi:

* Apa risiko yang ditimbulkan jika masih menggunakan `mysql_*`?
* Kapan harus menggunakan `PDO`, dan kapan cukup dengan `MySQLi`?

### Tugas Latihan:

1. Buat koneksi ke database `perpustakaan` menggunakan `mysqli` (OOP).
2. Buat koneksi ke database yang sama menggunakan `PDO`.
3. Buat form input siswa yang datanya disimpan ke database menggunakan prepared statement (dengan mysqli dan PDO).
4. Simulasikan pemindahan kode dari MySQL ke PostgreSQL. Analisa kode mana yang tetap, dan mana yang perlu diubah.

---

## 8. Kesimpulan

* PHP telah berevolusi dari `mysql_*` ke `mysqli` dan `PDO` untuk peningkatan keamanan dan fleksibilitas.
* `mysql_*` sudah tidak didukung lagi dan harus dihindari.
* `mysqli` cocok untuk penggunaan MySQL secara khusus.
* `PDO` cocok untuk proyek jangka panjang, multi-database, atau proyek dengan keamanan tinggi.
* Penggunaan driver yang tepat berdampak besar pada keamanan, performa, dan kemudahan migrasi aplikasi.

---

## Navigasi

[⏮ Bab Sebelumnya](../10-form-handling/README.md) | [🏠 Beranda](../README.md) | [⏭ Lanjut: PDO Mendalam](../13-pdo-detail/README.md)
