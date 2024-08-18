### **Bab 20: Typography**

#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Memahami berbagai properti CSS yang digunakan untuk mengatur tampilan teks di halaman web.
- Menggunakan properti seperti `font-family`, `font-size`, `font-weight`, `line-height`, `text-align`, dan `text-decoration` untuk mengatur dan menata teks dengan baik.
- Menerapkan prinsip-prinsip tipografi yang baik untuk meningkatkan keterbacaan dan estetika teks di halaman web.

#### **Materi:**

1. **Apa Itu Typography dalam CSS?**
   - **Definisi Typography:**
     - Typography dalam CSS mengacu pada serangkaian properti yang digunakan untuk mengontrol tampilan dan tata letak teks di halaman web. Ini mencakup pemilihan font, ukuran teks, berat font, perataan, jarak antar baris, dan dekorasi teks.
   - **Mengapa Typography Penting?**
     - Typography yang baik dapat meningkatkan keterbacaan, daya tarik visual, dan pengalaman pengguna secara keseluruhan di halaman web. Menggunakan properti CSS untuk tipografi memungkinkan kalian menciptakan tampilan teks yang konsisten dan profesional.

2. **Properti-Properti Utama dalam Typography**

   - **`font-family`**
     - **Penjelasan:**
       - Properti `font-family` digunakan untuk menentukan jenis font yang akan digunakan pada teks. Kalian bisa menyertakan daftar beberapa font sebagai fallback jika font pertama tidak tersedia di perangkat pengguna.
       - Font-family biasanya terdiri dari dua jenis: font serif (misalnya, Times New Roman) dan font sans-serif (misalnya, Arial).
     - **Contoh Penggunaan:**
       ```css
       body {
           font-family: 'Arial', 'Helvetica', sans-serif;
       }
       ```
       - **Penjelasan:**
         - Teks di halaman akan menggunakan font Arial, jika tidak tersedia, akan jatuh ke Helvetica, dan jika kedua-duanya tidak tersedia, akan menggunakan font sans-serif default.

   - **`font-size`**
     - **Penjelasan:**
       - Properti `font-size` menentukan ukuran teks. Ukuran teks bisa diatur menggunakan satuan seperti piksel (`px`), em, rem, atau persen (`%`).
       - Penggunaan `em` dan `rem` lebih dianjurkan untuk membuat ukuran teks yang responsif dan dapat diskalakan.
     - **Contoh Penggunaan:**
       ```css
       p {
           font-size: 16px; /* Ukuran tetap */
       }

       h1 {
           font-size: 2em; /* 2 kali ukuran font default */
       }
       ```
       - **Penjelasan:**
         - Teks paragraf akan memiliki ukuran 16 piksel, sementara heading 1 akan memiliki ukuran dua kali lipat dari ukuran font default.

   - **`font-weight`**
     - **Penjelasan:**
       - Properti `font-weight` mengatur ketebalan teks. Nilai umum untuk font-weight adalah `normal`, `bold`, dan nilai numerik dari 100 hingga 900, di mana 400 adalah normal dan 700 adalah bold.
     - **Contoh Penggunaan:**
       ```css
       p {
           font-weight: normal;
       }

       h1 {
           font-weight: bold;
       }

       strong {
           font-weight: 700; /* Setara dengan bold */
       }
       ```

   - **`line-height`**
     - **Penjelasan:**
       - Properti `line-height` menentukan jarak vertikal antara baris-baris teks dalam elemen. Mengatur `line-height` dengan baik dapat meningkatkan keterbacaan teks.
       - `line-height` bisa diatur dengan nilai unitless, em, rem, atau persen. Nilai `line-height: 1.5` umumnya digunakan untuk membuat jarak antar baris yang lebih nyaman dibaca.
     - **Contoh Penggunaan:**
       ```css
       p {
           line-height: 1.5; /* 1.5 kali ukuran font */
       }

       h1 {
           line-height: 1.2;
       }
       ```

   - **`text-align`**
     - **Penjelasan:**
       - Properti `text-align` digunakan untuk mengatur perataan teks dalam elemen. Teks dapat diratakan ke kiri (`left`), kanan (`right`), tengah (`center`), atau rata kanan-kiri (`justify`).
     - **Contoh Penggunaan:**
       ```css
       p {
           text-align: justify;
       }

       h1 {
           text-align: center;
       }
       ```
       - **Penjelasan:**
         - Paragraf akan diratakan ke kanan-kiri, sementara heading 1 akan diratakan ke tengah.

   - **`text-decoration`**
     - **Penjelasan:**
       - Properti `text-decoration` mengontrol dekorasi tambahan pada teks, seperti garis bawah (`underline`), garis di atas teks (`overline`), atau garis di tengah teks (`line-through`).
     - **Contoh Penggunaan:**
       ```css
       a {
           text-decoration: none; /* Menghilangkan garis bawah pada link */
       }

       .strikethrough {
           text-decoration: line-through; /* Menambahkan garis di tengah teks */
       }
       ```

