### **Bab 4: Text Formatting HTML**

#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Memahami fungsi dan penggunaan tag HTML untuk memformat teks.
- Mengidentifikasi peran setiap tag dalam memperindah dan mengatur teks di halaman web.
- Menggunakan tag-tag ini untuk membuat halaman web yang lebih terstruktur dan menarik.

#### **Materi:**

1. **Tag `<h1>` hingga `<h6>`**
   - **Apa Itu Tag `<h1>` hingga `<h6>`?**
     - Tag `<h1>` hingga `<h6>` digunakan untuk membuat heading atau judul di halaman web. Kalau diibaratkan dengan sekolah, `<h1>` adalah seperti papan nama besar di gerbang sekolah yang menunjukkan nama sekolah, sementara `<h6>` adalah tulisan kecil di papan pengumuman di dalam kelas. Heading `<h1>` adalah yang paling besar dan penting, sedangkan `<h6>` adalah yang paling kecil.
   
   - **Mengapa Heading Penting?**
     - Heading membantu mengatur konten dan membuatnya lebih mudah dibaca. Ketika kalian menulis artikel panjang atau membuat halaman web dengan banyak informasi, heading ini membantu memecah konten menjadi bagian-bagian yang lebih mudah dipahami, seperti judul dan subjudul di buku pelajaran kalian.

   - **Contoh Penggunaan:**
     ```html
     <h1>Judul Utama</h1>
     <h2>Sub Judul</h2>
     <h3>Sub-sub Judul</h3>
     ```

   - **Kapan Menggunakan Setiap Jenis Heading?**
     - Gunakan `<h1>` untuk judul utama halaman, seperti judul proyek kalian. Gunakan `<h2>` hingga `<h6>` untuk subjudul atau bagian yang lebih spesifik, seperti judul bab atau sub bab dalam buku.

2. **Tag `<p>`**
   - **Apa Itu Tag `<p>`?**
     - Tag `<p>` digunakan untuk membuat paragraf teks di halaman web. Anggap saja `<p>` seperti paragraf dalam esai atau laporan yang kalian buat di sekolah. Setiap kali kalian ingin memulai paragraf baru, gunakan tag `<p>`.

   - **Mengapa Paragraf Penting?**
     - Paragraf membantu memecah teks panjang menjadi bagian-bagian yang lebih mudah dicerna. Ini membantu pembaca untuk mengikuti alur cerita atau penjelasan kalian dengan lebih baik.

   - **Contoh Penggunaan:**
     ```html
     <p>Ini adalah paragraf pertama yang menjelaskan tentang pentingnya HTML dalam pembuatan halaman web.</p>
     <p>Ini adalah paragraf kedua yang memberikan contoh penggunaan tag HTML dalam memformat teks.</p>
     ```

   - **Tips Menulis Paragraf:**
     - Setiap paragraf harus berfokus pada satu ide utama. Ini seperti ketika kalian menulis esai, pastikan setiap paragraf memiliki tujuan yang jelas dan mendukung keseluruhan argumen atau cerita kalian.

3. **Tag `<br>`**
   - **Apa Itu Tag `<br>`?**
     - Tag `<br>` digunakan untuk menyisipkan baris baru di teks tanpa memulai paragraf baru. Kalau kalian butuh pindah ke baris berikutnya seperti saat menulis puisi atau daftar di tengah paragraf, gunakan `<br>`. Di sekolah, ini seperti memulai baris baru tanpa mengganti paragraf saat menulis catatan.

   - **Contoh Penggunaan:**
     ```html
     <p>Baris pertama.<br>Baris kedua setelah pindah baris dengan <br> tanpa memulai paragraf baru.</p>
     ```

   - **Kapan Menggunakan `<br>`?**
     - Gunakan `<br>` saat kalian butuh memisahkan teks dengan baris baru tapi tetap dalam satu paragraf, misalnya saat membuat alamat atau menulis bait puisi.

4. **Tag `<hr>`**
   - **Apa Itu Tag `<hr>`?**
     - Tag `<hr>` digunakan untuk membuat garis horizontal yang memisahkan konten di halaman web. Ini bisa diibaratkan seperti pembatas halaman di buku atau garis di tengah papan tulis yang memisahkan materi berbeda. 

   - **Mengapa `<hr>` Penting?**
     - Garis horizontal ini berguna untuk memisahkan bagian-bagian konten yang berbeda, seperti memisahkan bab atau topik dalam artikel panjang. Ini membantu visual pembaca dalam memahami kapan satu topik berakhir dan topik lain dimulai.

   - **Contoh Penggunaan:**
     ```html
     <h2>Bagian Pertama</h2>
     <p>Konten untuk bagian pertama.</p>
     <hr>
     <h2>Bagian Kedua</h2>
     <p>Konten untuk bagian kedua.</p>
     ```

   - **Tips Menggunakan `<hr>`:**
     - Jangan terlalu sering menggunakan `<hr>`. Gunakan hanya saat benar-benar perlu memisahkan bagian besar dalam konten kalian.

