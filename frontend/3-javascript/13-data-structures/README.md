### **Bab 37: Data Structures**

#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Memahami dan menggunakan struktur data **Map**, **WeakMap**, **Set**, dan **WeakSet** dalam JavaScript.
- Menggunakan JSON (JavaScript Object Notation) untuk pertukaran data dan penyimpanan.

#### **Materi:**

1. **Map**
   - **Definisi Map:**
     - `Map` adalah koleksi pasangan key-value (kunci-nilai) di mana setiap key bisa berupa tipe data apa pun. Ini berbeda dari objek biasa yang hanya menerima string atau simbol sebagai key.
   - **Mengapa Map Penting?**
     - `Map` menyediakan cara efisien untuk menyimpan pasangan key-value, terutama ketika key tidak harus berupa string.
   - **Membuat dan Menggunakan Map:**
     ```javascript
     let siswa = new Map();

     // Menambahkan data ke dalam Map
     siswa.set("nama", "Ahmad");
     siswa.set("kelas", "XI PPLG A");

     // Mengakses data dalam Map
     console.log(siswa.get("nama")); // Output: Ahmad
     console.log(siswa.get("kelas")); // Output: XI PPLG A

     // Mengecek keberadaan key dalam Map
     console.log(siswa.has("nama")); // Output: true

     // Menghapus data dalam Map
     siswa.delete("kelas");

     // Mengetahui ukuran Map
     console.log(siswa.size); // Output: 1
     ```
     - **Penjelasan:**
       - `Map` memungkinkan kalian untuk menggunakan tipe data apa pun sebagai key. Dalam contoh ini, `nama` dan `kelas` digunakan sebagai key untuk menyimpan data siswa.

2. **WeakMap**
   - **Definisi WeakMap:**
     - `WeakMap` mirip dengan `Map`, tetapi key-nya harus berupa objek dan tidak mencegah pengumpulan sampah (garbage collection). Ini berarti jika tidak ada referensi lain ke objek yang digunakan sebagai key, objek tersebut dapat dihapus dari memori.
   - **Mengapa WeakMap Penting?**
     - `WeakMap` digunakan ketika kalian ingin menyimpan data yang terikat pada objek, tetapi tidak ingin mencegah objek tersebut dari penghapusan otomatis oleh garbage collector.
   - **Contoh Penggunaan WeakMap:**
     ```javascript
     let siswa = new WeakMap();
     let info = {};

     siswa.set(info, { nama: "Alya", kelas: "XI PPLG A" });

     console.log(siswa.get(info)); // Output: { nama: 'Alya', kelas: 'XI PPLG A' }

     // Jika objek info dihapus, data dalam WeakMap juga hilang
     info = null;
     ```

3. **Set**
   - **Definisi Set:**
     - `Set` adalah koleksi nilai yang unik, artinya tidak ada duplikasi nilai yang diperbolehkan dalam `Set`.
   - **Mengapa Set Penting?**
     - `Set` digunakan ketika kalian ingin memastikan bahwa kumpulan nilai tidak mengandung duplikat.
   - **Membuat dan Menggunakan Set:**
     ```javascript
     let kelas = new Set();

     // Menambahkan nilai ke dalam Set
     kelas.add("XI PPLG A");
     kelas.add("XII PPLG B");
     kelas.add("XI PPLG A"); // Duplikasi, tidak akan ditambahkan

     // Mengecek ukuran Set
     console.log(kelas.size); // Output: 2

     // Mengecek keberadaan nilai dalam Set
     console.log(kelas.has("XI PPLG A")); // Output: true

     // Menghapus nilai dari Set
     kelas.delete("XII PPLG B");
     console.log(kelas.size); // Output: 1
     ```

