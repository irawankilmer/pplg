### **Bab 34: Arrays**

#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Memahami apa itu array dan bagaimana array digunakan untuk menyimpan data berurut dalam JavaScript.
- Mengetahui cara membuat dan mengelola array menggunakan metode dasar seperti **push**, **pop**, **shift**, **unshift**.
- Menggunakan metode lanjutan seperti **map**, **filter**, dan **reduce** untuk memanipulasi dan bekerja dengan data dalam array.

#### **Materi:**

1. **Apa Itu Array?**
   - **Definisi Array:**
     - Array adalah struktur data yang digunakan untuk menyimpan daftar elemen dalam urutan tertentu. Setiap elemen dalam array diakses melalui indeks numerik yang dimulai dari 0.
   - **Mengapa Array Penting?**
     - Array penting karena memungkinkan kalian menyimpan dan mengelola banyak data dalam satu variabel. Ini sangat berguna ketika kalian perlu bekerja dengan kumpulan data, seperti daftar nama, angka, atau objek.

2. **Membuat Array**
   - **Penjelasan:**
     - Array dapat dibuat menggunakan sintaks literal array `[]` atau dengan kata kunci `new Array()`.
   - **Contoh Penggunaan:**
     ```javascript
     let fruits = ["Apple", "Banana", "Orange"];
     let numbers = [1, 2, 3, 4, 5];
     let mixedArray = [1, "Hello", true, null];
     ```
     - **Penjelasan:**
       - Array `fruits` menyimpan tiga elemen string, `numbers` menyimpan lima elemen angka, dan `mixedArray` menyimpan elemen-elemen dengan berbagai tipe data.

3. **Mengakses Elemen dalam Array**
   - **Penjelasan:**
     - Elemen dalam array diakses menggunakan indeks, dengan indeks pertama dimulai dari 0.
   - **Contoh Penggunaan:**
     ```javascript
     let fruits = ["Apple", "Banana", "Orange"];
     console.log(fruits[0]); // Output: Apple
     console.log(fruits[2]); // Output: Orange
     ```
     - **Penjelasan:**
       - `fruits[0]` mengakses elemen pertama "Apple", dan `fruits[2]` mengakses elemen ketiga "Orange".

4. **Mengubah dan Menambahkan Elemen dalam Array**
   - **Penjelasan:**
     - Kalian dapat mengubah nilai elemen dalam array dengan menetapkan nilai baru pada indeks tertentu, atau menambahkan elemen baru dengan menetapkan nilai pada indeks baru.
   - **Contoh Penggunaan:**
     ```javascript
     let fruits = ["Apple", "Banana", "Orange"];
     fruits[1] = "Mango"; // Mengubah "Banana" menjadi "Mango"
     fruits[3] = "Pineapple"; // Menambahkan "Pineapple" sebagai elemen baru
     console.log(fruits); // Output: ["Apple", "Mango", "Orange", "Pineapple"]
     ```

5. **Metode Dasar untuk Mengelola Array**

   - **`push()`:**
     - **Penjelasan:**
       - Metode `push()` menambahkan satu atau lebih elemen ke akhir array dan mengembalikan panjang baru dari array.
     - **Contoh Penggunaan:**
       ```javascript
       let fruits = ["Apple", "Banana"];
       fruits.push("Orange", "Mango");
       console.log(fruits); // Output: ["Apple", "Banana", "Orange", "Mango"]
       ```

   - **`pop()`:**
     - **Penjelasan:**
       - Metode `pop()` menghapus elemen terakhir dari array dan mengembalikan elemen tersebut.
     - **Contoh Penggunaan:**
       ```javascript
       let fruits = ["Apple", "Banana", "Orange"];
       let lastFruit = fruits.pop();
       console.log(lastFruit); // Output: Orange
       console.log(fruits); // Output: ["Apple", "Banana"]
       ```

   - **`shift()`:**
     - **Penjelasan:**
       - Metode `shift()` menghapus elemen pertama dari array dan mengembalikan elemen tersebut, menggeser indeks elemen lain ke kiri.
     - **Contoh Penggunaan:**
       ```javascript
       let fruits = ["Apple", "Banana", "Orange"];
       let firstFruit = fruits.shift();
       console.log(firstFruit); // Output: Apple
       console.log(fruits); // Output: ["Banana", "Orange"]
       ```

   - **`unshift()`:**
     - **Penjelasan:**
       - Metode `unshift()` menambahkan satu atau lebih elemen ke awal array dan mengembalikan panjang baru dari array.
     - **Contoh Penggunaan:**
       ```javascript
       let fruits = ["Banana", "Orange"];
       fruits.unshift("Apple", "Mango");
       console.log(fruits); // Output: ["Apple", "Mango", "Banana", "Orange"]
       ```

