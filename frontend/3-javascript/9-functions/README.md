### **Bab 33: Functions**

#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Memahami konsep dasar function dalam JavaScript dan peran pentingnya dalam pengembangan aplikasi.
- Menggunakan berbagai cara untuk mendefinisikan function, termasuk **function declaration**, **function expression**, dan **arrow functions**.
- Mengetahui cara kerja parameter dan nilai balik (return values) dalam function.
- Memahami perbedaan antara berbagai jenis function dan kapan menggunakannya.

#### **Materi:**

1. **Apa Itu Function?**
   - **Definisi Function:**
     - Function adalah blok kode yang dirancang untuk melakukan tugas tertentu. Function dapat dipanggil (dieksekusi) kapan saja dalam program, yang memungkinkan kalian untuk mengulang kode tanpa perlu menuliskannya kembali.
   - **Mengapa Function Penting?**
     - Function penting karena membantu membuat kode lebih modular, reusable (dapat digunakan kembali), dan lebih mudah dipahami serta dikelola. Dengan function, kalian dapat membagi program menjadi bagian-bagian kecil yang melakukan tugas tertentu.

2. **Function Declaration**
   - **Penjelasan:**
     - Function declaration adalah cara paling umum untuk mendefinisikan function dalam JavaScript. Function yang dideklarasikan dengan cara ini dapat dipanggil sebelum dideklarasikan karena hoisting.
   - **Sintaks Dasar:**
     ```javascript
     function functionName(parameters) {
         // kode yang akan dieksekusi
     }
     ```
   - **Contoh Penggunaan:**
     ```javascript
     function greet(name) {
         console.log("Hello, " + name + "!");
     }

     greet("Alya"); // Output: Hello, Alya!
     ```
     - **Penjelasan:**
       - Function `greet` dideklarasikan dengan parameter `name`. Ketika function ini dipanggil dengan argumen `"Alya"`, ia mencetak pesan "Hello, Alya!" ke konsol.

3. **Function Expression**
   - **Penjelasan:**
     - Function expression adalah cara lain untuk mendefinisikan function. Function ini tidak memiliki nama (anonymous function) dan sering disimpan dalam variabel. Tidak seperti function declaration, function expression tidak dihoist, sehingga harus dideklarasikan sebelum digunakan.
   - **Sintaks Dasar:**
     ```javascript
     const functionName = function(parameters) {
         // kode yang akan dieksekusi
     };
     ```
   - **Contoh Penggunaan:**
     ```javascript
     const greet = function(name) {
         console.log("Hello, " + name + "!");
     };

     greet("Anisa"); // Output: Hello, Anisa!
     ```
     - **Penjelasan:**
       - Function `greet` didefinisikan sebagai function expression dan disimpan dalam variabel `greet`. Function ini bekerja sama seperti function declaration, tetapi harus dideklarasikan sebelum dipanggil.

4. **Arrow Functions**
   - **Penjelasan:**
     - Arrow functions adalah cara ringkas untuk menulis function expression. Arrow functions memiliki sintaks yang lebih singkat dan tidak memiliki `this` sendiri, yang membuatnya ideal untuk penggunaan dalam konteks di mana `this` tidak perlu diubah.
   - **Sintaks Dasar:**
     ```javascript
     const functionName = (parameters) => {
         // kode yang akan dieksekusi
     };
     ```
   - **Contoh Penggunaan:**
     ```javascript
     const greet = (name) => {
         console.log("Hello, " + name + "!");
     };

     greet("Irfan"); // Output: Hello, Irfan!
     ```
     - **Penjelasan:**
       - Arrow function `greet` didefinisikan dengan sintaks yang lebih singkat. Arrow functions tidak memiliki `this` atau `arguments` sendiri, yang membuatnya cocok untuk function sederhana atau callback.

   - **Arrow Function dengan Sintaks Lebih Singkat:**
     - Jika function hanya memiliki satu parameter dan satu pernyataan, kalian bisa menghilangkan kurung kurawal dan kata kunci `return`:
     ```javascript
     const greet = name => console.log("Hello, " + name + "!");

     greet("Itsma"); // Output: Hello, Itsma!
     ```
     - **Penjelasan:**
       - Arrow function ini lebih singkat dan masih memberikan hasil yang sama.

5. **Parameters dan Arguments dalam Function**
   - **Penjelasan:**
     - Parameters adalah variabel yang didefinisikan dalam tanda kurung saat function dibuat. Arguments adalah nilai yang dikirim ke function saat function dipanggil.
   - **Contoh Penggunaan:**
     ```javascript
     function add(a, b) {
         return a + b;
     }

     let sum = add(5, 10);
     console.log(sum); // Output: 15
     ```
     - **Penjelasan:**
       - Function `add` memiliki dua parameter, `a` dan `b`. Ketika dipanggil dengan argumen `5` dan `10`, function ini mengembalikan hasil penjumlahan kedua angka tersebut.

   - **Default Parameters:**
     - JavaScript memungkinkan kalian untuk menetapkan nilai default untuk parameters jika tidak ada argumen yang diberikan.
     ```javascript
     function greet(name = "Guest") {
         console.log("Hello, " + name + "!");
     }

     greet(); // Output: Hello, Guest!
     ```
     - **Penjelasan:**
       - Function `greet` memiliki parameter default `"Guest"`, sehingga jika tidak ada argumen yang diberikan, `"Guest"` akan digunakan sebagai nama.

