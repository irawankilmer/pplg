# **Bab 9 - Superglobals dalam PHP**

## **Tujuan Pembelajaran**
Pada akhir pertemuan ini, kalian diharapkan mampu:
- Memahami konsep superglobals dan fungsinya dalam PHP.
- Menggunakan berbagai superglobals untuk mengelola data dalam aplikasi web.
- Mengimplementasikan superglobals dalam skenario praktis seperti pengelolaan form, sesi, dan cookie.

## **Materi yang Akan Dibahas**
1. Pengertian Superglobals
2. Penjelasan Masing-Masing Superglobals
   - `$_GLOBALS`
   - `$_SERVER`
   - `$_REQUEST`
   - `$_POST`
   - `$_GET`
   - `$_FILES`
   - `$_ENV`
   - `$_COOKIE`
   - `$_SESSION`
3. Studi Kasus: Aplikasi Sederhana Menggunakan Superglobals

---

## **1. Pengertian Superglobals**

### **Apa Itu Superglobals?**
Superglobals adalah array asosiatif bawaan di PHP yang selalu tersedia di semua lingkup (scope), tanpa perlu mendeklarasikannya sebagai global. Superglobals ini digunakan untuk mengakses variabel, informasi server, input dari form, data sesi, cookie, dan banyak lagi.

## **2. Penjelasan Masing-Masing Superglobals**

### **1. `$_GLOBALS`**
`$_GLOBALS` adalah superglobal yang digunakan untuk mengakses semua variabel global di seluruh script PHP. Ini memungkinkan kalian untuk mengakses variabel global dari mana saja, termasuk dari dalam fungsi atau file lain yang disertakan.

**Contoh:**
```php
<?php
  $nama = "Hilman";
  function tampilkanNama() {
    echo $_GLOBALS['nama'];
  }
  tampilkanNama(); // Menampilkan "Hilman"
?>
```

### **2. `$_SERVER`**
`$_SERVER` berisi informasi tentang server dan lingkungan eksekusi PHP. Ini mencakup detail seperti header, jalur, dan lokasi skrip.

**Contoh:**
```php
<?php
  echo $_SERVER['SERVER_NAME']; // Menampilkan nama server
  echo $_SERVER['PHP_SELF']; // Menampilkan nama file yang sedang dijalankan
?>
```

### **3. `$_REQUEST`**
`$_REQUEST` digunakan untuk mengumpulkan data setelah mengirimkan form HTML. Ini berisi data yang dikirimkan melalui metode `GET`, `POST`, dan `COOKIE`.

**Contoh:**
```php
<?php
  echo $_REQUEST['nama']; // Menampilkan nilai dari input 'nama' dari form yang dikirimkan
?>
```

### **4. `$_POST`**
`$_POST` digunakan untuk mengumpulkan data dari form yang dikirimkan menggunakan metode `POST`. Ini adalah cara yang aman untuk mengirimkan data yang sensitif seperti kata sandi atau informasi pribadi.

**Contoh:**
```php
<?php
  if ($_SERVER["REQUEST_METHOD"] == "POST") {
    echo "Nama: " . $_POST['nama']; // Menampilkan nilai dari input 'nama'
  }
?>
```

### **5. `$_GET`**
`$_GET` digunakan untuk mengumpulkan data dari URL (query string). Data yang dikirimkan melalui `GET` akan terlihat di URL dan biasanya digunakan untuk permintaan data yang tidak sensitif.

**Contoh:**
```php
<?php
  echo "Nama: " . $_GET['nama']; // Menampilkan nilai dari parameter 'nama' di URL
?>
```

### **6. `$_FILES`**
`$_FILES` digunakan untuk mengumpulkan informasi tentang file yang diunggah melalui form. Ini mencakup nama file, tipe file, ukuran file, dan lokasi sementara di server.

**Contoh:**
```php
<?php
  if ($_SERVER["REQUEST_METHOD"] == "POST") {
    $namaFile = $_FILES['file']['name'];
    $lokasiSementara = $_FILES['file']['tmp_name'];
    move_uploaded_file($lokasiSementara, "uploads/" . $namaFile);
    echo "File berhasil diunggah: " . $namaFile;
  }
?>
```

