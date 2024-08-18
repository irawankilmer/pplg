# **Bab 8 - Array dalam PHP**

## **Tujuan Pembelajaran**
Pada akhir pertemuan ini, kalian diharapkan mampu:
- Memahami konsep dasar array dan jenis-jenisnya dalam PHP.
- Menggunakan array numerik dan asosiatif untuk menyimpan dan mengelola data.
- Mengimplementasikan array multidimensi untuk menyimpan data yang lebih kompleks.
- Melakukan operasi dasar pada array seperti menambah, mengubah, menghapus, dan iterasi.

## **Materi yang Akan Dibahas**
1. Pengenalan Array dalam PHP
2. Array Numerik
3. Array Asosiatif
4. Array Multidimensi
5. Operasi Dasar pada Array
6. Studi Kasus: Pengelolaan Data Siswa dengan Array

---

## **1. Pengenalan Array dalam PHP**

### **Apa Itu Array?**
Array adalah struktur data yang memungkinkan kalian untuk menyimpan beberapa nilai dalam satu variabel. Setiap nilai dalam array disebut elemen, dan setiap elemen dapat diakses menggunakan indeks atau kunci yang unik.

### **Manfaat Menggunakan Array:**
- **Penyimpanan Data Terkait**: Array memungkinkan kalian untuk menyimpan dan mengelola sekumpulan data yang terkait dalam satu variabel.
- **Akses Cepat**: Dengan indeks atau kunci, kalian dapat dengan cepat mengakses dan memanipulasi elemen dalam array.
- **Fleksibilitas**: Array dapat digunakan untuk menyimpan data dari tipe apa pun, termasuk string, integer, objek, dan bahkan array lainnya.

## **2. Array Numerik**

### **Apa Itu Array Numerik?**
Array numerik adalah array yang menggunakan indeks numerik untuk mengakses elemen-elemen di dalamnya. Indeks dalam array numerik dimulai dari 0.

### **Cara Membuat Array Numerik:**
Kalian dapat membuat array numerik dengan menggunakan fungsi `array()` atau dengan menuliskan elemen-elemen langsung di dalam kurung siku `[]`.

**Contoh:**
```php
<?php
  $siswa = array("Amanda", "Hilman", "Anisa");
  // atau
  $siswa = ["Amanda", "Hilman", "Anisa"];

  echo $siswa[0]; // Menampilkan "Amanda"
?>
```

### **Iterasi Array Numerik:**
Kalian dapat menggunakan loop `for` atau `foreach` untuk mengiterasi elemen-elemen dalam array numerik.

**Contoh:**
```php
<?php
  foreach ($siswa sebagai $nama) {
    echo "Nama siswa: $nama<br>";
  }
?>
```

## **3. Array Asosiatif**

### **Apa Itu Array Asosiatif?**
Array asosiatif adalah array yang menggunakan kunci (key) string untuk mengakses elemen-elemen di dalamnya, bukan indeks numerik. Ini sangat berguna ketika kalian ingin menyimpan data yang berpasangan, seperti nama dan nilai.

### **Cara Membuat Array Asosiatif:**
Kalian dapat membuat array asosiatif dengan menggunakan fungsi `array()` atau dengan menuliskan elemen-elemen dalam format `kunci => nilai` di dalam kurung siku `[]`.

**Contoh:**
```php
<?php
  $nilaiSiswa = array("Amanda" => 85, "Hilman" => 90, "Anisa" => 78);
  // atau
  $nilaiSiswa = ["Amanda" => 85, "Hilman" => 90, "Anisa" => 78];

  echo $nilaiSiswa["Hilman"]; // Menampilkan 90
?>
```

### **Iterasi Array Asosiatif:**
Kalian dapat menggunakan loop `foreach` untuk mengiterasi elemen-elemen dalam array asosiatif.

**Contoh:**
```php
<?php
  foreach ($nilaiSiswa sebagai $nama => $nilai) {
    echo "Nama: $nama, Nilai: $nilai<br>";
  }
?>
```

## **4. Array Multidimensi**

### **Apa Itu Array Multidimensi?**
Array multidimensi adalah array yang berisi satu atau lebih array di dalamnya. Ini sangat berguna untuk menyimpan data yang lebih kompleks, seperti tabel data atau informasi yang memiliki banyak atribut.

### **Cara Membuat Array Multidimensi:**
Array multidimensi dapat dibuat dengan menempatkan array di dalam array lain.

