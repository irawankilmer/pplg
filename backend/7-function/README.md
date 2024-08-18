# **Bab 7 - Fungsi dan Pemrograman Modular dalam PHP**

## **Tujuan Pembelajaran**
Pada akhir pertemuan ini, kalian diharapkan mampu:
- Memahami konsep dasar fungsi dalam PHP dan bagaimana cara membuatnya.
- Menggunakan fungsi untuk membuat kode yang lebih modular dan terstruktur.
- Mengimplementasikan fungsi dalam skenario pemrograman yang nyata.
- Memahami konsep variabel lokal dan global dalam konteks fungsi.

## **Materi yang Akan Dibahas**
1. Pengertian dan Manfaat Fungsi
2. Cara Membuat Fungsi di PHP
3. Parameter dan Argumen dalam Fungsi
4. Pengembalian Nilai dari Fungsi
5. Variabel Lokal dan Global dalam Fungsi
6. Fungsi Anonim dan Closure
7. Praktik Terbaik dalam Pemrograman Modular
8. Studi Kasus: Aplikasi Pengelolaan Nilai Siswa

---

## **1. Pengertian dan Manfaat Fungsi**

### **Apa Itu Fungsi?**
Fungsi adalah blok kode yang dirancang untuk melakukan tugas tertentu dan dapat digunakan kembali dalam program. Dengan menggunakan fungsi, kalian bisa mengorganisir kode menjadi bagian-bagian yang lebih kecil dan lebih mudah dikelola.

### **Manfaat Menggunakan Fungsi:**
- **Penggunaan Ulang**: Fungsi memungkinkan kalian untuk menulis kode sekali dan menggunakannya berulang kali di berbagai tempat dalam program.
- **Pengelolaan Kode**: Membuat kode lebih modular, sehingga lebih mudah dipahami, diuji, dan dipelihara.
- **Reduksi Duplikasi Kode**: Mengurangi pengulangan kode yang sama di berbagai bagian program, yang dapat mengurangi kesalahan dan memudahkan perawatan kode.

## **2. Cara Membuat Fungsi di PHP**

### **Sintaks Dasar Fungsi**
Untuk mendefinisikan fungsi di PHP, kalian menggunakan kata kunci `function`, diikuti dengan nama fungsi, tanda kurung `()`, dan blok kode yang diapit oleh tanda kurung kurawal `{}`.

**Contoh Fungsi Sederhana:**
```php
<?php
  function sapaSiswa() {
    echo "Selamat datang di SMK Assalam Samarang!";
  }

  sapaSiswa(); // Memanggil fungsi sapaSiswa
?>
```
Dalam contoh di atas, fungsi `sapaSiswa` mencetak pesan "Selamat datang di SMK Assalam Samarang!" setiap kali dipanggil.

## **3. Parameter dan Argumen dalam Fungsi**

### **Parameter**
Parameter adalah variabel yang ditetapkan dalam tanda kurung saat mendefinisikan fungsi. Mereka bertindak sebagai placeholder untuk nilai yang akan diberikan ketika fungsi dipanggil.

**Contoh Fungsi dengan Parameter:**
```php
<?php
  function sapaSiswaDenganNama($nama) {
    echo "Selamat datang, $nama!";
  }

  sapaSiswaDenganNama("Hilman"); // Menampilkan "Selamat datang, Hilman!"
?>
```
Dalam contoh ini, `$nama` adalah parameter, dan ketika fungsi dipanggil dengan argumen `"Hilman"`, fungsi tersebut mencetak pesan dengan nama siswa.

### **Argumen**
Argumen adalah nilai yang kalian berikan ke parameter saat memanggil fungsi. Kalian bisa memberikan argumen berupa variabel atau nilai langsung.

**Contoh:**
```php
<?php
  $namaSiswa = "Alya";
  sapaSiswaDenganNama($namaSiswa); // Menampilkan "Selamat datang, Alya!"
?>
```

### **Parameter Default**
PHP juga memungkinkan kalian untuk memberikan nilai default pada parameter. Jika fungsi dipanggil tanpa argumen, parameter akan menggunakan nilai default ini.