### **7. `$_ENV`**
`$_ENV` berisi variabel lingkungan (environment variables) yang disediakan oleh sistem operasi di mana server PHP berjalan. Variabel ini biasanya digunakan untuk konfigurasi sistem.

**Contoh:**
```php
<?php
  echo $_ENV['PATH']; // Menampilkan variabel lingkungan PATH
?>
```

### **8. `$_COOKIE`**
`$_COOKIE` digunakan untuk mengakses data yang disimpan dalam cookie di browser pengguna. Cookie adalah data kecil yang dikirim oleh server dan disimpan di komputer pengguna untuk melacak informasi seperti preferensi pengguna atau status login.

**Contoh:**
```php
<?php
  setcookie("namaPengguna", "Hilman", time() + 3600); // Membuat cookie yang berlaku selama 1 jam
  echo $_COOKIE['namaPengguna']; // Menampilkan nilai cookie 'namaPengguna'
?>
```

### **9. `$_SESSION`**
`$_SESSION` digunakan untuk menyimpan informasi tentang sesi pengguna di seluruh halaman web. Tidak seperti cookie, data sesi disimpan di server, bukan di komputer pengguna.

**Contoh:**
```php
<?php
  session_start(); // Memulai sesi
  $_SESSION['namaPengguna'] = "Hilman";
  echo $_SESSION['namaPengguna']; // Menampilkan nilai sesi 'namaPengguna'
?>
```

## **3. Studi Kasus: Aplikasi Sederhana Menggunakan Superglobals**

### **Deskripsi Masalah**
Kita akan membuat aplikasi sederhana yang menggunakan berbagai superglobals untuk mengelola data form, cookie, dan sesi pengguna.

### **Langkah-Langkah Implementasi**
1. **Mengelola Data Form dengan `$_POST`:**
   ```php
   <?php
   if ($_SERVER["REQUEST_METHOD"] == "POST") {
     $nama = $_POST['nama'];
     echo "Nama yang dimasukkan: $nama";
   }
   ?>
   ```

2. **Menggunakan `$_GET` untuk Mengambil Data dari URL:**
   ```php
   <?php
   echo "Halaman: " . $_GET['page'];
   ?>
   ```

3. **Menyimpan dan Mengakses Cookie dengan `$_COOKIE`:**
   ```php
   <?php
   setcookie("pengguna", "Alya", time() + 3600); // Menyimpan cookie selama 1 jam
   echo "Pengguna: " . $_COOKIE['pengguna'];
   ?>
   ```

4. **Mengelola Sesi Pengguna dengan `$_SESSION`:**
   ```php
   <?php
   session_start();
   $_SESSION['status'] = "LoggedIn";
   echo "Status sesi: " . $_SESSION['status'];
   ?>
   ```

### **Kesimpulan**
Superglobals adalah alat penting dalam PHP yang memungkinkan kalian untuk mengelola data yang diterima dari pengguna, server, dan lingkungan dengan cara yang efisien. Dengan memahami dan menggunakan superglobals dengan benar, kalian dapat membangun aplikasi web yang lebih interaktif dan dinamis.

---

### **Aktivitas**

1. **Diskusi Kelompok:**
   - **Topik:** Apa saja keuntungan dan tantangan dalam menggunakan superglobals dibandingkan variabel biasa?
   - **Tujuan:** Memahami peran dan pentingnya superglobals dalam pengembangan aplikasi web.

2. **Latihan:**
   - **Tugas:** Buatlah aplikasi PHP sederhana yang menggunakan superglobals untuk menerima input dari form, menyimpan data dalam sesi, dan menampilkan data yang disimpan dalam cookie.
   - **Output:** Aplikasi PHP yang menggunakan superglobals secara efektif untuk mengelola data.
---

# **Bab 9 Lanjutan – Session dan Cookie dalam PHP**

---

## 🎯 **Tujuan Pembelajaran**

Setelah mempelajari bab ini, kalian diharapkan:

