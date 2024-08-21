# **Bab 13 - Database Driver: MySQLi dengan Pendekatan Prosedural**

## **Tujuan Pembelajaran**
Setelah menyelesaikan bab ini, kalian diharapkan dapat:
- Memahami dasar penggunaan MySQLi dengan pendekatan prosedural.
- Menghubungkan aplikasi PHP ke database MySQL dengan MySQLi.
- Melakukan operasi CRUD (Create, Read, Update, Delete) menggunakan MySQLi.
- Memilih metode pengambilan data yang sesuai dengan kebutuhan.

## **Materi yang Akan Dibahas**
1. Pengantar MySQLi
2. Menghubungkan PHP ke MySQL
3. Fungsi-Fungsi MySQLi yang Sering Digunakan
   - `mysqli_connect()`
   - `mysqli_query()`
   - Metode Mengambil Data:
     - `mysqli_fetch_assoc()`
     - `mysqli_fetch_row()`
     - `mysqli_fetch_array()`
     - `mysqli_fetch_object()`
     - `mysqli_fetch_all()`
   - `mysqli_real_escape_string()`
   - `mysqli_close()`
4. Praktik CRUD (Create, Read, Update, Delete) dengan MySQLi

---

## **1. Pengantar MySQLi**

### **Apa Itu MySQLi?**
MySQLi, singkatan dari MySQL Improved, adalah sebuah ekstensi PHP yang digunakan untuk berkomunikasi dengan database MySQL. MySQLi menyediakan berbagai fitur canggih, seperti dukungan untuk prepared statements, transaksi, dan multi-query.

### **Pendekatan Prosedural dalam MySQLi**
Pendekatan prosedural menggunakan fungsi-fungsi PHP tradisional untuk melakukan berbagai operasi dengan MySQL. Ini adalah pendekatan yang sederhana dan sangat mirip dengan cara-cara lama yang mungkin sudah kalian kenal.

## **2. Menghubungkan PHP ke MySQL**

Sebelum melakukan operasi apa pun pada database, hal pertama yang harus kita lakukan adalah menghubungkan aplikasi PHP ke database MySQL.

### **Contoh Koneksi:**
```php
<?php
$servername = "localhost";
$username = "root";
$password = "password_kalian";
$dbname = "nama_database";

// Membuat koneksi
$conn = mysqli_connect($servername, $username, $password, $dbname);

// Cek koneksi
if (!$conn) {
    die("Koneksi gagal: " . mysqli_connect_error());
}
echo "Koneksi berhasil!";
?>
```

### **Penjelasan:**
- **`mysqli_connect()`** digunakan untuk menghubungkan PHP ke database MySQL. Jika koneksi gagal, `mysqli_connect_error()` akan memberi tahu kita apa yang salah.

## **3. Fungsi-Fungsi MySQLi yang Sering Digunakan**

Setelah terhubung ke database, kita akan menggunakan beberapa fungsi dasar untuk berinteraksi dengan data.

### **1. `mysqli_connect()`**
Ini fungsi yang digunakan untuk menghubungkan aplikasi PHP kalian dengan database MySQL.

### **2. `mysqli_query()`**
Fungsi ini digunakan untuk menjalankan query SQL. Misalnya, kita ingin mengambil semua data siswa dari database.

**Contoh Penggunaan:**
```php
<?php
$sql = "SELECT * FROM siswa";
$result = mysqli_query($conn, $sql);
```

### **Metode Mengambil Data**

Ketika kalian menjalankan query SELECT, kalian perlu mengambil data hasil query. MySQLi menyediakan beberapa metode berbeda untuk ini.

### **1. `mysqli_fetch_assoc()`**
Metode ini mengembalikan satu baris data dalam bentuk array asosiatif, di mana nama kolom menjadi kunci.

**Contoh Penggunaan:**
```php
<?php
while ($row = mysqli_fetch_assoc($result)) {
    echo "Nama: " . $row["nama"] . " - Email: " . $row["email"] . "<br>";
}
?>
```

### **2. `mysqli_fetch_row()`**
Metode ini mengembalikan satu baris data sebagai array numerik, di mana indeks adalah posisi kolom dalam query.

**Contoh Penggunaan:**
```php
<?php
while ($row = mysqli_fetch_row($result)) {
    echo "Nama: " . $row[0] . " - Email: " . $row[1] . "<br>";
}
?>
```

### **3. `mysqli_fetch_array()`**
Metode ini mengembalikan satu baris data dan memungkinkan kalian mengakses data baik secara asosiatif maupun numerik.

**Contoh Penggunaan:**
```php
<?php
while ($row = mysqli_fetch_array($result, MYSQLI_BOTH)) {
    echo "Nama: " . $row[0] . " (ID: " . $row["id"] . ")";
}
?>
```

### **4. `mysqli_fetch_object()`**
Metode ini mengembalikan satu baris data sebagai objek, di mana nama kolom menjadi properti dari objek.

**Contoh Penggunaan:**
```php
<?php
while ($row = mysqli_fetch_object($result)) {
    echo "Nama: " . $row->nama . " - Email: " . $row->email . "<br>";
}
?>
```

