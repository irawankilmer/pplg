# **Bab 11 – Validasi Data dalam PHP**

---

## 🎯 **Tujuan Pembelajaran**

Setelah mempelajari bab ini, kalian diharapkan mampu:

* Memahami konsep **validasi data input** dan pentingnya dalam aplikasi web.
* Melakukan validasi **form input** menggunakan fungsi-fungsi PHP.
* Mengetahui perbedaan antara **validasi** dan **sanitasi** data.
* Menghindari data palsu, kosong, atau berbahaya sebelum diproses atau disimpan.

---

## 📚 **1. Apa Itu Validasi Data?**

### ✅ **Definisi:**

Validasi data adalah proses untuk **memastikan bahwa input dari pengguna sesuai dengan format atau aturan tertentu** sebelum digunakan atau disimpan ke database.

---

### 🧠 **Mengapa Validasi Itu Penting?**

Bayangkan jika website sekolah membiarkan kolom "email siswa" diisi dengan nama kucing, atau bahkan kode berbahaya. Tanpa validasi:

* Aplikasi bisa error.
* Database bisa rusak.
* Bisa terjadi **serangan keamanan** (SQL Injection, XSS, dll).

---

## 📦 **2. Jenis Validasi Data**

| Jenis Validasi          | Tujuan                                                        |
| ----------------------- | ------------------------------------------------------------- |
| **Required**            | Memastikan data tidak kosong                                  |
| **Format**              | Memastikan data sesuai tipe (angka, email, dll)               |
| **Panjang**             | Memastikan jumlah karakter tertentu                           |
| **Nilai**               | Batas nilai minimum/maksimum (angka)                          |
| **Kecocokan**           | Misal: password & konfirmasi harus sama                       |
| **Whitelist/Blacklist** | Memastikan hanya karakter yang diperbolehkan yang boleh masuk |

---

## ⚙️ **3. Fungsi Validasi yang Sering Digunakan di PHP**

Berikut ini adalah daftar **fungsi bawaan PHP** yang paling sering digunakan untuk validasi input:

---

### 📌 1. **empty()**

Cek apakah variabel kosong ("" / null / 0 / false / array kosong).

```php
if (empty($_POST['nama'])) {
    echo "Nama tidak boleh kosong!";
}
```

---

### 📌 2. **isset()**

Cek apakah variabel sudah diatur atau dikirim (berbeda dengan `empty`).

```php
if (isset($_POST['email'])) {
    // Validasi email di sini
}
```

---

### 📌 3. **is\_numeric()**

Cek apakah input berupa angka (termasuk string angka seperti "123").

```php
if (!is_numeric($_POST['umur'])) {
    echo "Umur harus berupa angka!";
}
```

---

### 📌 4. **strlen()**

Menghitung jumlah karakter string.

```php
$password = $_POST['password'];
if (strlen($password) < 8) {
    echo "Password minimal 8 karakter.";
}
```

---

### 📌 5. **filter\_var()**

Fungsi serbaguna untuk **validasi dan sanitasi** input.

#### Contoh validasi email:

```php
$email = $_POST['email'];
if (!filter_var($email, FILTER_VALIDATE_EMAIL)) {
    echo "Format email tidak valid!";
}
```

#### Contoh validasi angka:

```php
$nilai = $_POST['nilai'];
if (!filter_var($nilai, FILTER_VALIDATE_INT)) {
    echo "Input harus berupa bilangan bulat!";
}
```

---

### 📌 6. **preg\_match()**

Cocokkan input dengan pola (*regular expression*). Sangat kuat dan fleksibel!

#### Contoh validasi hanya huruf dan spasi:

```php
$nama = $_POST['nama'];
if (!preg_match("/^[a-zA-Z\s]+$/", $nama)) {
    echo "Nama hanya boleh huruf dan spasi!";
}
```

---

## 🧹 **4. Sanitasi Data**

**Sanitasi** = membersihkan data dari karakter berbahaya, biasanya dilakukan **sebelum menyimpan ke database atau menampilkannya ke browser**.

### 📌 Contoh fungsi sanitasi:

```php
$nama = htmlspecialchars(trim($_POST['nama']));
```

