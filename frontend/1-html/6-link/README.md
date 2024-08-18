### **Bab 6: Links dalam HTML**

#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Memahami fungsi dan penggunaan tag `<a>` untuk membuat hyperlink di halaman web.
- Mengidentifikasi peran atribut `href` dan `target` dalam menentukan tujuan dan perilaku link.
- Menggunakan tag `<a>` untuk membuat link yang mengarahkan ke halaman lain atau bagian tertentu dari halaman yang sama.

#### **Materi:**

1. **Tag `<a>` dan Atribut `href`**
   - **Apa Itu Tag `<a>`?**
     - Tag `<a>` adalah singkatan dari "anchor", yang digunakan untuk membuat hyperlink di halaman web. Hyperlink adalah teks atau gambar yang bisa diklik oleh pengguna untuk pindah ke halaman lain atau sumber lain di internet. Dalam konteks sekolah, kalian bisa bayangkan `<a>` seperti pintu yang menghubungkan satu kelas dengan kelas lain—mengklik link seperti membuka pintu dan berpindah ke ruangan baru.
   
   - **Atribut `href`: Menentukan Tujuan Link**
     - Atribut `href` (hypertext reference) pada tag `<a>` menentukan tujuan dari link tersebut. Ini seperti alamat tujuan yang kalian masukkan ketika kalian ingin mengunjungi rumah teman. Jika kalian tidak menambahkan `href`, maka link tidak akan membawa kalian ke mana pun.

   - **Contoh Penggunaan:**
     ```html
     <a href="https://www.google.com">Kunjungi Google</a>
     ```
     Di contoh ini, teks "Kunjungi Google" akan menjadi hyperlink. Ketika kalian mengklik teks ini, browser kalian akan membuka situs Google.

   - **Menggunakan Link untuk Navigasi Internal**
     - Kalian juga bisa menggunakan tag `<a>` untuk membuat link yang mengarahkan ke bagian lain dari halaman yang sama. Misalnya, kalian bisa membuat daftar isi di bagian atas halaman yang mengarahkan ke setiap bab di halaman tersebut. Ini seperti daftar isi di buku pelajaran yang membantu kalian langsung menuju ke bab tertentu.

   - **Contoh Penggunaan Navigasi Internal:**
     ```html
     <a href="#bab1">Bab 1: Pengenalan HTML</a>
     <h2 id="bab1">Bab 1: Pengenalan HTML</h2>
     ```

2. **Atribut `target`: Mengatur Cara Link Dibuka**
   - **Apa Itu Atribut `target`?**
     - Atribut `target` menentukan bagaimana link akan dibuka—apakah di tab atau jendela baru, atau di tab atau jendela yang sama. Ini seperti memilih apakah kalian ingin membuka buku di halaman baru atau melanjutkan di halaman yang sedang kalian baca.

   - **Menggunakan `target="_blank"` untuk Membuka Link di Tab Baru**
     - Ketika kalian menambahkan `target="_blank"` pada tag `<a>`, link akan terbuka di tab baru. Ini sangat berguna ketika kalian ingin menjaga halaman utama tetap terbuka, misalnya, saat kalian membuka referensi dari halaman lain tanpa meninggalkan halaman utama.

   - **Contoh Penggunaan:**
     ```html
     <a href="https://www.wikipedia.org" target="_blank">Buka Wikipedia di tab baru</a>
     ```

3. **Menghubungkan Halaman-Halaman di Situs Web Kalian**
   - **Membuat Link Antar Halaman Internal**
     - Ketika kalian membuat situs web yang terdiri dari beberapa halaman, tag `<a>` dapat digunakan untuk menghubungkan halaman-halaman ini. Misalnya, kalian bisa membuat link dari halaman utama ke halaman "Tentang Kami" atau "Kontak". Ini seperti menavigasi antar ruangan di sekolah—dari ruang kelas ke perpustakaan atau ke kantor guru.

   - **Contoh Penggunaan di Situs Web Sekolah:**
     ```html
     <a href="tentang.html">Tentang Kelas XI PPLG 1</a>
     <a href="kontak.html">Kontak Guru</a>
     ```

