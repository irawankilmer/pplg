### **Bab 10: Semantic HTML**

#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Memahami fungsi dan penggunaan elemen semantik dalam HTML.
- Mengidentifikasi perbedaan antara elemen semantik dan elemen non-semantik.
- Menggunakan elemen semantik seperti `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, dan `<footer>` untuk membuat struktur halaman web yang lebih bermakna dan mudah dipahami.

#### **Materi:**

1. **Apa Itu Elemen Semantik?**
   - **Definisi Elemen Semantik:**
     - Elemen semantik adalah elemen HTML yang tidak hanya menyajikan konten kepada pengguna tetapi juga memberikan makna atau arti yang jelas tentang isi konten tersebut kepada browser dan mesin pencari. Ini membuat struktur halaman web lebih terorganisir dan mudah diakses, baik untuk manusia maupun untuk mesin seperti search engine dan screen reader.
   - **Perbedaan dengan Elemen Non-Semantik:**
     - Elemen non-semantik seperti `<div>` dan `<span>` tidak memberikan informasi apa pun tentang isi kontennya. Sementara elemen semantik seperti `<header>`, `<footer>`, dan `<article>` secara eksplisit menjelaskan fungsi dan posisi konten dalam halaman web.

2. **Tag `<header>`**
   - **Apa Itu `<header>`?**
     - Tag `<header>` digunakan untuk mendefinisikan bagian header dari sebuah halaman atau bagian dari halaman. Header biasanya berisi elemen seperti logo, judul, dan navigasi utama. Dalam konteks web, ini mirip dengan bagian atas buku atau surat kabar yang berisi judul dan informasi pengantar.
   
   - **Kapan Menggunakan `<header>`?**
     - Kalian dapat menggunakan `<header>` di bagian atas halaman web atau di dalam elemen lain seperti `<article>` atau `<section>` untuk menunjukkan bagian pengantar atau judul dari konten tersebut.

   - **Contoh Penggunaan:**
     ```html
     <header>
         <h1>Selamat Datang di Situs Kelas XI PPLG 1</h1>
         <nav>
             <ul>
                 <li><a href="#home">Home</a></li>
                 <li><a href="#profil">Profil</a></li>
                 <li><a href="#kontak">Kontak</a></li>
             </ul>
         </nav>
     </header>
     ```

3. **Tag `<nav>`**
   - **Apa Itu `<nav>`?**
     - Tag `<nav>` digunakan untuk mendefinisikan bagian navigasi dari sebuah halaman web. Bagian ini biasanya berisi link atau menu yang membantu pengguna menavigasi ke bagian lain dari situs atau halaman tersebut.

   - **Kapan Menggunakan `<nav>`?**
     - Gunakan `<nav>` untuk menampung daftar link navigasi yang mengarah ke bagian utama dari situs kalian, seperti link ke halaman utama, profil, kontak, atau halaman lain yang penting.

   - **Contoh Penggunaan:**
     ```html
     <nav>
         <ul>
             <li><a href="#home">Home</a></li>
             <li><a href="#profil">Profil</a></li>
             <li><a href="#kontak">Kontak</a></li>
         </ul>
     </nav>
     ```

4. **Tag `<main>`**
   - **Apa Itu `<main>`?**
     - Tag `<main>` digunakan untuk mendefinisikan konten utama dari halaman web. Ini adalah bagian yang berisi informasi utama yang ingin kalian sampaikan kepada pengguna. Hanya boleh ada satu `<main>` dalam satu halaman web, dan ini tidak boleh mencakup konten berulang seperti sidebar, footer, atau navigasi.

   - **Kapan Menggunakan `<main>`?**
     - Gunakan `<main>` untuk menampung bagian utama dari konten halaman, seperti artikel, postingan blog, atau informasi utama yang ingin disampaikan.

   - **Contoh Penggunaan:**
     ```html
     <main>
         <h2>Profil Kelas XI PPLG 1</h2>
         <p>Kelas XI PPLG 1 adalah kelas yang penuh dengan siswa berbakat di bidang pemrograman dan desain web.</p>
     </main>
     ```

5. **Tag `<section>`**
   - **Apa Itu `<section>`?**
     - Tag `<section>` digunakan untuk membagi konten dalam halaman menjadi beberapa bagian yang logis. Setiap `<section>` biasanya memiliki tema atau topik tertentu, dan dapat berisi header, paragraf, gambar, atau elemen lainnya.

   - **Kapan Menggunakan `<section>`?**
     - Gunakan `<section>` untuk mengelompokkan konten yang memiliki kesamaan topik atau tema, seperti bagian berita terbaru, fitur utama, atau layanan yang ditawarkan.

   - **Contoh Penggunaan:**
     ```html
     <section id="berita">
         <h2>Berita Terbaru</h2>
         <article>
             <h3>Pemrograman Web</h3>
             <p>Siswa XI PPLG 1 baru saja menyelesaikan proyek pemrograman web pertama mereka.</p>
         </article>
         <article>
             <h3>Desain Grafis</h3>
             <p>Kelas telah memulai modul baru tentang desain grafis menggunakan Adobe Photoshop.</p>
         </article>
     </section>
     ```

6. **Tag `<article>`**
   - **Apa Itu `<article>`?**
     - Tag `<article>` digunakan untuk mendefinisikan bagian konten independen yang bisa berdiri sendiri dan sering kali bisa dibagikan atau dipindahkan ke halaman lain tanpa kehilangan konteks. Contohnya adalah artikel berita, postingan blog, atau cerita individu dalam halaman web.

   - **Kapan Menggunakan `<article>`?**
     - Gunakan `<article>` untuk konten yang memiliki arti lengkap dan bisa dibaca terpisah dari konten lain, seperti artikel, postingan blog, atau berita.

   - **Contoh Penggunaan:**
     ```html
     <article>
         <h2>Pameran Teknologi Kelas XI PPLG 1</h2>
         <p>Kelas XI PPLG 1 akan mengadakan pameran teknologi untuk menampilkan proyek mereka dalam pemrograman dan desain.</p>
     </article>
     ```

7. **Tag `<footer>`**
   - **Apa Itu `<footer>`?**
     - Tag `<footer>` digunakan untuk mendefinisikan bagian bawah atau penutup dari halaman web atau bagian dari halaman. Biasanya berisi informasi seperti hak cipta, link tambahan, atau informasi kontak.

   - **Kapan Menggunakan `<footer>`?**
     - Gunakan `<footer>` untuk menampung informasi penutup atau informasi tambahan yang biasanya ditempatkan di bagian bawah halaman.

   - **Contoh Penggunaan:**
     ```html
     <footer>
         <p>&copy; 2024 Kelas XI PPLG 1. Semua hak dilindungi.</p>
         <nav>
             <ul>
                 <li><a href="#home">Home</a></li>
                 <li><a href="#profil">Profil</a></li>
                 <li><a href="#kontak">Kontak</a></li>
             </ul>
         </nav>
     </footer>
     ```

#### **Praktikum Lengkap:**

1. **Latihan 1: Membuat Struktur Halaman Web dengan Elemen Semantik**
   - Cobalah buat halaman web sederhana yang mencakup header, navigasi, konten utama, beberapa bagian yang berbeda dengan `<section>`, sebuah artikel, dan footer.

   **Contoh Praktik:**
   ```html
   <!DOCTYPE html>
   <html>
   <head>
       <title>Situs Kelas XI PPLG 1</title>
   </head>
   <body>
       <header>
           <h1>Selamat Datang di Situs Kelas XI PPLG 1</h1>
           <nav>
               <ul>
                   <li><a href="#home">Home</a></li>
                   <li><a href="#profil">Profil</a></li>
                   <li><a href="#kontak">Kontak</a></li>
               </ul>
           </nav>
       </header>

       <main>
           <section id="profil">
               <h2>Profil Kelas</h2>
               <p>Kelas XI PPLG 1 adalah kelas yang berfokus pada pemrograman dan desain web.</p>
           </section>

           <section id="berita">
               <h2>Berita Terbaru</h2>
               <article>
                   <h3>Pemrograman Web</h3>
                   <p>Siswa XI PPLG 1 baru saja menyelesaikan proyek pemrograman web pertama mereka.</p>
               </article>
               <article>
                   <h3>Desain Grafis</h3>
                   <p>Kelas telah memulai modul baru tentang desain grafis menggunakan Adobe Photoshop.</p>
               </article>
           </section>
       </main>

       <footer>
           <p>&copy; 2024 Kelas XI PPLG 1. Semua hak dilindungi.</p>
           <nav>
               <ul>
                   <li><a href="#home">Home</a></li>
                   <li><a href="#profil">

