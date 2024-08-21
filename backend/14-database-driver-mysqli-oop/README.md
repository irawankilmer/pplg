Berikut adalah pembahasan lengkap tentang **Bab 14 - MySQLi dengan Pendekatan OOP (Object-Oriented Programming)**:

---

# **Bab 14 - MySQLi dengan Pendekatan OOP**

## **Tujuan Pembelajaran**
Setelah menyelesaikan bab ini, kalian diharapkan dapat:
- Memahami konsep dasar MySQLi dengan pendekatan berorientasi objek (OOP).
- Menghubungkan aplikasi PHP ke database MySQL menggunakan MySQLi dalam mode OOP.
- Melakukan operasi CRUD (Create, Read, Update, Delete) menggunakan MySQLi dengan pendekatan OOP.
- Memahami kapan sebaiknya menggunakan pendekatan OOP dibandingkan dengan prosedural dalam pengembangan aplikasi.

## **Materi yang Akan Dibahas**
1. Pengantar MySQLi dengan Pendekatan OOP
2. Koneksi ke Database dengan MySQLi OOP
3. Metode-Metode Utama MySQLi OOP
   - `__construct()`
   - `query()`
   - `prepare()`
   - `execute()`
   - `fetch_assoc()`, `fetch_row()`, `fetch_array()`, `fetch_object()`, `fetch_all()`
   - `real_escape_string()`
   - `close()`
4. Implementasi CRUD dengan MySQLi OOP
   - Create (Membuat Data)
   - Read (Membaca Data)
   - Update (Memperbarui Data)
   - Delete (Menghapus Data)
5. Studi Kasus: Aplikasi Sederhana Menggunakan MySQLi OOP
6. Perbandingan antara Pendekatan Prosedural dan OOP
7. Aktivitas

---

## **1. Pengantar MySQLi dengan Pendekatan OOP**

### **Apa Itu MySQLi dengan Pendekatan OOP?**
MySQLi OOP adalah cara menggunakan ekstensi MySQLi di PHP dengan gaya berorientasi objek. Dalam pendekatan ini, kalian akan bekerja dengan objek dan metode daripada fungsi-fungsi prosedural. Pendekatan OOP memberikan struktur yang lebih rapi dan skalabilitas yang lebih baik, terutama untuk proyek-proyek besar.

### **Mengapa Menggunakan OOP?**
Pendekatan OOP lebih modular dan lebih mudah untuk dikelola dalam jangka panjang. Dengan OOP, kalian dapat memanfaatkan konsep-konsep seperti enkapsulasi, pewarisan, dan polimorfisme, yang memungkinkan kalian untuk menulis kode yang lebih bersih, terorganisir, dan reusable.

## **2. Koneksi ke Database dengan MySQLi OOP**

Sebelum melakukan operasi apa pun pada database, hal pertama yang harus kita lakukan adalah menghubungkan aplikasi PHP ke database MySQL.

### **Contoh Koneksi:**
```php
<?php
class Database {
    private $host = "localhost";
    private $username = "root";
    private $password = "password_kalian";
    private $dbname = "nama_database";
    public $conn;

    public function __construct() {
        $this->conn = new mysqli($this->host, $this->username, $this->password, $this->dbname);

        if ($this->conn->connect_error) {
            die("Koneksi gagal: " . $this->conn->connect_error);
        }
    }

    public function close() {
        $this->conn->close();
    }
}

$db = new Database();
echo "Koneksi berhasil!";
$db->close();
?>
```

### **Penjelasan:**
- **`__construct()`**: Ini adalah metode konstruktor yang dipanggil saat objek dari kelas `Database` dibuat. Metode ini digunakan untuk menginisialisasi koneksi ke database.
- **`$this->conn = new mysqli(...)`**: Baris ini membuat koneksi baru ke database menggunakan objek MySQLi.
- **`$this->conn->connect_error`**: Digunakan untuk mengecek apakah koneksi berhasil. Jika tidak, kode akan menghentikan eksekusi dengan pesan error.

## **3. Metode-Metode Utama MySQLi OOP**

Setelah kalian terhubung ke database, berikut adalah beberapa metode utama yang akan sering digunakan dalam MySQLi dengan pendekatan OOP.

### **1. `query()`**
Metode `query()` digunakan untuk menjalankan query SQL sederhana.

**Contoh Penggunaan:**
```php
<?php
$sql = "SELECT * FROM siswa";
$result = $db->conn->query($sql);
```

### **2. `prepare()` dan `execute()`**
Metode `prepare()` digunakan untuk mempersiapkan query SQL dengan placeholder, sedangkan `execute()` digunakan untuk menjalankan query yang telah dipersiapkan.

**Contoh Penggunaan:**
```php
<?php
$stmt = $db->conn->prepare("INSERT INTO siswa (nama, email) VALUES (?, ?)");
$stmt->bind_param("ss", $nama, $email);

$nama = "Alya";
$email = "alya@example.com";
$stmt->execute();

echo "Data berhasil ditambahkan!";
$stmt->close();
?>
```

### **3. Metode Pengambilan Data**

Sama seperti pendekatan prosedural, MySQLi dengan OOP juga menawarkan berbagai metode untuk mengambil data hasil query.

