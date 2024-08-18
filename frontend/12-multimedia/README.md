### **Bab 12: Multimedia dalam HTML**

#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Memahami cara menambahkan elemen multimedia seperti audio dan video ke dalam halaman web menggunakan HTML.
- Menggunakan atribut dan elemen terkait untuk mengontrol pemutaran media, seperti `controls`, `autoplay`, dan `<source>`.
- Menyajikan konten multimedia yang responsif dan kompatibel dengan berbagai perangkat dan browser.

#### **Materi:**

1. **Tag `<audio>`**
   - **Apa Itu `<audio>`?**
     - Tag `<audio>` digunakan untuk menyematkan file audio di halaman web. Dengan tag ini, kalian bisa menambahkan musik, podcast, atau efek suara langsung ke dalam halaman web kalian.

   - **Atribut Penting pada `<audio>`:**
     - **`controls`**: Menambahkan kontrol pemutar seperti play, pause, dan volume, sehingga pengguna dapat mengontrol pemutaran audio.
     - **`autoplay`**: Memulai pemutaran audio secara otomatis ketika halaman dimuat. Ini harus digunakan dengan hati-hati karena bisa mengganggu pengguna.
     - **`loop`**: Memutar audio secara berulang tanpa henti.
     - **`muted`**: Memulai pemutaran audio dalam keadaan mute.
     - **`preload`**: Mengontrol bagaimana browser memuat file audio (nilai umum: `none`, `metadata`, `auto`).

   - **Tag `<source>` untuk Format yang Berbeda:**
     - Tag `<source>` digunakan di dalam `<audio>` untuk menyertakan berbagai format file audio. Ini penting karena browser yang berbeda mungkin mendukung format audio yang berbeda (misalnya, MP3, Ogg, atau WAV).

   - **Contoh Penggunaan:**
     ```html
     <audio controls>
         <source src="audio/music.mp3" type="audio/mpeg">
         <source src="audio/music.ogg" type="audio/ogg">
         Browser Anda tidak mendukung elemen audio.
     </audio>
     ```
     - **Penjelasan:**
       - Jika browser tidak mendukung format MP3, ia akan mencoba format Ogg. Jika keduanya tidak didukung, teks fallback akan ditampilkan.

2. **Tag `<video>`**
   - **Apa Itu `<video>`?**
     - Tag `<video>` digunakan untuk menyematkan file video di halaman web. Dengan tag ini, kalian bisa menambahkan video edukasi, presentasi, atau konten visual lainnya.

   - **Atribut Penting pada `<video>`:**
     - **`controls`**: Menambahkan kontrol pemutar video seperti play, pause, volume, dan fullscreen.
     - **`autoplay`**: Memulai pemutaran video secara otomatis ketika halaman dimuat. Ini harus digunakan dengan hati-hati.
     - **`loop`**: Memutar video secara berulang tanpa henti.
     - **`muted`**: Memulai pemutaran video dalam keadaan mute.
     - **`poster`**: Menentukan gambar yang akan ditampilkan sebelum video diputar.
     - **`width` dan `height`**: Menentukan dimensi video. Ini membantu memastikan video sesuai dengan tata letak halaman.

   - **Tag `<source>` untuk Format yang Berbeda:**
     - Seperti pada audio, tag `<source>` di dalam `<video>` digunakan untuk menyertakan berbagai format file video. Format umum yang didukung termasuk MP4, WebM, dan Ogg.

   - **Contoh Penggunaan:**
     ```html
     <video controls width="640" height="360" poster="images/poster.jpg">
         <source src="video/movie.mp4" type="video/mp4">
         <source src="video/movie.ogg" type="video/ogg">
         Browser Anda tidak mendukung elemen video.
     </video>
     ```
     - **Penjelasan:**
       - Gambar poster akan ditampilkan sebelum video diputar. Jika MP4 tidak didukung, browser akan mencoba format Ogg.

3. **Atribut dan Elemen Pendukung Lainnya:**
   - **`controlsList`**: Digunakan untuk mengatur kontrol tambahan seperti kemampuan untuk mengunduh video (`nodownload`), mematikan kontrol default (`nofullscreen`), atau menyembunyikan bar waktu (`noremoteplayback`).
   - **`track`**: Digunakan untuk menyertakan subtitle atau teks lain yang relevan dalam video. Ini sangat penting untuk aksesibilitas dan membuat konten video lebih inklusif.
   
   **Contoh Penggunaan `track`:**
   ```html
   <video controls>
       <source src="video/movie.mp4" type="video/mp4">
       <track src="subtitles_en.vtt" kind="subtitles" srclang="en" label="English">
       Browser Anda tidak mendukung elemen video.
   </video>
   ```

