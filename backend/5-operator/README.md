# **Bab 5 - Operator dalam PHP**

## **Tujuan Pembelajaran**
Pada akhir pertemuan ini, kalian diharapkan mampu:
- Memahami berbagai jenis operator yang tersedia dalam PHP.
- Menggunakan operator untuk melakukan operasi aritmatika, logika, perbandingan, dan lainnya.
- Memahami prioritas operator dan cara kerjanya dalam ekspresi kompleks.

## **Materi yang Akan Dibahas**
1. Pengenalan Operator
2. Operator Aritmatika
3. Operator Penugasan
4. Operator Perbandingan
5. Operator Logika
6. Operator Bitwise
7. Operator Increment dan Decrement
8. Operator String
9. Operator Array
10. Prioritas Operator

---

## **1. Pengenalan Operator**

### **Apa Itu Operator?**
Operator adalah simbol atau kata kunci yang digunakan untuk melakukan operasi pada satu atau lebih nilai (operand). Misalnya, operator penjumlahan (`+`) digunakan untuk menjumlahkan dua nilai, sedangkan operator logika (`&&`) digunakan untuk melakukan operasi logika pada dua nilai boolean.

PHP menyediakan berbagai macam operator yang dapat kalian gunakan untuk berbagai keperluan, seperti operasi aritmatika, perbandingan, logika, dan lainnya.

## **2. Operator Aritmatika**

Operator aritmatika digunakan untuk melakukan operasi matematika dasar seperti penjumlahan, pengurangan, perkalian, pembagian, dan modulus.

**Jenis-Jenis Operator Aritmatika:**
- **Penjumlahan (`+`)**: Menjumlahkan dua nilai.
  ```php
  <?php
    $a = 10;
    $b = 5;
    $hasil = $a + $b; // $hasil = 15
  ?>
  ```
- **Pengurangan (`-`)**: Mengurangkan nilai kedua dari nilai pertama.
  ```php
  <?php
    $hasil = $a - $b; // $hasil = 5
  ?>
  ```
- **Perkalian (`*`)**: Mengalikan dua nilai.
  ```php
  <?php
    $hasil = $a * $b; // $hasil = 50
  ?>
  ```
- **Pembagian (`/`)**: Membagi nilai pertama dengan nilai kedua.
  ```php
  <?php
    $hasil = $a / $b; // $hasil = 2
  ?>
  ```
- **Modulus (`%`)**: Menghasilkan sisa bagi dari pembagian dua nilai.
  ```php
  <?php
    $hasil = $a % $b; // $hasil = 0 (karena 10 dibagi 5 tidak bersisa)
  ?>
  ```

### **Penggunaan dalam Program:**
Operator aritmatika sering digunakan dalam operasi perhitungan, seperti menghitung rata-rata nilai siswa atau menghitung total harga dalam aplikasi belanja online.

## **3. Operator Penugasan**

Operator penugasan digunakan untuk menetapkan nilai ke variabel. Operator penugasan yang paling umum adalah `=`.

**Jenis-Jenis Operator Penugasan:**
- **Penugasan Sederhana (`=`)**: Mengatur nilai variabel di sebelah kiri dengan nilai di sebelah kanan.
  ```php
  <?php
    $x = 10; // $x sekarang bernilai 10
  ?>
  ```
- **Penugasan dengan Operasi Aritmatika**: Kalian bisa menggabungkan operator aritmatika dengan operator penugasan.
  - **Penjumlahan dan Penugasan (`+=`)**:
    ```php
    <?php
      $x += 5; // Sama dengan $x = $x + 5
    ?>
    ```
  - **Pengurangan dan Penugasan (`-=`)**:
    ```php
    <?php
      $x -= 5; // Sama dengan $x = $x - 5
    ?>
    ```
  - **Perkalian dan Penugasan (`*=`)**:
    ```php
    <?php
      $x *= 5; // Sama dengan $x = $x * 5
    ?>
    ```
  - **Pembagian dan Penugasan (`/=`)**:
    ```php
    <?php
      $x /= 5; // Sama dengan $x = $x / 5
    ?>
    ```
  - **Modulus dan Penugasan (`%=`)**:
    ```php
    <?php
      $x %= 5; // Sama dengan $x = $x % 5
    ?>
    ```

### **Penggunaan dalam Program:**
Operator penugasan digunakan di seluruh program untuk menginisialisasi variabel dan memperbarui nilainya berdasarkan operasi tertentu.

## **4. Operator Perbandingan**

Operator perbandingan digunakan untuk membandingkan dua nilai dan mengembalikan nilai boolean (`true` atau `false`).

**Jenis-Jenis Operator Perbandingan:**
- **Sama dengan (`==`)**: Mengecek apakah dua nilai sama.
  ```php
  <?php
    $a = 10;
    $b = "10";
    var_dump($a == $b); // Mengembalikan true karena nilai sama, meskipun tipe berbeda
  ?>
  ```
