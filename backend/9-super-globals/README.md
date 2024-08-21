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
### Navigasi
[⏮ Array](../8-array/README.md) || [Home 🏘](../README.md) || [Form Handling ⏭](../10-form-handling/README.md)