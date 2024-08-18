# **Bab 2 - Konfigurasi Lingkungan dan Dasar PHP**

## **Tujuan Pembelajaran**
Pada akhir pertemuan ini, kalian diharapkan mampu:
- Menginstal dan mengonfigurasi lingkungan pengembangan PHP dengan benar.
- Memahami sintaks dasar PHP dan cara mengintegrasikan PHP dengan HTML.
- Menjalankan skrip PHP sederhana di server lokal.

## **Materi yang Akan Dibahas**
1. Instalasi dan Konfigurasi Server Lokal
2. Penulisan Skrip PHP Pertama
3. Menyisipkan PHP di dalam HTML dan Sebaliknya
4. Praktik Terbaik dalam Menulis Kode PHP

---

## **1. Instalasi dan Konfigurasi Server Lokal**

### **Mengapa Kita Perlu Server Lokal?**
Sebelum kalian bisa menjalankan kode PHP, kalian memerlukan server yang bisa memproses kode tersebut. Di sinilah peran server lokal, seperti XAMPP, MAMP, atau LAMP. Server lokal memungkinkan kalian untuk menjalankan dan menguji aplikasi PHP di komputer kalian sendiri.

### **Langkah-Langkah Instalasi**
- **XAMPP (untuk Windows dan Mac):**
  1. Unduh XAMPP dari situs resmi Apache Friends.
  2. Instal dengan mengikuti petunjuk yang diberikan. Pastikan kalian memilih modul Apache dan MySQL.
  3. Setelah instalasi selesai, buka kontrol panel XAMPP dan start Apache serta MySQL.

- **MAMP (untuk Mac):**
  1. Unduh MAMP dari situs resmi MAMP.
  2. Instal dan jalankan MAMP.
  3. Buka halaman start MAMP di browser untuk memastikan instalasi berhasil.

- **LAMP (untuk Linux):**
  1. Buka terminal dan install Apache, MySQL, dan PHP menggunakan package manager.
  2. Konfigurasikan Apache untuk menjalankan PHP.
  3. Restart Apache untuk mulai menggunakan LAMP.

### **Mengonfigurasi File php.ini**
Setelah instalasi server lokal, file **php.ini** adalah tempat di mana kalian bisa mengonfigurasi berbagai pengaturan PHP. Misalnya:
- **Error Reporting:** Mengaktifkan atau menonaktifkan laporan error untuk debugging.
- **Upload Max Filesize:** Mengatur ukuran maksimum file yang bisa di-upload.
- **Memory Limit:** Mengatur jumlah memori yang bisa digunakan oleh skrip PHP.

**Contoh Nyata di Sekolah:**
Bayangkan Anwar Nurjaman dari kelas XI PPLG A ingin membuat situs sekolah untuk proyek tugas akhirnya. Dia memerlukan server lokal untuk menguji kode PHP yang ditulisnya sebelum situs tersebut diunggah ke internet. Dengan server lokal, Anwar bisa menjalankan situs sekolahnya di laptop pribadi, melihat hasilnya, dan melakukan perubahan dengan cepat.

## **2. Penulisan Skrip PHP Pertama**

### **Sintaks Dasar PHP**
PHP adalah bahasa pemrograman yang sangat fleksibel, dan sintaks dasarnya mudah dipahami. Skrip PHP selalu dimulai dengan `<?php` dan diakhiri dengan `?>`.

```php
<?php
  echo "Halo, SMK Assalam Samarang!";
?>
```
Kode di atas akan menampilkan teks "Halo, SMK Assalam Samarang!" di browser kalian.

### **Praktik Menulis Kode PHP yang Baik**
- **Gunakan Komentar:** Tambahkan komentar pada kode kalian untuk menjelaskan apa yang dilakukan oleh bagian tertentu dari skrip. Ini sangat membantu ketika kalian atau orang lain membaca kembali kode tersebut di masa mendatang.
  ```php
  // Ini adalah komentar satu baris
  /* Ini adalah komentar 
     multi-baris */
  ```
- **Struktur Kode yang Rapi:** Gunakan indentasi yang konsisten dan pisahkan kode menjadi blok-blok yang logis. Ini akan membuat kode kalian lebih mudah dibaca dan dipelihara.

## **3. Menyisipkan PHP di dalam HTML dan Sebaliknya**

PHP dan HTML adalah pasangan yang serasi dalam pengembangan web. PHP memungkinkan kalian untuk membuat konten dinamis di dalam HTML, sementara HTML memberi struktur dan tampilan pada halaman web.

### **Menyisipkan PHP di dalam HTML**

