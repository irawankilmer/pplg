### **Bab 36: Classes**

#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Memahami konsep dasar classes dalam JavaScript dan bagaimana mereka digunakan untuk membuat blueprint dari objek.
- Membuat kelas dengan constructor, properti, dan metode.
- Mengimplementasikan pewarisan (inheritance) dalam classes untuk membuat hierarki objek yang lebih kompleks.

#### **Materi:**

1. **Apa Itu Class?**
   - **Definisi Class:**
     - Class adalah blueprint atau cetak biru untuk membuat objek dengan properti dan metode yang telah ditentukan sebelumnya. Meskipun JavaScript bukan bahasa berorientasi objek secara ketat, ES6 memperkenalkan sintaks `class` untuk mempermudah pembuatan dan pewarisan objek.
   - **Mengapa Class Penting?**
     - Class penting karena memungkinkan kalian untuk membuat struktur kode yang lebih terorganisir dan modular. Dengan menggunakan classes, kalian dapat mengelompokkan data dan perilaku yang terkait dalam satu unit, yang membuat kode lebih mudah dibaca, dipelihara, dan digunakan kembali.

2. **Membuat Class**
   - **Penjelasan:**
     - Kelas dibuat menggunakan kata kunci `class`, diikuti dengan nama kelas. Di dalam kelas, kalian dapat mendefinisikan properti dan metode.
   - **Sintaks Dasar:**
     ```javascript
     class Student {
         constructor(name, age, grade) {
             this.name = name;
             this.age = age;
             this.grade = grade;
         }

         introduce() {
             console.log(`Hello, my name is ${this.name}, I am in grade ${this.grade}.`);
         }
     }
     ```
   - **Penjelasan:**
     - Dalam contoh ini, kelas `Student` memiliki constructor yang menginisialisasi properti `name`, `age`, dan `grade`. Kelas ini juga memiliki metode `introduce` yang mencetak pesan perkenalan menggunakan properti-properti tersebut.

3. **Constructor dalam Class**
   - **Penjelasan:**
     - Constructor adalah metode khusus yang dijalankan saat instance dari kelas dibuat. Constructor digunakan untuk menginisialisasi properti objek yang baru dibuat.
   - **Contoh Penggunaan:**
     ```javascript
     class Student {
         constructor(name, age, grade) {
             this.name = name;
             this.age = age;
             this.grade = grade;
         }
     }

     let student1 = new Student("Alya", 17, "XI PPLG A");
     console.log(student1); // Output: Student { name: 'Alya', age: 17, grade: 'XI PPLG A' }
     ```
     - **Penjelasan:**
       - Ketika `student1` dibuat menggunakan `new Student("Alya", 17, "XI PPLG A")`, constructor dipanggil dan properti `name`, `age`, dan `grade` diinisialisasi sesuai dengan argumen yang diberikan.

4. **Metode dalam Class**
   - **Penjelasan:**
     - Kalian dapat mendefinisikan metode dalam class yang dapat dipanggil pada instance dari class tersebut. Metode ini beroperasi pada data yang disimpan dalam instance (melalui `this`).
   - **Contoh Penggunaan:**
     ```javascript
     class Student {
         constructor(name, age, grade) {
             this.name = name;
             this.age = age;
             this.grade = grade;
         }

         introduce() {
             console.log(`Hello, my name is ${this.name}, I am in grade ${this.grade}.`);
         }
     }

     let student1 = new Student("Alya", 17, "XI PPLG A");
     student1.introduce(); // Output: Hello, my name is Alya, I am in grade XI PPLG A.
     ```
     - **Penjelasan:**
       - Metode `introduce` mencetak pesan perkenalan yang mengakses properti `name` dan `grade` dari instance `student1`.

5. **Pewarisan (Inheritance) dalam Class**
   - **Penjelasan:**
     - Pewarisan memungkinkan kalian membuat kelas baru berdasarkan kelas yang sudah ada, mewarisi semua properti dan metode dari kelas induk (parent class). Kalian bisa menambahkan atau mengganti properti dan metode di kelas turunan (child class).
   - **Sintaks Dasar:**
     ```javascript
     class Person {
         constructor(name, age) {
             this.name = name;
             this.age = age;
         }

         introduce() {
             console.log(`Hello, my name is ${this.name}.`);
         }
     }

     class Student extends Person {
         constructor(name, age, grade) {
             super(name, age);
             this.grade = grade;
         }

         introduce() {
             super.introduce();
             console.log(`I am in grade ${this.grade}.`);
         }
     }
     ```
   - **Penjelasan:**
     - Kelas `Student` mewarisi dari kelas `Person` dengan menggunakan kata kunci `extends`. Di dalam constructor `Student`, `super(name, age)` digunakan untuk memanggil constructor dari kelas `Person`, sehingga `name` dan `age` diinisialisasi oleh kelas induk.

   - **Contoh Penggunaan:**
     ```javascript
     let student1 = new Student("Alya", 17, "XI PPLG A");
     student1.introduce();
     // Output:
     // Hello, my name is Alya.
     // I am in grade XI PPLG A.
     ```
     - **Penjelasan:**
       - Ketika `student1.introduce()` dipanggil, metode `introduce` di kelas `Student` memanggil metode `introduce` dari kelas `Person` menggunakan `super.introduce()`, dan kemudian mencetak informasi tambahan tentang `grade`.