| Fungsi               | Tujuan                                      |
| -------------------- | ------------------------------------------- |
| `trim()`             | Menghapus spasi di awal/akhir               |
| `htmlspecialchars()` | Mencegah XSS (konversi `<` jadi `&lt;` dll) |
| `strip_tags()`       | Menghapus tag HTML                          |

---

## 🔐 **5. Validasi Ganda (Server-Side & Client-Side)**

Validasi bisa dilakukan di:

* **Client-side** (HTML5, JavaScript) → cepat, tapi bisa dilewati.
* **Server-side (PHP)** → wajib! Karena paling aman.

💡 *Client-side validasi hanya sebagai pelengkap. Validasi utama tetap di server!*

---

## 🔒 **6. Contoh Lengkap Validasi Form (PHP)**

```php
<?php
$errors = [];

if ($_SERVER["REQUEST_METHOD"] == "POST") {
    // Validasi nama
    $nama = trim($_POST['nama']);
    if (empty($nama)) {
        $errors[] = "Nama wajib diisi.";
    } elseif (!preg_match("/^[a-zA-Z\s]+$/", $nama)) {
        $errors[] = "Nama hanya boleh huruf dan spasi.";
    }

    // Validasi email
    $email = trim($_POST['email']);
    if (!filter_var($email, FILTER_VALIDATE_EMAIL)) {
        $errors[] = "Format email tidak valid.";
    }

    // Validasi umur
    $umur = $_POST['umur'];
    if (!is_numeric($umur) || $umur < 10 || $umur > 100) {
        $errors[] = "Umur harus angka antara 10-100.";
    }

    // Jika tidak ada error
    if (empty($errors)) {
        echo "Data berhasil divalidasi dan diproses.";
        // Simpan ke database atau proses lebih lanjut
    } else {
        foreach ($errors as $error) {
            echo "<p>$error</p>";
        }
    }
}
?>
```

---

## 📌 **7. Validasi Password dan Konfirmasi**

```php
$password = $_POST['password'];
$konfirmasi = $_POST['konfirmasi'];

if ($password !== $konfirmasi) {
    echo "Password dan konfirmasi tidak cocok!";
} elseif (strlen($password) < 8) {
    echo "Password minimal 8 karakter.";
}
```

---

## 🧪 **8. Latihan Praktik Validasi Data**

### 📝 Latihan 1 – Form Validasi Nama & Email

1. Buat form HTML dengan input:

   * Nama (tidak boleh kosong, hanya huruf)
   * Email (format valid)

2. Buat file PHP untuk memproses dan menampilkan error jika input tidak sesuai.

---

### 📝 Latihan 2 – Validasi Lengkap

Buat form:

* Nama (wajib, huruf saja)
* Email (valid)
* Umur (angka antara 15 – 60)
* Password dan konfirmasi (minimal 8 karakter, harus sama)

Tampilkan error jika ada, dan pesan sukses jika semua valid.

---

## 📊 **9. Ringkasan Fungsi Validasi PHP**

| Fungsi               | Kegunaan                          |
| -------------------- | --------------------------------- |
| `empty()`            | Cek apakah input kosong           |
| `isset()`            | Cek apakah variabel sudah dikirim |
| `is_numeric()`       | Cek angka                         |
| `strlen()`           | Cek panjang karakter              |
| `filter_var()`       | Validasi email, int, IP, URL      |
| `preg_match()`       | Cek pola huruf, angka, regex      |
| `trim()`             | Hilangkan spasi awal/akhir        |
| `htmlspecialchars()` | Mencegah XSS                      |
| `strip_tags()`       | Hilangkan tag HTML                |

---

## 🧠 **10. Penutup: Best Practice Validasi**

* Lakukan validasi **di server-side**, walaupun sudah ada validasi HTML.
* Selalu **bersihkan input** dari pengguna.
* Gunakan `filter_var()` untuk data standar seperti email, int, URL.
* Gunakan `preg_match()` untuk validasi kustom seperti nama hanya huruf.
* Jangan pernah percaya sepenuhnya pada input user—**user bisa mengirimkan apapun**.