* Memahami perbedaan mendasar antara **session** dan **cookie**.
* Menggunakan session untuk menyimpan data pengguna di sisi server.
* Menggunakan cookie untuk menyimpan data ringan di sisi client (browser).
* Mengetahui cara membuat, membaca, dan menghapus session dan cookie.
* Mampu membangun simulasi **login** sederhana berbasis session.

---

## 🧠 **1. Pengantar: Mengapa Kita Butuh Session dan Cookie?**

PHP adalah bahasa server-side yang **tidak menyimpan data antar halaman secara otomatis**. Artinya, jika pengguna berpindah dari satu halaman ke halaman lain, data seperti nama, login, dan pilihan mereka akan **hilang** jika tidak disimpan.

👉 Di sinilah peran **Session dan Cookie**:

* Untuk **mengingat data** antar halaman.
* Untuk **melacak status pengguna** (apakah sedang login, preferensi warna, keranjang belanja, dll).
* Untuk **mengamankan proses-proses sensitif**, seperti login.

---

## 📦 **2. Analogi Sederhana**

### 🍪 **Cookie: Catatan Disimpan oleh Pengguna**

Bayangkan kamu masuk ke perpustakaan dan diberi **catatan kecil** yang berisi daftar buku yang kamu pinjam. Catatan ini **kamu simpan sendiri**, dan saat kembali besok, kamu menunjukkannya ke petugas.

* Data disimpan di **sisi pengguna (browser)**.
* Bisa dimanipulasi/dihapus oleh pengguna.

### 🗃️ **Session: Catatan Disimpan oleh Server**

Sekarang bayangkan kamu masuk ke ruang TU dan petugas menuliskan namamu serta tujuanmu di **buku besar TU**. Kamu hanya perlu menunjukkan ID untuk mengakses catatanmu. Catatannya **tidak bisa kamu lihat atau ubah**.

* Data disimpan di **server**.
* Lebih aman karena pengguna tidak bisa langsung mengakses atau memanipulasinya.

---

## 🔍 **3. Perbandingan Session vs Cookie**

| Fitur                 | **Session**                    | **Cookie**                       |
| --------------------- | ------------------------------ | -------------------------------- |
| Lokasi penyimpanan    | Server                         | Browser (Client)                 |
| Kapasitas penyimpanan | Besar (tergantung server)      | Kecil (sekitar 4KB)              |
| Keamanan              | Lebih aman                     | Rentan jika tidak dienkripsi     |
| Akses pengguna        | Tidak bisa diakses langsung    | Bisa dilihat/dihapus oleh user   |
| Expired               | Saat browser ditutup (default) | Bisa diatur waktunya             |
| Cocok untuk           | Login, proses rahasia          | Preferensi ringan seperti bahasa |

---

## 🔧 **4. Session dalam PHP**

### 🚩 Aturan Utama:

* **Selalu panggil `session_start()` di baris paling atas sebelum HTML dimulai!**
* Gunakan array `$_SESSION` untuk menyimpan data.
* Data session disimpan secara **unik untuk setiap pengguna** berdasarkan ID sesi mereka.

---

### 📌 Contoh 1 – Menyimpan Data ke Session

```php
<?php
session_start();
$_SESSION['nama'] = "Ahmad Zaki";
$_SESSION['kelas'] = "XI PPLG A";
echo "Data telah disimpan ke session.";
?>
```

---

### 📌 Contoh 2 – Mengambil Data dari Session

```php
<?php
session_start();
echo "Nama: " . $_SESSION['nama'] . "<br>";
echo "Kelas: " . $_SESSION['kelas'];
?>
```

---

### 📌 Contoh 3 – Menghapus Session

```php
<?php
session_start();
session_unset();    // Menghapus semua isi $_SESSION
session_destroy();  // Menghancurkan session
echo "Session telah dihapus.";
?>
```

---

## 🔐 **5. Cookie dalam PHP**

### 🔧 Aturan Utama:

* Gunakan fungsi `setcookie()` untuk membuat cookie.
* Cookie akan tersedia pada **permintaan (request) berikutnya**.
* Data dapat diakses melalui `$_COOKIE`.