- **Identik (`===`)**: Mengecek apakah dua nilai dan tipe datanya sama.
  ```php
  <?php
    var_dump($a === $b); // Mengembalikan false karena tipe data berbeda
  ?>
  ```
- **Tidak Sama dengan (`!=` atau `<>`)**: Mengecek apakah dua nilai tidak sama.
  ```php
  <?php
    var_dump($a != $b); // Mengembalikan false karena nilai sama
  ?>
  ```
- **Tidak Identik (`!==`)**: Mengecek apakah dua nilai atau tipe datanya tidak sama.
  ```php
  <?php
    var_dump($a !== $b); // Mengembalikan true karena tipe data berbeda
  ?>
  ```
- **Lebih Besar dari (`>`)**: Mengecek apakah nilai pertama lebih besar dari nilai kedua.
  ```php
  <?php
    var_dump($a > $b); // Mengembalikan false
  ?>
  ```
- **Lebih Kecil dari (`<`)**: Mengecek apakah nilai pertama lebih kecil dari nilai kedua.
  ```php
  <?php
    var_dump($a < $b); // Mengembalikan false
  ?>
  ```
- **Lebih Besar atau Sama dengan (`>=`)**: Mengecek apakah nilai pertama lebih besar atau sama dengan nilai kedua.
  ```php
  <?php
    var_dump($a >= $b); // Mengembalikan true
  ?>
  ```
- **Lebih Kecil atau Sama dengan (`<=`)**: Mengecek apakah nilai pertama lebih kecil atau sama dengan nilai kedua.
  ```php
  <?php
    var_dump($a <= $b); // Mengembalikan true
  ?>
  ```

### **Penggunaan dalam Program:**
Operator perbandingan sangat penting dalam membuat keputusan dalam program, seperti mengecek apakah nilai siswa memenuhi syarat untuk lulus atau tidak.

## **5. Operator Logika**

Operator logika digunakan untuk melakukan operasi logika pada dua nilai boolean. Operator logika mengembalikan nilai boolean (`true` atau `false`) berdasarkan hasil operasi.

**Jenis-Jenis Operator Logika:**
- **Dan (`&&` atau `and`)**: Mengembalikan true jika kedua operand adalah true.
  ```php
  <?php
    $x = true;
    $y = false;
    var_dump($x && $y); // Mengembalikan false
  ?>
  ```
- **Atau (`||` atau `or`)**: Mengembalikan true jika salah satu operand adalah true.
  ```php
  <?php
    var_dump($x || $y); // Mengembalikan true
  ?>
  ```
- **Tidak (`!`)**: Mengembalikan kebalikan dari nilai boolean.
  ```php
  <?php
    var_dump(!$x); // Mengembalikan false
  ?>
  ```

### **Penggunaan dalam Program:**
Operator logika sering digunakan dalam pernyataan kondisional untuk menggabungkan beberapa kondisi, seperti memeriksa apakah seorang siswa lulus dan memenuhi kriteria tambahan lainnya.

## **6. Operator Bitwise**

Operator bitwise digunakan untuk melakukan operasi pada level bit. Ini biasanya digunakan dalam pemrograman tingkat rendah atau ketika kalian perlu mengoptimalkan penggunaan memori.

**Jenis-Jenis Operator Bitwise:**
- **AND Bitwise (`&`)**: Membandingkan setiap bit dari dua angka dan mengembalikan 1 jika kedua bit tersebut adalah 1.
  ```php
  <?php
    $a = 6; // 110 dalam biner
    $b = 3; // 011 dalam biner
    $c = $a & $b; // 010 dalam biner (2 dalam desimal)
  ?>
  ```
- **OR Bitwise (`|`)**: Membandingkan setiap bit dari dua angka dan mengembalikan 1 jika salah satu dari bit tersebut adalah 1.
  ```php
  <?php
    $c = $a | $b; // 111 dalam biner (7 dalam desimal)
  ?>
  ```
- **XOR Bitwise (`^`)**: Membandingkan setiap bit dari dua angka dan mengembalikan 1 jika hanya satu dari bit tersebut yang bernilai 1.
  ```php
  <?php
    $c = $a ^ $b; // 101 dalam biner (5 dalam desimal)
  ?>
  ```
- **NOT Bitwise (`~`)**: Mengubah setiap bit menjadi nilai kebalikannya (0 menjadi 1 dan 1 menjadi 0).
  ```php
  <?php
    $c = ~$a; // 001 dalam biner (dalam representasi komplement dua)
  ?>
  ```
- **Left Shift (`<<`)**: Menggeser bit ke kiri sebanyak jumlah yang ditentukan.
  ```php
  <?php
    $c = $a << 1; // 1100 dalam biner (12 dalam desimal)
  ?>
  ```
- **Right Shift (`>>`)**: Menggeser bit ke kanan sebanyak jumlah yang ditentukan.
  ```php
  <?php
    $c = $a >> 1; // 011 dalam biner (3 dalam desimal)
  ?>
  ```

