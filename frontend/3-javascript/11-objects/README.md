### **Bab 35: Objects**

#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Memahami apa itu objek dalam JavaScript dan bagaimana objek digunakan untuk menyimpan data dalam bentuk pasangan key-value.
- Membuat dan bekerja dengan objek, termasuk menambah, mengubah, dan menghapus properti serta metode dalam objek.
- Menggunakan **this** keyword untuk mengakses properti dalam metode objek.
- Memahami konsep **prototypes** dan bagaimana mereka digunakan untuk pewarisan dalam JavaScript.

#### **Materi Lengkap:**

1. **Apa Itu Objek?**
   - **Definisi Objek:**
     - Objek adalah struktur data kompleks yang memungkinkan kalian untuk menyimpan data dalam bentuk pasangan key-value. Setiap key dalam objek disebut sebagai properti, dan nilainya bisa berupa tipe data apa pun, termasuk angka, string, array, atau bahkan objek lain.
   - **Mengapa Objek Penting?**
     - Objek penting karena memungkinkan kalian untuk mengelompokkan data yang saling terkait dalam satu struktur, mempermudah pengelolaan data kompleks, dan menciptakan aplikasi yang lebih terorganisir.

2. **Membuat Objek**
   - **Penjelasan:**
     - Objek dapat dibuat menggunakan sintaks literal objek `{}` atau dengan menggunakan kata kunci `new Object()`.
   - **Sintaks Dasar:**
     ```javascript
     let student = {
         name: "Alya",
         age: 17,
         grade: "XI"
     };
     ```
     - **Penjelasan:**
       - Objek `student` memiliki tiga properti: `name`, `age`, dan `grade`. Setiap properti terdiri dari key dan value yang dipisahkan oleh titik dua (`:`).

3. **Mengakses dan Mengubah Properti Objek**
   - **Penjelasan:**
     - Kalian dapat mengakses properti objek menggunakan dot notation (`.`) atau bracket notation (`[]`). Properti dalam objek dapat diubah dengan menetapkan nilai baru ke properti tersebut.
   - **Contoh Penggunaan:**
     ```javascript
     let student = {
         name: "Alya",
         age: 17,
         grade: "XI"
     };

     // Mengakses properti
     console.log(student.name); // Output: Alya
     console.log(student["age"]); // Output: 17

     // Mengubah properti
     student.grade = "XII";
     console.log(student.grade); // Output: XII

     student["age"] = 18;
     console.log(student.age); // Output: 18
     ```

4. **Menambah dan Menghapus Properti Objek**
   - **Penjelasan:**
     - Kalian dapat menambah properti baru ke objek atau menghapus properti yang ada.
   - **Menambah Properti:**
     - Properti baru dapat ditambahkan ke objek menggunakan dot notation atau bracket notation.
     ```javascript
     let student = {
         name: "Alya",
         age: 17
     };

     // Menambah properti
     student.grade = "XI";
     student["school"] = "SMA Negeri 1";
     console.log(student); // Output: {name: "Alya", age: 17, grade: "XI", school: "SMA Negeri 1"}
     ```
   - **Menghapus Properti:**
     - Properti dapat dihapus dari objek menggunakan kata kunci `delete`.
     ```javascript
     let student = {
         name: "Alya",
         age: 17,
         grade: "XI"
     };

     // Menghapus properti
     delete student.grade;
     console.log(student); // Output: {name: "Alya", age: 17}
     ```

5. **Menambahkan Metode dalam Objek**
   - **Penjelasan:**
     - Metode adalah function yang menjadi properti dalam objek. Metode memungkinkan objek untuk melakukan tindakan atau menghitung nilai berdasarkan data yang ada dalam objek.
   - **Contoh Penggunaan:**
     ```javascript
     let student = {
         name: "Alya",
         age: 17,
         greet: function() {
             console.log("Hello, my name is " + this.name);
         }
     };

     student.greet(); // Output: Hello, my name is Alya
     ```
     - **Penjelasan:**
       - Metode `greet` dalam objek `student` menggunakan `this` untuk mengakses properti `name` dalam objek yang sama.