4. **WeakSet**
   - **Definisi WeakSet:**
     - `WeakSet` mirip dengan `Set`, tetapi hanya dapat menyimpan objek dan objek dalam `WeakSet` dapat dihapus oleh garbage collector jika tidak ada referensi lain ke objek tersebut.
   - **Mengapa WeakSet Penting?**
     - `WeakSet` digunakan ketika kalian ingin menyimpan kumpulan objek sementara dan tidak ingin mencegah penghapusan otomatis objek yang tidak lagi digunakan.
   - **Contoh Penggunaan WeakSet:**
     ```javascript
     let kelas = new WeakSet();
     let siswa = { nama: "Alya" };

     kelas.add(siswa);

     console.log(kelas.has(siswa)); // Output: true

     // Jika objek siswa dihapus, data dalam WeakSet juga hilang
     siswa = null;
     ```

5. **JSON (JavaScript Object Notation)**
   - **Definisi JSON:**
     - JSON adalah format pertukaran data yang ringan dan mudah dibaca oleh manusia serta mesin. JSON sering digunakan untuk mengirimkan data antara server dan client.
   - **Mengapa JSON Penting?**
     - JSON adalah format standar yang digunakan untuk menyimpan dan mentransfer data dalam aplikasi web.
   - **Contoh Penggunaan JSON:**
     ```javascript
     let siswa = {
         nama: "Alya",
         kelas: "XI PPLG A"
     };

     // Mengonversi objek JavaScript ke JSON string
     let jsonString = JSON.stringify(siswa);
     console.log(jsonString); // Output: {"nama":"Alya","kelas":"XI PPLG A"}

     // Mengonversi JSON string kembali ke objek JavaScript
     let siswaObjek = JSON.parse(jsonString);
     console.log(siswaObjek); // Output: { nama: 'Alya', kelas: 'XI PPLG A' }
     ```
     - **Penjelasan:**
       - `JSON.stringify` mengonversi objek JavaScript menjadi string JSON, sedangkan `JSON.parse` mengonversi string JSON kembali menjadi objek JavaScript.

#### **Praktikum Lengkap:**

1. **Latihan 1: Menggunakan Map untuk Menyimpan Informasi Siswa**
   - Buat Map untuk menyimpan nama dan kelas siswa, lalu tampilkan informasi tersebut.
   **Contoh Praktik:**
   ```javascript
   let siswa = new Map();

   siswa.set("nama", "Budi");
   siswa.set("kelas", "XI PPLG B");

   console.log(`Nama: ${siswa.get("nama")}, Kelas: ${siswa.get("kelas")}`);
   ```

2. **Latihan 2: Menggunakan Set untuk Menyimpan Daftar Kelas Unik**
   - Buat Set untuk menyimpan nama kelas dan pastikan tidak ada duplikasi.
   **Contoh Praktik:**
   ```javascript
   let kelas = new Set();

   kelas.add("XI PPLG A");
   kelas.add("XII PPLG B");
   kelas.add("XI PPLG A"); // Ini tidak akan ditambahkan karena duplikat

   console.log(`Jumlah Kelas: ${kelas.size}`);
   ```

3. **Latihan 3: Mengonversi Objek ke JSON dan Sebaliknya**
   - Buat objek siswa, konversikan ke JSON, lalu konversikan kembali ke objek.
   **Contoh Praktik:**
   ```javascript
   let siswa = {
       nama: "Siti",
       kelas: "XII PPLG A"
   };

   let jsonString = JSON.stringify(siswa);
   console.log(`JSON String: ${jsonString}`);

   let siswaObjek = JSON.parse(jsonString);
   console.log(`Nama: ${siswaObjek.nama}, Kelas: ${siswaObjek.kelas}`);
   ```

#### **Diskusi dan Review:**

- **Kapan Sebaiknya Menggunakan Map daripada Objek?**
  - **Diskusi:**
    - `Map` lebih fleksibel karena bisa menggunakan tipe data apa pun sebagai key. Jika kalian membutuhkan key yang bukan string atau jika kalian membutuhkan fitur seperti iterasi dengan urutan penyisipan, `Map` adalah pilihan yang lebih baik.

- **Apa Keuntungan Menggunakan JSON dalam Aplikasi Web?**
  - **Diskusi:**
    - JSON sangat efisien dan mudah dipahami baik oleh manusia maupun mesin, membuatnya ideal untuk pertukaran data di antara server dan client. JSON juga didukung oleh banyak bahasa pemrograman, sehingga mudah diintegrasikan.