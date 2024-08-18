### **Bab 30: Equality Comparisons**

#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Memahami perbedaan antara `==`, `===`, dan `Object.is` dalam JavaScript.
- Mengetahui kapan harus menggunakan masing-masing jenis perbandingan untuk menghindari kesalahan dalam program.
- Menggunakan metode perbandingan ini dengan benar untuk memeriksa kesetaraan antara nilai-nilai dalam JavaScript.

#### **Materi:**

1. **Apa Itu Equality Comparisons?**
   - **Definisi:**
     - Equality comparisons adalah cara untuk membandingkan dua nilai dalam JavaScript untuk melihat apakah mereka dianggap sama atau tidak. Ada beberapa cara untuk melakukan ini, masing-masing dengan perilaku yang sedikit berbeda.
   - **Mengapa Equality Comparisons Penting?**
     - Memahami cara kerja equality comparisons sangat penting untuk menghindari bug dalam program. Perbedaan kecil antara `==`, `===`, dan `Object.is` bisa menghasilkan hasil yang tidak diinginkan jika tidak dipahami dengan benar.

2. **`==` (Loose Equality)**
   - **Penjelasan:**
     - Operator `==` disebut loose equality atau non-strict equality. Operator ini membandingkan dua nilai untuk kesetaraan setelah melakukan type coercion jika diperlukan. Dengan kata lain, JavaScript akan mencoba mengubah kedua nilai menjadi tipe data yang sama sebelum membandingkannya.
   - **Contoh Penggunaan:**
     ```javascript
     console.log(5 == "5"); // Output: true
     console.log(0 == false); // Output: true
     console.log(null == undefined); // Output: true
     ```
   - **Perilaku:**
     - Dalam contoh-contoh di atas, JavaScript melakukan type coercion sebelum membandingkan nilai, yang menghasilkan kesetaraan bahkan ketika tipe data berbeda.

   - **Kapan Menggunakan `==`:**
     - `==` bisa digunakan ketika kalian ingin memeriksa kesetaraan antara dua nilai dengan mengabaikan tipe data mereka, tetapi harus digunakan dengan hati-hati karena hasilnya bisa menjadi tidak terduga jika tidak memahami bagaimana type coercion bekerja.

3. **`===` (Strict Equality)**
   - **Penjelasan:**
     - Operator `===` disebut strict equality atau identitas ketat. Operator ini membandingkan dua nilai untuk kesetaraan tanpa melakukan type coercion. Ini berarti nilai harus memiliki tipe data yang sama dan nilai yang sama untuk dianggap sama.
   - **Contoh Penggunaan:**
     ```javascript
     console.log(5 === "5"); // Output: false
     console.log(0 === false); // Output: false
     console.log(null === undefined); // Output: false
     ```
   - **Perilaku:**
     - Dalam contoh-contoh di atas, karena tidak ada type coercion, nilai-nilai yang dibandingkan harus benar-benar sama dalam hal tipe data dan nilai agar dianggap sama.

   - **Kapan Menggunakan `===`:**
     - `===` sebaiknya digunakan ketika kalian membutuhkan perbandingan yang lebih ketat, memastikan bahwa tidak hanya nilai yang sama tetapi juga tipe data yang sama. Ini menghindari hasil yang tidak diinginkan dari type coercion yang tidak diinginkan.

4. **`Object.is` (SameValue)**
   - **Penjelasan:**
     - `Object.is` adalah metode yang diperkenalkan di ECMAScript 6 (ES6) yang membandingkan dua nilai dengan cara yang mirip dengan `===`, tetapi dengan beberapa perbedaan kecil dalam cara menangani nilai khusus seperti `NaN` dan `-0`.
   - **Perbedaan Utama antara `Object.is` dan `===`:**
     - **`NaN`:** `Object.is` menganggap `NaN` sama dengan `NaN`, sementara `===` tidak.
     - **`-0` dan `+0`:** `Object.is` menganggap `-0` dan `+0` sebagai nilai yang berbeda, sementara `===` menganggapnya sama.
   - **Contoh Penggunaan:**
     ```javascript
     console.log(Object.is(NaN, NaN)); // Output: true
     console.log(Object.is(-0, +0)); // Output: false
     ```
   - **Kapan Menggunakan `Object.is`:**
     - `Object.is` digunakan ketika kalian membutuhkan perbandingan yang lebih akurat untuk kasus-kasus khusus ini, terutama ketika menangani `NaN` dan nilai `0`.

5. **Kesimpulan Perbandingan: `==` vs. `===` vs. `Object.is`**
   - **`==`:**
     - Melakukan type coercion sebelum membandingkan nilai.
     - Gunakan dengan hati-hati ketika tipe data tidak menjadi masalah.
   - **`===`:**
     - Membandingkan nilai tanpa melakukan type coercion.
     - Gunakan untuk perbandingan yang lebih ketat dan aman.
   - **`Object.is`:**
     - Serupa dengan `===` tetapi memperlakukan `NaN` dan `-0` secara berbeda.
     - Gunakan untuk perbandingan kasus khusus di mana kalian perlu mempertimbangkan perbedaan `NaN` dan `-0`.

#### **Praktikum Lengkap:**

1. **Latihan 1: Menggunakan `==` dan `===` untuk Membandingkan Nilai**
   - Cobalah membandingkan berbagai nilai menggunakan `==` dan `===` dan amati perbedaan hasilnya.
   **Contoh Praktik:**
   ```javascript
   console.log(5 == "5");  // Output: true
   console.log(5 === "5"); // Output: false

   console.log(null == undefined);  // Output: true
   console.log(null === undefined); // Output: false
   ```

2. **Latihan 2: Eksperimen dengan `Object.is`**
   - Gunakan `Object.is` untuk membandingkan nilai-nilai khusus seperti `NaN` dan `-0`.
   **Contoh Praktik:**
   ```javascript
   console.log(Object.is(NaN, NaN)); // Output: true
   console.log(NaN === NaN); // Output: false

   console.log(Object.is(-0, +0)); // Output: false
   console.log(-0 === +0); // Output: true
   ```

#### **Diskusi dan Review:**

- **Kapan Kalian Sebaiknya Menggunakan `===` daripada `==`?**
  - Diskusikan pentingnya menggunakan `===` untuk menghindari hasil yang tidak diinginkan dari type coercion.
  
- **Apa Perbedaan Utama antara `Object.is` dan `===`, dan Kapan Harus Menggunakan `Object.is`?**
  - Diskusikan bagaimana `Object.is` menangani kasus khusus seperti `NaN` dan `-0` dan kapan metode ini lebih disukai daripada `===`.