6. **Metode Lanjutan untuk Mengelola Array**

   - **`map()`:**
     - **Penjelasan:**
       - Metode `map()` membuat array baru dengan hasil memanggil function yang disediakan pada setiap elemen array.
     - **Contoh Penggunaan:**
       ```javascript
       let numbers = [1, 2, 3, 4];
       let doubled = numbers.map(number => number * 2);
       console.log(doubled); // Output: [2, 4, 6, 8]
       ```
       - **Penjelasan:**
         - Array `doubled` dihasilkan dari menggandakan setiap elemen dalam array `numbers`.

   - **`filter()`:**
     - **Penjelasan:**
       - Metode `filter()` membuat array baru dengan semua elemen yang lolos uji yang disediakan oleh function yang disediakan.
     - **Contoh Penggunaan:**
       ```javascript
       let numbers = [1, 2, 3, 4, 5, 6];
       let evenNumbers = numbers.filter(number => number % 2 === 0);
       console.log(evenNumbers); // Output: [2, 4, 6]
       ```
       - **Penjelasan:**
         - Array `evenNumbers` hanya berisi angka-angka genap dari array `numbers`.

   - **`reduce()`:**
     - **Penjelasan:**
       - Metode `reduce()` menerapkan function pada setiap elemen array (dari kiri ke kanan) untuk mengurangi array menjadi satu nilai tunggal.
     - **Contoh Penggunaan:**
       ```javascript
       let numbers = [1, 2, 3, 4];
       let sum = numbers.reduce((total, number) => total + number, 0);
       console.log(sum); // Output: 10
       ```
       - **Penjelasan:**
         - Metode `reduce()` digunakan untuk menjumlahkan semua elemen dalam array `numbers`, menghasilkan total 10.

7. **Iterasi Menggunakan Loops pada Array**
   - **Menggunakan Loop `for`:**
     - **Penjelasan:**
       - Loop `for` sering digunakan untuk mengiterasi semua elemen dalam array, memberikan kontrol penuh atas indeks elemen.
     - **Contoh Penggunaan:**
       ```javascript
       let fruits = ["Apple", "Banana", "Orange"];

       for (let i = 0; i < fruits.length; i++) {
           console.log(fruits[i]);
       }
       ```
       - **Penjelasan:**
         - Loop ini akan mencetak setiap elemen dalam array `fruits`.

   - **Menggunakan Loop `for...of`:**
     - **Penjelasan:**
       - Loop `for...of` lebih sederhana dan digunakan untuk mengiterasi elemen array tanpa mengakses indeks secara langsung.
     - **Contoh Penggunaan:**
       ```javascript
       let fruits = ["Apple", "Banana", "Orange"];

       for (let fruit of fruits) {
           console.log(fruit);
       }
       ```
       - **Penjelasan:**
         - Loop ini akan mencetak setiap elemen dalam array `fruits` dengan cara yang lebih ringkas.

#### **Praktikum Lengkap:**

