# **Bab 6 - Control Flow (Alur Kontrol) dalam PHP**

## **Tujuan Pembelajaran**
Pada akhir pertemuan ini, kalian diharapkan mampu:
- Memahami konsep alur kontrol dalam pemrograman PHP.
- Menggunakan pernyataan kondisional (`if`, `else`, `elseif`, `switch`) untuk membuat keputusan dalam kode.
- Mengimplementasikan pengulangan dengan `for`, `while`, `do-while`, dan `foreach` untuk mengelola iterasi.
- Menggunakan `break`, `continue`, dan `return` untuk mengendalikan alur program.

## **Materi yang Akan Dibahas**
1. Pengantar Alur Kontrol
2. Pernyataan Kondisional
   - `if`
   - `else`
   - `elseif`
   - `switch`
3. Pernyataan Pengulangan
   - `for`
   - `while`
   - `do-while`
   - `foreach`
4. Kontrol Alur Tambahan
   - `break`
   - `continue`
   - `return`
5. Studi Kasus: Aplikasi Penilaian Siswa

---

## **1. Pengantar Alur Kontrol**

### **Apa Itu Alur Kontrol?**
Alur kontrol adalah mekanisme dalam bahasa pemrograman yang memungkinkan kalian untuk menentukan bagaimana dan kapan bagian tertentu dari kode dijalankan. Dalam PHP, alur kontrol sangat penting untuk membuat program yang dinamis, di mana hasil atau tindakan bergantung pada kondisi atau input tertentu.

Alur kontrol terdiri dari dua komponen utama: **pernyataan kondisional** dan **pernyataan pengulangan**. Pernyataan kondisional digunakan untuk membuat keputusan dalam kode, sementara pernyataan pengulangan digunakan untuk menjalankan blok kode berulang kali.

## **2. Pernyataan Kondisional**

### **`if`**
Pernyataan `if` digunakan untuk mengeksekusi blok kode hanya jika kondisi yang diberikan bernilai true.

**Sintaks:**
```php
<?php
  if ($kondisi) {
    // Kode yang dijalankan jika kondisi true
  }
?>
```
**Contoh:**
```php
<?php
  $nilai = 85;
  if ($nilai >= 75) {
    echo "Selamat, kamu lulus!";
  }
?>
```

### **`else`**
Pernyataan `else` digunakan untuk mengeksekusi blok kode jika kondisi `if` bernilai false.

**Sintaks:**
```php
<?php
  if ($kondisi) {
    // Kode jika kondisi true
  } else {
    // Kode jika kondisi false
  }
?>
```
**Contoh:**
```php
<?php
  $nilai = 60;
  if ($nilai >= 75) {
    echo "Selamat, kamu lulus!";
  } else {
    echo "Maaf, kamu harus mengulang.";
  }
?>
```

### **`elseif`**
Pernyataan `elseif` memungkinkan kalian untuk mengevaluasi beberapa kondisi dalam satu blok kontrol.

**Sintaks:**
```php
<?php
  if ($kondisi1) {
    // Kode jika kondisi1 true
  } elseif ($kondisi2) {
    // Kode jika kondisi2 true
  } else {
    // Kode jika semua kondisi false
  }
?>
```
**Contoh:**
```php
<?php
  $nilai = 85;
  if ($nilai >= 90) {
    echo "Nilai kamu A!";
  } elseif ($nilai >= 75) {
    echo "Nilai kamu B!";
  } else {
    echo "Nilai kamu C!";
  }
?>
```

### **`switch`**
Pernyataan `switch` digunakan untuk memilih salah satu dari beberapa blok kode yang akan dijalankan, berdasarkan nilai dari ekspresi.

**Sintaks:**
```php
<?php
  switch ($ekspresi) {
    case nilai1:
      // Kode jika ekspresi == nilai1
      break;
    case nilai2:
      // Kode jika ekspresi == nilai2
      break;
    default:
      // Kode jika tidak ada yang cocok
  }
?>
```
**Contoh:**
```php
<?php
  $grade = 'B';
  switch ($grade) {
    case 'A':
      echo "Luar biasa!";
      break;
    case 'B':
      echo "Bagus!";
      break;
    case 'C':
      echo "Cukup.";
      break;
    default:
      echo "Perlu usaha lebih.";
  }
?>
```

## **3. Pernyataan Pengulangan**

### **`for`**
Pernyataan `for` digunakan untuk mengulang blok kode dengan jumlah iterasi yang telah ditentukan.

**Sintaks:**
```php
<?php
  for ($i = 0; $i < 10; $i++) {
    // Kode yang dijalankan setiap kali loop
  }
?>
```
**Contoh:**
```php
<?php
  for ($i = 1; $i <= 5; $i++) {
    echo "Ini iterasi ke-$i<br>";
  }
?>
```

### **`while`**
Pernyataan `while` digunakan untuk menjalankan blok kode selama kondisi tertentu bernilai true.

**Sintaks:**
```php
<?php
  while ($kondisi) {
    // Kode yang dijalankan selama kondisi true
  }
?>
```
**Contoh:**
```php
<?php
  $i = 1;
  while ($i <= 5) {
    echo "Ini iterasi ke-$i<br>";
    $i++;
  }
?>
```

### **`do-while`**
Pernyataan `do-while` mirip dengan `while`, tetapi blok kode dijalankan setidaknya satu kali, bahkan jika kondisi bernilai false.