**Contoh Parameter Default:**
```php
<?php
  function sapaSiswaDenganNama($nama = "Siswa") {
    echo "Selamat datang, $nama!";
  }

  sapaSiswaDenganNama(); // Menampilkan "Selamat datang, Siswa!"
?>
```

## **4. Pengembalian Nilai dari Fungsi**

Fungsi tidak hanya digunakan untuk menampilkan output, tetapi juga bisa mengembalikan nilai ke bagian lain dari program menggunakan kata kunci `return`.

### **Contoh Fungsi dengan Pengembalian Nilai:**
```php
<?php
  function hitungLuasPersegi($sisi) {
    return $sisi * $sisi;
  }

  $luas = hitungLuasPersegi(4); // Mengembalikan 16
  echo "Luas persegi dengan sisi 4 adalah $luas";
?>
```
Dalam contoh di atas, fungsi `hitungLuasPersegi` mengembalikan hasil perhitungan, yang kemudian disimpan dalam variabel `$luas`.

### **Menghentikan Eksekusi dengan `return`**
Selain mengembalikan nilai, `return` juga dapat digunakan untuk menghentikan eksekusi fungsi sebelum kode mencapai akhir.

**Contoh:**
```php
<?php
  function cekKelulusan($nilai) {
    if ($nilai >= 75) {
      return "Lulus";
    } else {
      return "Tidak Lulus";
    }
  }

  echo cekKelulusan(80); // Menampilkan "Lulus"
?>
```

## **5. Variabel Lokal dan Global dalam Fungsi**

### **Variabel Lokal**
Variabel yang dideklarasikan di dalam fungsi hanya dapat diakses di dalam fungsi tersebut. Ini disebut sebagai variabel lokal.

**Contoh:**
```php
<?php
  function tampilkanNama() {
    $nama = "Amanda"; // Variabel lokal
    echo $nama;
  }

  tampilkanNama(); // Menampilkan "Amanda"
  echo $nama; // Error: Variabel tidak dikenali di luar fungsi
?>
```

### **Variabel Global**
Variabel global adalah variabel yang dideklarasikan di luar fungsi dan dapat diakses dari mana saja dalam program, kecuali dalam fungsi, kecuali kalian menggunakan kata kunci `global`.

**Contoh:**
```php
<?php
  $nama = "Anisa"; // Variabel global

  function tampilkanNama() {
    global $nama; // Mengakses variabel global di dalam fungsi
    echo $nama;
  }

  tampilkanNama(); // Menampilkan "Anisa"
?>
```

## **6. Fungsi Anonim dan Closure**

### **Fungsi Anonim**
Fungsi anonim adalah fungsi tanpa nama yang sering digunakan sebagai nilai untuk variabel atau sebagai argumen untuk fungsi lain.

**Contoh:**
```php
<?php
  $sapa = function($nama) {
    echo "Selamat datang, $nama!";
  };

  $sapa("Salsa"); // Menampilkan "Selamat datang, Salsa!"
?>
```

### **Closure**
Closure adalah fungsi anonim yang dapat mengakses variabel dari lingkup di mana ia didefinisikan, meskipun fungsi tersebut dijalankan di luar lingkup tersebut.

**Contoh:**
```php
<?php
  $pesan = "Selamat datang";

  $sapa = function($nama) use ($pesan) {
    echo "$pesan, $nama!";
  };

  $sapa("Salwa"); // Menampilkan "Selamat datang, Salwa!"
?>
```

## **7. Praktik Terbaik dalam Pemrograman Modular**

### **Pisahkan Fungsi Berdasarkan Tugas**
Pisahkan kode menjadi fungsi-fungsi kecil yang masing-masing melakukan tugas tertentu. Ini membuat kode lebih mudah dibaca dan dipelihara.

### **Gunakan Nama Fungsi yang Deskriptif**
Nama fungsi harus menjelaskan apa yang dilakukan oleh fungsi tersebut. Misalnya, `hitungLuasPersegi` lebih deskriptif daripada `luas`.