---

### 📌 Contoh 1 – Menyimpan Cookie

```php
<?php
setcookie("user", "Hani Fuziyani", time() + 3600); // Berlaku 1 jam
echo "Cookie telah diset.";
?>
```

### 📌 Contoh 2 – Mengakses Cookie

```php
<?php
if (isset($_COOKIE['user'])) {
    echo "Selamat datang, " . $_COOKIE['user'];
} else {
    echo "Cookie tidak tersedia.";
}
?>
```

### 📌 Contoh 3 – Menghapus Cookie

```php
<?php
setcookie("user", "", time() - 3600); // Waktu mundur = hapus cookie
echo "Cookie telah dihapus.";
?>
```

---

## 💻 **6. Simulasi Login Sederhana dengan Session**

### ✅ `login.php`

```php
<?php
session_start();
if ($_POST['username'] == "admin" && $_POST['password'] == "123") {
    $_SESSION['login'] = true;
    $_SESSION['user'] = "admin";
    header("Location: dashboard.php");
} else {
    echo "Login gagal!";
}
?>
```

### ✅ `dashboard.php`

```php
<?php
session_start();
if (!isset($_SESSION['login'])) {
    header("Location: login_form.html");
    exit;
}
echo "Selamat datang, " . $_SESSION['user'];
?>
```

### ✅ `logout.php`

```php
<?php
session_start();
session_destroy();
header("Location: login_form.html");
?>
```

---

## 🧭 **7. Diagram Alur Login Menggunakan Session**

```
[User Isi Form Login] 
        ↓
[login.php]
 - Cek username & password
 - Jika benar → Simpan $_SESSION['login']
        ↓
[dashboard.php]
 - Cek session login
 - Jika ada → tampilkan dashboard
 - Jika tidak ada → redirect ke login
```

---

## 🧠 **8. Tips Penting Session dan Cookie**

| Tips                                     | Penjelasan                                   |
| ---------------------------------------- | -------------------------------------------- |
| `session_start()` wajib di awal file PHP | Tanpa ini, `$_SESSION` tidak bisa digunakan  |
| Session cocok untuk data sensitif        | Contoh: status login, ID pengguna            |
| Gunakan cookie untuk hal ringan          | Contoh: preferensi bahasa, mode gelap/terang |
| Jangan simpan password di session/cookie | Selalu simpan hanya ID atau token saja       |

---

## 🧪 **9. Latihan Praktik**

### ✍️ Latihan 1 – Session Dasar

1. Buat file `simpan.php` yang menyimpan `nama` dan `kelas` ke session.
2. Buat `tampil.php` yang menampilkan isi session.
3. Buat `hapus.php` untuk menghapus session.

---

### ✍️ Latihan 2 – Cookie Sederhana

1. Buat file yang menyimpan nama user ke cookie.
2. Buat file lain yang menampilkan cookie tersebut jika ada.
3. Buat tombol untuk menghapus cookie.

---

### ✍️ Latihan 3 – Mini Project: Simulasi Login

* Gunakan form login sederhana.
* Validasi user dan simpan session.
* Tampilkan halaman dashboard jika login berhasil.
* Tambahkan logout yang menghapus session.

---

## 📚 **10. Penutup**

* **Session**: Digunakan untuk menyimpan data di server, cocok untuk informasi penting dan rahasia (seperti status login).
* **Cookie**: Digunakan untuk menyimpan data kecil di browser, cocok untuk preferensi pengguna.
* Keduanya sangat penting dalam membuat **aplikasi web yang interaktif dan personal**.

---

## 🔗 Bonus: Rekomendasi Implementasi Lanjutan

* Simpan ID user ke session setelah login dan gunakan untuk query database.
* Gunakan cookie dengan enkripsi jika menyimpan data penting.
* Gunakan session timeout (auto logout jika tidak aktif dalam beberapa menit).

### Navigasi
[⏮ Array](../8-array/README.md) || [Home 🏘](../README.md) || [Form Handling ⏭](../10-form-handling/README.md)