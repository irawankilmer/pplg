### **Bab 5: Lists dalam HTML**

#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Memahami fungsi dan penggunaan berbagai jenis list dalam HTML.
- Mengidentifikasi perbedaan antara unordered list, ordered list, dan bagaimana menggunakan list item.
- Menggunakan tag `<ul>`, `<ol>`, dan `<li>` untuk membuat list yang terstruktur di halaman web.

#### **Materi:**

1. **Unordered List (`<ul>`)**
   - **Apa Itu Unordered List?**
     - Unordered list, atau daftar tak berurut, adalah list di mana setiap item tidak memiliki urutan atau hierarki yang jelas. Dalam HTML, kalian menggunakan tag `<ul>` untuk membuat unordered list. Ibaratnya seperti daftar isi di buku catatan kalian yang mencantumkan poin-poin penting tanpa menunjukkan urutan tertentu, seperti daftar tugas yang harus diselesaikan tanpa urutan prioritas.
   
   - **Mengapa Unordered List Penting?**
     - Unordered list berguna saat kalian ingin menampilkan daftar item yang semuanya memiliki tingkat kepentingan yang sama. Misalnya, jika kalian sedang membuat daftar belanja atau poin-poin penting untuk rapat OSIS, ini adalah cara yang tepat untuk menampilkan informasi tersebut.

   - **Contoh Penggunaan:**
     ```html
     <ul>
         <li>Buku catatan</li>
         <li>Pulpen</li>
         <li>Pensil</li>
         <li>Penggaris</li>
     </ul>
     ```

   - **Bagaimana Ini Ditampilkan di Browser?**
     - Di browser, list ini akan ditampilkan sebagai daftar dengan setiap item didahului oleh bullet point atau titik kecil:
     ```
     • Buku catatan
     • Pulpen
     • Pensil
     • Penggaris
     ```

2. **Ordered List (`<ol>`)**
   - **Apa Itu Ordered List?**
     - Ordered list, atau daftar berurut, adalah list di mana setiap item memiliki urutan yang jelas dan ditandai dengan angka atau huruf. Tag `<ol>` digunakan untuk membuat ordered list. Ini seperti urutan langkah-langkah dalam instruksi atau urutan kegiatan dalam upacara bendera di sekolah, di mana setiap langkah harus dilakukan sesuai dengan urutan yang sudah ditentukan.

   - **Mengapa Ordered List Penting?**
     - Ordered list berguna saat urutan item penting untuk dipahami oleh pembaca. Misalnya, jika kalian memberikan petunjuk langkah demi langkah untuk menyelesaikan tugas atau prosedur di laboratorium, menggunakan ordered list akan sangat membantu.

   - **Contoh Penggunaan:**
     ```html
     <ol>
         <li>Masuk kelas dengan tertib</li>
         <li>Mendengarkan pengarahan dari guru</li>
         <li>Mengumpulkan tugas di depan kelas</li>
         <li>Mengerjakan soal latihan</li>
     </ol>
     ```

   - **Bagaimana Ini Ditampilkan di Browser?**
     - Di browser, list ini akan ditampilkan dengan nomor atau huruf yang menandai setiap item:
     ```
     1. Masuk kelas dengan tertib
     2. Mendengarkan pengarahan dari guru
     3. Mengumpulkan tugas di depan kelas
     4. Mengerjakan soal latihan
     ```

3. **List Item (`<li>`)**
   - **Apa Itu List Item?**
     - Tag `<li>` digunakan untuk mendefinisikan setiap item dalam list, baik itu unordered list (`<ul>`) maupun ordered list (`<ol>`). Ini adalah tag yang akan kalian gunakan untuk membuat poin-poin dalam list kalian. Kalau kita kembali ke analogi buku catatan, `<li>` adalah setiap item atau poin yang kalian tulis di daftar tugas atau daftar belanja.

   - **Bagaimana Cara Menggunakannya?**
     - Setiap item dalam list harus diletakkan di antara tag `<li>`. Kalian tidak bisa memiliki list tanpa menggunakan tag `<li>`, karena inilah yang membuat browser tahu bahwa item tersebut adalah bagian dari list.

   - **Contoh Penggunaan dalam Unordered List:**
     ```html
     <ul>
         <li>Buku catatan</li>
         <li>Pulpen</li>
         <li>Pensil</li>
         <li>Penggaris</li>
     </ul>
     ```

   - **Contoh Penggunaan dalam Ordered List:**
     ```html
     <ol>
         <li>Masuk kelas dengan tertib</li>
         <li>Mendengarkan pengarahan dari guru</li>
         <li>Mengumpulkan tugas di depan kelas</li>
         <li>Mengerjakan soal latihan</li>
     </ol>
     ```

