# **Bab 4 - Tipe Data dalam PHP**

## **Tujuan Pembelajaran**
Pada akhir pertemuan ini, kalian diharapkan mampu:
- Mengenali berbagai tipe data yang didukung oleh PHP.
- Memahami bagaimana PHP mengelola tipe data dan konversinya.
- Menggunakan tipe data yang tepat untuk berbagai keperluan dalam program.
- Memahami perbedaan antara penggunaan kutip satu (`'`) dan kutip dua (`"`) dalam string.

## **Materi yang Akan Dibahas**
1. Pengenalan Tipe Data dalam PHP
2. Tipe Data Primitif
3. Tipe Data Khusus
4. Konversi Tipe Data
5. Operasi dengan Tipe Data Berbeda
6. Perbedaan Penggunaan Kutip Satu (`'`) dan Kutip Dua (`"`)

---

## **1. Pengenalan Tipe Data dalam PHP**

### **Apa Itu Tipe Data?**
Tipe data adalah kategori yang digunakan untuk menentukan jenis data yang dapat disimpan dan diolah dalam sebuah variabel. Dalam PHP, tipe data menentukan bagaimana komputer menyimpan dan memproses data tersebut.

PHP adalah bahasa yang **loosely typed**, yang berarti kalian tidak perlu menentukan tipe data saat mendeklarasikan variabel. PHP akan menentukan tipe data berdasarkan nilai yang kalian masukkan ke dalam variabel.

**Contoh:**
```php
<?php
  $nama = "Amanda Aulia"; // String
  $umur = 17; // Integer
  $nilai = 85.5; // Float
?>
```
Dalam contoh di atas, PHP secara otomatis menetapkan tipe data yang sesuai untuk setiap variabel berdasarkan nilai yang diberikan.

## **2. Tipe Data Primitif**

### **1. String**
String adalah kumpulan karakter, seperti kata atau kalimat. Dalam PHP, string ditulis di antara tanda kutip tunggal (`'`) atau ganda (`"`).

**Contoh:**
```php
<?php
  $nama = "Hilman Attamimi";
  echo $nama; // Menampilkan "Hilman Attamimi"
?>
```

**Fungsi String:**
- **strlen()**: Menghitung panjang string.
- **strtoupper()**: Mengubah string menjadi huruf besar semua.
- **strtolower()**: Mengubah string menjadi huruf kecil semua.

**Contoh Penggunaan:**
```php
<?php
  $nama = "Siti Salma";
  echo strtoupper($nama); // Menampilkan "SITI SALMA"
?>
```

### **2. Integer**
Integer adalah bilangan bulat, baik positif maupun negatif, tanpa titik desimal. Tipe data ini biasanya digunakan untuk menghitung atau menyimpan jumlah.

**Contoh:**
```php
<?php
  $umur = 18;
  $tahunLulus = 2024;
?>
```

### **3. Float**
Float (atau double) adalah bilangan pecahan, yang berarti bilangan yang memiliki bagian desimal. Float biasanya digunakan untuk nilai yang membutuhkan presisi lebih, seperti angka dengan koma.

**Contoh:**
```php
<?php
  $nilaiUjian = 89.75;
?>
```

### **4. Boolean**
Boolean adalah tipe data yang hanya memiliki dua nilai: **true** atau **false**. Boolean sering digunakan dalam perbandingan dan pengambilan keputusan dalam program.

**Contoh:**
```php
<?php
  $lulus = true;
  $diterima = false;
?>
```

**Penggunaan dalam Kondisi:**
```php
<?php
  $nilai = 85;
  $lulus = $nilai > 75; // True jika nilai lebih besar dari 75
  if ($lulus) {
    echo "Selamat, kamu lulus!";
  }
?>
```

## **3. Tipe Data Khusus**

### **1. Array**
Array adalah kumpulan nilai yang disimpan dalam satu variabel. Setiap nilai dalam array memiliki indeks, yang dapat berupa angka (array numerik) atau string (array asosiatif).

**Contoh Array Numerik:**
```php
<?php
  $siswa = array("Amanda", "Hilman", "Anisa");
  echo $siswa[0]; // Menampilkan "Amanda"
?>
```

**Contoh Array Asosiatif:**
```php
<?php
  $nilaiSiswa = array("Amanda" => 85, "Hilman" => 90, "Anisa" => 78);
  echo $nilaiSiswa["Hilman"]; // Menampilkan 90
?>
```

### **2. Object**
Object adalah instance dari class yang merupakan template dari object. PHP mendukung pemrograman berorientasi objek (OOP), di mana kalian bisa mendefinisikan class dan membuat object dari class tersebut.

**Contoh:**
```php
<?php
  class Siswa {
    public $nama;
    public $umur;

    function tampilkanNama() {
      return $this->nama;
    }
  }

  $siswa1 = new Siswa();
  $siswa1->nama = "Nabila Laelatul Zahro";
  echo $siswa1->tampilkanNama(); // Menampilkan "Nabila Laelatul Zahro"
?>
```

### **3. NULL**
NULL adalah tipe data khusus yang hanya memiliki satu nilai, yaitu `NULL`. Ini digunakan untuk merepresentasikan variabel yang tidak memiliki nilai.

**Contoh:**
```php
<?php
  $x = null;
  var_dump($x); // Menampilkan NULL
?>
```

