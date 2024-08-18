### **Bab 15: Box Model**

#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Memahami konsep dasar dari CSS Box Model dan bagaimana setiap elemen dalam halaman web dipengaruhi oleh model ini.
- Mengetahui cara mengatur margin, border, padding, dan content untuk mengontrol tata letak dan tampilan elemen di halaman web.
- Menggunakan properti CSS untuk menyesuaikan ukuran dan posisi elemen dengan efektif.

#### **Materi:**

1. **Apa Itu CSS Box Model?**
   - **Definisi CSS Box Model:**
     - CSS Box Model adalah konsep dasar dalam CSS yang menjelaskan bagaimana elemen HTML dirender di halaman web. Setiap elemen dianggap sebagai sebuah kotak yang terdiri dari empat komponen: content (konten), padding (jarak antara konten dan border), border (garis tepi elemen), dan margin (jarak antara border dan elemen lain).
   - **Mengapa Box Model Penting?**
     - Memahami Box Model sangat penting karena ini mempengaruhi bagaimana elemen ditempatkan dan berinteraksi dengan elemen lain di halaman. Ini juga membantu dalam mengontrol tata letak dan ruang antar elemen.

2. **Komponen-Komponen Box Model**

   - **Content:**
     - **Content** adalah area di mana teks, gambar, atau elemen lainnya ditampilkan. Ukuran dari content bisa diatur menggunakan properti `width` dan `height`.
     - **Contoh Pengaturan Ukuran Content:**
       ```css
       div {
           width: 200px;
           height: 100px;
       }
       ```

   - **Padding:**
     - **Padding** adalah ruang di antara content dan border. Padding membuat jarak di dalam border, memberikan ruang di sekitar konten elemen tanpa mempengaruhi margin.
     - **Cara Mengatur Padding:**
       - Padding bisa diatur untuk keempat sisi elemen (atas, kanan, bawah, kiri) dengan satu nilai atau nilai yang berbeda untuk masing-masing sisi.
       - **Contoh Penggunaan Padding:**
         ```css
         div {
             padding: 20px; /* Padding sama di semua sisi */
         }

         div {
             padding: 10px 20px; /* Padding vertikal 10px, horizontal 20px */
         }

         div {
             padding: 10px 15px 20px 25px; /* Padding: atas, kanan, bawah, kiri */
         }
         ```

   - **Border:**
     - **Border** adalah garis tepi yang mengelilingi padding dan content. Border bisa dikustomisasi dengan lebar, gaya, dan warna tertentu.
     - **Properti Border yang Umum Digunakan:**
       - `border-width`: Mengatur lebar border.
       - `border-style`: Mengatur gaya border (solid, dashed, dotted, dll.).
       - `border-color`: Mengatur warna border.
       - **Contoh Penggunaan Border:**
         ```css
         div {
             border: 2px solid black; /* Border 2px, solid, warna hitam */
         }

         div {
             border-width: 1px 2px 3px 4px; /* Border atas, kanan, bawah, kiri */
             border-style: solid;
             border-color: red green blue yellow; /* Warna border atas, kanan, bawah, kiri */
         }
         ```

   - **Margin:**
     - **Margin** adalah ruang di luar border yang memisahkan elemen satu dengan elemen lain. Margin tidak memiliki warna atau gaya, tetapi menentukan jarak antara elemen-elemen di halaman.
     - **Cara Mengatur Margin:**
       - Margin bisa diatur sama seperti padding: satu nilai untuk semua sisi, atau nilai berbeda untuk setiap sisi.
       - **Contoh Penggunaan Margin:**
         ```css
         div {
             margin: 20px; /* Margin sama di semua sisi */
         }

         div {
             margin: 10px 20px; /* Margin vertikal 10px, horizontal 20px */
         }

         div {
             margin: 10px 15px 20px 25px; /* Margin: atas, kanan, bawah, kiri */
         }
         ```