5. **Tag `<strong>` dan `<em>`**
   - **Apa Itu Tag `<strong>` dan `<em>`?**
     - Tag `<strong>` digunakan untuk menebalkan teks, memberikan penekanan kuat, sementara `<em>` digunakan untuk memiringkan teks, memberikan penekanan lebih lembut atau berbeda. Bayangkan `<strong>` seperti menyorot bagian penting di catatan pelajaran kalian dengan spidol tebal, dan `<em>` seperti memberi catatan tambahan dengan huruf miring.

   - **Mengapa `<strong>` dan `<em>` Penting?**
     - Penekanan ini membantu menarik perhatian pembaca ke bagian tertentu dari teks yang penting atau memerlukan perhatian lebih. Ini seperti menyoroti poin-poin penting saat kalian belajar untuk ujian.

   - **Contoh Penggunaan:**
     ```html
     <p><strong>Penting:</strong> Jangan lupa untuk selalu menutup tag HTML dengan benar.</p>
     <p>Penggunaan tag <em>italic</em> bisa menambahkan variasi dalam gaya teks kalian.</p>
     ```

   - **Kapan Menggunakan `<strong>` dan `<em>`?**
     - Gunakan `<strong>` untuk informasi yang sangat penting yang perlu diperhatikan oleh pembaca. Gunakan `<em>` untuk kata atau frasa yang ingin kalian tekankan secara halus, mungkin untuk memberikan nuansa atau penekanan berbeda.

#### **Praktikum Lengkap:**

1. **Latihan 1: Membuat Struktur Heading**
   - Buatlah halaman HTML dengan beberapa heading yang menunjukkan struktur seperti judul besar dan subjudul kecil.

   **Kode Contoh:**
   ```html
   <!DOCTYPE html>
   <html>
   <head>
       <title>Struktur Heading</title>
   </head>
   <body>
       <h1>Judul Utama</h1>
       <h2>Sub Judul 1</h2>
       <h3>Sub-sub Judul 1</h3>
       <h2>Sub Judul 2</h2>
       <h3>Sub-sub Judul 2</h3>
   </body>
   </html>
   ```

2. **Latihan 2: Memformat Paragraf dan Menambahkan Garis Pemisah**
   - Buat halaman HTML yang memiliki beberapa paragraf dengan garis pemisah di antaranya.

   **Kode Contoh:**
   ```html
   <!DOCTYPE html>
   <html>
   <head>
       <title>Paragraf dan Garis Pemisah</title>
   </head>
   <body>
       <p>Ini adalah paragraf pertama yang memberikan pengenalan tentang topik.</p>
       <hr>
       <p>Ini adalah paragraf kedua yang menjelaskan lebih lanjut tentang topik.</p>
   </body>
   </html>
   ```

3. **Latihan 3: Menyoroti dan Menekankan Teks**
   - Buat halaman HTML yang menggunakan `<strong>` dan `<em>` untuk menyoroti bagian penting dan memberikan penekanan berbeda pada teks.

   **Kode Contoh:**
   ```html
   <!DOCTYPE html>
   <html>
   <head>
       <title>Menyoroti Teks</title>
   </head>
   <body>
       <p><strong>Penting:</strong> Selalu perhatikan detail saat menulis kode HTML.</p>
       <p>Gunakan <em>italic</em> untuk memberikan penekanan yang lebih halus.</p>
   </body>
   </html>
   ```

#### **Diskusi dan Review:**

- **Mengapa Memformat Teks Itu Penting?**
  - **Diskusi:** Memformat teks dengan benar membantu pembaca dalam memahami konten kalian. Seperti di buku pelajaran, judul dan subjudul membantu membagi materi menjadi bagian-bagian yang lebih mudah dicerna.

- **Kapan Harus Menggunakan `<strong>` dan `<em>`?**
  - **Diskusi:** Gunakan `<strong>` untuk informasi penting yang ingin kalian tekankan kepada pembaca. Gunakan `<em>` ketika kalian ingin memberikan penekanan tambahan tanpa terlalu menonjolkan.