6. **Static Methods dalam Class**
   - **Penjelasan:**
     - Static methods adalah metode yang tidak beroperasi pada instance tertentu dari kelas tetapi pada kelas itu sendiri. Static methods dipanggil langsung pada kelas, bukan pada instance dari kelas.
   - **Sintaks Dasar:**
     ```javascript
     class MathHelper {
         static add(a, b) {
             return a + b;
         }
     }

     console.log(MathHelper.add(5, 10)); // Output: 15
     ```
     - **Penjelasan:**
       - Metode `add` dalam kelas `MathHelper` adalah metode statis yang menambahkan dua angka. Metode ini dipanggil langsung pada kelas `MathHelper` tanpa perlu membuat instance dari kelas tersebut.

7. **Getters dan Setters dalam Class**
   - **Penjelasan:**
     - Getters dan setters adalah metode khusus dalam class yang digunakan untuk mengakses dan mengubah properti objek. Mereka menyediakan cara yang lebih terkontrol untuk mengelola akses ke properti.
   - **Sintaks Dasar:**
     ```javascript
     class Student {
         constructor(name, age) {
             this.name = name;
             this.age = age;
         }

         get studentAge() {
             return this.age;
         }

         set studentAge(newAge) {
             if (newAge > 0) {
                 this.age = newAge;
             } else {
                 console.log("Invalid age");
             }
         }
     }

     let student1 = new Student("Alya", 17);
     console.log(student1.studentAge); // Output: 17

     student1.studentAge = 18;
     console.log(student1.studentAge); // Output: 18

     student1.studentAge = -1; // Output: Invalid age
     ```
     - **Penjelasan:**
       - Getters dan setters memberikan kontrol lebih terhadap akses dan modifikasi properti `age`. Setter `studentAge` memeriksa apakah nilai baru valid sebelum menetapkannya.

#### **Praktikum Lengkap:**

1. **Latihan 1: Membuat Class Sederhana**
   - Buat kelas `Student` dengan properti `name`, `age`, dan `grade`, serta metode `introduce` untuk memperkenalkan diri.
   **Contoh Praktik:**
   ```javascript
   class Student {
       constructor(name, age, grade) {
           this.name = name;
           this.age = age;
           this.grade = grade;
       }

       introduce() {
           console.log(`Hello, my name is ${this.name}, I am in grade ${this.grade}.`);
       }
   }

   let student1 = new Student("Anisa", 16, "XI PPLG B");
   student1.introduce(); // Output: Hello, my name is Anisa, I am in grade XI PPLG B.
   ```

2. **Latihan 2: Menggunakan Pewarisan untuk Membuat Kelas Turunan**
   - Buat kelas `Teacher` yang mewarisi dari kelas `Person` dan tambahkan properti `subject`.
   **Contoh Praktik:**
   ```javascript
   class Person {
       constructor(name, age) {
           this.name = name;
           this.age = age;
       }

       introduce() {
           console.log(`Hello, my name is ${this.name}.`);
       }
   }

   class Teacher extends Person {
       constructor(name, age, subject) {
           super(name, age);
           this.subject = subject;
       }

       introduce() {
           super.introduce();
           console.log(`I teach ${this.subject}.`);
       }
   }

   let teacher1 = new Teacher("Mr

. Zaki", 30, "Mathematics");
   teacher1.introduce();
   // Output:
   // Hello, my name is Mr. Zaki.
   // I teach Mathematics.
   ```

3. **Latihan 3: Menggunakan Static Methods dalam Class**
   - Buat kelas `Calculator` dengan metode statis `multiply` untuk mengalikan dua angka.
   **Contoh Praktik:**
   ```javascript
   class Calculator {
       static multiply(a, b) {
           return a * b;
       }
   }

   console.log(Calculator.multiply(5, 10)); // Output: 50
   ```

4. **Latihan 4: Menggunakan Getters dan Setters**
   - Buat kelas `Book` dengan properti `title` dan `price`, serta getter dan setter untuk `price`.
   **Contoh Praktik:**
   ```javascript
   class Book {
       constructor(title, price) {
           this.title = title;
           this.price = price;
       }

       get bookPrice() {
           return this.price;
       }

       set bookPrice(newPrice) {
           if (newPrice > 0) {
               this.price = newPrice;
           } else {
               console.log("Invalid price");
           }
       }
   }

   let book1 = new Book("JavaScript Basics", 50);
   console.log(book1.bookPrice); // Output: 50

   book1.bookPrice = 60;
   console.log(book1.bookPrice); // Output: 60

   book1.bookPrice = -10; // Output: Invalid price
   ```

#### **Diskusi dan Review:**

- **Apa Kelebihan Menggunakan Classes Dibandingkan dengan Fungsi Konstruktor Biasa?**
  - **Diskusi:**
    - Classes menawarkan sintaks yang lebih bersih dan intuitif untuk membuat dan mengelola objek. Dengan classes, pewarisan dan penggunaan metode menjadi lebih sederhana dan konsisten dibandingkan dengan fungsi konstruktor tradisional.

- **Kapan Menggunakan Pewarisan dalam Classes?**
  - **Diskusi:**
    - Pewarisan digunakan ketika kalian ingin membuat kelas baru yang memiliki sifat dasar dari kelas yang ada, tetapi dengan tambahan atau modifikasi tertentu. Ini memungkinkan kode yang lebih terstruktur dan modular.

- **Bagaimana Static Methods Dapat Digunakan dalam Classes?**
  - **Diskusi:**
    - Static methods berguna untuk fungsi yang tidak memerlukan data instance tertentu dari kelas, seperti fungsi utilitas yang bekerja pada data umum.