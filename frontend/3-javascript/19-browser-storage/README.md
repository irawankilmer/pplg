### **Bab 43: Browser Storage**

#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Memahami konsep penyimpanan data di browser menggunakan **localStorage** dan **sessionStorage**.
- Menyimpan, mengambil, dan menghapus data di **localStorage** dan **sessionStorage**.
- Memahami perbedaan antara **localStorage** dan **sessionStorage** serta kapan sebaiknya menggunakan masing-masing.

#### **Materi:**

1. **Apa Itu Browser Storage?**
   - **Definisi Browser Storage:**
     - Browser storage adalah metode penyimpanan data di sisi client yang memungkinkan data tetap ada bahkan setelah halaman web ditutup atau di-refresh. JavaScript menyediakan dua jenis penyimpanan: **localStorage** dan **sessionStorage**.
   - **Mengapa Browser Storage Penting?**
     - Browser storage penting karena memungkinkan kalian untuk menyimpan data pengguna secara lokal di browser, yang dapat digunakan kembali ketika pengguna mengunjungi halaman atau ketika mereka membuka halaman kembali nanti.

2. **localStorage**
   - **Penjelasan:**
     - `localStorage` adalah jenis penyimpanan di browser yang menyimpan data tanpa tanggal kadaluwarsa. Data yang disimpan di `localStorage` tetap ada bahkan setelah browser ditutup dan dibuka kembali.
   - **Fitur Utama:**
     - Penyimpanan data tetap ada setelah halaman di-refresh atau browser ditutup dan dibuka kembali.
     - Kapasitas penyimpanan sekitar 5MB per domain.
   - **Contoh Penggunaan `localStorage`:**
     ```javascript
     // Menyimpan data
     localStorage.setItem("username", "Ahmad");

     // Mengambil data
     let username = localStorage.getItem("username");
     console.log(username); // Output: Ahmad

     // Menghapus data
     localStorage.removeItem("username");

     // Menghapus semua data
     localStorage.clear();
     ```
     - **Penjelasan:**
       - Pada contoh di atas, `setItem` digunakan untuk menyimpan data ke `localStorage`, `getItem` digunakan untuk mengambil data, `removeItem` untuk menghapus data tertentu, dan `clear` untuk menghapus semua data di `localStorage`.

3. **sessionStorage**
   - **Penjelasan:**
     - `sessionStorage` adalah jenis penyimpanan di browser yang menyimpan data hanya selama sesi halaman. Data yang disimpan akan hilang setelah tab atau jendela browser ditutup.
   - **Fitur Utama:**
     - Penyimpanan data hanya ada selama sesi browser (tab) aktif.
     - Kapasitas penyimpanan sekitar 5MB per domain.
   - **Contoh Penggunaan `sessionStorage`:**
     ```javascript
     // Menyimpan data
     sessionStorage.setItem("sessionId", "12345");

     // Mengambil data
     let sessionId = sessionStorage.getItem("sessionId");
     console.log(sessionId); // Output: 12345

     // Menghapus data
     sessionStorage.removeItem("sessionId");

     // Menghapus semua data
     sessionStorage.clear();
     ```
     - **Penjelasan:**
       - Pada contoh di atas, `sessionStorage` bekerja dengan cara yang sama seperti `localStorage`, tetapi data hanya bertahan selama sesi browser aktif.

4. **Perbedaan antara localStorage dan sessionStorage**
   - **Durasi Penyimpanan:**
     - `localStorage`: Data bertahan hingga dihapus secara eksplisit, bahkan setelah browser ditutup dan dibuka kembali.
     - `sessionStorage`: Data hanya bertahan selama sesi browser aktif. Jika tab atau jendela ditutup, data akan hilang.
   - **Penggunaan yang Direkomendasikan:**
     - Gunakan `localStorage` untuk data yang perlu dipertahankan lebih lama atau antar sesi browser.
     - Gunakan `sessionStorage` untuk data yang hanya relevan selama sesi aktif pengguna, seperti data yang terkait dengan tampilan sementara atau navigasi.

5. **Menyimpan Objek di localStorage atau sessionStorage**
   - **Penjelasan:**
     - `localStorage` dan `sessionStorage` hanya dapat menyimpan string, sehingga jika kalian ingin menyimpan objek, kalian harus mengonversinya menjadi JSON string menggunakan `JSON.stringify`.
   - **Contoh Penggunaan:**
     ```javascript
     let user = {
         name: "Alya",
         age: 17,
         school: "SMK Assalam Samarang"
     };

     // Menyimpan objek ke localStorage
     localStorage.setItem("user", JSON.stringify(user));

     // Mengambil objek dari localStorage
     let retrievedUser = JSON.parse(localStorage.getItem("user"));
     console.log(retrievedUser.name); // Output: Alya
     ```
     - **Penjelasan:**
       - Pada contoh ini, objek `user` dikonversi menjadi string JSON sebelum disimpan di `localStorage`. Ketika diambil kembali, string JSON tersebut dikonversi kembali menjadi objek menggunakan `JSON.parse`.

