### **Bab 28: Type Casting**

#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Memahami apa itu type casting dan perannya dalam JavaScript.
- Membedakan antara **type conversion** (konversi tipe data secara eksplisit) dan **type coercion** (konversi tipe data secara implisit).
- Menggunakan teknik-teknik explicit casting untuk mengubah tipe data dalam JavaScript.
- Mengerti bagaimana JavaScript melakukan implicit casting secara otomatis dalam berbagai situasi.

#### **Materi:**

1. **Apa Itu Type Casting?**
   - **Definisi Type Casting:**
     - Type casting adalah proses mengubah tipe data dari suatu nilai menjadi tipe data lain. Dalam JavaScript, proses ini dapat dilakukan secara eksplisit (oleh programmer) atau secara implisit (oleh JavaScript itu sendiri).
   - **Mengapa Type Casting Penting?**
     - Type casting penting karena memungkinkan kalian untuk mengontrol bagaimana data ditangani dan diproses dalam program. Misalnya, saat menggabungkan angka dan string, kalian mungkin perlu memastikan bahwa hasil akhirnya adalah string, bukan angka.

2. **Explicit Casting (Konversi Tipe Data Secara Eksplisit)**
   - **Penjelasan:**
     - Explicit casting adalah ketika kalian secara sengaja mengubah tipe data dengan menggunakan fungsi atau metode tertentu. Ini memberikan kontrol penuh atas bagaimana tipe data diubah.
   - **Metode-Metode Explicit Casting:**
     - **Mengubah ke String (`String()`)**
       - **Penjelasan:**
         - Kalian bisa mengubah tipe data menjadi string dengan menggunakan fungsi `String()` atau dengan metode `toString()`.
       - **Contoh Penggunaan:**
         ```javascript
         let number = 42;
         let numberAsString = String(number);
         console.log(typeof numberAsString); // Output: string

         let boolean = true;
         let booleanAsString = boolean.toString();
         console.log(typeof booleanAsString); // Output: string
         ```
     - **Mengubah ke Number (`Number()`)**
       - **Penjelasan:**
         - Untuk mengubah nilai menjadi tipe data number, kalian bisa menggunakan fungsi `Number()`.
       - **Contoh Penggunaan:**
         ```javascript
         let str = "123";
         let strAsNumber = Number(str);
         console.log(typeof strAsNumber); // Output: number

         let boolean = false;
         let booleanAsNumber = Number(boolean);
         console.log(booleanAsNumber); // Output: 0
         ```
     - **Mengubah ke Boolean (`Boolean()`)**
       - **Penjelasan:**
         - Kalian bisa mengubah tipe data menjadi boolean menggunakan fungsi `Boolean()`. Nilai-nilai yang dianggap `falsy` seperti `0`, `""`, `null`, `undefined`, dan `NaN` akan dikonversi menjadi `false`.
       - **Contoh Penggunaan:**
         ```javascript
         let str = "hello";
         let strAsBoolean = Boolean(str);
         console.log(strAsBoolean); // Output: true

         let emptyStr = "";
         let emptyStrAsBoolean = Boolean(emptyStr);
         console.log(emptyStrAsBoolean); // Output: false
         ```

3. **Implicit Casting (Konversi Tipe Data Secara Implisit)**
   - **Penjelasan:**
     - Implicit casting, atau type coercion, adalah ketika JavaScript secara otomatis mengubah tipe data untuk menyesuaikan dengan operasi yang dilakukan. Ini sering terjadi tanpa sepengetahuan kalian dan bisa menyebabkan hasil yang tidak terduga jika tidak dipahami dengan baik.
   - **Contoh Umum Implicit Casting:**
     - **Penggabungan String dengan Number:**
       - **Penjelasan:**
         - Ketika kalian menggabungkan string dan number, JavaScript secara otomatis mengubah number menjadi string.
       - **Contoh Penggunaan:**
         ```javascript
         let result = "The answer is " + 42;
         console.log(result); // Output: The answer is 42
         console.log(typeof result); // Output: string
         ```
     - **Operasi Matematika dengan String yang Berisi Angka:**
       - **Penjelasan:**
         - Jika kalian melakukan operasi matematika pada string yang berisi angka, JavaScript akan secara otomatis mengubah string tersebut menjadi number.
       - **Contoh Penggunaan:**
         ```javascript
         let sum = "10" - 2;
         console.log(sum); // Output: 8
         console.log(typeof sum); // Output: number
         ```
       - **Penjelasan:**
         - Dalam kasus ini, JavaScript mengubah `"10"` menjadi `10` dan kemudian melakukan pengurangan.

     - **Boolean Context (Konteks Boolean):**
       - **Penjelasan:**
         - Ketika suatu nilai digunakan dalam konteks boolean, seperti dalam kondisi `if`, JavaScript secara otomatis mengubah nilai tersebut menjadi boolean.
       - **Contoh Penggunaan:**
         ```javascript
         let value = "hello";
         if (value) {
             console.log("Value is truthy");
         }
         // Output: Value is truthy
         ```
       - **Penjelasan:**
         - JavaScript menganggap string non-kosong sebagai `true` dalam konteks boolean.

