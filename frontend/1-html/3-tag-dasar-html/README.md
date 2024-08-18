### **Bab 3: Basic Tags HTML**

#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Memahami fungsi dan penggunaan tag dasar dalam HTML.
- Mengidentifikasi peran setiap tag dalam struktur dasar halaman web.
- Menggunakan tag-tag dasar untuk membuat kerangka dasar sebuah halaman web.

#### **Materi:**

1. **Tag `<html>`**
   - **Apa itu `<html>`?**
     - Tag `<html>` adalah elemen dasar dalam setiap dokumen HTML. Tag ini berfungsi sebagai "kerangka utama" yang membungkus semua konten dalam sebuah halaman web. Bayangkan tag `<html>` seperti gedung sekolah yang menampung semua ruangan, mulai dari kelas, kantin, hingga ruang guru. Semua elemen HTML lainnya, seperti teks, gambar, dan video, harus berada di dalam tag `<html>` ini.
   
   - **Mengapa `<html>` Penting?**
     - Tanpa tag `<html>`, browser tidak akan tahu bahwa dokumen yang sedang kalian buat adalah halaman web yang perlu di-render. Tag ini juga menjadi titik awal bagi semua elemen HTML lainnya untuk diatur dalam struktur yang logis.

   - **Contoh Penggunaan:**
     ```html
     <html>
        <!-- Semua konten HTML kalian ada di sini -->
     </html>
     ```

   - **Apa yang Terjadi Jika Tag `<html>` Tidak Ada?**
     - Jika kalian tidak menggunakan tag `<html>`, browser mungkin masih akan menampilkan konten kalian, tapi ini bukan cara yang benar untuk menulis HTML. Ibaratnya, ini seperti membangun rumah tanpa fondasi—mungkin bisa berdiri, tapi sangat rentan terhadap kerusakan.

2. **Tag `<head>`**
   - **Apa itu `<head>`?**
     - Tag `<head>` adalah bagian dari dokumen HTML yang digunakan untuk menyimpan informasi meta (informasi tentang halaman itu sendiri) dan link ke sumber daya eksternal seperti file CSS. Kalian bisa bayangkan tag `<head>` seperti kepala sekolah yang mengurus segala sesuatu yang penting di balik layar, tetapi tidak langsung berhubungan dengan siswa.

   - **Mengapa `<head>` Penting?**
     - Informasi yang ada di dalam tag `<head>` sangat penting untuk pengaturan halaman web kalian, meskipun konten di dalamnya tidak terlihat oleh pengguna. Misalnya, tag `<title>` yang ada di dalam `<head>` menentukan judul halaman yang muncul di tab browser.

   - **Contoh Penggunaan:**
     ```html
     <html>
     <head>
         <title>Judul Halaman Web</title>
     </head>
     </html>
     ```

   - **Apa yang Biasanya Dimasukkan ke dalam `<head>`?**
     - Selain `<title>`, kalian juga bisa menambahkan meta tag seperti `<meta charset="UTF-8">` untuk mengatur karakter encoding, atau `<link rel="stylesheet" href="styles.css">` untuk menghubungkan halaman HTML kalian dengan file CSS eksternal.

3. **Tag `<body>`**
   - **Apa itu `<body>`?**
     - Tag `<body>` adalah bagian dari dokumen HTML yang menampung semua konten yang akan dilihat dan diinteraksi oleh pengguna. Mulai dari teks, gambar, video, hingga form input, semuanya diletakkan di dalam tag `<body>`. Kalau tadi `<html>` itu gedung sekolah, maka `<body>` adalah seluruh ruangan dan fasilitas yang kalian gunakan sehari-hari di dalam gedung itu.

   - **Mengapa `<body>` Penting?**
     - Tanpa `<body>`, kalian tidak akan bisa menampilkan apa pun di halaman web. Semua elemen visual yang dilihat pengguna harus diletakkan di dalam tag `<body>` ini.

   - **Contoh Penggunaan:**
     ```html
     <html>
     <head>
         <title>Judul Halaman Web</title>
     </head>
     <body>
         <h1>Selamat Datang di Halaman Web Saya</h1>
         <p>Ini adalah paragraf pertama saya.</p>
     </body>
     </html>
     ```

   - **Apa yang Bisa Dimasukkan ke dalam `<body>`?**
     - Kalian bisa memasukkan berbagai elemen seperti heading (`<h1>`, `<h2>`), paragraf (`<p>`), gambar (`<img>`), link (`<a>`), dan banyak lagi.