6. **Menggunakan `this` Keyword**
   - **Penjelasan:**
     - `this` adalah keyword dalam JavaScript yang mengacu pada konteks eksekusi saat ini. Dalam metode objek, `this` biasanya mengacu pada objek tempat metode itu dipanggil.
   - **Contoh Penggunaan:**
     ```javascript
     let student = {
         name: "Alya",
         age: 17,
         introduce: function() {
             console.log("Hi, I am " + this.name + " and I am " + this.age + " years old.");
         }
     };

     student.introduce(); // Output: Hi, I am Alya and I am 17 years old.
     ```
     - **Penjelasan:**
       - `this.name` mengacu pada `name` dalam objek `student`, dan `this.age` mengacu pada `age` dalam objek yang sama.

7. **Iterasi Properti Objek dengan `for...in`**
   - **Penjelasan:**
     - `for...in` loop digunakan untuk mengiterasi properti dalam objek. Ini berguna ketika kalian perlu bekerja dengan setiap properti dalam objek.
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
       - Loop ini akan mencetak setiap properti dan nilainya dalam objek `student`.

8. **Konsep Prototypes dalam JavaScript**
   - **Penjelasan:**
     - Prototypes adalah cara JavaScript mengimplementasikan pewarisan. Setiap objek di JavaScript memiliki prototype, yang merupakan objek lain. Objek dapat mewarisi properti dan metode dari prototype-nya.
   - **Contoh Penggunaan:**
     ```javascript
     function Student(name, age) {
         this.name = name;
         this.age = age;
     }

     Student.prototype.greet = function() {
         console.log("Hello, my name is " + this.name);
     };

     let student1 = new Student("Alya", 17);
     student1.greet(); // Output: Hello, my name is Alya
     ```
     - **Penjelasan:**
       - Dalam contoh ini, metode `greet` ditambahkan ke prototype `Student`, sehingga semua instance dari `Student` dapat menggunakan metode ini.

   - **Menggunakan `Object.create` untuk Pewarisan:**
     - `Object.create` memungkinkan kalian untuk membuat objek baru dan secara eksplisit menetapkan prototype-nya.
     ```javascript
     let person = {
         greet: function() {
             console.log("Hello!");
         }
     };

     let student = Object.create(person);
     student.name = "Alya";
     student.greet(); // Output: Hello!
     ```
     - **Penjelasan:**
       - Objek `student` mewarisi metode `greet` dari objek `person`.

#### **Praktikum Lengkap:**

1. **Latihan 1: Membuat dan Mengelola Objek Siswa**
   - Buat objek siswa dengan properti `name`, `age`, dan `grade`, kemudian tambahkan metode untuk memperkenalkan diri.
   **Contoh Praktik:**
   ```javascript
   let student = {
       name: "Alya",
       age: 17,
       grade: "XI",
       introduce: function() {
           console.log("Hello, my name is " + this.name + " and I am in grade " + this.grade);
       }
   };

   student.introduce(); // Output: Hello, my name is Alya and I am in grade XI
   ```

2. **Latihan 2: Menambah dan Menghapus Properti Objek**
   - Tambahkan properti `school` ke objek siswa dan kemudian hapus properti `grade`.
   **Contoh Praktik:**
   ```javascript
   let student = {
       name: "Alya",
       age: 17,
       grade: "XI"
   };

   student.school = "SMA Negeri 1";
   delete student.grade;

   console.log(student); // Output: {name: "Alya", age: 17, school: "SMA Negeri 1"}
   ```

3. **Latihan 3: Menggunakan `this` dalam Metode Objek**
   - Tambahkan metode `updateGrade` untuk mengubah nilai `grade` dan cetak pesan yang mengkonfirmasi perubahan tersebut.
   **Contoh Praktik:**
   ```javascript
   let student = {
       name: "Alya",
       age: 17,
       grade: "XI",
       updateGrade: function(newGrade) {
           this.grade = newGrade;
           console.log(this.name + " has been promoted to grade " + this.grade);
       }
   };

   student.updateGrade("XII"); // Output: Alya has been promoted to grade XII
   ```