**Sintaks:**
```php
<?php
  do {
    // Kode yang dijalankan setidaknya sekali
  } while ($kondisi);
?>
```
**Contoh:**
```php
<?php
  $i = 1;
  do {
    echo "Ini iterasi ke-$i<br>";
    $i++;
  } while ($i <= 5);
?>
```

### **`foreach`**
Pernyataan `foreach` digunakan untuk mengiterasi setiap elemen dalam array.

**Sintaks:**
```php
<?php
  foreach ($array as $nilai) {
    // Kode yang dijalankan untuk setiap elemen
  }
?>
```
**Contoh:**
```php
<?php
  $siswa = array("Amanda", "Hilman", "Anisa");
  foreach ($siswa as $nama) {
    echo "Nama siswa: $nama<br>";
  }
?>
```

## **4. Kontrol Alur Tambahan**

### **`break`**
`break` digunakan untuk keluar dari loop atau pernyataan `switch` sebelum waktu normalnya.

**Contoh:**
```php
<?php
  for ($i = 1; $i <= 10; $i++) {
    if ($i == 5) {
      break; // Keluar dari loop jika $i == 5
    }
    echo "Ini iterasi ke-$i<br>";
  }
?>
```

### **`continue`**
`continue` digunakan untuk melewati sisa kode dalam loop dan melanjutkan ke iterasi berikutnya.

**Contoh:**
```php
<?php
  for ($i = 1; $i <= 5; $i++) {
    if ($i == 3) {
      continue; // Lompat ke iterasi berikutnya jika $i == 3
    }
    echo "Ini iterasi ke-$i<br>";
  }
?>
```

### **`return`**
`return` digunakan untuk mengembalikan nilai dari sebuah fungsi dan menghentikan eksekusi fungsi tersebut.

**Contoh:**
```php
<?php
  function hitungLuas($panjang, $lebar) {
    return $panjang * $lebar; // Mengembalikan hasil perkalian
  }
  
  echo hitungLuas(5, 3); // Menampilkan 15
?>
```

## **5. Studi Kasus: Aplikasi Penilaian Siswa**

### **Deskripsi Masalah**
Kita akan membuat aplikasi sederhana yang dapat mengevaluasi nilai siswa dan memberikan penilaian (A, B, C, atau D) berdasarkan nilai yang mereka peroleh. Aplikasi ini juga akan menghitung rata-rata kelas dan menampilkan siswa yang mendapatkan nilai tertinggi dan terendah.

### **Langkah-Langkah Implementasi**
1. **Menggunakan Kondisi (`if-elseif-else`) untuk Menentukan Grade:**
   ```php
   <?php
   $nilai = 85;

   if ($nilai >= 90) {
     $grade = "A";
   } elseif ($nilai >= 75) {
     $grade = "B";
   } elseif ($nilai >= 60) {
     $grade = "C";
   } else {
     $grade = "D";
   }

   echo "Nilai kamu adalah $nilai, dengan grade $grade.";
   ?>
   ```

2. **Menggunakan Looping untuk Menghitung Rata-Rata:**
   ```php
   <?php
   $nilaiSiswa = array(85, 90, 78, 92, 88);
   $totalNilai = 0;
   $jumlahSiswa = count($nilaiSiswa);

   foreach ($nilaiSiswa as $nilai) {
     $totalNilai += $nilai;
   }

   $rataRata = $totalNilai / $jumlahSiswa;
   echo "Rata-rata nilai kelas adalah $rataRata.";
   ?>
   ```

3. **Menggunakan Looping dan Kondisi untuk Menemukan Nilai Tertinggi dan Terendah:**
   ```php
   <?php
   $nilaiTertinggi = max($nilaiSiswa);
   $nilaiTerendah = min($nilaiSiswa);

   echo "Nilai tertinggi di kelas adalah $nilaiTertinggi.";
   echo "Nilai terendah di kelas adalah $nilaiTerendah.";
   ?>
   ```

4. **Menggunakan Switch untuk Menentukan Pesan Berdasarkan Grade:**
   ```php
   <?php
   switch ($grade) {
     case "A":
       echo "Luar biasa, pertahankan prestasimu!";
       break;
     case "B":
       echo "Bagus, tetap berusaha lebih baik lagi!";
       break;
     case "C":
       echo "Cukup, perbanyak belajar!";
       break;
     case "D":
       echo "Perlu usaha lebih keras!";
       break;
     default:
       echo "Nilai tidak valid.";
   }
   ?>
   ```

### **Kesimpulan**
Dengan menggunakan kombinasi pernyataan kondisional, pengulangan, dan kontrol alur tambahan, kita dapat membangun aplikasi yang cukup kompleks namun mudah dipahami. Studi kasus ini menggambarkan bagaimana konsep alur kontrol dapat diterapkan untuk menyelesaikan masalah nyata, seperti evaluasi nilai siswa.

---

### **Aktivitas**

1. **Diskusi Kelompok:**
   - **Topik:** Bagaimana kombinasi antara `if-else`, `switch`, dan `looping` dapat digunakan untuk memecahkan masalah yang kompleks?
   - **Tujuan:** Memahami bagaimana mengintegrasikan berbagai jenis kontrol alur dalam satu program.

2. **Latihan:**
   - **Tugas:** Buatlah aplikasi penilaian sederhana yang bisa menghitung rata-rata nilai siswa, menentukan grade mereka, dan memberikan pesan motivasi berdasarkan grade.
   - **Output:** Aplikasi PHP yang berfungsi penuh untuk penilaian siswa.

---
### Navigasi
[⏮ Operator](../5-operator/README.md) || [Home 🏘](../README.md) || [Function ⏭](../7-function/README.md)