### **4. Resource**
Resource adalah tipe data khusus yang digunakan untuk merepresentasikan referensi ke sumber daya eksternal, seperti koneksi database atau file yang sedang dibuka.

**Contoh:**
```php
<?php
  $file = fopen("data.txt", "r"); // Membuka file untuk dibaca
  // $file sekarang adalah resource
?>
```

## **4. Konversi Tipe Data**

PHP secara otomatis melakukan konversi tipe data jika diperlukan, tetapi kalian juga bisa melakukan konversi secara manual.

**Contoh Otomatis:**
```php
<?php
  $x = "10"; // String
  $y = $x + 5; // PHP otomatis mengonversi $x menjadi integer
  echo $y; // Menampilkan 15
?>
```

**Contoh Manual:**
```php
<?php
  $x = "10.5"; // String
  $y = (int)$x; // Mengonversi $x menjadi integer secara manual
  echo $y; // Menampilkan 10
?>
```

## **5. Operasi dengan Tipe Data Berbeda**

PHP memungkinkan kalian untuk melakukan operasi aritmatika dan logika dengan tipe data yang berbeda. Namun, hasilnya bisa bervariasi tergantung pada tipe data yang terlibat.

**Contoh:**
```php
<?php
  $x = "10"; // String
  $y = 20; // Integer
  $z = $x + $y; // PHP mengonversi $x menjadi integer dan menjumlahkannya dengan $y
  echo $z; // Menampilkan 30
?>
```

Namun, sebaiknya kalian berhati-hati dalam mencampur tipe data yang berbeda dalam operasi untuk menghindari hasil yang tidak terduga.

## **6. Perbedaan Penggunaan Kutip Satu (`'`) dan Kutip Dua (`"`)**

### **Kutip Satu (`'`):**
Kutip satu digunakan untuk mendefinisikan string yang isinya tidak memerlukan parsing khusus oleh PHP. Artinya, jika kalian menggunakan kutip satu, PHP akan menganggap semua karakter di dalamnya sebagai bagian dari string, kecuali karakter escape seperti `\'`.

**Contoh:**
```php
<?php
  $nama = 'Hilman Attamimi';
  echo 'Nama siswa: $nama'; // Menampilkan 'Nama siswa: $nama' (tanpa mengganti $nama dengan nilai variabel)
?>
```
Dalam contoh di atas, `$nama` akan ditampilkan sebagai teks literal, bukan sebagai nilai variabel.

### **Kutip Dua (`"`):**
Kutip dua digunakan ketika kalian ingin menyertakan variabel atau karakter escape dalam string. PHP akan mem-parsing isi string yang berada di antara kutip dua dan mengganti variabel dengan nilainya.

**Contoh:**
```php
<?php
  $nama = "Hilman Attamimi";
  echo "Nama siswa: $nama"; // Menampilkan "Nama siswa: Hilman Attamimi"
?>
```
Di sini, PHP mengganti `$nama` dengan nilai variabel tersebut, yaitu "Hilman Attamimi".

### **Penggunaan Karakter Escape:**
- **Kutip Satu (`\'`)**: Jika kalian perlu menggunakan tanda kutip satu di dalam string yang diapit oleh kutip satu, gunakan backslash (`\`) sebagai escape character.
  ```php
  <?php
    echo 'Ini adalah \'kutipan\' dalam string.';
  ?>
  ```
- **Kutip Dua (`\"`)**: Jika kalian perlu menggunakan tanda kutip dua di dalam string yang diapit oleh kutip dua, gunakan backslash (`\`) sebagai escape character.
  ```php
  <?php
    echo "Ini adalah \"kutipan\" dalam string.";
  ?>
  ```
  
### **Kapan Menggunakan Kutip Satu atau Kutip Dua?**

- **Kutip Satu (`'`)**: 
  - Gunakan kutip satu jika string kalian tidak mengandung variabel yang perlu di-parsing oleh PHP. Ini sedikit lebih cepat dalam eksekusi karena PHP tidak perlu memproses string tersebut.
  - Cocok untuk string yang tidak perlu memanfaatkan karakter escape atau variabel.

- **Kutip Dua (`"`):**
  - Gunakan kutip dua jika kalian perlu menyertakan variabel dalam string atau ingin menggunakan karakter escape yang dikenali oleh PHP seperti `\n` untuk baris baru.
  - Cocok untuk string dinamis yang membutuhkan penggantian nilai variabel di dalamnya.

---

### **Aktivitas**

1. **Diskusi Kelompok:**
   - **Topik:** Mengapa penting untuk memahami perbedaan antara kutip satu dan kutip dua dalam PHP?
   - **Tujuan:** Memahami kapan harus menggunakan kutip satu atau kutip dua untuk mengoptimalkan kode dan menghindari kesalahan.

2. **Latihan:**
   - **Tugas:** Buat skrip PHP yang menampilkan kalimat yang berisi variabel dan karakter escape. Uji coba menggunakan kutip satu dan kutip dua untuk melihat perbedaannya.
   - **Output:** Skrip PHP yang menunjukkan perbedaan hasil antara penggunaan kutip satu dan kutip dua.

---
### Navigasi
[⏮ Variable](../3-variable/README.md) || [Home 🏘](../README.md) || [Tipe Data ⏭](../5-operator/README.md)