1. **Latihan 1: Menggunakan Metode Dasar untuk Mengelola Array**
   - Buat array dari nama siswa dan tambahkan, hapus elemen menggunakan `push`, `pop`, `shift`, dan `unshift`.
   **Contoh Praktik:**
   ```javascript
   let students = ["Alya", "Anisa", "Irfan"];

   students.push("Nessa");
   console.log(students); // Output: ["Alya", "Anisa", "Irfan", "Nessa"]

   let lastStudent = students.pop();
   console.log(lastStudent); // Output: Nessa
   console.log(students); // Output: ["Alya", "Anisa", "Irfan"]

   students.unshift("Amanda");
   console.log(students); // Output: ["Amanda", "Alya", "Anisa", "Irfan"]

   let firstStudent = students.shift();
   console.log(firstStudent); // Output: Amanda
   console.log(students); // Output: ["Alya", "Anisa", "I

rfan"]
   ```

2. **Latihan 2: Menggunakan `map` untuk Memanipulasi Array**
   - Gunakan metode `map` untuk membuat array baru yang berisi panjang karakter dari setiap nama siswa.
   **Contoh Praktik:**
   ```javascript
   let students = ["Alya", "Anisa", "Irfan"];

   let nameLengths = students.map(student => student.length);
   console.log(nameLengths); // Output: [4, 5, 5]
   ```

3. **Latihan 3: Menggunakan `filter` untuk Menyaring Data dalam Array**
   - Gunakan metode `filter` untuk membuat array baru yang hanya berisi siswa dengan nama lebih dari 4 karakter.
   **Contoh Praktik:**
   ```javascript
   let students = ["Alya", "Anisa", "Irfan"];

   let longNames = students.filter(student => student.length > 4);
   console.log(longNames); // Output: ["Anisa", "Irfan"]
   ```

4. **Latihan 4: Menggunakan `reduce` untuk Mengakumulasi Nilai dalam Array**
   - Gunakan metode `reduce` untuk menghitung total panjang semua nama siswa dalam array.
   **Contoh Praktik:**
   ```javascript
   let students = ["Alya", "Anisa", "Irfan"];

   let totalLength = students.reduce((total, student) => total + student.length, 0);
   console.log(totalLength); // Output: 14
   ```

5. **Latihan 5: Iterasi pada Array Menggunakan Loop**
   - Gunakan loop `for` dan `for...of` untuk mencetak nama-nama siswa.
   **Contoh Praktik:**
   ```javascript
   let students = ["Alya", "Anisa", "Irfan"];

   // Menggunakan loop for
   for (let i = 0; i < students.length; i++) {
       console.log(students[i]);
   }

   // Menggunakan loop for...of
   for (let student of students) {
       console.log(student);
   }
   ```

#### **Diskusi dan Review:**

- **Kapan Sebaiknya Menggunakan `map`, `filter`, dan `reduce`?**
  - **Diskusi:**
    - `map` digunakan ketika kalian ingin membuat array baru dengan memodifikasi setiap elemen dalam array asli.
    - `filter` digunakan ketika kalian ingin membuat array baru yang hanya berisi elemen-elemen yang memenuhi kondisi tertentu.
    - `reduce` digunakan ketika kalian ingin mengakumulasi atau mengurangi array menjadi satu nilai berdasarkan semua elemen.

- **Apa Perbedaan Antara `push` dan `unshift` dalam Menambahkan Elemen ke Array?**
  - **Diskusi:**
    - `push` menambahkan elemen ke akhir array, sedangkan `unshift` menambahkannya ke awal array. Pilih sesuai dengan di mana kalian ingin menempatkan elemen baru dalam array.

- **Bagaimana `for...of` Mempermudah Iterasi pada Array Dibandingkan dengan `for` Biasa?**
  - **Diskusi:**
    - `for...of` memberikan cara yang lebih bersih dan sederhana untuk mengiterasi elemen array tanpa perlu mengakses indeks, membuat kode lebih mudah dibaca.