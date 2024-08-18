### **Bab 32: Loops/Looping**

#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Memahami konsep dasar loops (perulangan) dalam JavaScript.
- Menggunakan berbagai jenis loops seperti **for**, **for...in**, **for...of**, **while**, dan **do...while** untuk mengulang eksekusi kode.
- Memahami kapan dan bagaimana menggunakan setiap jenis loop untuk mengelola alur program secara efisien.

#### **Materi:**

1. **Apa Itu Loops?**
   - **Definisi Loops:**
     - Loops adalah struktur kontrol yang memungkinkan kalian untuk mengeksekusi sekelompok kode berulang kali hingga kondisi tertentu terpenuhi. Dengan menggunakan loops, kalian bisa mengotomatiskan tugas-tugas yang berulang tanpa harus menulis kode yang sama berkali-kali.
   - **Mengapa Loops Penting?**
     - Loops penting karena membantu mengurangi redundansi dalam kode, membuat program lebih efisien, dan mempermudah pengelolaan tugas-tugas yang melibatkan pengulangan, seperti memproses elemen dalam array atau mengulangi tindakan tertentu hingga kondisi tertentu tercapai.

2. **Loop `for`**
   - **Penjelasan:**
     - Loop `for` adalah loop yang paling umum digunakan dalam JavaScript. Loop ini terdiri dari tiga bagian: inisialisasi, kondisi, dan increment/decrement. Loop `for` biasanya digunakan ketika kalian tahu berapa kali loop harus dijalankan.
   - **Sintaks Dasar:**
     ```javascript
     for (initialization; condition; increment/decrement) {
         // kode yang akan dieksekusi berulang kali
     }
     ```
   - **Contoh Penggunaan:**
     ```javascript
     for (let i = 0; i < 5; i++) {
         console.log("Angka: " + i);
     }
     ```
     - **Penjelasan:**
       - Loop ini akan mencetak "Angka: 0" hingga "Angka: 4" di konsol. Inisialisasi `let i = 0` terjadi sekali, kondisi `i < 5` diperiksa sebelum setiap iterasi, dan `i++` dijalankan setelah setiap iterasi.

3. **Loop `while`**
   - **Penjelasan:**
     - Loop `while` mengeksekusi kode berulang kali selama kondisi yang diberikan adalah `true`. Loop `while` cocok digunakan ketika kalian tidak tahu pasti berapa kali loop harus dijalankan dan hanya ingin loop berhenti ketika kondisi tertentu tercapai.
   - **Sintaks Dasar:**
     ```javascript
     while (condition) {
         // kode yang akan dieksekusi selama kondisi true
     }
     ```
   - **Contoh Penggunaan:**
     ```javascript
     let i = 0;

     while (i < 5) {
         console.log("Angka: " + i);
         i++;
     }
     ```
     - **Penjelasan:**
       - Loop ini akan mencetak "Angka: 0" hingga "Angka: 4" di konsol. Loop terus berjalan selama `i < 5` adalah `true`, dan `i++` dijalankan di setiap iterasi.

4. **Loop `do...while`**
   - **Penjelasan:**
     - Loop `do...while` mirip dengan loop `while`, tetapi perbedaannya adalah loop ini akan selalu mengeksekusi blok kode setidaknya sekali, karena kondisi diperiksa setelah eksekusi blok kode.
   - **Sintaks Dasar:**
     ```javascript
     do {
         // kode yang akan dieksekusi setidaknya sekali
     } while (condition);
     ```
   - **Contoh Penggunaan:**
     ```javascript
     let i = 0;

     do {
         console.log("Angka: " + i);
         i++;
     } while (i < 5);
     ```
     - **Penjelasan:**
       - Loop ini akan mencetak "Angka: 0" hingga "Angka: 4" di konsol. Bahkan jika kondisi awalnya `false`, blok kode tetap akan dijalankan sekali sebelum kondisi diperiksa.

5. **Loop `for...in`**
   - **Penjelasan:**
     - Loop `for...in` digunakan untuk mengiterasi properti enumerable dari objek. Ini biasanya digunakan untuk mengiterasi properti dalam objek.
   - **Sintaks Dasar:**
     ```javascript
     for (let key in object) {
         // kode untuk setiap properti dalam objek
     }
     ```
   - **Contoh Penggunaan:**
     ```javascript
     let student = {
         name: "Alya",
         age: 17,
         grade: "XI"
     };

     for (let key in student) {
         console.log(key + ": " + student[key]);
     }
     ```
     - **Penjelasan:**
       - Loop ini akan mencetak "name: Alya", "age: 17", dan "grade: XI" di konsol. Setiap properti dalam objek `student` akan diakses satu per satu.

