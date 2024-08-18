### **Bab 31: Control Flow**

#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Memahami konsep dasar control flow dan bagaimana mengontrol aliran logika dalam program JavaScript.
- Menggunakan pernyataan **if**, **else**, dan **switch** untuk membuat keputusan dalam program.
- Mengatur logika program agar berjalan sesuai dengan kondisi tertentu menggunakan struktur control flow.

#### **Materi:**

1. **Apa Itu Control Flow?**
   - **Definisi Control Flow:**
     - Control flow adalah urutan di mana pernyataan dieksekusi dalam program. JavaScript, seperti bahasa pemrograman lainnya, mengeksekusi kode secara berurutan, baris demi baris, kecuali jika diperintahkan untuk melompat ke bagian lain dari kode, melompati kode, atau mengulang bagian dari kode.
   - **Mengapa Control Flow Penting?**
     - Control flow penting karena memungkinkan kalian untuk membuat program yang dinamis dan interaktif. Tanpa control flow, program hanya akan berjalan dalam urutan linier, tanpa kemampuan untuk membuat keputusan atau melakukan tindakan yang berbeda berdasarkan input atau kondisi tertentu.

2. **Pernyataan `if`**
   - **Penjelasan:**
     - Pernyataan `if` adalah dasar dari control flow dalam JavaScript. Pernyataan ini digunakan untuk mengeksekusi sekelompok kode hanya jika kondisi tertentu terpenuhi (kondisi bernilai `true`).
   - **Sintaks Dasar:**
     ```javascript
     if (condition) {
         // kode yang akan dieksekusi jika kondisi true
     }
     ```
   - **Contoh Penggunaan:**
     ```javascript
     let age = 18;

     if (age >= 18) {
         console.log("Kalian sudah dewasa.");
     }
     ```
     - **Penjelasan:**
       - Dalam contoh ini, jika nilai `age` lebih besar atau sama dengan 18, maka pesan "Kalian sudah dewasa." akan ditampilkan di konsol.

3. **Pernyataan `else`**
   - **Penjelasan:**
     - Pernyataan `else` digunakan bersama dengan `if` untuk mengeksekusi sekelompok kode jika kondisi `if` tidak terpenuhi (`false`).
   - **Sintaks Dasar:**
     ```javascript
     if (condition) {
         // kode yang dieksekusi jika kondisi true
     } else {
         // kode yang dieksekusi jika kondisi false
     }
     ```
   - **Contoh Penggunaan:**
     ```javascript
     let age = 16;

     if (age >= 18) {
         console.log("Kalian sudah dewasa.");
     } else {
         console.log("Kalian masih di bawah umur.");
     }
     ```
     - **Penjelasan:**
       - Dalam contoh ini, jika `age` kurang dari 18, maka pesan "Kalian masih di bawah umur." akan ditampilkan.

4. **Pernyataan `else if`**
   - **Penjelasan:**
     - Pernyataan `else if` digunakan untuk memeriksa beberapa kondisi. Jika kondisi pertama tidak terpenuhi, maka kondisi `else if` berikutnya akan diperiksa.
   - **Sintaks Dasar:**
     ```javascript
     if (condition1) {
         // kode untuk condition1
     } else if (condition2) {
         // kode untuk condition2
     } else {
         // kode jika semua kondisi false
     }
     ```
   - **Contoh Penggunaan:**
     ```javascript
     let score = 75;

     if (score >= 90) {
         console.log("Nilai A");
     } else if (score >= 80) {
         console.log("Nilai B");
     } else if (score >= 70) {
         console.log("Nilai C");
     } else {
         console.log("Nilai D");
     }
     ```
     - **Penjelasan:**
       - Dalam contoh ini, beberapa kondisi diperiksa untuk menentukan nilai siswa berdasarkan skor mereka.

5. **Pernyataan `switch`**
   - **Penjelasan:**
     - Pernyataan `switch` digunakan ketika kalian perlu membandingkan satu ekspresi dengan beberapa kemungkinan nilai. Ini lebih rapi dan mudah dibaca daripada menggunakan banyak pernyataan `else if`.
   - **Sintaks Dasar:**
     ```javascript
     switch (expression) {
         case value1:
             // kode untuk value1
             break;
         case value2:
             // kode untuk value2
             break;
         // tambahkan case lain jika diperlukan
         default:
             // kode jika tidak ada nilai yang cocok
     }
     ```
   - **Contoh Penggunaan:**
     ```javascript
     let grade = "B";

     switch (grade) {
         case "A":
             console.log("Luar biasa!");
             break;
         case "B":
             console.log("Bagus sekali!");
             break;
         case "C":
             console.log("Cukup.");
             break;
         case "D":
             console.log("Harus lebih baik.");
             break;
         default:
             console.log("Nilai tidak valid.");
     }
     ```
     - **Penjelasan:**
       - Dalam contoh ini, nilai `grade` dibandingkan dengan beberapa kemungkinan nilai, dan blok kode yang sesuai dieksekusi. Jika tidak ada nilai yang cocok, kode dalam blok `default` akan dieksekusi.

6. **Menggunakan `switch` dengan Multiple Cases**
   - **Penjelasan:**
     - Dalam `switch`, kalian juga bisa mengelompokkan beberapa case untuk mengeksekusi kode yang sama.
   - **Contoh Penggunaan:**
     ```javascript
     let day = 3;

     switch (day) {
         case 1:
         case 2:
         case 3:
         case 4:
         case 5:
             console.log("Hari kerja.");
             break;
         case 6:
         case 7:
             console.log("Akhir pekan.");
             break;
         default:
             console.log("Hari tidak valid.");
     }
     ```
     - **Penjelasan:**
       - Dalam contoh ini, beberapa case dikelompokkan untuk mengeksekusi kode yang sama, misalnya untuk semua hari kerja.

