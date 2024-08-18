### **Bab 38: Error Handling**

#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Memahami konsep dasar penanganan kesalahan (error handling) dalam JavaScript.
- Menggunakan **try**, **catch**, **finally**, dan **throw** untuk menangani kesalahan dalam kode JavaScript.
- Menangani kesalahan secara efektif untuk mencegah aplikasi berhenti atau berperilaku tidak diinginkan.

#### **Materi:**

1. **Apa Itu Error Handling?**
   - **Definisi Error Handling:**
     - Error handling adalah proses menangani kesalahan yang terjadi selama eksekusi program, seperti kesalahan sintaks, kesalahan runtime, atau kesalahan logika, sehingga aplikasi tidak berhenti secara tiba-tiba.
   - **Mengapa Error Handling Penting?**
     - Error handling penting karena memungkinkan kalian untuk mengelola kesalahan dengan cara yang terkontrol, memberikan pengalaman pengguna yang lebih baik, dan meminimalkan potensi kerusakan pada aplikasi.

2. **Menggunakan `try...catch`**
   - **Penjelasan:**
     - Blok `try` digunakan untuk menjalankan kode yang mungkin menyebabkan kesalahan. Jika kesalahan terjadi, eksekusi akan berpindah ke blok `catch`, di mana kesalahan tersebut dapat ditangani.
   - **Sintaks Dasar:**
     ```javascript
     try {
         // kode yang mungkin menyebabkan kesalahan
     } catch (error) {
         // kode untuk menangani kesalahan
     }
     ```
   - **Contoh Penggunaan:**
     ```javascript
     try {
         let siswa = null;
         console.log(siswa.name); // Ini akan menyebabkan kesalahan
     } catch (error) {
         console.log("Terjadi kesalahan: " + error.message);
     }
     ```
     - **Penjelasan:**
       - Pada contoh di atas, akses ke properti `name` dari objek `null` menyebabkan kesalahan. Blok `catch` menangkap kesalahan tersebut dan mencetak pesan kesalahan.

3. **Menggunakan `finally`**
   - **Penjelasan:**
     - Blok `finally` digunakan untuk mengeksekusi kode setelah `try` dan `catch`, terlepas dari apakah kesalahan terjadi atau tidak. Ini berguna untuk membersihkan sumber daya atau melakukan tugas akhir lainnya.
   - **Sintaks Dasar:**
     ```javascript
     try {
         // kode yang mungkin menyebabkan kesalahan
     } catch (error) {
         // kode untuk menangani kesalahan
     } finally {
         // kode yang akan selalu dijalankan
     }
     ```
   - **Contoh Penggunaan:**
     ```javascript
     try {
         let siswa = { nama: "Alya" };
         console.log(siswa.name); // Ini tidak akan menyebabkan kesalahan
     } catch (error) {
         console.log("Terjadi kesalahan: " + error.message);
     } finally {
         console.log("Eksekusi selesai.");
     }
     ```
     - **Penjelasan:**
       - Blok `finally` akan selalu dijalankan, sehingga pesan "Eksekusi selesai." akan ditampilkan, bahkan jika tidak ada kesalahan.

4. **Menggunakan `throw` untuk Membuat Kesalahan Sendiri**
   - **Penjelasan:**
     - Kalian dapat menggunakan `throw` untuk secara eksplisit membuat kesalahan. Ini berguna ketika kalian ingin memvalidasi data atau menandai situasi yang tidak diinginkan dalam kode.
   - **Sintaks Dasar:**
     ```javascript
     throw new Error("Pesan kesalahan");
     ```
   - **Contoh Penggunaan:**
     ```javascript
     function cekUmur(umur) {
         if (umur < 18) {
             throw new Error("Kalian harus berusia minimal 18 tahun.");
         } else {
             console.log("Kalian cukup umur.");
         }
     }

     try {
         cekUmur(16);
     } catch (error) {
         console.log("Kesalahan: " + error.message);
     }
     ```
     - **Penjelasan:**
       - Pada contoh di atas, jika usia kurang dari 18 tahun, kesalahan akan dibuat menggunakan `throw`. Blok `catch` kemudian menangkap kesalahan tersebut dan mencetak pesan kesalahan.

