### **Bab 27: Data Types**

#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Memahami berbagai jenis data (data types) yang tersedia dalam JavaScript.
- Mengetahui perbedaan antara primitive types dan reference types.
- Menggunakan operator `typeof` untuk memeriksa tipe data.
- Memahami cara kerja dan penggunaan tipe data dalam JavaScript.

#### **Materi:**

1. **Apa Itu Data Types?**
   - **Definisi Data Types:**
     - Data types (tipe data) dalam JavaScript merujuk pada jenis data yang dapat disimpan dalam variabel. JavaScript memiliki tipe data dasar (primitive types) dan tipe data referensi (reference types).
   - **Mengapa Data Types Penting?**
     - Memahami tipe data penting karena menentukan operasi yang dapat dilakukan pada data tersebut. Misalnya, kalian dapat menjumlahkan angka, tetapi tidak bisa menjumlahkan string dengan cara yang sama.

2. **Primitive Types dalam JavaScript**
   - **Penjelasan:**
     - Primitive types adalah tipe data yang paling dasar dalam JavaScript. Tipe data ini disimpan langsung dalam memori dan diakses melalui nilai (by value).
   - **Jenis-Jenis Primitive Types:**
     - **`String`**
       - **Penjelasan:**
         - String adalah urutan karakter yang digunakan untuk merepresentasikan teks. String dapat didefinisikan menggunakan tanda kutip tunggal (`'`), tanda kutip ganda (`"`), atau backticks (`` ` ``).
       - **Contoh Penggunaan:**
         ```javascript
         let greeting = "Hello, world!";
         let name = 'Alya';
         let template = `Nama saya adalah ${name}`;
         ```
       - **Penjelasan:**
         - String dapat digunakan untuk menyimpan teks, dan template literals (dengan backticks) memungkinkan penyisipan variabel dalam string.

     - **`Number`**
       - **Penjelasan:**
         - Number adalah tipe data untuk menyimpan angka. JavaScript hanya memiliki satu tipe data numerik untuk bilangan bulat dan bilangan desimal.
       - **Contoh Penggunaan:**
         ```javascript
         let age = 17;
         let pi = 3.14;
         let largeNumber = 1e6; // 1 juta
         ```
       - **Penjelasan:**
         - Variabel `age` menyimpan bilangan bulat, `pi` menyimpan bilangan desimal, dan `largeNumber` menyimpan bilangan besar menggunakan notasi eksponensial.

     - **`Boolean`**
       - **Penjelasan:**
         - Boolean adalah tipe data yang hanya memiliki dua nilai: `true` atau `false`. Tipe data ini biasanya digunakan untuk mengontrol alur program, seperti dalam kondisi `if`.
       - **Contoh Penggunaan:**
         ```javascript
         let isAdult = true;
         let isStudent = false;
         ```
       - **Penjelasan:**
         - Boolean digunakan untuk merepresentasikan kondisi logis dalam program.

     - **`Undefined`**
       - **Penjelasan:**
         - `Undefined` adalah tipe data yang menunjukkan bahwa variabel telah dideklarasikan tetapi belum diinisialisasi dengan nilai apa pun.
       - **Contoh Penggunaan:**
         ```javascript
         let job;
         console.log(job); // Output: undefined
         ```
       - **Penjelasan:**
         - Variabel `job` telah dideklarasikan tetapi belum diberi nilai, sehingga nilainya adalah `undefined`.

     - **`Null`**
       - **Penjelasan:**
         - `Null` adalah tipe data yang secara eksplisit diatur untuk menunjukkan bahwa variabel tidak memiliki nilai.
       - **Contoh Penggunaan:**
         ```javascript
         let car = null;
         console.log(car); // Output: null
         ```
       - **Penjelasan:**
         - Variabel `car` secara eksplisit disetel ke `null`, menunjukkan bahwa variabel ini tidak memiliki nilai.

     - **`Symbol`**
       - **Penjelasan:**
         - `Symbol` adalah tipe data yang digunakan untuk membuat nilai unik yang tidak dapat diganggu gugat. Biasanya digunakan untuk properti unik pada objek.
       - **Contoh Penggunaan:**
         ```javascript
         let uniqueId = Symbol("id");
         console.log(uniqueId); // Output: Symbol(id)
         ```
       - **Penjelasan:**
         - `Symbol` digunakan ketika kalian membutuhkan identitas unik, misalnya untuk properti objek.

3. **Reference Types dalam JavaScript**
   - **Penjelasan:**
     - Reference types adalah tipe data yang disimpan dalam bentuk referensi ke lokasi memori. Ini termasuk objek, array, dan fungsi.
   - **Jenis-Jenis Reference Types:**
     - **`Object`**
       - **Penjelasan:**
         - Objek adalah tipe data kompleks yang memungkinkan kalian menyimpan koleksi pasangan kunci-nilai (key-value pairs). Objek sering digunakan untuk menyimpan data yang terkait dengan entitas tertentu.
       - **Contoh Penggunaan:**
         ```javascript
         let person = {
             name: "Alya",
             age: 17,
             isStudent: true
         };
         console.log(person.name); // Output: Alya
         ```
       - **Penjelasan:**
         - Objek `person` memiliki properti `name`, `age`, dan `isStudent` yang dapat diakses menggunakan dot notation.

     - **`Array`**
       - **Penjelasan:**
         - Array adalah tipe data yang digunakan untuk menyimpan daftar berurutan dari elemen. Elemen array dapat diakses menggunakan indeks numerik.
       - **Contoh Penggunaan:**
         ```javascript
         let colors = ["red", "green", "blue"];
         console.log(colors[1]); // Output: green
         ```
       - **Penjelasan:**
         - Array `colors` menyimpan tiga elemen, dan elemen kedua dapat diakses menggunakan indeks `1`.

     - **`Function`**
       - **Penjelasan:**
         - Function adalah tipe data yang menyimpan blok kode yang dapat dieksekusi. Function memungkinkan kalian mengelompokkan instruksi yang dapat dipanggil kapan saja.
       - **Contoh Penggunaan:**
         ```javascript
         function greet() {
             console.log("Hello!");
         }
         greet(); // Output: Hello!
         ```
       - **Penjelasan:**
         - Function `greet` menyimpan instruksi untuk mencetak "Hello!" ke konsol dan dapat dipanggil kapan saja dalam program.

4. **Menggunakan `typeof` untuk Memeriksa Tipe Data**
   - **Penjelasan:**
     - `typeof` adalah operator yang digunakan untuk memeriksa tipe data dari variabel atau nilai.
   - **Contoh Penggunaan:**
     ```javascript
     console.log(typeof "Hello"); // Output: string
     console.log(typeof 42); // Output: number
     console.log(typeof true); // Output: boolean
     console.log(typeof undefined); // Output: undefined
     console.log(typeof null); // Output: object
     console.log(typeof Symbol("id")); // Output: symbol
     console.log(typeof { name: "Alya" }); // Output: object
     console.log(typeof [1, 2, 3]); // Output: object
     console.log(typeof function(){}); // Output: function
     ```
   - **Penjelasan:**
     - Operator `typeof` berguna untuk memverifikasi tipe data dalam program, terutama ketika kalian perlu memastikan tipe data yang tepat untuk logika tertentu.

5. **Tipe Data Dinamis dalam JavaScript**
   - **Penjelasan:**
     - JavaScript adalah bahasa pemrograman dengan tipe data dinamis, yang berarti kalian bisa mengubah tipe data dari variabel kapan saja.
   - **Contoh Penggunaan:**
     ```javascript
     let dynamicVar = "Hello";
     console.log(typeof dynamicVar); // Output: string

     dynamicVar = 42;
     console.log(typeof dynamicVar); // Output: number
     ```
   - **Penjelasan:**
     - Variabel `dynamicVar` awalnya bertipe `string`, tetapi kemudian dapat diubah menjadi `number`. Ini memberi fleksibilitas, tetapi juga bisa menyebabkan bug jika tidak berhati-hati.

#### **Praktikum Lengkap:**

1. **Latihan 1: Eksperimen dengan Primitive Types**
   - Cobalah mendeklarasikan variabel dengan berbagai jenis primitive types dan gunakan operator `typeof` untuk memeriksa tipe data mereka.

   **Contoh Praktik:**
   ```javascript
   let text = "Hello, world!";
   let number = 123;
   let isTrue = true;
   let nothing;
   let empty = null;
   let unique = Symbol("unique");

   console.log(typeof text); // Output: string
   console.log(typeof number); // Output: number
   console.log(typeof isTrue); // Output: boolean
   console.log(typeof nothing); // Output: undefined
   console.log(typeof empty); // Output: object
   console.log(typeof unique); // Output: symbol
   ```

2. **Latihan 2: Membuat dan Mengakses Objek dan Array**
   - Buatlah objek dan array, kemudian akses nilai-nilai di dalamnya menggunakan dot notation dan indeks array.

   **Contoh Praktik:**
   ```javascript
   let student = {
       name: "Alya",
      

 age: 17,
       subjects: ["Matematika", "Fisika", "Kimia"]
   };

   console.log(student.name); // Output: Alya
   console.log(student.subjects[1]); // Output: Fisika

   let scores = [85, 90, 88];
   console.log(scores[0]); // Output: 85
   console.log(scores.length); // Output: 3
   ```

#### **Diskusi dan Review:**

- **Apa Perbedaan Antara `undefined` dan `null`?**
  - Diskusikan perbedaan antara `undefined` yang menandakan variabel belum diberi nilai, dan `null` yang menandakan variabel secara eksplisit tidak memiliki nilai.

- **Kapan Kalian Harus Menggunakan `let`, `const`, atau `var` untuk Mengelola Tipe Data?**
  - Diskusikan pilihan terbaik untuk mendeklarasikan variabel berdasarkan tipe data dan kebutuhan program.