Profil</a></li>
                   <li><a href="#kontak">Kontak</a></li>
               </ul>
           </nav>
       </footer>
   </body>
   </html>
   ```

2. **Latihan 2: Menggunakan `<section>` dan `<article>` untuk Konten Berita**
   - Buat halaman yang menampilkan beberapa artikel berita, masing-masing dalam `<article>` yang berbeda, dan letakkan semua artikel tersebut dalam `<section>` yang sama.

   **Contoh Praktik:**
   ```html
   <!DOCTYPE html>
   <html>
   <head>
       <title>Berita XI PPLG 1</title>
   </head>
   <body>
       <header>
           <h1>Berita Terbaru dari Kelas XI PPLG 1</h1>
       </header>

       <main>
           <section id="berita">
               <h2>Berita Terkini</h2>
               <article>
                   <h3>Proyek Web Selesai</h3>
                   <p>Siswa XI PPLG 1 berhasil menyelesaikan proyek pemrograman web yang menantang.</p>
               </article>
               <article>
                   <h3>Pelatihan Desain Grafis</h3>
                   <p>Kelas telah memulai pelatihan intensif dalam desain grafis, bekerja dengan perangkat lunak profesional.</p>
               </article>
           </section>
       </main>

       <footer>
           <p>&copy; 2024 Kelas XI PPLG 1. Informasi dan berita terbaru untuk Anda.</p>
       </footer>
   </body>
   </html>
   ```

#### **Diskusi dan Review:**

- **Mengapa Penggunaan Elemen Semantik Itu Penting?**
  - Diskusikan bagaimana elemen semantik membuat halaman web lebih terstruktur, memudahkan mesin pencari dalam mengindeks konten, dan meningkatkan aksesibilitas bagi pengguna dengan kebutuhan khusus.

- **Bagaimana Cara Menggunakan Elemen Semantik untuk Meningkatkan SEO?**
  - Diskusikan bagaimana elemen seperti `<header>`, `<nav>`, dan `<main>` membantu mesin pencari memahami konten halaman dan meningkatkan visibilitas halaman di hasil pencarian.