4. **Tag `<title>`**
   - **Apa itu `<title>`?**
     - Tag `<title>` menentukan judul dari halaman web kalian, yang akan muncul di tab browser. Ini adalah bagian penting dari `<head>`. Kalian bisa bayangkan tag `<title>` sebagai judul buku yang kalian baca—meskipun judul ini tidak ada di setiap halaman buku, itu tetap memberikan informasi penting tentang isi buku tersebut.

   - **Mengapa `<title>` Penting?**
     - Judul halaman ini sangat penting, karena memberikan informasi singkat tentang apa yang ada di halaman tersebut. Selain itu, `<title>` juga digunakan oleh mesin pencari seperti Google untuk menentukan bagaimana halaman kalian muncul di hasil pencarian.

   - **Contoh Penggunaan:**
     ```html
     <html>
     <head>
         <title>Halaman Web Pertama Saya</title>
     </head>
     <body>
         <h1>Halo, Dunia!</h1>
         <p>Selamat datang di halaman web pertama saya.</p>
     </body>
     </html>
     ```

   - **Apa yang Harus Diperhatikan Saat Menulis `<title>`?**
     - Pastikan judul kalian singkat dan relevan dengan konten halaman. Jangan lupa bahwa ini juga yang akan dilihat orang ketika mereka bookmark halaman kalian, jadi buatlah sejelas mungkin.

#### **Praktikum Lengkap:**

1. **Latihan 1: Membuat Struktur Dasar HTML**
   - Buatlah halaman HTML sederhana yang menggunakan semua tag dasar (`<html>`, `<head>`, `<body>`, dan `<title>`).

   **Kode Contoh:**
   ```html
   <!DOCTYPE html>
   <html>
   <head>
       <title>Halaman Web Kelas XI PPLG 1</title>
   </head>
   <body>
       <h1>Halo, Dunia!</h1>
       <p>Ini adalah halaman web pertama yang dibuat oleh Anggie Maryani dari kelas XI PPLG 1.</p>
   </body>
   </html>
   ```

2. **Latihan 2: Menambahkan Meta Tag dan Link CSS**
   - Perluas kode HTML di atas dengan menambahkan meta tag untuk pengaturan karakter dan link ke file CSS eksternal.

   **Kode Contoh:**
   ```html
   <!DOCTYPE html>
   <html>
   <head>
       <meta charset="UTF-8">
       <title>Halaman Web Kelas XI PPLG 1</title>
       <link rel="stylesheet" href="styles.css">
   </head>
   <body>
       <h1>Halo, Dunia!</h1>
       <p>Ini adalah halaman web pertama yang dibuat oleh Anwar Nurjaman dari kelas XI PPLG 1.</p>
   </body>
   </html>
   ```

#### **Diskusi dan Review:**

- **Mengapa Struktur HTML Penting?**
  - **Diskusi:** Struktur HTML yang baik memastikan bahwa halaman web kalian dapat dibaca dan di-render dengan benar oleh semua browser. Selain itu, struktur yang jelas dan terorganisir juga memudahkan kalian untuk mengelola dan memperbarui konten halaman di masa depan.

- **Apa Peran `<head>` dan `<body>` dalam Sebuah Halaman Web?**
  - **Diskusi:** `<head>` menyimpan semua informasi penting yang dibutuhkan untuk pengaturan halaman, sementara `<body>` adalah tempat kalian menempatkan semua konten yang ingin ditampilkan kepada pengguna.