### **Bab 16: Positioning**

#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Memahami berbagai jenis positioning dalam CSS dan bagaimana masing-masing bekerja.
- Menggunakan positioning untuk mengontrol penempatan elemen-elemen di halaman web.
- Menerapkan teknik positioning untuk membuat tata letak yang lebih dinamis dan responsif.

#### **Materi:**

1. **Apa Itu CSS Positioning?**
   - **Definisi Positioning:**
     - Positioning dalam CSS mengacu pada metode yang digunakan untuk menentukan posisi elemen di halaman web. Dengan menggunakan properti `position`, kalian dapat mengontrol bagaimana dan di mana elemen-elemen ditempatkan dalam dokumen HTML.
   - **Mengapa Positioning Penting?**
     - Positioning memungkinkan kalian untuk menempatkan elemen secara presisi di halaman, baik itu di atas, di bawah, atau di samping elemen lainnya. Ini juga penting untuk membuat tata letak yang dinamis dan menarik.

2. **Jenis-Jenis Positioning dalam CSS**

   - **Static Positioning (position: static)**
     - **Penjelasan:**
       - Static adalah positioning default untuk semua elemen HTML. Elemen dengan `position: static` akan ditempatkan di posisi defaultnya dalam aliran dokumen, mengikuti urutan elemen di HTML tanpa perubahan.
       - Elemen dengan positioning static tidak bisa dipindahkan menggunakan properti top, bottom, left, atau right.
     - **Contoh Penggunaan:**
       ```css
       .box {
           position: static;
           background-color: lightgray;
       }
       ```
       - **HTML:**
         ```html
         <div class="box">Ini adalah elemen dengan posisi static.</div>
         ```

   - **Relative Positioning (position: relative)**
     - **Penjelasan:**
       - Relative positioning memungkinkan kalian memindahkan elemen dari posisi defaultnya dengan menggunakan properti top, bottom, left, dan right. Namun, ruang yang disediakan untuk elemen tersebut di aliran dokumen tidak berubah, yang berarti elemen tersebut masih meninggalkan "jejak" di posisi aslinya.
     - **Contoh Penggunaan:**
       ```css
       .box {
           position: relative;
           top: 20px;
           left: 10px;
           background-color: lightblue;
       }
       ```
       - **HTML:**
         ```html
         <div class="box">Ini adalah elemen dengan posisi relative.</div>
         ```

   - **Absolute Positioning (position: absolute)**
     - **Penjelasan:**
       - Absolute positioning memindahkan elemen dari aliran dokumen biasa dan menempatkannya relatif terhadap elemen induk terdekat yang memiliki positioning selain `static`. Jika tidak ada induk yang diposisikan, elemen tersebut akan diposisikan relatif terhadap halaman (viewport).
       - Properti top, bottom, left, dan right dapat digunakan untuk mengatur posisi elemen.
     - **Contoh Penggunaan:**
       ```css
       .container {
           position: relative;
           height: 200px;
           background-color: lightgray;
       }

       .box {
           position: absolute;
           top: 50px;
           left: 30px;
           background-color: lightcoral;
       }
       ```
       - **HTML:**
         ```html
         <div class="container">
             <div class="box">Ini adalah elemen dengan posisi absolute.</div>
         </div>
         ```

   - **Fixed Positioning (position: fixed)**
     - **Penjelasan:**
       - Fixed positioning memindahkan elemen dari aliran dokumen biasa dan menempatkannya relatif terhadap viewport (layar browser). Elemen dengan posisi fixed akan tetap berada di tempat yang sama di layar meskipun halaman digulir.
     - **Contoh Penggunaan:**
       ```css
       .box {
           position: fixed;
           top: 0;
           right: 0;
           width: 100px;
           background-color: lightgreen;
       }
       ```
       - **HTML:**
         ```html
         <div class="box">Ini adalah elemen dengan posisi fixed.</div>
         ```

   - **Sticky Positioning (position: sticky)**
     - **Penjelasan:**
       - Sticky positioning adalah gabungan dari relative dan fixed positioning. Elemen dengan `position: sticky` akan diposisikan secara relative sampai mencapai titik tertentu di layar, setelah itu elemen tersebut akan "menempel" di posisi itu seperti elemen fixed. Ini sering digunakan untuk membuat header atau navigasi yang tetap terlihat saat pengguna menggulir halaman.
     - **Contoh Penggunaan:**
       ```css
       .box {
           position: sticky;
           top: 0;
           background-color: yellow;
           padding: 10px;
       }
       ```
       - **HTML:**
         ```html
         <div class="box">Ini adalah elemen dengan posisi sticky.</div>
         <p>Scroll down to see the effect...</p>
         <p>Scroll down to see the effect...</p>
         <p>Scroll down to see the effect...</p>
         ```