4. **Contoh Penggunaan dengan Data Siswa**
   - **Menghubungkan ke Profil Siswa**
     - Misalkan kalian membuat situs web untuk kelas XI PPLG 1, dan kalian ingin setiap nama siswa bisa diklik untuk melihat profil mereka. Kalian bisa menggunakan tag `<a>` untuk membuat link ke halaman profil masing-masing siswa.

   **Contoh Penggunaan:**
   ```html
   <ul>
       <li><a href="profil/alya_salsabila.html">Alya Salsabila</a></li>
       <li><a href="profil/amanda_aulia.html">Amanda Aulia</a></li>
       <li><a href="profil/anggie_maryani.html">Anggie Maryani</a></li>
   </ul>
   ```
   Di contoh ini, setiap nama siswa bisa diklik untuk membuka halaman profil mereka yang berbeda.

#### **Praktikum Lengkap:**

1. **Latihan 1: Membuat Link Eksternal**
   - Buatlah halaman HTML dengan link eksternal yang mengarahkan ke situs web favorit kalian, seperti Google atau Wikipedia.

   **Kode Contoh:**
   ```html
   <!DOCTYPE html>
   <html>
   <head>
       <title>Link Eksternal</title>
   </head>
   <body>
       <a href="https://www.google.com" target="_blank">Kunjungi Google</a>
   </body>
   </html>
   ```

2. **Latihan 2: Membuat Navigasi Internal**
   - Buatlah halaman HTML yang memiliki daftar isi di bagian atas yang mengarahkan ke berbagai bagian di halaman yang sama.

   **Kode Contoh:**
   ```html
   <!DOCTYPE html>
   <html>
   <head>
       <title>Navigasi Internal</title>
   </head>
   <body>
       <a href="#profil1">Profil Alya Salsabila</a> | 
       <a href="#profil2">Profil Amanda Aulia</a> | 
       <a href="#profil3">Profil Anggie Maryani</a>

       <h2 id="profil1">Profil Alya Salsabila</h2>
       <p>Alya adalah siswa kelas XI PPLG 1 yang sangat berbakat dalam desain grafis.</p>

       <h2 id="profil2">Profil Amanda Aulia</h2>
       <p>Amanda adalah siswa kelas XI PPLG 1 yang aktif dalam kegiatan OSIS.</p>

       <h2 id="profil3">Profil Anggie Maryani</h2>
       <p>Anggie adalah siswa kelas XI PPLG 1 yang memiliki minat besar dalam pemrograman.</p>
   </body>
   </html>
   ```

3. **Latihan 3: Membuat Link Antar Halaman Internal**
   - Buatlah halaman HTML yang menghubungkan halaman utama ke halaman lain di situs web kelas kalian.

   **Kode Contoh:**
   ```html
   <!DOCTYPE html>
   <html>
   <head>
       <title>Halaman Utama XI PPLG 1</title>
   </head>
   <body>
       <h1>Selamat Datang di Halaman Utama XI PPLG 1</h1>
       <p>Untuk informasi lebih lanjut, kunjungi halaman berikut:</p>
       <a href="tentang.html">Tentang Kelas XI PPLG 1</a> | 
       <a href="kontak.html">Kontak Guru</a>
   </body>
   </html>
   ```

#### **Diskusi dan Review:**

- **Kapan Menggunakan Link Eksternal vs Link Internal?**
  - **Diskusi:** Gunakan link eksternal ketika kalian ingin mengarahkan pengguna ke situs di luar domain kalian, seperti Google atau Wikipedia. Gunakan link internal untuk navigasi di dalam situs kalian sendiri, seperti halaman "Tentang Kami" atau "Kontak".

- **Mengapa Navigasi Internal Penting?**
  - **Diskusi:** Navigasi internal memudahkan pengguna untuk bergerak antar bagian dalam halaman yang sama, seperti daftar isi yang membantu kalian langsung menuju bab tertentu dalam buku.