3. **Properti-Proporsi Tambahan untuk Typography**

   - **`font-style`**
     - **Penjelasan:**
       - Properti `font-style` digunakan untuk mengatur gaya font seperti italic atau normal.
     - **Contoh Penggunaan:**
       ```css
       em {
           font-style: italic; /* Teks miring */
       }
       ```

   - **`letter-spacing` dan `word-spacing`**
     - **Penjelasan:**
       - `letter-spacing` mengatur jarak antar karakter, sedangkan `word-spacing` mengatur jarak antar kata.
     - **Contoh Penggunaan:**
       ```css
       p {
           letter-spacing: 0.05em; /* Menambahkan sedikit jarak antar karakter */
           word-spacing: 0.1em; /* Menambahkan jarak antar kata */
       }
       ```

   - **`text-transform`**
     - **Penjelasan:**
       - Properti `text-transform` mengontrol pengubahan teks menjadi huruf besar (`uppercase`), huruf kecil (`lowercase`), atau huruf kapital pada setiap kata (`capitalize`).
     - **Contoh Penggunaan:**
       ```css
       h2 {
           text-transform: uppercase; /* Mengubah teks menjadi huruf besar */
       }
       ```

4. **Penggunaan Font Eksternal dengan Google Fonts**

   - **Menggunakan Google Fonts:**
     - Kalian bisa menambahkan font eksternal ke halaman web dengan menggunakan Google Fonts. Caranya adalah dengan menambahkan link ke font yang diinginkan dalam bagian `<head>` dari HTML, kemudian menerapkan font tersebut menggunakan `font-family`.
     - **Contoh Penggunaan:**
       ```html
       <head>
           <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap">
       </head>
       <style>
           body {
               font-family: 'Roboto', sans-serif;
           }
       </style>
       ```

5. **Contoh Penggunaan Typography dalam Desain Halaman Web**

   - **Contoh Praktik Typography:**
     ```css
     body {
         font-family: 'Arial', sans-serif;
         font-size: 16px;
         line-height: 1.6;
         color: #333;
     }

     h1, h2, h3 {
         font-family: 'Georgia', serif;
         font-weight: bold;
         text-align: center;
         margin-bottom: 20px;
     }

     p {
         margin-bottom: 15px;
         text-align: justify;
     }

     a {
         color: #0066cc;
         text-decoration: none;
     }

     a:hover {
         text-decoration: underline;
     }
     ```

   **HTML:**
   ```html
   <body>
       <h1>Selamat Datang di Situs Kami</h1>
       <p>Teks paragraf ini diratakan kanan-kiri dan memiliki jarak antar baris yang nyaman untuk dibaca.</p>
       <p>Font yang digunakan pada teks ini adalah Arial, sementara heading menggunakan Georgia.</p>
       <a href="#">Ini adalah link</a>
   </body>
   ```

#### **Praktikum Lengkap:**

1. **Latihan 1: Menggunakan Berbagai Font dan Ukuran Teks**
   - Buatlah halaman yang menggunakan beberapa jenis font dan ukuran teks yang berbeda untuk melihat bagaimana mereka mempengaruhi tampilan halaman.

   **Contoh Praktik:**
   ```css
   body {
       font-family: 'Verdana', sans-serif;
       font-size: 14px;
   }

   h1 {
       font-family: 'Times New Roman', serif;
       font-size: 2.5em;
   }

   p {
       font-size: 16px;
       line-height: 1.5;
   }
   ```

   **HTML:**
   ```html
   <body>
       <h1>Heading Utama</h1>
       <p>Ini adalah paragraf dengan font Verdana dan ukuran 16px.</p>
       <p>Ukuran font pada teks ini sedikit lebih kecil, dengan line-height yang cukup untuk kenyamanan membaca.</p>
  

 </body>
   ```

2. **Latihan 2: Menerapkan Gaya Teks dengan Dekorasi dan Transformasi**
   - Buatlah halaman dengan teks yang menggunakan berbagai dekorasi dan transformasi untuk melihat efeknya.

   **Contoh Praktik:**
   ```css
   h2 {
       text-transform: uppercase;
       text-align: center;
   }

   p {
       text-decoration: underline;
       font-style: italic;
   }

   .important {
       font-weight: bold;
       text-decoration: line-through;
   }
   ```

   **HTML:**
   ```html
   <h2>Ini adalah Judul</h2>
   <p>Ini adalah paragraf dengan garis bawah dan teks miring.</p>
   <p class="important">Ini adalah teks penting yang dicoret dan ditebalkan.</p>
   ```

#### **Diskusi dan Review:**

- **Bagaimana Menggunakan Typography untuk Meningkatkan Keterbacaan?**
  - Diskusikan bagaimana pemilihan font, ukuran teks, dan jarak antar baris dapat meningkatkan keterbacaan dan kenyamanan membaca di halaman web.

- **Apa Tantangan dalam Memilih Font yang Tepat?**
  - Diskusikan tantangan dalam memilih font yang sesuai dengan tema situs dan memastikan font tersebut tersedia di semua perangkat pengguna.