5. **Menggunakan `Error` Objects**
   - **Penjelasan:**
     - Objek `Error` dalam JavaScript memiliki properti `name` dan `message`, yang memberikan informasi lebih lanjut tentang kesalahan yang terjadi.
   - **Contoh Penggunaan:**
     ```javascript
     try {
         throw new Error("Ini adalah pesan kesalahan.");
     } catch (error) {
         console.log(error.name); // Output: Error
         console.log(error.message); // Output: Ini adalah pesan kesalahan.
     }
     ```
     - **Penjelasan:**
       - Pada contoh ini, sebuah objek `Error` dibuat dengan pesan tertentu, dan `name` serta `message` dari kesalahan tersebut ditampilkan di konsol.

#### **Praktikum Lengkap:**

1. **Latihan 1: Menggunakan `try...catch` untuk Menangani Kesalahan**
   - Buat sebuah blok `try...catch` untuk menangani kesalahan saat mencoba mengakses properti objek yang tidak ada.
   **Contoh Praktik:**
   ```javascript
   try {
       let siswa = { nama: "Anisa" };
       console.log(siswa.kelas); // Properti 'kelas' tidak ada
   } catch (error) {
       console.log("Terjadi kesalahan: " + error.message);
   }
   ```

2. **Latihan 2: Menambahkan Blok `finally` untuk Membersihkan Sumber Daya**
   - Tambahkan blok `finally` untuk mencetak pesan bahwa eksekusi telah selesai, terlepas dari apakah terjadi kesalahan atau tidak.
   **Contoh Praktik:**
   ```javascript
   try {
       let siswa = { nama: "Irfan" };
       console.log(siswa.kelas); // Properti 'kelas' tidak ada
   } catch (error) {
       console.log("Terjadi kesalahan: " + error.message);
   } finally {
       console.log("Eksekusi telah selesai.");
   }
   ```

3. **Latihan 3: Menggunakan `throw` untuk Validasi Data**
   - Buat function yang memvalidasi input dan menggunakan `throw` untuk membuat kesalahan jika input tidak valid.
   **Contoh Praktik:**
   ```javascript
   function cekNama(nama) {
       if (nama === "") {
           throw new Error("Nama tidak boleh kosong.");
       } else {
           console.log("Nama kalian adalah " + nama);
       }
   }

   try {
       cekNama(""); // Ini akan menyebabkan kesalahan
   } catch (error) {
       console.log("Kesalahan: " + error.message);
   }
   ```

4. **Latihan 4: Membuat dan Menggunakan Objek `Error`**
   - Buat dan tangani objek `Error` untuk kesalahan khusus yang dapat kalian atur dalam program.
   **Contoh Praktik:**
   ```javascript
   try {
       throw new Error("Terjadi kesalahan dalam sistem.");
   } catch (error) {
       console.log("Nama Kesalahan: " + error.name);
       console.log("Pesan Kesalahan: " + error.message);
   }
   ```

#### **Diskusi dan Review:**

- **Mengapa Penting untuk Menangani Kesalahan dengan `try...catch`?**
  - **Diskusi:**
    - Menangani kesalahan dengan `try...catch` penting untuk mencegah aplikasi kalian dari berhenti tiba-tiba ketika terjadi kesalahan. Ini memungkinkan kalian untuk menangani kesalahan dengan cara yang lebih terkontrol, memberikan pesan kesalahan yang lebih informatif kepada pengguna.

- **Kapan Sebaiknya Menggunakan `throw` untuk Membuat Kesalahan Sendiri?**
  - **Diskusi:**
    - `throw` digunakan ketika kalian ingin memvalidasi input atau situasi tertentu dalam kode dan ingin secara eksplisit menandai kondisi kesalahan. Ini memberikan kontrol lebih besar terhadap bagaimana dan kapan kesalahan terjadi.

- **Bagaimana Blok `finally` Membantu dalam Membersihkan Sumber Daya?**
  - **Diskusi:**
    - Blok `finally` membantu memastikan bahwa kode tertentu selalu dieksekusi, seperti membersihkan sumber daya atau menutup koneksi, bahkan jika terjadi kesalahan. Ini berguna untuk menjaga integritas aplikasi kalian.