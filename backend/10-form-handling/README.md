# **Bab 10 - Form Handling dalam PHP**

## **Tujuan Pembelajaran**
Pada akhir pertemuan ini, kalian diharapkan mampu:
- Memahami perbedaan antara metode `GET` dan `POST` dalam pengiriman data form.
- Melakukan validasi form untuk memastikan data yang diterima sesuai dengan kebutuhan.
- Menerapkan sanitasi input untuk mencegah serangan keamanan seperti SQL Injection dan XSS.

## **Materi yang Akan Dibahas**
1. Pengenalan Form Handling
2. Metode `GET` dan `POST`
3. Validasi Form
4. Sanitasi Input
5. Studi Kasus: Penerapan Form Handling dalam Aplikasi Sederhana

---

## **1. Pengenalan Form Handling**

### **Apa Itu Form Handling?**
Form handling adalah proses pengelolaan data yang dikirimkan melalui form HTML ke server untuk diproses lebih lanjut. Dalam PHP, form handling memungkinkan kalian untuk menerima data input dari pengguna, memvalidasinya, dan kemudian mengambil tindakan berdasarkan data tersebut.

Form HTML adalah salah satu cara utama untuk mengumpulkan input dari pengguna, seperti nama, alamat email, kata sandi, dan lainnya. Data ini kemudian dikirimkan ke server menggunakan metode `GET` atau `POST`.

### **Contoh Form HTML:**
```html
<form action="proses.php" method="post">
  <label for="nama">Nama:</label>
  <input type="text" id="nama" name="nama">
  <input type="submit" value="Submit">
</form>
```
Dalam contoh di atas, data dari form akan dikirimkan ke file `proses.php` menggunakan metode `POST`.

## **2. Metode `GET` dan `POST**

### **Perbedaan Antara `GET` dan `POST`**
Metode `GET` dan `POST` adalah dua cara utama untuk mengirimkan data form dari browser ke server.

- **GET**: Data dikirimkan melalui URL. Ini berarti data akan terlihat di URL, dan biasanya digunakan untuk permintaan data yang tidak sensitif.
- **POST**: Data dikirimkan melalui tubuh permintaan HTTP. Ini lebih aman dibandingkan `GET` karena data tidak terlihat di URL dan cocok untuk mengirimkan informasi yang lebih sensitif.

### **Penggunaan Metode `GET`:**
Metode `GET` biasanya digunakan untuk mengambil data dari server atau untuk mengirimkan permintaan yang tidak mengubah status data di server.

**Contoh Form dengan Metode `GET`:**
```html
<form action="proses.php" method="get">
  <label for="nama">Nama:</label>
  <input type="text" id="nama" name="nama">
  <input type="submit" value="Submit">
</form>
```
Ketika form ini dikirimkan, data akan muncul di URL seperti `proses.php?nama=Hilman`.

### **Penggunaan Metode `POST`:**
Metode `POST` biasanya digunakan untuk mengirimkan data yang dapat mengubah status data di server, seperti saat menyimpan data baru atau mengubah data yang ada.

**Contoh Form dengan Metode `POST`:**
```html
<form action="proses.php" method="post">
  <label for="nama">Nama:</label>
  <input type="text" id="nama" name="nama">
  <input type="submit" value="Submit">
</form>
```
Ketika form ini dikirimkan, data tidak akan terlihat di URL dan akan dikirimkan melalui tubuh permintaan HTTP.

## **3. Validasi Form**

### **Mengapa Validasi Penting?**
Validasi form adalah proses memastikan bahwa data yang diterima dari pengguna sesuai dengan kebutuhan dan harapan sistem. Tanpa validasi, data yang tidak sesuai atau berbahaya dapat masuk ke dalam sistem, yang bisa menyebabkan masalah atau bahkan celah keamanan.

### **Jenis-Jenis Validasi:**

1. **Validasi Sisi Klien (Client-Side Validation):**
   - Dilakukan di browser pengguna sebelum data dikirimkan ke server.
   - Menggunakan HTML5 atau JavaScript untuk memvalidasi data.
   - Contoh: Memastikan bahwa kolom email diisi dengan format email yang benar.

   **Contoh:**
   ```html
   <form action="proses.php" method="post">
     <label for="email">Email:</label>
     <input type="email" id="email" name="email" required>
     <input type="submit" value="Submit">
   </form>
   ```

