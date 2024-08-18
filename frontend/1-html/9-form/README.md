### **Bab 9: Forms dalam HTML**

#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Memahami fungsi dan penggunaan berbagai elemen form dalam HTML.
- Mengidentifikasi cara membuat form yang interaktif dan dapat digunakan untuk mengumpulkan data dari pengguna.
- Menggunakan elemen-elemen seperti `<form>`, `<input>`, `<textarea>`, `<button>`, `<select>`, `<option>`, dan `<label>` secara efektif dalam pembuatan form.

#### **Materi:**

1. **Tag `<form>`**
   - **Apa Itu Tag `<form>`?**
     - Tag `<form>` adalah elemen dasar yang digunakan untuk membuat form di halaman web. Semua elemen input yang dimaksudkan untuk mengirimkan data kepada server harus ditempatkan di dalam tag `<form>`. Form ini bisa digunakan untuk berbagai tujuan, seperti mendaftarkan pengguna, mengumpulkan feedback, atau mengisi data kontak.

   - **Atribut Penting pada Tag `<form>`:**
     - **`action`**: Atribut ini menentukan URL tempat data form akan dikirim ketika pengguna mengklik tombol submit. Ini adalah alamat server atau script yang akan memproses data form.
     - **`method`**: Atribut ini menentukan metode pengiriman data, biasanya menggunakan `GET` atau `POST`.
       - **GET**: Data dikirim sebagai bagian dari URL, cocok untuk pencarian atau navigasi sederhana.
       - **POST**: Data dikirim dalam body request, cocok untuk data yang lebih besar atau sensitif, seperti password.

   - **Contoh Penggunaan:**
     ```html
     <form action="/submit_form" method="POST">
       <!-- Elemen input form akan ditempatkan di sini -->
     </form>
     ```

2. **Tag `<input>`**
   - **Apa Itu Tag `<input>`?**
     - Tag `<input>` digunakan untuk membuat berbagai jenis kontrol input di dalam form. Kontrol ini bisa berupa kotak teks, checkbox, radio button, dan lain-lain, tergantung pada nilai atribut `type` yang digunakan.

   - **Atribut Penting pada Tag `<input>`:**
     - **`type`**: Menentukan jenis input yang akan ditampilkan. Beberapa nilai umum untuk `type` adalah:
       - **`text`**: Untuk input teks satu baris.
       - **`password`**: Untuk input teks yang disembunyikan (biasanya untuk password).
       - **`email`**: Untuk input alamat email yang valid.
       - **`number`**: Untuk input angka.
       - **`radio`**: Untuk pilihan radio (hanya satu pilihan yang bisa dipilih dalam grup).
       - **`checkbox`**: Untuk kotak centang (multiple pilihan bisa dipilih).
       - **`submit`**: Untuk tombol submit form.
     - **`name`**: Atribut ini memberikan nama pada input dan digunakan sebagai kunci untuk data yang dikirimkan ke server.
     - **`value`**: Menentukan nilai awal dari input.
     - **`placeholder`**: Menampilkan teks petunjuk di dalam input saat belum diisi.

   - **Contoh Penggunaan untuk Input Teks:**
     ```html
     <form action="/submit_form" method="POST">
       <label for="nama">Nama:</label>
       <input type="text" id="nama" name="nama" placeholder="Masukkan nama Anda">
     </form>
     ```

   - **Contoh Penggunaan untuk Checkbox dan Radio Button:**
     ```html
     <form action="/submit_form" method="POST">
       <label>Pilih Mata Pelajaran:</label><br>
       <input type="checkbox" id="matematika" name="matapelajaran" value="matematika">
       <label for="matematika">Matematika</label><br>
       <input type="checkbox" id="bahasa_inggris" name="matapelajaran" value="bahasa_inggris">
       <label for="bahasa_inggris">Bahasa Inggris</label><br>

       <label>Pilih Jenis Kelamin:</label><br>
       <input type="radio" id="pria" name="gender" value="pria">
       <label for="pria">Pria</label><br>
       <input type="radio" id="wanita" name="gender" value="wanita">
       <label for="wanita">Wanita</label><br>
     </form>
     ```

3. **Tag `<textarea>`**
   - **Apa Itu Tag `<textarea>`?**
     - Tag `<textarea>` digunakan untuk membuat kotak teks multiline, yang memungkinkan pengguna untuk memasukkan teks panjang seperti komentar atau deskripsi. Tidak seperti `<input type="text">`, `<textarea>` memungkinkan pengguna untuk menulis lebih dari satu baris teks.

   - **Atribut Penting pada Tag `<textarea>`:**
     - **`rows`** dan **`cols`**: Menentukan ukuran dari kotak teks dalam jumlah baris dan kolom.
     - **`name`**: Sama seperti pada `<input>`, ini menentukan nama data yang akan dikirim ke server.

   - **Contoh Penggunaan:**
     ```html
     <form action="/submit_form" method="POST">
       <label for="komentar">Komentar:</label><br>
       <textarea id="komentar" name="komentar" rows="4" cols="50" placeholder="Tulis komentar Anda di sini..."></textarea>
     </form>
     ```

4. **Tag `<button>`**
   - **Apa Itu Tag `<button>`?**
     - Tag `<button>` digunakan untuk membuat tombol yang dapat mengirim form atau melakukan tindakan tertentu. Atribut `type` pada `<button>` menentukan fungsinya:
       - **`submit`**: Mengirim form.
       - **`reset`**: Mengatur ulang semua input dalam form.
       - **`button`**: Sebagai tombol biasa yang bisa dikombinasikan dengan JavaScript untuk berbagai fungsi.

   - **Contoh Penggunaan:**
     ```html
     <form action="/submit_form" method="POST">
       <button type="submit">Kirim</button>
       <button type="reset">Reset</button>
     </form>
     ```