6. **Return Values dalam Function**
   - **Penjelasan:**
     - Function dapat mengembalikan nilai menggunakan kata kunci `return`. Nilai yang dikembalikan dapat digunakan atau disimpan dalam variabel.
   - **Contoh Penggunaan:**
     ```javascript
     function multiply(a, b) {
         return a * b;
     }

     let product = multiply(4, 5);
     console.log(product); // Output: 20
     ```
     - **Penjelasan:**
       - Function `multiply` mengembalikan hasil perkalian dari `a` dan `b`. Nilai ini kemudian disimpan dalam variabel `product` dan dicetak ke konsol.

   - **Return tanpa Nilai:**
     - Jika function tidak memiliki pernyataan `return`, function tersebut secara default mengembalikan `undefined`.
     ```javascript
     function noReturn() {
         console.log("Ini tidak mengembalikan apa-apa.");
     }

     let result = noReturn();
     console.log(result); // Output: undefined
     ```

7. **Function dengan Callback**
   - **Penjelasan:**
     - Function dapat menerima function lain sebagai parameter, yang disebut callback. Ini berguna untuk tugas-tugas asinkron atau ketika kalian ingin menjalankan function setelah tugas tertentu selesai.
   - **Contoh Penggunaan:**
     ```javascript
     function greet(name, callback) {
         console.log("Hello, " + name + "!");
         callback();
     }

     function sayGoodbye() {
         console.log("Goodbye!");
     }

     greet("Nessa", sayGoodbye);
     // Output:
     // Hello, Nessa!
     // Goodbye!
     ```
     - **Penjelasan:**
       - Dalam contoh ini, `greet` menerima function `sayGoodbye` sebagai callback. Setelah mencetak pesan "Hello", function `sayGoodbye` dipanggil untuk mencetak "Goodbye!".

#### **Praktikum Lengkap:**

1. **Latihan 1: Membuat Function Menggunakan Function Declaration**
   - Buat function untuk menghitung luas persegi panjang.
   **Contoh Praktik:**
   ```javascript
   function calculateArea(length, width) {
       return length * width;
   }

   let area = calculateArea(5, 10);
   console.log("Luas: " + area); // Output: Luas: 50
   ```

2. **Latihan 2: Menggunakan Function Expression untuk Menghitung Keliling**
   - Buat function expression untuk menghitung keliling persegi panjang.
   **Contoh Praktik:**
   ```javascript
   const calculatePerimeter = function(length, width) {
       return 2 * (length + width);
   };

   let perimeter = calculatePerimeter(5, 10);
   console.log("Keliling: " + perimeter); // Output: Keliling: 30
   ```

3. **Latihan 3: Menggunakan Arrow Functions untuk Menghitung Luas Lingkaran**
   - Buat arrow function untuk menghitung luas lingkaran dengan parameter radius.
   **Contoh Praktik:**
   ```javascript
   const calculateCircleArea = radius => Math.PI * radius * radius;

   let circleArea = calculateCircleArea(7);
   console.log("Luas Lingkaran: " + circleArea.toFixed(2)); // Output: Luas Lingkaran: 153.94
   ```

4. **Latihan 4: Function dengan Default Parameters**
   - Buat function yang menghitung volume kubus dengan panjang sisi default 1.
   **Contoh Praktik:**
   ```javascript
   function calculateVolume(side = 1) {
       return side ** 3;
   }

   console.log("Volume Kubus: " + calculateVolume(3)); // Output: Volume Kubus: 27
   console.log("Volume Default: "

 + calculateVolume()); // Output: Volume Default: 1
   ```

5. **Latihan 5: Menggunakan Function dengan Callback**
   - Buat function yang memproses array angka dan menggunakan callback untuk menentukan tindakan pada setiap elemen.
   **Contoh Praktik:**
   ```javascript
   function processNumbers(numbers, callback) {
       for (let number of numbers) {
           callback(number);
       }
   }

   function logNumber(number) {
       console.log("Number: " + number);
   }

   processNumbers([1, 2, 3, 4], logNumber);
   // Output:
   // Number: 1
   // Number: 2
   // Number: 3
   // Number: 4
   ```

#### **Diskusi dan Review:**

- **Kapan Menggunakan Function Declaration vs Function Expression?**
  - **Diskusi:**
    - Function declaration lebih fleksibel karena dapat dihoist, artinya dapat dipanggil sebelum dideklarasikan. Namun, function expression memungkinkan kalian untuk mendefinisikan function dalam konteks yang lebih dinamis, seperti dalam callback.

- **Apa Kelebihan Arrow Functions dan Kapan Menggunakannya?**
  - **Diskusi:**
    - Arrow functions menawarkan sintaks yang lebih singkat dan tidak memiliki `this` sendiri, yang membuatnya ideal untuk callback atau function sederhana. Namun, untuk function yang membutuhkan akses ke `this` kontekstual, function declaration atau expression lebih cocok.

- **Bagaimana Default Parameters Membantu dalam Menulis Function?**
  - **Diskusi:**
    - Default parameters mempermudah penanganan argumen opsional, sehingga kalian dapat membuat function yang lebih fleksibel dan menghindari penggunaan banyak pernyataan `if` untuk memeriksa apakah argumen diberikan atau tidak.