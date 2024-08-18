### **Bab 29: Operators**

#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Memahami berbagai jenis operator yang tersedia dalam JavaScript, termasuk operator assignment, comparison, arithmetic, bitwise, logical, dan conditional.
- Menggunakan operator-operator ini untuk melakukan operasi dasar dan kompleks dalam JavaScript.
- Memahami bagaimana operator bekerja dalam konteks yang berbeda, termasuk dalam kontrol aliran logika program.

#### **Materi Lengkap:**

1. **Apa Itu Operator?**
   - **Definisi Operator:**
     - Operator adalah simbol atau kata kunci yang digunakan untuk melakukan operasi pada nilai atau variabel dalam program. Operator memungkinkan kalian untuk melakukan perhitungan matematika, membandingkan nilai, menggabungkan logika, dan banyak lagi.
   - **Mengapa Operator Penting?**
     - Operator adalah komponen dasar dari bahasa pemrograman yang memungkinkan kalian untuk memanipulasi data dan mengontrol aliran program. Tanpa operator, kalian tidak dapat melakukan operasi dasar seperti penjumlahan, perbandingan, atau pengambilan keputusan.

2. **Assignment Operators**
   - **Penjelasan:**
     - Assignment operators digunakan untuk menetapkan nilai ke variabel. Operator yang paling umum adalah `=`, tetapi ada juga varian lain seperti `+=`, `-=`, `*=`, dan `/=`.
   - **Jenis-Jenis Assignment Operators:**
     - **`=` (Assignment):**
       - **Penjelasan:**
         - Operator ini digunakan untuk menetapkan nilai ke variabel.
       - **Contoh Penggunaan:**
         ```javascript
         let x = 10;
         let y = 5;
         ```
     - **`+=` (Addition Assignment):**
       - **Penjelasan:**
         - Operator ini menambahkan nilai ke variabel dan kemudian menetapkan hasilnya ke variabel yang sama.
       - **Contoh Penggunaan:**
         ```javascript
         let x = 10;
         x += 5; // x sekarang adalah 15
         ```
     - **`-=` (Subtraction Assignment):**
       - **Penjelasan:**
         - Operator ini mengurangi nilai dari variabel dan kemudian menetapkan hasilnya ke variabel yang sama.
       - **Contoh Penggunaan:**
         ```javascript
         let y = 10;
         y -= 3; // y sekarang adalah 7
         ```
     - **`*=` (Multiplication Assignment):**
       - **Penjelasan:**
         - Operator ini mengalikan nilai variabel dengan nilai yang ditentukan dan menetapkan hasilnya ke variabel yang sama.
       - **Contoh Penggunaan:**
         ```javascript
         let z = 4;
         z *= 2; // z sekarang adalah 8
         ```
     - **`/=` (Division Assignment):**
       - **Penjelasan:**
         - Operator ini membagi nilai variabel dengan nilai yang ditentukan dan menetapkan hasilnya ke variabel yang sama.
       - **Contoh Penggunaan:**
         ```javascript
         let w = 20;
         w /= 4; // w sekarang adalah 5
         ```
     - **`%=` (Modulus Assignment):**
       - **Penjelasan:**
         - Operator ini menghitung sisa pembagian dari dua nilai dan menetapkan hasilnya ke variabel yang sama.
       - **Contoh Penggunaan:**
         ```javascript
         let r = 10;
         r %= 3; // r sekarang adalah 1
         ```

3. **Comparison Operators**
   - **Penjelasan:**
     - Comparison operators digunakan untuk membandingkan dua nilai. Operator-operator ini mengembalikan nilai boolean (`true` atau `false`) berdasarkan hasil perbandingan.
   - **Jenis-Jenis Comparison Operators:**
     - **`==` (Equal to):**
       - **Penjelasan:**
         - Operator ini membandingkan dua nilai untuk kesetaraan setelah melakukan type coercion jika diperlukan.
       - **Contoh Penggunaan:**
         ```javascript
         console.log(5 == "5"); // Output: true
         ```
     - **`===` (Strict Equal to):**
       - **Penjelasan:**
         - Operator ini membandingkan dua nilai untuk kesetaraan tanpa melakukan type coercion.
       - **Contoh Penggunaan:**
         ```javascript
         console.log(5 === "5"); // Output: false
         ```
     - **`!=` (Not Equal to):**
       - **Penjelasan:**
         - Operator ini mengembalikan `true` jika dua nilai tidak sama setelah type coercion.
       - **Contoh Penggunaan:**
         ```javascript
         console.log(5 != "5"); // Output: false
         ```
     - **`!==` (Strict Not Equal to):**
       - **Penjelasan:**
         - Operator ini mengembalikan `true` jika dua nilai tidak sama tanpa melakukan type coercion.
       - **Contoh Penggunaan:**
         ```javascript
         console.log(5 !== "5"); // Output: true
         ```
     - **`>` (Greater than):**
       - **Penjelasan:**
         - Operator ini mengembalikan `true` jika nilai pertama lebih besar dari nilai kedua.
       - **Contoh Penggunaan:**
         ```javascript
         console.log(10 > 5); // Output: true
         ```
     - **`>=` (Greater than or Equal to):**
       - **Penjelasan:**
         - Operator ini mengembalikan `true` jika nilai pertama lebih besar atau sama dengan nilai kedua.
       - **Contoh Penggunaan:**
         ```javascript
         console.log(10 >= 10); // Output: true
         ```
     - **`<` (Less than):**
       - **Penjelasan:**
         - Operator ini mengembalikan `true` jika nilai pertama lebih kecil dari nilai kedua.
       - **Contoh Penggunaan:**
         ```javascript
         console.log(5 < 10); // Output: true
         ```
     - **`<=` (Less than or Equal to):**
       - **Penjelasan:**
         - Operator ini mengembalikan `true` jika nilai pertama lebih kecil atau sama dengan nilai kedua.
       - **Contoh Penggunaan:**
         ```javascript
         console.log(5 <= 5); // Output: true
         ```