4. **Nested List (List Bersarang)**
   - **Apa Itu Nested List?**
     - Nested list adalah list yang terdapat di dalam list lain. Misalnya, jika kalian sedang membuat daftar tugas kelompok, kalian mungkin memiliki tugas utama dengan sub-tugas di bawahnya. Dalam HTML, kalian bisa membuat nested list dengan menempatkan list di dalam list item (`<li>`).

   - **Mengapa Nested List Penting?**
     - Nested list membantu kalian untuk mengelompokkan informasi yang berhubungan satu sama lain. Ini sangat berguna saat kalian perlu menunjukkan hierarki atau sub-bagian dari sebuah topik, seperti agenda rapat dengan poin-poin utama dan sub-poin di bawahnya.

   - **Contoh Penggunaan:**
     ```html
     <ul>
         <li>Tugas Kelompok</li>
         <ul>
             <li>Menulis laporan</li>
             <li>Membuat presentasi</li>
             <li>Latihan presentasi</li>
         </ul>
         <li>Ujian Praktik</li>
         <li>Persiapan Pameran</li>
     </ul>
     ```

   - **Bagaimana Ini Ditampilkan di Browser?**
     - Di browser, nested list akan ditampilkan dengan indentasi untuk menunjukkan hierarki:
     ```
     • Tugas Kelompok
         • Menulis laporan
         • Membuat presentasi
         • Latihan presentasi
     • Ujian Praktik
     • Persiapan Pameran
     ```

#### **Praktikum Lengkap:**

1. **Latihan 1: Membuat Unordered List**
   - Buatlah halaman HTML dengan unordered list yang mencantumkan daftar perlengkapan sekolah.

   **Kode Contoh:**
   ```html
   <!DOCTYPE html>
   <html>
   <head>
       <title>Daftar Perlengkapan Sekolah</title>
   </head>
   <body>
       <ul>
           <li>Buku catatan</li>
           <li>Pulpen</li>
           <li>Pensil</li>
           <li>Penggaris</li>
       </ul>
   </body>
   </html>
   ```

2. **Latihan 2: Membuat Ordered List**
   - Buatlah halaman HTML dengan ordered list yang mencantumkan urutan kegiatan dalam satu hari di sekolah.

   **Kode Contoh:**
   ```html
   <!DOCTYPE html>
   <html>
   <head>
       <title>Urutan Kegiatan di Sekolah</title>
   </head>
   <body>
       <ol>
           <li>Masuk kelas dengan tertib</li>
           <li>Mendengarkan pengarahan dari guru</li>
           <li>Mengumpulkan tugas di depan kelas</li>
           <li>Mengerjakan soal latihan</li>
       </ol>
   </body>
   </html>
   ```

3. **Latihan 3: Membuat Nested List**
   - Buatlah halaman HTML dengan nested list yang mencantumkan tugas kelompok dengan sub-tugas di bawahnya.

   **Kode Contoh:**
   ```html
   <!DOCTYPE html>
   <html>
   <head>
       <title>Tugas Kelompok</title>
   </head>
   <body>
       <ul>
           <li>Tugas Kelompok</li>
           <ul>
               <li>Menulis laporan</li>
               <li>Membuat presentasi</li>
               <li>Latihan presentasi</li>
           </ul>
           <li>Ujian Praktik</li>
           <li>Persiapan Pameran</li>
       </ul>
   </body>
   </html>
   ```

#### **Diskusi dan Review:**

- **Kapan Menggunakan Unordered List vs Ordered List?**
  - **Diskusi:** Gunakan unordered list ketika urutan item tidak penting, seperti daftar belanja atau perlengkapan. Gunakan ordered list ketika urutan penting, seperti langkah-langkah dalam petunjuk atau instruksi.

- **Mengapa Nested List Berguna?**
  - **Diskusi:** Nested list membantu kalian mengelompokkan informasi yang terkait, menunjukkan hierarki, atau sub-poin dalam daftar utama. Ini memudahkan pembaca dalam memahami hubungan antar item.