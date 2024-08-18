### **Bab 7: Images dalam HTML**

#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Memahami fungsi dan penggunaan tag `<img>` untuk menampilkan gambar di halaman web.
- Mengidentifikasi peran atribut `src`, `alt`, `width`, dan `height` dalam menentukan sumber dan tampilan gambar.
- Menggunakan tag `<img>` untuk menambahkan gambar ke halaman web dengan ukuran dan deskripsi yang tepat.

#### **Materi:**

1. **Tag `<img>` dan Atribut `src`**
   - **Apa Itu Tag `<img>`?**
     - Tag `<img>` digunakan untuk menampilkan gambar di halaman web. Tag ini tidak memiliki penutup (self-closing), yang berarti kalian hanya perlu menggunakan tag pembuka `<img>` saja. Bayangkan tag `<img>` seperti jendela di mana kalian bisa melihat gambar yang ada di luar ruangan—hanya saja, kali ini gambarnya ada di halaman web kalian.

   - **Atribut `src`: Menentukan Sumber Gambar**
     - Atribut `src` (source) pada tag `<img>` menentukan lokasi file gambar yang ingin kalian tampilkan. Ini seperti alamat atau jalur menuju gambar yang tersimpan, baik di komputer kalian atau di internet.

   - **Contoh Penggunaan:**
     ```html
     <img src="gambar/sekolah.jpg" alt="Gambar Sekolah">
     ```
     Di contoh ini, gambar yang terletak di folder "gambar" dengan nama file "sekolah.jpg" akan ditampilkan di halaman web. Jika gambar tersebut berada di internet, kalian bisa menuliskan URL lengkapnya.

2. **Atribut `alt`: Menambahkan Deskripsi Gambar**
   - **Apa Itu Atribut `alt`?**
     - Atribut `alt` digunakan untuk memberikan deskripsi teks alternatif yang akan ditampilkan jika gambar tidak bisa dimuat atau diakses oleh pengguna. Deskripsi ini juga membantu pengguna dengan keterbatasan penglihatan yang menggunakan screen reader untuk memahami konten gambar.

   - **Mengapa Atribut `alt` Penting?**
     - Selain membantu dalam aksesibilitas, `alt` juga penting untuk SEO (Search Engine Optimization). Mesin pencari menggunakan deskripsi ini untuk memahami konten gambar di halaman kalian.

   - **Contoh Penggunaan:**
     ```html
     <img src="gambar/sekolah.jpg" alt="Foto gedung sekolah">
     ```

   - **Tips Menulis `alt`:**
     - Pastikan deskripsi `alt` singkat namun cukup informatif untuk menjelaskan apa yang ada di gambar.

3. **Atribut `width` dan `height`: Mengatur Ukuran Gambar**
   - **Mengapa Mengatur Ukuran Gambar?**
     - Mengatur ukuran gambar membantu memastikan gambar tidak terlalu besar atau kecil untuk tampil di halaman web. Ini juga membantu menjaga konsistensi tata letak dan membuat halaman lebih cepat diakses, terutama jika gambar dioptimalkan dengan baik.

   - **Cara Menggunakan Atribut `width` dan `height`:**
     - Atribut `width` dan `height` digunakan untuk menentukan lebar dan tinggi gambar dalam satuan piksel. Misalnya, jika kalian ingin gambar tampil dengan lebar 300 piksel dan tinggi 200 piksel, kalian bisa mengaturnya dengan atribut ini.

   - **Contoh Penggunaan:**
     ```html
     <img src="gambar/sekolah.jpg" alt="Foto gedung sekolah" width="300" height="200">
     ```

   - **Tips Mengatur Ukuran Gambar:**
     - Pastikan kalian menjaga proporsi gambar dengan benar agar gambar tidak terlihat terdistorsi. Jika kalian mengatur hanya satu dari atribut `width` atau `height`, proporsi gambar akan tetap terjaga secara otomatis.

4. **Contoh Penggunaan dengan Data Siswa**
   - **Menambahkan Foto Siswa di Halaman Profil**
     - Misalkan kalian membuat halaman profil untuk siswa di kelas XI PPLG 1 dan ingin menampilkan foto siswa tersebut. Kalian bisa menggunakan tag `<img>` untuk menampilkan foto bersama dengan deskripsi alternatif yang sesuai.

   **Contoh Penggunaan:**
   ```html
   <h2>Profil Siswa: Alya Salsabila</h2>
   <img src="foto/alya_salsabila.jpg" alt="Foto Alya Salsabila" width="200" height="300">
   <p>Alya Salsabila adalah siswa kelas XI PPLG 1 yang memiliki minat besar dalam desain grafis.</p>
   ```

#### **Praktikum Lengkap:**

1. **Latihan 1: Menambahkan Gambar dengan `src` dan `alt`**
   - Buatlah halaman HTML yang menampilkan gambar dengan deskripsi alternatif yang sesuai.

   **Kode Contoh:**
   ```html
   <!DOCTYPE html>
   <html>
   <head>
       <title>Gambar Sekolah</title>
   </head>
   <body>
       <img src="gambar/sekolah.jpg" alt="Foto gedung sekolah">
   </body>
   </html>
   ```

2. **Latihan 2: Mengatur Ukuran Gambar dengan `width` dan `height`**
   - Buatlah halaman HTML yang menampilkan gambar dengan ukuran yang diatur menggunakan atribut `width` dan `height`.

   **Kode Contoh:**
   ```html
   <!DOCTYPE html>
   <html>
   <head>
       <title>Gambar dengan Ukuran Tertentu</title>
   </head>
   <body>
       <img src="gambar/sekolah.jpg" alt="Foto gedung sekolah" width="400" height="300">
   </body>
   </html>
   ```

3. **Latihan 3: Menambahkan Foto Siswa dengan Deskripsi**
   - Buatlah halaman HTML yang menampilkan foto siswa dari kelas XI PPLG 1 dengan deskripsi yang sesuai.

   **Kode Contoh:**
   ```html
   <!DOCTYPE html>
   <html>
   <head>
       <title>Profil Siswa: Alya Salsabila</title>
   </head>
   <body>
       <h2>Profil Siswa: Alya Salsabila</h2>
       <img src="foto/alya_salsabila.jpg" alt="Foto Alya Salsabila" width="200" height="300">
       <p>Alya Salsabila adalah siswa kelas XI PPLG 1 yang memiliki minat besar dalam desain grafis.</p>
   </body>
   </html>
   ```

#### **Diskusi dan Review:**

- **Mengapa `alt` Itu Penting?**
  - **Diskusi:** `alt` membantu aksesibilitas dengan memberikan deskripsi gambar untuk pengguna yang tidak dapat melihat gambar. Ini juga meningkatkan SEO dengan memberikan informasi kepada mesin pencari tentang isi gambar.

- **Bagaimana Cara Memastikan Gambar Tidak Terlihat Terdistorsi?**
  - **Diskusi:** Pastikan untuk menjaga proporsi gambar dengan mengatur hanya satu dari atribut `width` atau `height`, atau menghitung ulang kedua atribut tersebut untuk menjaga rasio asli gambar.