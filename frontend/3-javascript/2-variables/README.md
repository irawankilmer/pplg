### **Bab 26: Variables**

#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Memahami apa itu variabel dalam JavaScript dan mengapa variabel penting dalam pemrograman.
- Mengetahui cara mendeklarasikan variabel menggunakan `var`, `let`, dan `const`.
- Memahami konsep scope (cakupan) variabel, hoisting, dan kapan menggunakan masing-masing jenis variabel.

#### **Materi:**

1. **Apa Itu Variabel?**
   - **Definisi Variabel:**
     - Variabel adalah wadah untuk menyimpan data yang dapat digunakan dan dimanipulasi dalam program. Variabel memungkinkan kalian untuk menyimpan nilai seperti angka, teks, atau objek, dan menggunakannya kembali di bagian lain dari program.
   - **Mengapa Variabel Penting?**
     - Variabel mempermudah pengelolaan data dalam program. Tanpa variabel, kalian harus menulis ulang nilai berulang kali, yang tidak efisien dan membuat kode sulit dibaca serta diubah.

2. **Deklarasi Variabel dalam JavaScript**
   - **`var`**
     - **Penjelasan:**
       - `var` adalah cara lama untuk mendeklarasikan variabel dalam JavaScript. Variabel yang dideklarasikan dengan `var` memiliki cakupan (scope) fungsional atau global, yang bisa menyebabkan masalah jika tidak digunakan dengan hati-hati.
     - **Contoh Penggunaan:**
       ```javascript
       var name = "Alya";
       console.log(name); // Output: Alya
       ```
       - **Penjelasan:**
         - Variabel `name` berisi nilai `"Alya"`, dan nilai tersebut dapat digunakan kembali di seluruh fungsi atau skrip.

   - **`let`**
     - **Penjelasan:**
       - `let` adalah cara yang lebih modern untuk mendeklarasikan variabel. Variabel yang dideklarasikan dengan `let` memiliki cakupan blok, yang lebih aman karena variabel hanya bisa diakses dalam blok tempat ia dideklarasikan.
     - **Contoh Penggunaan:**
       ```javascript
       let age = 17;
       if (age >= 17) {
           let canVote = true;
           console.log("Kalian bisa memilih.");
       }
       // console.log(canVote); // Error: canVote is not defined
       ```
       - **Penjelasan:**
         - Variabel `canVote` hanya tersedia dalam blok `if`, sehingga lebih aman dari penggunaan yang tidak disengaja di luar blok tersebut.

   - **`const`**
     - **Penjelasan:**
       - `const` digunakan untuk mendeklarasikan variabel yang nilainya tidak akan berubah. Seperti `let`, variabel `const` juga memiliki cakupan blok.
     - **Contoh Penggunaan:**
       ```javascript
       const birthYear = 2005;
       console.log(birthYear); // Output: 2005
       // birthYear = 2006; // Error: Assignment to constant variable.
       ```
       - **Penjelasan:**
         - Variabel `birthYear` tidak dapat diubah setelah dideklarasikan, yang membuatnya ideal untuk nilai yang tidak boleh diubah selama program berjalan.

3. **Konsep Scope dalam Variabel**
   - **Scope Fungsional (`var`):**
     - Variabel yang dideklarasikan dengan `var` memiliki cakupan fungsional, yang berarti mereka hanya dapat diakses dalam fungsi tempat mereka dideklarasikan.
     - **Contoh:**
       ```javascript
       function greet() {
           var greeting = "Halo!";
           console.log(greeting);
       }
       greet(); // Output: Halo!
       // console.log(greeting); // Error: greeting is not defined
       ```

   - **Scope Blok (`let` dan `const`):**
     - Variabel yang dideklarasikan dengan `let` atau `const` memiliki cakupan blok, yang berarti mereka hanya dapat diakses dalam blok kode tempat mereka dideklarasikan.
     - **Contoh:**
       ```javascript
       if (true) {
           let message = "Hai!";
           const pi = 3.14;
           console.log(message); // Output: Hai!
           console.log(pi); // Output: 3.14
       }
       // console.log(message); // Error: message is not defined
       // console.log(pi); // Error: pi is not defined
       ```

4. **Hoisting dalam JavaScript**
   - **Penjelasan:**
     - Hoisting adalah perilaku JavaScript di mana deklarasi variabel dan fungsi dipindahkan ke bagian atas scope mereka sebelum kode dieksekusi. Namun, hanya deklarasi yang dihoist, bukan inisialisasi.
     - **Contoh dengan `var`:**
       ```javascript
       console.log(hoistedVar); // Output: undefined
       var hoistedVar = "Ini dihoist!";
       ```
       - **Penjelasan:**
         - Variabel `hoistedVar` dideklarasikan tetapi belum diinisialisasi ketika diakses, jadi nilainya adalah `undefined`.
     - **Contoh dengan `let` dan `const`:**
       ```javascript
       // console.log(hoistedLet); // Error: Cannot access 'hoistedLet' before initialization
       let hoistedLet = "Tidak dihoist!";
       ```
       - **Penjelasan:**
         - `let` dan `const` tidak dapat diakses sebelum deklarasi, sehingga menyebabkan error jika mencoba mengaksesnya.

5. **Kapan Menggunakan `var`, `let`, dan `const`**
   - **Menggunakan `var`:**
     - Sebaiknya hindari penggunaan `var` karena dapat menyebabkan masalah dengan scope yang tidak diharapkan.
   - **Menggunakan `let`:**
     - Gunakan `let` ketika variabel yang kalian butuhkan mungkin berubah nilainya selama program berjalan.
   - **Menggunakan `const`:**
     - Gunakan `const` untuk variabel yang nilainya tidak akan berubah, seperti konstanta atau nilai tetap.

#### **Praktikum Lengkap:**

1. **Latihan 1: Mendeklarasikan Variabel dengan `var`, `let`, dan `const`**
   - Cobalah mendeklarasikan variabel dengan ketiga cara ini dan lihat perbedaan dalam cakupan dan perilaku mereka.

   **Contoh Praktik:**
   ```javascript
   var globalVar = "Ini var global";
   let blockLet = "Ini let dalam blok";
   const constantVal = "Ini konstanta";

   function testScope() {
       console.log(globalVar); // Bisa diakses
       console.log(blockLet); // Bisa diakses
       console.log(constantVal); // Bisa diakses
   }

   testScope();
   // console.log(globalVar); // Bisa diakses
   // console.log(blockLet); // Tidak bisa diakses di luar blok
   // console.log(constantVal); // Tidak bisa diakses di luar blok
   ```

2. **Latihan 2: Eksperimen dengan Hoisting**
   - Cobalah eksperimen dengan hoisting untuk memahami bagaimana JavaScript memindahkan deklarasi variabel ke atas scope.

   **Contoh Praktik:**
   ```javascript
   console.log(hoistedVar); // Output: undefined
   var hoistedVar = "Ini dihoist!";

   // console.log(hoistedLet); // Error: Cannot access 'hoistedLet' before initialization
   let hoistedLet = "Tidak dihoist!";
   ```

#### **Diskusi dan Review:**

- **Kapan Kalian Harus Menggunakan `let` daripada `var`?**
  - Diskusikan kapan lebih baik menggunakan `let` untuk menghindari masalah dengan scope variabel.
  
- **Mengapa `const` Lebih Aman untuk Nilai yang Tidak Berubah?**
  - Diskusikan keuntungan menggunakan `const` untuk nilai-nilai yang seharusnya tidak berubah sepanjang program.