### **5. `mysqli_fetch_all()`**
Metode ini mengembalikan semua baris data dari hasil query sekaligus dalam bentuk array multidimensi.

**Contoh Penggunaan:**
```php
<?php
$rows = mysqli_fetch_all($result, MYSQLI_ASSOC);
foreach ($rows as $row) {
    echo "Nama: " . $row["nama"] . " - Email: " . $row["email"] . "<br>";
}
?>
```

### **6. `mysqli_real_escape_string()`**
Fungsi ini digunakan untuk membersihkan input dari pengguna agar aman dari serangan SQL Injection.

**Contoh Penggunaan:**
```php
<?php
$nama = mysqli_real_escape_string($conn, $_POST['nama']);
$sql = "INSERT INTO siswa (nama) VALUES ('$nama')";
mysqli_query($conn, $sql);
?>
```

### **7. `mysqli_close()`**
Ini digunakan untuk menutup koneksi ke database setelah kalian selesai melakukan operasi.

**Contoh Penggunaan:**
```php
<?php
mysqli_close($conn);
?>
```

## **4. Praktik CRUD dengan MySQLi**

Sekarang mari kita lihat bagaimana kita bisa menerapkan semua fungsi di atas dalam operasi CRUD.

### **Create (Membuat Data)**
```php
<?php
$nama = mysqli_real_escape_string($conn, $_POST['nama']);
$email = mysqli_real_escape_string($conn, $_POST['email']);
$sql = "INSERT INTO siswa (nama, email) VALUES ('$nama', '$email')";
if (mysqli_query($conn, $sql)) {
    echo "Data berhasil ditambahkan!";
} else {
    echo "Error: " . mysqli_error($conn);
}
?>
```

### **Read (Membaca Data)**
```php
<?php
$sql = "SELECT * FROM siswa WHERE id = 1";
$result = mysqli_query($conn, $sql);
if ($row = mysqli_fetch_assoc($result)) {
    echo "Nama: " . $row["nama"] . " - Email: " . $row["email"];
} else {
    echo "Tidak ada data ditemukan";
}
?>
```

### **Update (Memperbarui Data)**
```php
<?php
$namaBaru = mysqli_real_escape_string($conn, $_POST['nama']);
$emailBaru = mysqli_real_escape_string($conn, $_POST['email']);
$sql = "UPDATE siswa SET nama='$namaBaru', email='$emailBaru' WHERE id=1";
if (mysqli_query($conn, $sql)) {
    echo "Data berhasil diperbarui!";
} else {
    echo "Error: " . mysqli_error($conn);
}
?>
```

### **Delete (Menghapus Data)**
```php
<?php
$sql = "DELETE FROM siswa WHERE id=1";
if (mysqli_query($conn, $sql)) {
    echo "Data berhasil dihapus!";
} else {
    echo "Error: " . mysqli_error($conn);
}
?>
```

---

## **Kesimpulan**

Dengan memahami dan menggunakan MySQLi dengan pendekatan prosedural, kalian sekarang bisa melakukan berbagai operasi dasar pada database MySQL, seperti membuat, membaca, memperbarui, dan menghapus data. Kalian juga telah belajar tentang berbagai metode pengambilan data dan kapan harus menggunakan masing-masing metode berdasarkan kebutuhan aplikasi.

**Ingat:**
- **Keamanan:** Selalu gunakan `mysqli_real_escape_string()` untuk mengamankan input pengguna agar terhindar dari serangan SQL Injection.
- **Koneksi:** Jangan lupa untuk menutup koneksi setelah selesai menggunakan `mysqli_close()`.

Jika kalian sudah merasa nyaman dengan pendekatan prosedural, nanti kita akan melanjutkan ke pendekatan OOP (Object-Oriented Programming) dengan MySQLi untuk memberi kalian pandangan yang lebih luas tentang bagaimana cara lain yang bisa digunakan untuk mengelola database.


## **Aktivitas**

1. **Diskusi Kelompok:**
   - **Topik:** Bagaimana memilih metode fetch yang tepat berdasarkan skenario yang kalian hadapi?
   - **Tujuan:** Memahami kapan dan mengapa menggunakan masing-masing metode fetch (`mysqli_fetch_assoc()`, `mysqli_fetch_row()`, `mysqli_fetch_array()`, `mysqli_fetch_object()`, `mysqli_fetch_all()`) dalam situasi yang berbeda.

2. **Latihan:**
   - **Tugas:** Buatlah aplikasi PHP sederhana yang mengimplementasikan CRUD menggunakan MySQLi. Dalam aplikasi ini, coba terapkan berbagai metode fetch yang telah dipelajari, dan identifikasi kapan kalian sebaiknya menggunakan metode tertentu berdasarkan kebutuhan.
   - **Output:** Sebuah aplikasi CRUD sederhana dengan dokumentasi yang menjelaskan pilihan metode fetch dan alasan di balik penggunaannya.

---
### Navigasi
[⏮ Database Driver PDO](../12-database-driver-pdo/README.md) || [Home 🏘](../README.md) || [Database Driver MySqli Object ⏭](../14-database-driver-mysqli-oop/README.md)