7. **Pentingnya `break` dalam `switch`**
   - **Penjelasan:**
     - Pernyataan `break` digunakan untuk menghentikan eksekusi `switch` setelah case yang cocok ditemukan. Tanpa `break`, JavaScript akan terus mengeksekusi semua case berikutnya (yang disebut "fall-through"), yang mungkin tidak diinginkan.
   - **Contoh Tanpa `break`:**
     ```javascript
     let day = 2;

     switch (day) {
         case 1:
             console.log("Senin");
         case 2:
             console.log("Selasa");
         case 3:
             console.log("Rabu");
         default:
             console.log("Hari tidak valid.");
     }
     ```
     - **Penjelasan:**
       - Tanpa `break`, semua case setelah case yang cocok juga akan dieksekusi, menghasilkan keluaran yang tidak diinginkan.

#### **Praktikum Lengkap:**

1. **Latihan 1: Menggunakan `if`, `else`, dan `else if` untuk Mengambil Keputusan**
   - Buatlah kondisi untuk menentukan level keanggotaan berdasarkan usia.
   **Contoh Praktik:**
   ```javascript
   let age = 25;

   if (age < 12) {
       console.log("Keanggotaan Anak-anak");
   } else if (age < 18) {
       console.log("Keanggotaan Remaja");
   } else if (age < 60) {
       console.log("Keanggotaan Dewasa");
   } else {
       console.log("Keanggotaan Lansia");
   }
   ```

2. **Latihan 2: Menggunakan `switch` untuk Menentukan Kategori Produk**
   - Gunakan `switch` untuk menentukan kategori produk berdasarkan jenis produk.
   **Contoh Praktik:**
   ```javascript
   let productType = "Electronics";

   switch (productType) {
       case "Clothing":
           console.log("Kategori: Pakaian");
           break;
       case "Electronics":
           console.log("Kategori: Elektronik");
           break;
       case "Food":
           console.log("Kategori: Makanan");
           break;
       default:
           console.log("Kategori tidak ditemukan.");
   }
   ```

3. **Latihan 3: Menggunakan `switch` dengan Multiple Cases**
   - Gunakan `switch` untuk menentukan apakah hari tertentu adalah hari kerja atau akhir pekan.
   **Contoh Praktik:**
   ```javascript
   let day = 6;

   switch (day) {
       case 1:
       case 2:
       case 3:
       case 4:
       case 5:
           console.log("Hari kerja.");
           break;
       case 6:
       case 7:
           console.log("Akhir pekan.");
           break;
       default:
           console.log("Hari tidak valid.");
   }
   ```

#### **Diskusi dan Review:**

- **Apa Perbedaan Antara `if` dan `switch`, dan Kapan Menggunakan Masing-Masing?**
  - **Diskusi:**
    - `if` digunakan ketika kalian perlu memeriksa kondisi yang kompleks atau menggunakan operator perbandingan seperti `>`, `<`, `<=`, atau `>=`. Ini sangat fleksibel dan dapat menangani berbagai jenis ekspresi logika.
    - `switch` lebih cocok ketika kalian hanya perlu memeriksa satu ekspresi terhadap beberapa kemungkinan nilai yang tetap, seperti angka atau string. `switch` juga lebih mudah dibaca saat ada banyak kondisi yang harus diperiksa dengan nilai tetap.

- **Mengapa `break` Penting dalam `switch`?**
  - **Diskusi:**
    - `break` digunakan untuk mencegah "fall-through", yaitu ketika eksekusi terus berlanjut ke case berikutnya meskipun case yang cocok telah ditemukan. Tanpa `break`, JavaScript akan mengeksekusi semua case yang ada di bawah case yang cocok, yang biasanya bukan perilaku yang diinginkan.
    - `break` membantu menjaga struktur `switch` tetap bersih dan memastikan bahwa hanya satu case yang dieksekusi.

- **Bagaimana Struktur `if-else` Dapat Digunakan untuk Meningkatkan Logika Program?**
  - **Diskusi:**
    - Struktur `if-else` memungkinkan kalian membuat program yang lebih dinamis dengan kemampuan untuk merespons berbagai situasi. Misalnya, kalian bisa menggunakan `if-else` untuk memvalidasi input pengguna, memeriksa status tertentu, atau mengelola alur program berdasarkan berbagai kondisi.
    - Dengan memanfaatkan `else if`, kalian bisa menangani berbagai skenario dengan lebih efisien, memastikan bahwa setiap kemungkinan kondisi telah dipertimbangkan dalam logika program.

- **Kapan Sebaiknya Menggunakan `else if` daripada Hanya Menggunakan `else`?**
  - **Diskusi:**
    - `else if` digunakan ketika ada lebih dari dua kemungkinan kondisi yang perlu diperiksa. Ini memungkinkan kalian untuk menambahkan beberapa cabang logika, bukan hanya memilih antara dua opsi.
    - `else` digunakan sebagai penanganan kasus terakhir jika tidak ada kondisi `if` atau `else if` sebelumnya yang terpenuhi. Ini berguna untuk menangani kasus default atau kondisi yang tidak terduga.