2. **Validasi Sisi Server (Server-Side Validation):**
   - Dilakukan di server setelah data diterima dari pengguna.
   - Sangat penting untuk memastikan bahwa data yang masuk aman dan valid.
   - Contoh: Memastikan bahwa kolom nama tidak kosong dan hanya berisi huruf.

   **Contoh:**
   ```php
   <?php
   if ($_SERVER["REQUEST_METHOD"] == "POST") {
     if (empty($_POST["nama"])) {
       echo "Nama wajib diisi.";
     } elseif (!preg_match("/^[a-zA-Z ]*$/", $_POST["nama"])) {
       echo "Hanya huruf dan spasi yang diperbolehkan.";
     } else {
       echo "Nama: " . htmlspecialchars($_POST["nama"]);
     }
   }
   ?>
   ```

## **4. Sanitasi Input**

### **Apa Itu Sanitasi Input?**
Sanitasi input adalah proses membersihkan data input dari karakter atau pola yang berpotensi berbahaya sebelum digunakan dalam aplikasi. Ini penting untuk mencegah berbagai serangan keamanan, seperti SQL Injection dan Cross-Site Scripting (XSS).

### **Teknik Sanitasi Input:**

1. **Menggunakan `htmlspecialchars()`:**
   - Mengonversi karakter khusus menjadi entitas HTML untuk mencegah XSS.
   - Contoh: Mengubah `<` menjadi `&lt;`, `>` menjadi `&gt;`.

   **Contoh:**
   ```php
   <?php
   $nama = htmlspecialchars($_POST["nama"]);
   echo "Nama yang aman: $nama";
   ?>
   ```

2. **Menggunakan `filter_var()`:**
   - Memvalidasi dan menyaring data dengan filter bawaan PHP.
   - Contoh: Memastikan bahwa input adalah email yang valid.

   **Contoh:**
   ```php
   <?php
   $email = filter_var($_POST["email"], FILTER_SANITIZE_EMAIL);
   if (filter_var($email, FILTER_VALIDATE_EMAIL)) {
     echo "Email yang valid: $email";
   } else {
     echo "Email tidak valid.";
   }
   ?>
   ```

## **5. Studi Kasus: Penerapan Form Handling dalam Aplikasi Sederhana**

### **Deskripsi Masalah**
Kita akan membuat aplikasi sederhana yang menerima input dari pengguna melalui form, memvalidasi input, dan menampilkannya di halaman yang sama setelah memproses data tersebut.

### **Langkah-Langkah Implementasi:**

1. **Membuat Form untuk Input Data:**
   ```html
   <form action="<?php echo htmlspecialchars($_SERVER["PHP_SELF"]);?>" method="post">
     <label for="nama">Nama:</label>
     <input type="text" id="nama" name="nama" required>
     <label for="email">Email:</label>
     <input type="email" id="email" name="email" required>
     <input type="submit" value="Submit">
   </form>
   ```

2. **Validasi dan Sanitasi Input di Server:**
   ```php
   <?php
   $nama = $email = "";
   if ($_SERVER["REQUEST_METHOD"] == "POST") {
     $nama = htmlspecialchars($_POST["nama"]);
     $email = filter_var($_POST["email"], FILTER_SANITIZE_EMAIL);

     if (!filter_var($email, FILTER_VALIDATE_EMAIL)) {
       echo "Email tidak valid.";
     } else {
       echo "Nama: $nama<br>";
       echo "Email: $email";
     }
   }
   ?>
   ```

3. **Menampilkan Data yang Telah Divalidasi dan Disanitasi:**
   Data yang telah disanitasi dan divalidasi akan ditampilkan di halaman yang sama setelah pengguna mengirimkan form.

### **Kesimpulan**
Dengan penerapan form handling yang benar, termasuk validasi dan sanitasi input, kalian dapat mengelola data yang dikirimkan oleh pengguna dengan aman dan efektif. Penggunaan metode `GET` dan `POST` sesuai dengan kebutuhan, serta implementasi teknik sanitasi yang tepat, akan melindungi aplikasi dari berbagai potensi serangan seperti XSS. Studi kasus yang telah kita bahas menunjukkan bagaimana konsep ini dapat diterapkan dalam skenario nyata untuk membangun aplikasi web yang aman dan andal.

---

### **Aktivitas**

1. **Diskusi Kelompok:**
   - **Topik:** Bagaimana kalian dapat memastikan bahwa semua data yang diterima dari form pengguna aman dan valid?
   - **Tujuan:** Memahami pentingnya validasi dan sanitasi input dalam mencegah serangan terhadap aplikasi web.

2. **Latihan:**
   - **Tugas:** Buatlah aplikasi PHP sederhana yang menerima input dari form, memvalidasi input tersebut, dan menampilkannya di halaman yang sama setelah memprosesnya.
   - **Output:** Aplikasi PHP yang mengimplementasikan form handling dengan validasi dan sanitasi input yang benar.

---
### Navigasi
[⏮ Super Globals](../9-super-globals/README.md) || [Home 🏘](../README.md) || [Database Driver Intro ⏭](../11-database-driver-intro/README.md)