6. **Contoh Kasus Penggunaan localStorage dan sessionStorage**
   - **Contoh Kasus untuk `localStorage`:**
     - Menyimpan preferensi pengguna seperti tema (terang atau gelap) yang harus bertahan meskipun pengguna menutup dan membuka kembali browser.
     - **Contoh:**
       ```javascript
       let theme = "dark";
       localStorage.setItem("theme", theme);
       ```
   - **Contoh Kasus untuk `sessionStorage`:**
     - Menyimpan informasi formulir sementara yang hanya relevan selama sesi saat ini.
     - **Contoh:**
       ```javascript
       sessionStorage.setItem("formData", JSON.stringify({ name: "Ahmad", age: 17 }));
       ```

#### **Praktikum Lengkap:**

1. **Latihan 1: Menyimpan dan Mengambil Data dari localStorage**
   - Simpan nama pengguna di `localStorage` dan ambil kembali untuk ditampilkan di halaman.
   **Contoh Praktik:**
   ```javascript
   // Menyimpan nama pengguna di localStorage
   localStorage.setItem("username", "Budi");

   // Mengambil dan menampilkan nama pengguna
   let username = localStorage.getItem("username");
   console.log("Nama pengguna: " + username); // Output: Nama pengguna: Budi
   ```

2. **Latihan 2: Menyimpan Objek di sessionStorage**
   - Simpan objek data siswa di `sessionStorage` dan ambil kembali untuk ditampilkan.
   **Contoh Praktik:**
   ```javascript
   let student = {
       name: "Anisa",
       class: "XI PPLG A"
   };

   // Menyimpan objek di sessionStorage
   sessionStorage.setItem("student", JSON.stringify(student));

   // Mengambil dan menampilkan data siswa
   let retrievedStudent = JSON.parse(sessionStorage.getItem("student"));
   console.log("Nama siswa: " + retrievedStudent.name); // Output: Nama siswa: Anisa
   ```

3. **Latihan 3: Menghapus Data dari localStorage**
   - Simpan dan kemudian hapus data dari `localStorage`.
   **Contoh Praktik:**
   ```javascript
   localStorage.setItem("username", "Budi");

   // Menghapus data dari localStorage
   localStorage.removeItem("username");

   let username = localStorage.getItem("username");
   console.log("Nama pengguna: " + (username || "Data tidak ditemukan")); // Output: Nama pengguna: Data tidak ditemukan
   ```

4. **Latihan 4: Menggunakan sessionStorage untuk Menyimpan Data Sesi**
   - Simpan data sementara di `sessionStorage` yang akan dihapus ketika tab atau jendela ditutup.
   **Contoh Praktik:**
   ```javascript
   sessionStorage.setItem("pageVisit", "1");

   let visitCount = sessionStorage.getItem("pageVisit");
   console.log("Kunjungan halaman: " + visitCount); // Output: Kunjungan halaman: 1

   // Tambahkan logika untuk memperbarui kunjungan halaman jika diperlukan
   ```

#### **Diskusi dan Review:**

- **Kapan Sebaiknya Menggunakan `localStorage` dan Kapan Sebaiknya Menggunakan `sessionStorage`?**
  - **Diskusi:**
    - `localStorage` digunakan untuk data yang perlu dipertahankan antar sesi, seperti preferensi pengguna atau pengaturan yang perlu diingat untuk waktu yang lama. `sessionStorage` digunakan untuk data yang hanya relevan selama sesi aktif, seperti data form sementara atau informasi navigasi.

- **Apa Batasan dari `localStorage` dan `sessionStorage`?**
  - **Diskusi:**
    - Keduanya memiliki batasan ukuran sekitar 5MB per domain, yang cukup untuk banyak kasus penggunaan, tetapi tidak cocok untuk menyimpan data besar. Mereka juga hanya bisa menyimpan string, jadi objek harus dikonversi menjadi string JSON sebelum disimpan.

- **Bagaimana Cara Menyimpan dan Mengambil Objek di `localStorage` atau `sessionStorage`?**
  - **Diskusi:**
    - Gunakan `JSON.stringify()` untuk mengonversi objek menjadi string sebelum menyimpannya, dan `JSON.parse()` untuk mengonversinya kembali menjadi objek ketika mengambil data dari `localStorage` atau `sessionStorage`.