4. **Arithmetic Operators**
   - **Penjelasan:**
     - Arithmetic operators digunakan untuk melakukan operasi matematika dasar pada angka.
   - **Jenis-Jenis Arithmetic Operators:**
     - **`+` (Addition):**
       - **Penjelasan:**
         - Operator ini digunakan untuk menjumlahkan dua nilai.
       - **Contoh Penggunaan:**
         ```javascript
         let sum = 10 + 5;
         console.log(sum); // Output: 15
         ```
     - **`-` (Subtraction):**
       - **Penjelasan:**
         - Operator ini digunakan untuk mengurangi satu nilai dari nilai lainnya.
       - **Contoh Penggunaan:**
         ```javascript
         let difference = 10 - 5;
         console.log(difference); // Output: 5
         ```
     - **`*` (Multiplication):**
       - **Penjelasan:**
         - Operator ini digunakan untuk mengalikan dua nilai.
       - **Contoh Penggunaan:**
         ```javascript
         let product = 10 * 5;
         console.log(product); // Output: 50
         ```
     - **`/` (Division):**
       - **Penjelasan:**
         - Operator ini digunakan untuk membagi satu nilai dengan nilai lainnya.
       - **Contoh Penggunaan:**
         ```javascript
         let quotient = 10 / 2;
         console.log(quotient); // Output: 5
         ```
     - **`%` (Modulus):**
       - **Penjelasan:**
         - Operator ini mengembalikan sisa pembagian dari dua nilai.
       - **Contoh Penggunaan:**
         ```javascript
         let remainder = 10 % 3;
         console.log(remainder); // Output: 1
         ```

5. **Bitwise Operators**
   - **Penjelasan:**
     - Bitwise operators digunakan untuk melakukan operasi pada representasi biner dari nilai. Mereka bekerja pada bit individual dari operand.
   - **Jenis-Jenis Bitwise Operators:**
     - **`&` (AND):**
       - **Penjelasan:**
         - Operator ini membandingkan bit individual dari dua angka, dan mengembalikan `1` jika kedua bit adalah `1`.
       - **Contoh Penggunaan:**
         ```javascript
         let result = 5 & 1; // 5: 0101, 1: 0001
         console.log(result); // Output: 1 (0001)
         ```
     - **`|` (OR):**
       - **Penjelasan:**
         - Operator ini membandingkan bit individual dari dua angka, dan mengembalikan `1` jika salah satu bit adalah `1`.
       - **Contoh Penggunaan:**
         ```javascript
         let result = 5 | 1; // 5: 0101, 1: 0001
         console.log(result); // Output: 5 (0101)
         ```
     - **`^` (XOR):**
       - **Penjelasan:**
         - Operator XOR (exclusive OR) membandingkan bit individual dari dua angka, dan mengembalikan `1` jika hanya satu dari bit tersebut adalah `1` (tidak keduanya).
       - **Contoh Penggunaan:**
         ```javascript
         let result = 5 ^ 1; // 5: 0101, 1: 0001
         console.log(result); // Output: 4 (0100)
         ```
     - **`~` (NOT):**
       - **Penjelasan:**
         - Operator NOT (`~`) membalik semua bit dalam angka, mengubah `0` menjadi `1` dan `1` menjadi `0`. Ini menghasilkan representasi bit komplementer dari angka tersebut.
       - **Contoh Penggunaan:**
         ```javascript
         let result = ~5; // 5: 0101
         console.log(result); // Output: -6 (bitwise negasi)
         ```
     - **`<<` (Left Shift):**
       - **Penjelasan:**
         - Operator ini menggeser bit dari angka ke kiri dengan jumlah posisi tertentu, mengisi bit yang baru dengan `0`. Ini setara dengan mengalikan angka dengan 2 pangkat jumlah posisi.
       - **Contoh Penggunaan:**
         ```javascript
         let result = 5 << 1; // 5: 0101
         console.log(result); // Output: 10 (1010)
         ```
     - **`>>` (Right Shift):**
       - **Penjelasan:**
         - Operator ini menggeser bit dari angka ke kanan dengan jumlah posisi tertentu. Bit paling kiri (yang mengisi tempat bit yang bergeser) bergantung pada tanda dari angka tersebut (0 untuk angka positif).
       - **Contoh Penggunaan:**
         ```javascript
         let result = 5 >> 1; // 5: 0101
         console.log(result); // Output: 2 (0010)
         ```
     - **`>>>` (Unsigned Right Shift):**
       - **Penjelasan:**
         - Operator ini menggeser bit dari angka ke kanan tanpa mempertimbangkan tanda dari angka tersebut, selalu mengisi bit paling kiri dengan `0`.
       - **Contoh Penggunaan:**
         ```javascript
         let result = -5 >>> 1;
         console.log(result); // Output: 2147483645
         ```