- **`fetch_assoc()`**: Mengambil satu baris hasil query sebagai array asosiatif.
- **`fetch_row()`**: Mengambil satu baris hasil query sebagai array numerik.
- **`fetch_array()`**: Mengambil satu baris hasil query sebagai array asosiatif dan numerik.
- **`fetch_object()`**: Mengambil satu baris hasil query sebagai objek.
- **`fetch_all()`**: Mengambil semua baris hasil query sekaligus.

### **Contoh Penggunaan:**
```php
<?php
$sql = "SELECT * FROM siswa";
$result = $db->conn->query($sql);

while ($row = $result->fetch_assoc()) {
    echo "Nama: " . $row["nama"] . " - Email: " . $row["email"] . "<br>";
}
?>
```

### **4. `real_escape_string()`**
Metode ini digunakan untuk membersihkan input pengguna agar aman dari serangan SQL Injection.

**Contoh Penggunaan:**
```php
<?php
$nama = $db->conn->real_escape_string($_POST['nama']);
$email = $db->conn->real_escape_string($_POST['email']);
$sql = "INSERT INTO siswa (nama, email) VALUES ('$nama', '$email')";
$db->conn->query($sql);
?>
```

### **5. `close()`**
Metode ini digunakan untuk menutup koneksi ke database.

**Contoh Penggunaan:**
```php
<?php
$db->conn->close();
?>
```

## **4. Implementasi CRUD dengan MySQLi OOP**

Setelah memahami metode dasar, mari kita terapkan semua ini dalam operasi CRUD.

### **Create (Membuat Data)**
```php
<?php
$stmt = $db->conn->prepare("INSERT INTO siswa (nama, email) VALUES (?, ?)");
$stmt->bind_param("ss", $nama, $email);

$nama = "Alya";
$email = "alya@example.com";
$stmt->execute();

echo "Data berhasil ditambahkan!";
$stmt->close();
?>
```

### **Read (Membaca Data)**
```php
<?php
$sql = "SELECT * FROM siswa WHERE id = 1";
$result = $db->conn->query($sql);
if ($row = $result->fetch_assoc()) {
    echo "Nama: " . $row["nama"] . " - Email: " . $row["email"];
} else {
    echo "Tidak ada data ditemukan";
}
?>
```

### **Update (Memperbarui Data)**
```php
<?php
$stmt = $db->conn->prepare("UPDATE siswa SET nama=?, email=? WHERE id=?");
$stmt->bind_param("ssi", $namaBaru, $emailBaru, $id);

$namaBaru = "Alya Salsabila";
$emailBaru = "alya.salsabila@example.com";
$id = 1;
$stmt->execute();

echo "Data berhasil diperbarui!";
$stmt->close();
?>
```

### **Delete (Menghapus Data)**
```php
<?php
$stmt = $db->conn->prepare("DELETE FROM siswa WHERE id=?");
$stmt->bind_param("i", $id);

$id = 1;
$stmt->execute();

echo "Data berhasil dihapus!";
$stmt->close();
?>
```

## **5. Studi Kasus: Aplikasi Sederhana Menggunakan MySQLi OOP**

Kita akan membangun aplikasi sederhana untuk mengelola data siswa. Aplikasi ini akan mencakup fitur untuk menambah, membaca, memperbarui, dan menghapus data siswa dari database.

1. **Langkah Pertama**: Buatlah kelas `Database` seperti contoh di atas untuk mengelola koneksi ke database.
2. **Langkah Kedua**: Implementasikan CRUD dengan menggunakan metode MySQLi OOP.
3. **Langkah Ketiga**: Tambahkan fitur keamanan dengan menggunakan `real_escape_string()` dan prepared statements.

## **6. Perbandingan antara Pendekatan Prosedural dan OOP**

### **Prosedural:**
- Lebih sederhana dan mudah dipahami untuk proyek kecil.
- Kurang terstruktur, sehingga sulit di-maintain dalam proyek besar.

### **OOP:**
- Lebih terstruktur dan modular, cocok untuk proyek besar.
- Memungkinkan penggunaan konsep OOP seperti pewarisan dan polimorfisme, membuat kode lebih reusable.

## **7. Aktivitas**

1. **Diskusi Kelompok:**
   - **Topik:** Apa perbedaan utama antara pendekatan prosedural dan OOP dalam penggunaan MySQLi? Diskusikan skenario di mana satu pendekatan lebih baik digunakan daripada yang lain.
   - **Tujuan:** Memahami kapan sebaiknya menggunakan pendekatan OOP dan kapan sebaiknya menggunakan pendekatan prosedural dalam pengembangan aplikasi.

2. **Latihan:**
   - **Tugas:** Buatlah aplikasi PHP sederhana yang mengimplementasikan CRUD menggunakan MySQLi dengan pendekatan OOP. Aplikasi ini harus mencakup fitur untuk menambah, membaca, memperbarui, dan menghapus data siswa. Pastikan untuk menggunakan metode `prepare()` dan `execute()` untuk meningkatkan keamanan aplikasi.
   - **Output:** Sebuah aplikasi CRUD sederhana dengan MySQLi OOP yang aman dan efektif, dilengkapi dengan dokumentasi yang menjelaskan alasan penggunaan OOP dan pilihan metode fetch yang digunakan.