### **Penggunaan dalam Program:**
Operator bitwise sering digunakan dalam aplikasi yang memerlukan operasi di tingkat biner, seperti enkripsi, kompresi data, atau pemrograman perangkat keras.

## **7. Operator Increment dan Decrement**

Operator increment (`++`) dan decrement (`--`) digunakan untuk menambah atau mengurangi nilai variabel dengan satu.

**Jenis-Jenis Operator Increment dan Decrement:**
- **Increment (`++`)**: Menambah nilai variabel dengan satu.
  ```php
  <?php
    $x = 5;
    $x++; // $x sekarang bernilai 6
  ?>
  ```
- **Decrement (`--`)**: Mengurangi nilai variabel dengan satu.
  ```php
  <?php
    $x--; // $x sekarang bernilai 4
  ?>
  ```

### **Pre-Increment dan Post-Increment:**
- **Pre-Increment (`++$x`)**: Nilai variabel ditambah satu sebelum digunakan dalam ekspresi.
- **Post-Increment (`$x++`)**: Nilai variabel ditambah satu setelah digunakan dalam ekspresi.

**Contoh:**
```php
<?php
  $x = 5;
  echo ++$x; // Menampilkan 6
  echo $x++; // Menampilkan 6, lalu $x menjadi 7
  echo $x; // Menampilkan 7
?>
```

### **Penggunaan dalam Program:**
Operator ini sering digunakan dalam loop atau pengulangan untuk mengontrol jumlah iterasi.

## **8. Operator String**

Operator string digunakan untuk menggabungkan dua string. PHP menggunakan operator titik (`.`) untuk menggabungkan string.

**Contoh:**
```php
<?php
  $namaDepan = "Amanda";
  $namaBelakang = "Aulia";
  $namaLengkap = $namaDepan . " " . $namaBelakang; // Menghasilkan "Amanda Aulia"
  echo $namaLengkap;
?>
```

### **Penggunaan dalam Program:**
Operator string sering digunakan untuk menyusun pesan, membangun query SQL secara dinamis, atau menghasilkan konten HTML.

## **9. Operator Array**

PHP menyediakan operator khusus untuk bekerja dengan array. Operator ini memungkinkan kalian untuk menggabungkan, membandingkan, dan memanipulasi array.

**Jenis-Jenis Operator Array:**
- **Penggabungan Array (`+`)**: Menggabungkan dua array. Jika ada kunci yang sama, nilai dari array pertama yang akan dipertahankan.
  ```php
  <?php
    $array1 = array("a" => "apel", "b" => "jeruk");
    $array2 = array("b" => "pisang", "c" => "mangga");
    $result = $array1 + $array2; // $result berisi array("a" => "apel", "b" => "jeruk", "c" => "mangga")
  ?>
  ```
- **Perbandingan Array (`==`, `===`, `!=`, `!==`)**: Digunakan untuk membandingkan dua array berdasarkan elemen dan urutannya.
  ```php
  <?php
    var_dump($array1 == $array2); // Mengembalikan false karena array berbeda
  ?>
  ```

### **Penggunaan dalam Program:**
Operator array sangat berguna dalam pemrosesan data yang kompleks, seperti manipulasi data pengguna atau pengelolaan data dari form.

## **10. Prioritas Operator**

Prioritas operator menentukan urutan di mana operator dalam ekspresi dievaluasi. Operator dengan prioritas lebih tinggi dievaluasi lebih dahulu. Jika dua operator memiliki prioritas yang sama, PHP mengevaluasi dari kiri ke kanan.

**Contoh:**
```php
<?php
  $x = 5 + 3 * 2; // Hasilnya 11 karena * memiliki prioritas lebih tinggi daripada +
?>
```
Jika kalian ingin mengubah urutan evaluasi, gunakan tanda kurung:
```php
<?php
  $x = (5 + 3) * 2; // Hasilnya 16
?>
```

### **Penggunaan dalam Program:**
Memahami prioritas operator penting untuk menulis ekspresi yang kompleks dengan hasil yang benar.

---

### **Aktivitas**

1. **Diskusi Kelompok:**
   - **Topik:** Bagaimana prioritas operator dapat mempengaruhi hasil perhitungan dalam program PHP?
   - **Tujuan:** Memahami pentingnya prioritas operator dalam menulis kode yang benar dan efisien.

2. **Latihan:**
   - **Tugas:** Buat skrip PHP yang menggunakan berbagai jenis operator. Uji coba dengan mengubah prioritas operator menggunakan tanda kurung.
   - **Output:** Skrip PHP yang menampilkan hasil perhitungan dengan berbagai operator dan prioritasnya.

---
### Navigasi
[⏮ Tipe Data](../4-tipe-data/README.md) || [Home 🏘](../README.md) || [Control Flow ⏭](../6-control-flow/README.md)