5. **Tag `<select>` dan `<option>`**
   - **Apa Itu Tag `<select>`?**
     - Tag `<select>` digunakan untuk membuat dropdown list, memungkinkan pengguna untuk memilih satu dari beberapa pilihan yang telah ditentukan. Di dalam `<select>`, tag `<option>` digunakan untuk mendefinisikan setiap pilihan yang tersedia.

   - **Atribut Penting pada Tag `<select>`:**
     - **`name`**: Menentukan nama data yang akan dikirimkan ke server.
     - **`multiple`**: Menentukan apakah pengguna bisa memilih lebih dari satu pilihan.

   - **Contoh Penggunaan:**
     ```html
     <form action="/submit_form" method="POST">
       <label for="kelas">Pilih Kelas:</label>
       <select id="kelas" name="kelas">
         <option value="XI PPLG 1">XI PPLG 1</option>
         <option value="XI PPLG 2">XI PPLG 2</option>
         <option value="XI PPLG 3">XI PPLG 3</option>
       </select>
     </form>
     ```

6. **Tag `<label>`**
   - **Apa Itu Tag `<label>`?**
     - Tag `<label>` digunakan untuk memberikan label pada elemen form, membuatnya lebih mudah diakses. Menggunakan `<label>` dengan atribut `for` yang merujuk pada `id` elemen input yang relevan membuat form lebih mudah digunakan oleh semua pengguna, termasuk yang menggunakan alat bantu seperti screen reader.

   - **Contoh Penggunaan:**
     ```html
     <form action="/submit_form" method="POST">
       <label for="nama">Nama:</label>
       <input type="text" id="nama" name="nama" placeholder="Masukkan nama Anda">
     </form>
     ```

#### **Praktikum Lengkap:**

1. **Latihan 1: Membuat Form Pendaftaran Siswa**
   - Buatlah form sederhana untuk pendaftaran siswa baru dengan menggunakan berbagai elemen form seperti input teks, dropdown list, dan textarea.

   **Contoh Praktik:**
   ```html
   <!DOCTYPE html>
   <html>
   <head>
       <title>Form Pendaftaran Siswa</title>
   </head>
   <body>
       <h2>Form Pendaftaran Siswa Baru</h2>
       <form action="/submit_form" method="POST">
           <label for="nama">Nama:</label><br>
           <input type="text" id="nama" name="nama" placeholder="Masukkan nama Anda"><br><br>
           
           <label for="email">Email:</label><br>
           <input type="email" id="email" name="email" placeholder="Masukkan email Anda"><br><br>

           <label for="kelas">Pilih Kelas:</label><br>
           <select id="kelas" name="kelas">
               <option value="XI PPLG 1">XI PPLG 1</option>
               <option value="XI PPLG 2">XI PPLG 2</option>
               <option value="XI PPLG 3

">XI PPLG 3</option>
           </select><br><br>

           <label for="komentar">Komentar:</label><br>
           <textarea id="komentar" name="komentar" rows="4" cols="50" placeholder="Tulis komentar Anda di sini..."></textarea><br><br>

           <button type="submit">Kirim</button>
           <button type="reset">Reset</button>
       </form>
   </body>
   </html>
   ```

2. **Latihan 2: Membuat Form dengan Checkbox dan Radio Button**
   - Cobalah buat form yang memungkinkan pengguna untuk memilih mata pelajaran favorit dan jenis kelamin menggunakan checkbox dan radio button.

   **Contoh Praktik:**
   ```html
   <!DOCTYPE html>
   <html>
   <head>
       <title>Form Pilihan Mata Pelajaran</title>
   </head>
   <body>
       <h2>Pilihan Mata Pelajaran</h2>
       <form action="/submit_form" method="POST">
           <label>Pilih Mata Pelajaran:</label><br>
           <input type="checkbox" id="matematika" name="matapelajaran" value="matematika">
           <label for="matematika">Matematika</label><br>
           <input type="checkbox" id="bahasa_inggris" name="matapelajaran" value="bahasa_inggris">
           <label for="bahasa_inggris">Bahasa Inggris</label><br>
           <input type="checkbox" id="bahasa_indonesia" name="matapelajaran" value="bahasa_indonesia">
           <label for="bahasa_indonesia">Bahasa Indonesia</label><br><br>

           <label>Pilih Jenis Kelamin:</label><br>
           <input type="radio" id="pria" name="gender" value="pria">
           <label for="pria">Pria</label><br>
           <input type="radio" id="wanita" name="gender" value="wanita">
           <label for="wanita">Wanita</label><br><br>

           <button type="submit">Kirim</button>
       </form>
   </body>
   </html>
   ```

#### **Diskusi dan Review:**

- **Mengapa `method="POST"` Lebih Disarankan untuk Data Sensitif?**
  - Diskusikan bagaimana metode `POST` mengirimkan data melalui body request, yang lebih aman dibandingkan `GET` yang mengirimkan data melalui URL.

- **Bagaimana Cara Membuat Form yang Lebih Mudah Digunakan oleh Semua Pengguna?**
  - Diskusikan pentingnya menggunakan `label` yang tepat dan elemen form yang terstruktur untuk meningkatkan aksesibilitas, terutama bagi pengguna yang menggunakan alat bantu.