3. **Penggunaan Positioning dalam Tata Letak**
   - **Relative vs. Absolute Positioning:**
     - Relative positioning biasanya digunakan untuk membuat penyesuaian kecil pada posisi elemen dalam aliran dokumen, sedangkan absolute positioning digunakan untuk penempatan yang lebih bebas dan tidak terikat pada aliran dokumen.
   - **Fixed Positioning untuk Elemen Tetap:**
     - Fixed positioning sangat cocok untuk elemen yang harus tetap terlihat di layar, seperti header atau tombol navigasi.
   - **Sticky Positioning untuk Elemen yang Mengikuti Gulir:**
     - Sticky positioning sering digunakan untuk membuat elemen seperti header atau menu tetap terlihat saat pengguna menggulir halaman, tanpa harus tetap fixed di tempatnya.

4. **Contoh Penerapan Positioning dalam Desain Halaman Web**
   - **Contoh Praktik Positioning:**
     ```css
     .header {
         position: fixed;
         top: 0;
         width: 100%;
         background-color: #333;
         color: white;
         padding: 10px;
         text-align: center;
     }

     .content {
         margin-top: 60px;
         padding: 20px;
     }

     .sidebar {
         position: absolute;
         top: 80px;
         right: 20px;
         width: 200px;
         background-color: #f4f4f4;
         padding: 10px;
         border: 1px solid #ccc;
     }
     ```

   **HTML:**
   ```html
   <div class="header">
       Ini adalah header yang diposisikan secara fixed.
   </div>

   <div class="content">
       <p>Ini adalah konten utama halaman.</p>
       <p>Gunakan positioning untuk mengatur elemen di halaman.</p>
       <div class="sidebar">
           Ini adalah sidebar yang diposisikan secara absolute.
       </div>
   </div>
   ```

5. **Tips dan Praktik Terbaik dalam Menggunakan Positioning**
   - **Gunakan dengan Bijak:** Terlalu banyak menggunakan positioning dapat membuat tata letak menjadi rumit dan sulit dikelola. Gunakan positioning hanya ketika benar-benar diperlukan.
   - **Pahami Aliran Dokumen:** Memahami bagaimana positioning mempengaruhi aliran dokumen dan tata letak halaman sangat penting untuk menghindari hasil yang tidak diinginkan.
   - **Uji Responsivitas:** Pastikan untuk selalu menguji tata letak pada berbagai ukuran layar untuk memastikan positioning bekerja dengan baik di semua perangkat.

#### **Praktikum Lengkap:**

1. **Latihan 1: Menggunakan Relative dan Absolute Positioning**
   - Buatlah elemen dengan relative dan absolute positioning untuk melihat perbedaan bagaimana mereka diposisikan di halaman.

   **Contoh Praktik:**
   ```css
   .container {
       position: relative;
       width: 400px;
       height: 200px;
       background-color: lightgray;
   }

   .box {
       position: absolute;
       top: 50px;
       left: 100px;
       background-color: lightblue;
       padding: 10px;
   }
   ```

   **HTML:**
   ```html
   <div class="container">
       <div class="box">Ini adalah elemen dengan posisi absolute.</div>
   </div>
   ```

2. **Latihan 2: Menggunakan Fixed dan Sticky Positioning**
   - Cobalah buat halaman yang menggunakan fixed positioning untuk header dan sticky positioning untuk navigasi agar tetap terlihat saat halaman digulir.

   **Contoh Praktik:**
   ```css
   .header {
       position: fixed;
       top: 0;
       width: 100%;
       background-color: darkblue;
       color: white;
       text-align: center;
       padding: 10px;
   }

   .menu {
       position: sticky;
       top: 50px;
       background-color: yellow;
       padding: 10px;
       text-align: center;
   }

   .content {
       margin-top: 100px;
       padding: 20px;
   }
   ```

   **HTML:**
   ```html
   <div class="header">
       Header Tetap
   </div>
   <div class="menu">
       Menu Sticky
   </div>
   <div class="content">
      

 <p>Scroll down to see the effect...</p>
       <p>Scroll down to see the effect...</p>
       <p>Scroll down to see the effect...</p>
   </div>
   ```

#### **Diskusi dan Review:**

- **Bagaimana Menentukan Jenis Positioning yang Tepat?**
  - Diskusikan bagaimana memilih jenis positioning yang sesuai berdasarkan kebutuhan tata letak dan bagaimana positioning mempengaruhi elemen-elemen di sekitarnya.

- **Apa Tantangan dalam Menggunakan Positioning?**
  - Diskusikan tantangan umum seperti elemen yang saling tumpang tindih atau keluar dari aliran dokumen, dan cara mengatasi masalah tersebut.