**Contoh:**
```php
<?php
  $kelas = array(
    "XI PPLG A" => array(
      "Alya" => 85,
      "Hilman" => 90,
      "Anisa" => 78
    ),
    "XI PPLG B" => array(
      "Amanda" => 88,
      "Salsa" => 92,
      "Salwa" => 80
    )
  );

  echo $kelas["XI PPLG A"]["Hilman"]; // Menampilkan 90
?>
```

### **Iterasi Array Multidimensi:**
Kalian bisa menggunakan loop bersarang (nested loop) untuk mengiterasi elemen-elemen dalam array multidimensi.

**Contoh:**
```php
<?php
  foreach ($kelas sebagai $namaKelas => $siswa) {
    echo "Kelas: $namaKelas<br>";
    foreach ($siswa sebagai $nama => $nilai) {
      echo "- Nama: $nama, Nilai: $nilai<br>";
    }
    echo "<br>";
  }
?>
```

## **5. Operasi Dasar pada Array**

### **Menambah Elemen ke Array**
Kalian dapat menambah elemen baru ke array numerik dengan menempatkannya di akhir array.

**Contoh:**
```php
<?php
  $siswa[] = "Siti";
  echo $siswa[3]; // Menampilkan "Siti"
?>
```

Untuk array asosiatif, kalian bisa menambah elemen baru dengan menetapkan kunci dan nilai baru.

**Contoh:**
```php
<?php
  $nilaiSiswa["Siti"] = 88;
  echo $nilaiSiswa["Siti"]; // Menampilkan 88
?>
```

### **Mengubah Nilai Elemen**
Untuk mengubah nilai elemen dalam array, cukup tentukan indeks atau kunci dan tetapkan nilai baru.

**Contoh:**
```php
<?php
  $siswa[0] = "Aulia";
  echo $siswa[0]; // Menampilkan "Aulia"
?>
```

### **Menghapus Elemen dari Array**
Kalian dapat menggunakan fungsi `unset()` untuk menghapus elemen dari array.

**Contoh:**
```php
<?php
  unset($siswa[1]); // Menghapus elemen dengan indeks 1
  unset($nilaiSiswa["Hilman"]); // Menghapus elemen dengan kunci "Hilman"
?>
```

## **6. Studi Kasus: Pengelolaan Data Siswa dengan Array**

### **Deskripsi Masalah**
Kita akan membuat aplikasi sederhana untuk mengelola data siswa menggunakan array. Aplikasi ini akan mencakup fitur untuk menambah, mengubah, menghapus, dan menampilkan data siswa.

### **Langkah-Langkah Implementasi**
1. **Membuat Array Siswa:**
   ```php
   <?php
   $siswa = array("Alya", "Hilman", "Anisa");
   ?>
   ```

2. **Menambah Siswa Baru:**
   ```php
   <?php
   $siswa[] = "Siti";
   ?>
   ```

3. **Mengubah Nama Siswa:**
   ```php
   <?php
   $siswa[1] = "Aulia";
   ?>
   ```

4. **Menghapus Siswa:**
   ```php
   <?php
   unset($siswa[2]);
   ?>
   ```

5. **Menampilkan Data Siswa:**
   ```php
   <?php
   foreach ($siswa sebagai $nama) {
     echo "Nama siswa: $nama<br>";
   }
   ?>
   ```

### **Kesimpulan**
Dengan menggunakan array, kalian dapat dengan mudah mengelola data yang kompleks dan melakukan operasi seperti menambah, mengubah, dan menghapus data. Array numerik cocok untuk menyimpan data berurutan, array asosiatif untuk data berpasangan, dan array multidimensi untuk data yang lebih kompleks.

---

### **Aktivitas**

1. **Diskusi Kelompok:**
   - **Topik:** Kapan sebaiknya menggunakan array numerik, asosiatif, atau multidimensi?
   - **Tujuan:** Memahami kapan dan bagaimana menggunakan berbagai jenis array untuk memecahkan masalah yang berbeda.

2. **Latihan:**
   - **Tugas:** Buatlah aplikasi PHP sederhana yang mengelola data siswa dengan array. Tambahkan fitur untuk menambah, mengubah, menghapus, dan menampilkan data siswa.
   - **Output:** Aplikasi PHP yang menggunakan array untuk mengelola data siswa dengan cara yang efisien dan mudah dipahami.