3. **Model Perhitungan Ukuran dalam Box Model**
   - **Standard Box Model vs. Alternate Box Model:**
     - **Standard Box Model**: Lebar dan tinggi elemen hanya mencakup content, sedangkan padding dan border ditambahkan di luar ukuran yang ditentukan.
     - **Alternate Box Model (box-sizing: border-box)**: Lebar dan tinggi elemen mencakup padding dan border, yang berarti ukuran elemen tidak bertambah dengan penambahan padding atau border.

   - **Contoh Penggunaan Box Sizing:**
     ```css
     /* Standard Box Model */
     div {
         width: 200px;
         height: 100px;
         padding: 10px;
         border: 5px solid black;
     }
     /* Total width = 200px + 20px (padding) + 10px (border) = 230px */

     /* Alternate Box Model */
     div {
         box-sizing: border-box;
         width: 200px;
         height: 100px;
         padding: 10px;
         border: 5px solid black;
     }
     /* Total width = 200px (termasuk padding dan border) */
     ```

4. **Visualisasi Box Model**
   - **Menggunakan `outline` untuk Visualisasi:**
     - `outline` adalah properti CSS yang menambahkan garis di luar border, tetapi tidak mempengaruhi ukuran elemen atau tata letak. Ini berguna untuk debugging dan melihat bagaimana Box Model bekerja.
     - **Contoh Penggunaan Outline:**
       ```css
       div {
           outline: 2px dashed red;
       }
       ```

5. **Penggunaan Praktis Box Model**
   - **Mengatur Ruang Antar Elemen dengan Margin:**
     - Margin sering digunakan untuk mengatur ruang antar elemen secara keseluruhan. Menggunakan margin otomatis (`margin: auto`) bisa membantu memusatkan elemen dalam kontainer yang lebih besar.
   - **Menggunakan Padding untuk Spasi di Dalam Elemen:**
     - Padding digunakan untuk memberikan ruang di sekitar content, membuat elemen terlihat lebih seimbang dan tidak terlalu rapat.

6. **Contoh Penggunaan Box Model dalam Desain Halaman Web**
   - **Contoh Praktik Box Model:**
     ```css
     .card {
         width: 300px;
         padding: 20px;
         margin: 15px;
         border: 2px solid #ccc;
         background-color: #f9f9f9;
         box-sizing: border-box;
     }
     ```

   **HTML:**
   ```html
   <div class="card">
       <h2>Judul Kartu</h2>
       <p>Ini adalah contoh penggunaan Box Model dalam CSS.</p>
   </div>
   ```

#### **Praktikum Lengkap:**

1. **Latihan 1: Menggunakan Box Model untuk Menata Elemen**
   - Buatlah elemen yang menggunakan padding, border, dan margin untuk membuat kotak yang jelas dan terstruktur.

   **Contoh Praktik:**
   ```css
   .box {
       width: 200px;
       padding: 10px;
       margin: 20px;
       border: 5px solid black;
       background-color: lightgray;
   }
   ```

   **HTML:**
   ```html
   <div class="box">
       Ini adalah kotak yang menggunakan Box Model.
   </div>
   ```

2. **Latihan 2: Menggunakan Box Sizing untuk Mengatur Ukuran Elemen**
   - Cobalah buat elemen dengan `box-sizing: border-box` untuk memastikan padding dan border tidak menambah ukuran total elemen.

   **Contoh Praktik:**
   ```css
   .box {
       width: 200px;
       height: 100px;
       padding: 20px;
       border: 5px solid black;
       box-sizing: border-box;
       background-color: lightblue;
   }
   ```

   **HTML:**
   ```html
   <div class="box">
       Ini adalah kotak dengan box-sizing: border-box.
   </div>
   ```

#### **Diskusi dan Review:**

- **Bagaimana Perhitungan Ukuran dalam Box Model Mempengaruhi Desain Halaman?**
  - Diskusikan bagaimana pemahaman tentang perhitungan ukuran dalam Box Model dapat membantu kalian merencanakan tata letak halaman yang lebih akurat dan konsisten.

- **Kapan Menggunakan Standard Box Model dan Kapan Menggunakan Border-box?**
  - Diskusikan keuntungan dari masing-masing model dan situasi di mana salah satunya lebih cocok digunakan daripada yang lain.