### **Hindari Penggunaan Variabel Global**
Sebaiknya hindari penggunaan variabel global di dalam fungsi, karena dapat membuat kode sulit dipahami dan menimbulkan masalah saat debugging.

## **8. Studi Kasus: Aplikasi Pengelolaan Nilai Siswa**

### **Deskripsi Masalah**
Kita akan membuat aplikasi sederhana untuk mengelola nilai siswa. Aplikasi ini akan mencakup fungsi untuk menambah nilai siswa, menghitung rata-rata kelas, dan menampilkan siswa dengan nilai tertinggi dan terendah.

### **Langkah-Langkah Implementasi**
1. **Membuat Fungsi untuk Menambah Nilai Siswa:**
   ```php
   <?php
   function tambahNilai($nama, $nilai) {
     return array("nama" => $nama, "nilai" => $nilai);
   }

   $nilaiSiswa = array();
   $nilaiSiswa[] = tambahNilai("Hilman", 85);
   $nilaiSiswa[] = tambahNilai("Amanda", 90);
   ?>
   ```

2. **Membuat Fungsi untuk Menghitung Rata-Rata Kelas:**
   ```php
   <?php
   function hitungRataRata($nilaiSiswa) {
     $total = 0;
     foreach ($nilaiSiswa as $siswa) {
       $total += $siswa["nilai"];
     }
     return $total / count($nilaiSiswa);
   }

   $rataRata = hitungRataRata($nilaiSiswa);
   echo "Rata-rata kelas adalah $rataRata.";
   ?>
   ```

3. **Membuat Fungsi untuk Menemukan Siswa dengan Nilai Tertinggi dan Terendah:**
   ```php
   <?php
   function cariNilaiTertinggi($nilaiSiswa) {
     $tertinggi = $nilaiSiswa[0];
     foreach ($nilaiSiswa as $siswa) {
       if ($siswa["nilai"] > $tertinggi["nilai"]) {
         $tertinggi = $siswa;
       }
     }
     return $tertinggi;
   }

   function cariNilaiTerendah($nilaiSiswa) {
     $terendah = $nilaiSiswa[0];
     foreach ($nilaiSiswa as $siswa) {
       if ($siswa["nilai"] < $terendah["nilai"]) {
         $terendah = $siswa;
       }
     }
     return $terendah;
   }

   $tertinggi = cariNilaiTertinggi($nilaiSiswa);
   $terendah = cariNilaiTerendah($nilaiSiswa);

   echo "Siswa dengan nilai tertinggi adalah " . $tertinggi["nama"] . " dengan nilai " . $tertinggi["nilai"] . ".<br>";
   echo "Siswa dengan nilai terendah adalah " . $terendah["nama"] . " dengan nilai " . $terendah["nilai"] . ".";
   ?>
   ```

### **Kesimpulan**
Dengan membuat fungsi-fungsi ini, kita telah mengorganisir aplikasi menjadi bagian-bagian yang lebih modular dan mudah dipahami. Setiap fungsi memiliki tugas yang jelas, yang membuat kode lebih mudah dirawat dan dikembangkan. Studi kasus ini menunjukkan bagaimana fungsi dapat digunakan untuk membangun aplikasi yang lebih kompleks secara bertahap dan terstruktur.

---

### **Aktivitas**

1. **Diskusi Kelompok:**
   - **Topik:** Mengapa penting untuk membagi program menjadi fungsi-fungsi kecil dan spesifik?
   - **Tujuan:** Memahami manfaat pemrograman modular dalam hal efisiensi, pemeliharaan, dan skalabilitas.

2. **Latihan:**
   - **Tugas:** Buatlah aplikasi sederhana menggunakan fungsi yang mencakup perhitungan rata-rata nilai, mencari nilai tertinggi dan terendah, serta menampilkan laporan lengkap tentang hasil tersebut.
   - **Output:** Aplikasi PHP yang modular dan terstruktur, menggunakan fungsi untuk menyelesaikan berbagai tugas dalam pengelolaan nilai siswa.

---
### Navigasi
[⏮ Control Flow](../6-control-flow/README.md) || [Home 🏘](../README.md) || [Array ⏭](../8-array/README.md)