Salah satu kekuatan PHP adalah kemampuannya untuk disisipkan langsung ke dalam HTML, memungkinkan kalian untuk menghasilkan konten dinamis berdasarkan logika yang kalian tentukan.

**Contoh Sederhana:**
```php
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Selamat Datang di SMK Assalam Samarang</title>
</head>
<body>
    <h1><?php echo "Selamat Datang, Siswa SMK Assalam Samarang!"; ?></h1>
    <p>Ini adalah halaman web pertama kalian dengan PHP.</p>
</body>
</html>
```
Dalam contoh di atas, PHP digunakan untuk menghasilkan teks "Selamat Datang, Siswa SMK Assalam Samarang!" di dalam tag `<h1>` pada halaman HTML. Kalian bisa menambahkan logika PHP di bagian manapun dalam dokumen HTML kalian, selama berada di dalam tag `<?php ?>`.

### **Menyisipkan HTML di dalam PHP**

Sebaliknya, kalian juga bisa menyisipkan HTML di dalam kode PHP. Ini sangat berguna ketika kalian ingin menghasilkan struktur HTML yang lebih kompleks berdasarkan kondisi tertentu atau data dari database.

**Contoh:**
```php
<?php
  $nama_siswa = "Hilman Attamimi";
  echo "<h1>Selamat Datang, " . $nama_siswa . "!</h1>";
  echo "<p>Ini adalah halaman web dinamis yang menggunakan PHP untuk menampilkan nama siswa.</p>";
?>
```
Di sini, PHP digunakan untuk menampilkan nama siswa di dalam tag `<h1>` dan paragraf `<p>`. Dengan menyisipkan HTML di dalam PHP, kalian bisa menghasilkan halaman web yang berbeda untuk setiap siswa, berdasarkan data yang diambil dari sistem sekolah.

**Penggunaan Lanjutan:**
- **Logika Kondisional**: PHP memungkinkan kalian untuk menggunakan if-else statements untuk menampilkan konten HTML yang berbeda berdasarkan kondisi tertentu.
- **Looping**: Dengan menggunakan loop seperti `for` atau `foreach`, kalian bisa menghasilkan daftar elemen HTML (misalnya daftar siswa) secara otomatis berdasarkan data yang ada.

### **Bagaimana PHP Mengelola Konten Dinamis?**
Dengan PHP, kalian bisa menampilkan konten yang berbeda berdasarkan input pengguna atau kondisi tertentu. Misalnya, kalian bisa menampilkan pesan "Selamat Datang, Amanda Aulia!" jika siswa yang mengakses adalah Amanda Aulia dari kelas XI PPLG A.

## **4. Praktik Terbaik dalam Menulis Kode PHP**

### **Pisahkan Logika dari Tampilan**
Sebisa mungkin, pisahkan logika pemrograman dari kode HTML. Ini memudahkan kalian dalam memelihara dan mengembangkan aplikasi di masa mendatang.

### **Gunakan Variabel dan Fungsi**
Gunakan variabel untuk menyimpan data sementara yang sering digunakan. Fungsi membantu kalian untuk mengelompokkan kode yang melakukan tugas tertentu, sehingga kode kalian lebih modular dan mudah diatur.

### **Validasi Input**
Pastikan setiap input yang diterima dari pengguna divalidasi dan disanitasi. Ini penting untuk mencegah masalah keamanan seperti SQL Injection atau Cross-Site Scripting (XSS).

**Contoh Nyata:**
Misalnya, ketika Muamar dari kelas XII PPLG A membuat aplikasi form pendaftaran siswa baru, dia harus memastikan bahwa setiap data yang dimasukkan oleh calon siswa divalidasi dengan benar untuk mencegah kesalahan atau celah keamanan.

---

### **Aktivitas**

1. **Diskusi Kelompok:**
   - **Topik:** Mengapa konfigurasi lingkungan pengembangan yang benar penting dalam pengembangan aplikasi?
   - **Tujuan:** Memahami pentingnya konfigurasi yang tepat untuk menghindari masalah saat aplikasi di-deploy ke server produksi.

2. **Latihan:**
   - **Tugas:** Instal server lokal di komputer kalian dan tulis skrip PHP sederhana yang menampilkan pesan selamat datang. Lakukan uji coba di browser dan diskusikan hasilnya.
   - **Output:** Skrip PHP pertama yang berjalan dengan sukses di server lokal.

---
### Navigasi
[⏮ Pengantar](../1-pengantar/README.md) || [Home 🏘](../README.md) || [Variable ⏭](../3-variable/README.md)