4. **Perbedaan antara Type Conversion dan Type Coercion**
   - **Type Conversion (Explicit):**
     - **Penjelasan:**
       - Type conversion adalah ketika kalian secara eksplisit mengubah tipe data menggunakan fungsi atau metode, seperti `Number()`, `String()`, atau `Boolean()`.
     - **Contoh:**
       ```javascript
       let str = "100";
       let num = Number(str); // Mengubah string menjadi number secara eksplisit
       console.log(num); // Output: 100
       ```
   - **Type Coercion (Implicit):**
     - **Penjelasan:**
       - Type coercion adalah ketika JavaScript secara otomatis mengubah tipe data selama eksekusi program, biasanya sebagai hasil dari operasi atau konteks tertentu.
     - **Contoh:**
       ```javascript
       let num = "100" - 1; // Mengubah string menjadi number secara implisit
       console.log(num); // Output: 99
       ```

5. **Konsekuensi dan Perhatian dalam Implicit Casting**
   - **Penjelasan:**
     - Implicit casting bisa menghasilkan hasil yang tidak diharapkan jika tidak dipahami dengan baik. Sebagai contoh, penggabungan string dan number bisa menghasilkan string alih-alih penjumlahan angka.
   - **Contoh Perilaku Tak Terduga:**
     ```javascript
     let unexpected = "5" + 5;
     console.log(unexpected); // Output: 55
     console.log(typeof unexpected); // Output: string
     ```
     - **Penjelasan:**
       - Hasilnya adalah string `"55"` karena operator `+` mengakibatkan JavaScript mengubah angka menjadi string, bukan menjumlahkan angka.

#### **Praktikum Lengkap:**

1. **Latihan 1: Eksperimen dengan Explicit Casting**
   - Cobalah mengubah tipe data menggunakan berbagai fungsi casting seperti `Number()`, `String()`, dan `Boolean()`.

   **Contoh Praktik:**
   ```javascript
   let boolValue = true;
   let boolAsString = String(boolValue);
   console.log(boolAsString); // Output: "true"
   console.log(typeof boolAsString); // Output: string

   let str = "123";
   let strAsNumber = Number(str);
   console.log(strAsNumber); // Output: 123
   console.log(typeof strAsNumber); // Output: number
   ```

2. **Latihan 2: Mengamati Implicit Casting dalam Operasi**
   - Lakukan operasi yang melibatkan string dan number, dan amati bagaimana JavaScript melakukan implicit casting.

   **Contoh Praktik:**
   ```javascript
   let result1 = "10" + 2;
   console.log(result1); // Output: "102"

   let result2 = "10" - 2;
   console.log(result2); // Output: 8
   ```

#### **Diskusi dan Review:**

- **Kapan Lebih Baik Menggunakan Explicit Casting daripada Mengandalkan Implicit Casting?**
  - Diskusikan pentingnya menggunakan explicit casting untuk menghindari hasil yang tidak diinginkan, terutama ketika bekerja dengan data dari sumber eksternal atau input pengguna.
  
- **Apa Risiko yang Terkait dengan Implicit Casting dalam JavaScript?**
  - Diskusikan situasi di mana implicit casting bisa menyebabkan bug atau hasil yang tidak terduga dalam program.