4. **Praktik Terbaik dalam Penggunaan Multimedia:**
   - **Format Video dan Audio yang Berbeda:**
     - Selalu sertakan beberapa format video dan audio untuk memastikan kompatibilitas dengan berbagai browser. Format yang umum digunakan:
       - **Audio**: MP3, Ogg, WAV
       - **Video**: MP4, WebM, Ogg
   - **Optimasi Ukuran File:**
     - Pastikan ukuran file multimedia dioptimalkan untuk web agar halaman tetap cepat dimuat. Gunakan kompresi dan resolusi yang sesuai dengan kebutuhan konten.
   - **Aksesibilitas:**
     - Sertakan `track` untuk subtitle dan gunakan `alt` atau fallback text untuk memastikan konten multimedia dapat diakses oleh semua pengguna.

5. **Contoh Lengkap Implementasi Multimedia:**
   - **Contoh Halaman dengan Audio dan Video:**
   ```html
   <!DOCTYPE html>
   <html lang="id">
   <head>
       <meta charset="UTF-8">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <title>Multimedia dalam HTML</title>
   </head>
   <body>
       <h1>Belajar dengan Multimedia di Kelas XI PPLG 1</h1>

       <h2>Contoh Audio</h2>
       <p>Dengarkan audio berikut untuk memahami lebih lanjut tentang materi:</p>
       <audio controls>
           <source src="audio/lesson.mp3" type="audio/mpeg">
           <source src="audio/lesson.ogg" type="audio/ogg">
           Browser Anda tidak mendukung elemen audio.
       </audio>

       <h2>Contoh Video</h2>
       <p>Tonton video ini untuk melihat contoh penerapan pemrograman web:</p>
       <video controls width="640" height="360" poster="images/poster.jpg">
           <source src="video/lesson.mp4" type="video/mp4">
           <source src="video/lesson.webm" type="video/webm">
           <source src="video/lesson.ogg" type="video/ogg">
           <track src="subtitles_en.vtt" kind="subtitles" srclang="en" label="English">
           Browser Anda tidak mendukung elemen video.
       </video>
   </body>
   </html>
   ```

#### **Praktikum Lengkap:**

1. **Latihan 1: Menambahkan Audio ke Halaman Web**
   - Buatlah halaman HTML yang menampilkan kontrol audio dengan beberapa format file yang berbeda untuk memastikan kompatibilitas.

   **Contoh Praktik:**
   ```html
   <!DOCTYPE html>
   <html lang="id">
   <head>
       <meta charset="UTF-8">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <title>Contoh Audio</title>
   </head>
   <body>
       <h1>Dengarkan Audio</h1>
       <audio controls>
           <source src="audio/contoh.mp3" type="audio/mpeg">
           <source src="audio/contoh.ogg" type="audio/ogg">
           Browser Anda tidak mendukung elemen audio.
       </audio>
   </body>
   </html>
   ```

2. **Latihan 2: Menambahkan Video dengan Poster dan Subtitles**
   - Buatlah halaman HTML yang menampilkan video dengan gambar poster dan subtitle yang mendukung aksesibilitas.

   **Contoh Praktik:**
   ```html
   <!DOCTYPE html>
   <html lang="id">
   <head>
       <meta charset="UTF-8">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <title>Contoh Video</title>
   </head>
   <body>
       <h1>Tonton Video Ini</h1>
       <video controls width="640" height="360" poster="images/poster.jpg">
           <source src="video/contoh.mp4" type="video/mp4">
           <source src="video/contoh.webm" type="video/webm">
           <track src="subtitles_id.vtt" kind="subtitles" srclang="id" label="Bahasa Indonesia">
           Browser Anda tidak mendukung elemen video.
       </video>
   </body>
   </html>
   ```

#### **Diskusi dan Review:**

- **Mengapa Penting Menyediakan Berbagai Format untuk Audio dan Video?**
  - Diskusikan bagaimana menyediakan berbagai format file membantu memastikan

 bahwa konten multimedia dapat diakses di berbagai browser dan perangkat.

- **Bagaimana Cara Menggunakan Konten Multimedia dengan Bertanggung Jawab?**
  - Diskusikan praktik terbaik dalam penggunaan multimedia, seperti menghindari autoplay yang mengganggu dan memastikan bahwa semua pengguna, termasuk mereka yang menggunakan perangkat bantu, dapat mengakses konten multimedia dengan mudah.