6. **Logical Operators**
   - **Penjelasan:**
     - Logical operators digunakan untuk menggabungkan pernyataan logika dan mengembalikan nilai boolean (`true` atau `false`).
   - **Jenis-Jenis Logical Operators:**
     - **`&&` (Logical AND):**
       - **Penjelasan:**
         - Operator ini mengembalikan `true` jika kedua operand bernilai `true`, dan `false` jika salah satunya `false`.
       - **Contoh Penggunaan:**
         ```javascript
         let isAdult = true;
         let hasID = true;
         console.log(isAdult && hasID); // Output: true
         ```
     - **`||` (Logical OR):**
       - **Penjelasan:**
         - Operator ini mengembalikan `true` jika salah satu atau kedua operand bernilai `true`.
       - **Contoh Penggunaan:**
         ```javascript
         let isAdult = true;
         let hasID = false;
         console.log(isAdult || hasID); // Output: true
         ```
     - **`!` (Logical NOT):**
       - **Penjelasan:**
         - Operator ini membalik nilai boolean, mengubah `true` menjadi `false` dan sebaliknya.
       - **Contoh Penggunaan:**
         ```javascript
         let isAdult = true;
         console.log(!isAdult); // Output: false
         ```

7. **Conditional (Ternary) Operator**
   - **Penjelasan:**
     - Conditional operator adalah operator yang digunakan untuk melakukan operasi berbasis kondisi dalam satu baris. Operator ini juga dikenal sebagai operator ternary karena melibatkan tiga operand.
   - **Sintaks:**
     - `condition ? expr1 : expr2`
     - **Penjelasan:**
       - Jika `condition` bernilai `true`, maka `expr1` akan dievaluasi dan hasilnya akan dikembalikan. Jika `condition` bernilai `false`, maka `expr2` akan dievaluasi dan hasilnya akan dikembalikan.
   - **Contoh Penggunaan:**
     ```javascript
     let age = 18;
     let canVote = (age >= 18) ? "Yes" : "No";
     console.log(canVote); // Output: Yes
     ```

#### **Praktikum Lengkap:**

1. **Latihan 1: Menggunakan Assignment Operators**
   - Cobalah berbagai assignment operators untuk memanipulasi nilai variabel.
   **Contoh Praktik:**
   ```javascript
   let a = 10;
   a += 5;  // a = a + 5
   console.log(a); // Output: 15

   a *= 2;  // a = a * 2
   console.log(a); // Output: 30
   ```

2. **Latihan 2: Melakukan Perbandingan Menggunakan Comparison Operators**
   - Lakukan berbagai perbandingan menggunakan comparison operators dan amati hasilnya.
   **Contoh Praktik:**
   ```javascript
   let b = 20;
   console.log(b > 15); // Output: true
   console.log(b === "20"); // Output: false
   ```

3. **Latihan 3: Melakukan Perhitungan Menggunakan Arithmetic Operators**
   - Gunakan arithmetic operators untuk melakukan berbagai operasi matematika.
   **Contoh Praktik:**
   ```javascript
   let c = 50;
   let d = c / 5;
   console.log(d); // Output: 10

   let remainder = c % 7;
   console.log(remainder); // Output: 1
   ```

4. **Latihan 4: Eksperimen dengan Bitwise Operators**
   - Lakukan operasi bitwise pada angka dan amati hasilnya.
   **Contoh Praktik:**
   ```javascript
   let e = 5;  // 0101 in binary
   let f = e << 1;  // Left shift
   console.log(f); // Output: 10 (1010 in binary)
   ```

5. **Latihan 5: Menggunakan Logical dan Conditional Operators**
   - Gunakan logical dan conditional operators untuk membuat keputusan berbasis kondisi dalam program.
   **Contoh Praktik:**
   ```javascript
   let g = true;
   let h = false;
   let i = g || h;
   console.log(i); // Output: true

   let j = 18;
   let canDrive = (j >= 16) ? "Yes" : "No";
   console.log(canDrive); // Output: Yes
   ```

#### **Diskusi dan Review:**

- **Bagaimana Operator-Operator Ini Digunakan Bersama-sama dalam Logika Program?**
  - Diskusikan bagaimana operator-operator ini dapat digabungkan untuk membuat logika program yang lebih kompleks.
  
- **Apa Perbedaan Utama antara `==` dan `===` dalam Comparison Operators?**
  - Diskusikan pentingnya menggunakan strict equality (`===`) untuk menghindari masalah yang disebabkan oleh type coercion yang tidak diinginkan.