6. **Loop `for...of`**
   - **Penjelasan:**
     - Loop `for...of` digunakan untuk mengiterasi iterable seperti array, string, atau objek dengan iterable iterator. Loop ini sangat berguna untuk mengiterasi elemen dalam array.
   - **Sintaks Dasar:**
     ```javascript
     for (let element of iterable) {
         // kode untuk setiap elemen dalam iterable
     }
     ```
   - **Contoh Penggunaan:**
     ```javascript
     let colors = ["red", "green", "blue"];

     for (let color of colors) {
         console.log(color);
     }
     ```
     - **Penjelasan:**
       - Loop ini akan mencetak "red", "green", dan "blue" di konsol. Setiap elemen dalam array `colors` diakses satu per satu.

7. **Menggunakan `break` dan `continue` dalam Loops**
   - **`break`:**
     - **Penjelasan:**
       - Pernyataan `break` digunakan untuk menghentikan loop sepenuhnya sebelum kondisi loop selesai.
     - **Contoh Penggunaan:**
       ```javascript
       for (let i = 0; i < 10; i++) {
           if (i === 5) {
               break;
           }
           console.log("Angka: " + i);
       }
       ```
       - **Penjelasan:**
         - Loop ini akan berhenti sepenuhnya ketika `i` mencapai 5, dan tidak akan mencetak angka setelah itu.
   - **`continue`:**
     - **Penjelasan:**
       - Pernyataan `continue` digunakan untuk melewati iterasi saat ini dan melanjutkan ke iterasi berikutnya.
     - **Contoh Penggunaan:**
       ```javascript
       for (let i = 0; i < 10; i++) {
           if (i === 5) {
               continue;
           }
           console.log("Angka: " + i);
       }
       ```
       - **Penjelasan:**
         - Loop ini akan melewati iterasi ketika `i` adalah 5, sehingga angka 5 tidak akan dicetak, tetapi loop akan melanjutkan mencetak angka berikutnya.

#### **Praktikum Lengkap:**

1. **Latihan 1: Menggunakan `for` untuk Mengiterasi Array**
   - Gunakan loop `for` untuk mengiterasi elemen-elemen dalam array dan mencetak setiap elemen.
   **Contoh Praktik:**
   ```javascript
   let fruits = ["apple", "banana", "orange"];

   for (let i = 0; i < fruits.length; i++) {
       console.log(fruits[i]);
   }
   ```

2. **Latihan 2: Menggunakan `while` untuk Menjalankan Loop Hingga Kondisi Tercapai**
   - Gunakan loop `while` untuk mencetak angka dari 1 hingga 10.
   **Contoh Praktik:**
   ```javascript
   let i = 1;

   while (i <= 10) {
       console.log(i);
       i++;
   }
   ```

3. **Latihan 3: Menggunakan `for...in` untuk Mengiterasi Properti Objek**
   - Buat objek yang mewakili siswa, dan gunakan `for...in` untuk mencetak setiap properti dan nilai dalam objek.
   **Contoh Praktik:**
   ```javascript
   let student = {
       name: "Anisa",
       age: 17,
       class: "XI"
   };

   for (let key in student) {
       console.log(key + ": " + student[key]);
   }
   ```

4. **Latihan 4: Menggunakan `for...of` untuk Mengiterasi Elemen dalam String**
   - Gunakan loop `for...of` untuk mengiterasi setiap karakter dalam string dan mencetaknya satu per satu.
   **Contoh Praktik:**
   ```javascript
   let word = "JavaScript";

   for (let char of word) {
       console.log(char);
   }
   ```

5. **Latihan 5: Menggunakan `do...while` untuk Menjalankan Loop Setidaknya Sekali**
   - Gunakan loop `do...while` untuk meminta pengguna memasukkan angka hingga mereka memasukkan angka positif.
   **Contoh

 Praktik:**
   ```javascript
   let number;

   do {
       number = prompt("Masukkan angka positif:");
   } while (number <= 0);

   console.log("Kalian memasukkan: " + number);
   ```

#### **Diskusi dan Review:**

- **Kapan Menggunakan `for` vs `while`?**
  - **Diskusi:**
    - `for` digunakan ketika kalian tahu berapa kali loop harus dijalankan (misalnya, mengiterasi array).
    - `while` digunakan ketika kalian ingin loop berjalan hingga kondisi tertentu tercapai, dan jumlah iterasi tidak diketahui sebelumnya.

- **Apa Perbedaan Antara `for...in` dan `for...of`?**
  - **Diskusi:**
    - `for...in` digunakan untuk mengiterasi properti objek.
    - `for...of` digunakan untuk mengiterasi elemen dari iterable seperti array atau string.

- **Kapan Menggunakan `break` dan `continue` dalam Loops?**
  - **Diskusi:**
    - `break` digunakan ketika kalian perlu menghentikan loop sepenuhnya berdasarkan kondisi tertentu.
    - `continue` digunakan ketika kalian ingin melewati iterasi tertentu tetapi melanjutkan loop secara keseluruhan.