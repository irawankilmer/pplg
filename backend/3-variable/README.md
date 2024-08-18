# **Bab 3 - Variabel dalam PHP**

## **Tujuan Pembelajaran**
Pada akhir pertemuan ini, kalian diharapkan mampu:
- Memahami konsep variabel dan cara mendeklarasikannya dalam PHP.
- Menggunakan variabel untuk menyimpan dan mengelola data dalam program PHP.
- Mengerti perbedaan antara variabel lokal dan global serta penggunaan konstanta.

## **Materi yang Akan Dibahas**
1. Pengertian dan Deklarasi Variabel
2. Aturan Penamaan Variabel
3. Variabel Lokal dan Global
4. Konstanta dalam PHP

---

## **1. Pengertian dan Deklarasi Variabel**

### **Apa Itu Variabel?**
Variabel adalah tempat penyimpanan sementara untuk data yang bisa digunakan dan dimanipulasi dalam program. Dalam PHP, variabel digunakan untuk menyimpan nilai yang mungkin berubah selama program berjalan, seperti nama pengguna, angka, atau hasil perhitungan.

### **Deklarasi Variabel**
Di PHP, variabel didahului dengan tanda `$`, diikuti dengan nama variabel. Kalian tidak perlu mendeklarasikan tipe data variabel seperti di bahasa pemrograman lainnya, karena PHP adalah bahasa yang **loosely typed**. Ini berarti PHP secara otomatis mengenali tipe data yang disimpan dalam variabel berdasarkan nilai yang diberikan.

**Contoh Deklarasi:**
```php
<?php
  $nama = "Amanda Aulia"; // Variabel string
  $umur = 17; // Variabel integer
  $nilai = 85.5; // Variabel float
?>
```
Dalam contoh di atas, `$nama`, `$umur`, dan `$nilai` adalah variabel yang masing-masing menyimpan data dengan tipe yang berbeda.

### **Mengakses dan Mengubah Nilai Variabel**
Setelah variabel dideklarasikan, kalian bisa mengakses atau mengubah nilainya kapan saja di dalam program.

**Contoh:**
```php
<?php
  $nama = "Amanda Aulia";
  echo "Nama: " . $nama; // Menampilkan "Nama: Amanda Aulia"

  $nama = "Anisa"; // Mengubah nilai variabel
  echo "Nama baru: " . $nama; // Menampilkan "Nama baru: Anisa"
?>
```
Di sini, nilai `$nama` pertama kali diatur ke "Amanda Aulia", kemudian diubah menjadi "Anisa".

## **2. Aturan Penamaan Variabel**

### **Aturan Dasar Penamaan Variabel:**
1. **Harus dimulai dengan huruf atau underscore (`_`)**: Nama variabel tidak boleh dimulai dengan angka.
2. **Tidak boleh mengandung spasi**: Gunakan underscore (`_`) untuk menggantikan spasi, atau gunakan **camelCase**.
3. **Peka huruf besar/kecil (case-sensitive)**: `$nama` dan `$Nama` adalah dua variabel yang berbeda.

**Contoh Penamaan yang Benar:**
```php
<?php
  $namaDepan = "Amanda";
  $_usia = 17;
  $nilai_ujian = 85.5;
?>
```
**Contoh Penamaan yang Salah:**
```php
<?php
  $1nama = "Amanda"; // Salah: Tidak boleh diawali dengan angka
  $nama siswa = "Anisa"; // Salah: Tidak boleh ada spasi
?>
```

### **Best Practices Penamaan Variabel:**
- **Gunakan nama variabel yang deskriptif**: Ini akan memudahkan kalian atau orang lain untuk memahami kode kalian di kemudian hari. Misalnya, daripada menulis `$n`, lebih baik menulis `$nilaiUjian` untuk menunjukkan bahwa variabel tersebut menyimpan nilai ujian.
- **Gunakan camelCase atau underscore untuk penamaan yang lebih jelas**: Misalnya, `$namaDepan` atau `$nama_depan`.

## **3. Variabel Lokal dan Global**