4. **Latihan 4: Iterasi Properti Objek Menggunakan `for...in`**
   - Buat objek siswa dengan beberapa properti dan gunakan `for...in` untuk mengiterasi dan mencetak semua properti dan nilainya.
   **Contoh Praktik:**
   ```javascript
   let student = {
       name: "Alya",
       age: 17,
       grade: "XII",
       school: "SMA Negeri 1"
   };

   for (let key in student) {
       console.log(key + ": " + student[key]);
   }
   ```
   - **Penjelasan:**
     - Loop ini akan mencetak setiap properti dan nilainya dalam objek `student`, seperti "name: Alya", "age: 17", "grade: XII", dan "school: SMA Negeri 1".

5. **Latihan 5: Menggunakan Prototype untuk Menambahkan Metode**
   - Buat konstruktor untuk objek `Student` dan tambahkan metode `greet` ke prototype-nya sehingga semua instance dari `Student` dapat menggunakan metode ini.
   **Contoh Praktik:**
   ```javascript
   function Student(name, age) {
       this.name = name;
       this.age = age;
   }

   Student.prototype.greet = function() {
       console.log("Hello, I am " + this.name + " and I am " + this.age + " years old.");
   };

   let student1 = new Student("Alya", 17);
   let student2 = new Student("Anisa", 16);

   student1.greet(); // Output: Hello, I am Alya and I am 17 years old.
   student2.greet(); // Output: Hello, I am Anisa and I am 16 years old.
   ```
   - **Penjelasan:**
     - Dalam contoh ini, metode `greet` ditambahkan ke prototype dari `Student`. Semua instance dari `Student` (seperti `student1` dan `student2`) dapat menggunakan metode ini untuk mencetak pesan yang dipersonalisasi.

6. **Latihan 6: Menggunakan `Object.create` untuk Pewarisan**
   - Buat objek `person` dengan metode `greet` dan gunakan `Object.create` untuk membuat objek `student` yang mewarisi metode tersebut.
   **Contoh Praktik:**
   ```javascript
   let person = {
       greet: function() {
           console.log("Hello from " + this.name);
       }
   };

   let student = Object.create(person);
   student.name = "Alya";
   student.age = 17;

   student.greet(); // Output: Hello from Alya
   ```
   - **Penjelasan:**
     - Objek `student` dibuat menggunakan `Object.create(person)`, sehingga `student` mewarisi metode `greet` dari objek `person`. Ketika `student.greet()` dipanggil, ia mencetak pesan "Hello from Alya" menggunakan nama yang ditetapkan pada objek `student`.

---

#### **Diskusi dan Review:**

- **Bagaimana Cara Menentukan Kapan Menggunakan `this` dalam Objek?**
  - **Diskusi:**
    - `this` digunakan dalam metode objek untuk merujuk pada objek yang memanggil metode tersebut. Ini penting ketika kalian ingin metode bekerja dengan data yang ada dalam objek yang sama. `this` memastikan bahwa metode tetap dinamis dan dapat digunakan kembali di berbagai objek.

- **Apa Perbedaan Antara Menambahkan Metode Langsung ke Objek dan Menggunakan Prototypes?**
  - **Diskusi:**
    - Menambahkan metode langsung ke objek berarti setiap instance dari objek tersebut akan memiliki salinan metode itu sendiri, yang bisa memakan lebih banyak memori. Menggunakan prototype memungkinkan semua instance objek berbagi metode yang sama, yang lebih efisien dalam penggunaan memori dan lebih sesuai untuk pewarisan.

- **Bagaimana `Object.create` Memfasilitasi Pewarisan dalam JavaScript?**
  - **Diskusi:**
    - `Object.create` memungkinkan kalian untuk membuat objek baru dan secara eksplisit menetapkan prototype-nya. Ini memberikan fleksibilitas dalam menentukan pewarisan dan membuat hirarki objek yang lebih kompleks tanpa menggunakan fungsi konstruktor.