### **Variabel Lokal**
Variabel lokal adalah variabel yang dideklarasikan di dalam sebuah fungsi dan hanya bisa diakses di dalam fungsi tersebut.

**Contoh:**
```php
<?php
  function tampilkanNama() {
    $nama = "Nabila"; // Variabel lokal
    echo $nama;
  }

  tampilkanNama(); // Menampilkan "Nabila"
  echo $nama; // Error: Variabel tidak dikenali di luar fungsi
?>
```
Di sini, `$nama` adalah variabel lokal dan tidak bisa diakses di luar fungsi `tampilkanNama()`.

### **Variabel Global**
Variabel global adalah variabel yang dideklarasikan di luar fungsi dan bisa diakses dari mana saja dalam script, kecuali dari dalam fungsi, kecuali jika menggunakan kata kunci `global`.

**Contoh:**
```php
<?php
  $nama = "Hilman"; // Variabel global

  function tampilkanNama() {
    global $nama; // Mengakses variabel global di dalam fungsi
    echo $nama;
  }

  tampilkanNama(); // Menampilkan "Hilman"
?>
```
Dengan menggunakan kata kunci `global`, kita bisa mengakses variabel global di dalam fungsi.

### **Superglobals**
PHP menyediakan beberapa variabel superglobal yang bisa diakses dari mana saja dalam script tanpa harus mendeklarasikannya sebagai global. Beberapa contoh superglobal adalah:
- `$_GET`: Mengambil data dari URL (query string).
- `$_POST`: Mengambil data dari form yang dikirimkan dengan metode POST.
- `$_SESSION`: Menyimpan data yang akan digunakan di seluruh halaman dalam sesi yang sama.
- `$_SERVER`: Menyimpan informasi tentang server dan lingkungan eksekusi PHP.

**Contoh Penggunaan Superglobal:**
```php
<?php
  echo "User Agent: " . $_SERVER['HTTP_USER_AGENT'];
?>
```
Kode ini akan menampilkan informasi tentang browser yang digunakan oleh pengguna.

## **4. Konstanta dalam PHP**

### **Apa Itu Konstanta?**
Konstanta adalah nilai yang tidak berubah selama eksekusi skrip. Berbeda dengan variabel, setelah konstanta ditetapkan, nilainya tidak bisa diubah atau dihapus.

### **Deklarasi Konstanta**
Konstanta dideklarasikan menggunakan fungsi `define()` atau kata kunci `const`.

**Contoh:**
```php
<?php
  define("NAMA_SEKOLAH", "SMK Assalam Samarang");
  echo NAMA_SEKOLAH; // Menampilkan "SMK Assalam Samarang"
?>
```
Di sini, `NAMA_SEKOLAH` adalah konstanta yang nilainya tetap "SMK Assalam Samarang" sepanjang program.

### **Perbedaan Antara Variabel dan Konstanta:**
- **Nilai:** Variabel dapat berubah, sedangkan konstanta nilainya tetap.
- **Deklarasi:** Variabel menggunakan `$`, sedangkan konstanta tidak.
- **Ruang Lingkup:** Konstanta bersifat global dan dapat diakses dari mana saja dalam program, tanpa perlu mendeklarasikannya sebagai global.

---

### **Aktivitas**

1. **Diskusi Kelompok:**
   - **Topik:** Kapan kalian harus menggunakan variabel dan kapan harus menggunakan konstanta?
   - **Tujuan:** Memahami situasi di mana penggunaan variabel atau konstanta lebih tepat untuk memastikan program berjalan efisien.

2. **Latihan:**
   - **Tugas:** Buatlah skrip PHP sederhana yang menggunakan variabel untuk menyimpan informasi siswa (seperti nama, kelas, dan nilai), kemudian tampilkan informasi tersebut. Gunakan konstanta untuk menyimpan nama sekolah.
   - **Output:** Skrip PHP yang menampilkan informasi siswa secara dinamis dengan nama sekolah yang tetap.

---
### Navigasi
[⏮ Konfigurasi](../2-konfigurasi/README.md) || [Home 🏘](../README.md) || [Tipe Data ⏭](../4-tipe-data/README.md)