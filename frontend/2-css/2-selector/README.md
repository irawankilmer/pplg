### **Bab 14: CSS Selectors**

#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Memahami berbagai jenis selectors dalam CSS dan bagaimana penggunaannya.
- Menggunakan selectors dengan benar untuk menerapkan gaya pada elemen HTML secara spesifik.
- Meningkatkan keterampilan dalam mengatur tampilan halaman web dengan menggunakan selectors yang efektif.

#### **Materi:**

1. **Apa Itu CSS Selectors?**
   - **Definisi Selectors:**
     - Selectors adalah pola yang digunakan dalam CSS untuk memilih elemen HTML yang akan diberi gaya. Dengan selectors, kalian dapat menargetkan elemen tertentu dan mengaplikasikan gaya yang diinginkan, seperti warna, font, margin, padding, dan lain-lain.
   - **Mengapa Selectors Penting?**
     - Selectors memungkinkan kalian untuk menerapkan gaya secara spesifik dan efisien pada elemen tertentu dalam dokumen HTML, sehingga desain halaman web dapat diatur dengan lebih tepat dan rapi.

2. **Element Selectors**
   - **Apa Itu Element Selectors?**
     - Element selectors adalah selectors yang digunakan untuk menargetkan semua elemen tertentu dalam dokumen HTML. Misalnya, kalian bisa menargetkan semua elemen `<p>` atau `<h1>` di halaman.

   - **Contoh Penggunaan:**
     ```css
     p {
         color: black;
         font-size: 16px;
     }
     ```
     - **Penjelasan:**
       - Semua elemen `<p>` di halaman akan diberikan warna teks hitam dan ukuran font 16 piksel.

3. **Class Selectors**
   - **Apa Itu Class Selectors?**
     - Class selectors digunakan untuk menargetkan elemen dengan atribut `class` tertentu. Kalian bisa menggunakan class selectors untuk menerapkan gaya yang sama pada sekelompok elemen tanpa harus menulis ulang gaya tersebut berkali-kali.

   - **Cara Menggunakan Class Selectors:**
     - Class selectors dimulai dengan tanda titik (`.`) diikuti oleh nama class.
     - Class names dalam HTML diawali dengan atribut `class` pada elemen yang diinginkan.

   - **Contoh Penggunaan:**
     ```css
     .highlight {
         background-color: yellow;
         font-weight: bold;
     }
     ```
     ```html
     <p class="highlight">Ini adalah teks yang di-highlight.</p>
     <p class="highlight">Teks ini juga di-highlight.</p>
     ```
     - **Penjelasan:**
       - Semua elemen dengan class `highlight` akan memiliki latar belakang kuning dan teks yang tebal.

4. **ID Selectors**
   - **Apa Itu ID Selectors?**
     - ID selectors digunakan untuk menargetkan elemen dengan atribut `id` yang unik. Karena `id` harus unik dalam satu dokumen HTML, ID selectors hanya akan menargetkan satu elemen.

   - **Cara Menggunakan ID Selectors:**
     - ID selectors dimulai dengan tanda pagar (`#`) diikuti oleh nama ID.
     - ID names dalam HTML diawali dengan atribut `id` pada elemen yang diinginkan.

   - **Contoh Penggunaan:**
     ```css
     #header {
         background-color: blue;
         color: white;
         padding: 20px;
         text-align: center;
     }
     ```
     ```html
     <div id="header">Ini adalah header halaman.</div>
     ```
     - **Penjelasan:**
       - Elemen dengan `id="header"` akan memiliki latar belakang biru, teks berwarna putih, padding 20 piksel, dan teks yang disejajarkan ke tengah.

5. **Attribute Selectors**
   - **Apa Itu Attribute Selectors?**
     - Attribute selectors memungkinkan kalian untuk menargetkan elemen berdasarkan atribut tertentu yang ada pada elemen tersebut. Selectors ini sangat berguna ketika kalian ingin menargetkan elemen dengan atribut atau nilai atribut tertentu.

   - **Jenis Attribute Selectors:**
     - `[attribute]`: Menargetkan elemen yang memiliki atribut tertentu.
     - `[attribute=value]`: Menargetkan elemen yang memiliki atribut dengan nilai tertentu.
     - `[attribute~=value]`: Menargetkan elemen yang memiliki atribut dengan nilai yang mengandung kata tertentu.
     - `[attribute|=value]`: Menargetkan elemen yang memiliki atribut dengan nilai yang diawali dengan kata tertentu.

   - **Contoh Penggunaan:**
     ```css
     /* Menargetkan semua elemen dengan atribut title */
     [title] {
         border-bottom: 1px dotted black;
     }

     /* Menargetkan semua elemen dengan atribut href yang memiliki nilai https */
     a[href^="https"] {
         color: green;
     }

     /* Menargetkan semua elemen input dengan tipe teks */
     input[type="text"] {
         border: 1px solid #ccc;
         padding: 5px;
     }
     ```
     - **Penjelasan:**
       - `[title]` akan menambahkan garis bawah titik-titik pada semua elemen dengan atribut `title`.
       - `a[href^="https"]` akan mengubah warna teks dari semua link yang URL-nya diawali dengan `https` menjadi hijau.
       - `input[type="text"]` akan mengatur border dan padding pada semua elemen input dengan tipe teks.

6. **Pseudo-class Selectors**
   - **Apa Itu Pseudo-class Selectors?**
     - Pseudo-class selectors digunakan untuk menargetkan elemen berdasarkan keadaan atau status khusus yang tidak bisa ditargetkan dengan selectors biasa, seperti ketika elemen dalam keadaan hover, fokus, atau ketika merupakan elemen pertama dari jenisnya.

   - **Jenis Pseudo-class Selectors yang Umum:**
     - `:hover`: Menargetkan elemen ketika pengguna mengarahkan kursor di atasnya.
     - `:focus`: Menargetkan elemen yang sedang dalam fokus, biasanya pada form input.
     - `:nth-child(n)`: Menargetkan elemen berdasarkan urutan anak dalam parent.
     - `:first-child`: Menargetkan elemen yang merupakan anak pertama dalam parent.

   - **Contoh Penggunaan:**
     ```css
     /* Mengubah warna latar belakang ketika mouse hover di atas elemen */
     a:hover {
         background-color: lightblue;
     }

     /* Mengubah warna border pada input yang sedang fokus */
     input:focus {
         border-color: blue;
     }

     /* Menargetkan setiap elemen li yang merupakan anak kedua */
     li:nth-child(2) {
         color: red;
     }

     /* Menargetkan paragraf pertama dalam div */
     div p:first-child {
         font-weight: bold;
     }
     ```
     - **Penjelasan:**
       - `a:hover` akan mengubah latar belakang link menjadi biru muda ketika pengguna mengarahkan kursor di atasnya.
       - `input:focus` akan mengubah warna border elemen input menjadi biru ketika elemen tersebut dalam fokus.
       - `li:nth-child(2)` akan mengubah warna teks dari elemen `li` kedua menjadi merah.
       - `div p:first-child` akan membuat teks paragraf pertama dalam `div` menjadi tebal.

7. **Pseudo-element Selectors**
   - **Apa Itu Pseudo-element Selectors?**
     - Pseudo-element selectors digunakan untuk menargetkan bagian tertentu dari elemen, seperti huruf pertama dari paragraf atau isi sebelum dan sesudah elemen.

   - **Jenis Pseudo-element Selectors yang Umum:**
     - `::before`: Menyisipkan konten sebelum isi elemen.
     - `::after`: Menyisipkan konten setelah isi elemen.
     - `::first-letter`: Menargetkan huruf pertama dari teks di elemen.
     - `::first-line`: Menargetkan baris pertama dari teks di elemen.

   - **Contoh Penggunaan:**
     ```css
     /* Menambahkan ikon sebelum teks dalam elemen */
     .note::before {
         content: "📝 ";
         font-size: 20px;
     }

     /* Menambahkan tanda titik dua setelah teks dalam elemen */
     .definition::after {
         content: ":";
         margin-right: 5px;
     }

     /* Membuat huruf pertama dari paragraf lebih besar */
     p::first-letter {
         font-size: 2em;
         font-weight: bold;
     }

     /* Mengubah warna baris pertama dari teks paragraf */
     p::first-line {
         color: blue;
     }
     ```
     - **Penjelasan:**
       - `.note::before` akan menambahkan ikon catatan sebelum teks dalam elemen dengan class `note`.
       - `.definition::after` akan menambahkan tanda titik dua setelah teks dalam elemen dengan class `definition`.
       - `p::first-letter` akan membuat huruf pertama dari paragraf lebih besar dan tebal.
       - `p::first-line` akan mengubah warna teks dari baris pertama paragraf menjadi biru.

8. **Penggabungan Selectors**
   - **Penggabungan Selectors untuk Efisiensi:**
     - Kalian dapat menggabungkan berbagai selectors untuk menargetkan elemen dengan lebih spesifik dan efisien. Misalnya, kalian bisa menggabungkan class dan pseudo-class untuk menargetkan elemen tertentu dalam keadaan tertentu.

   - **Contoh Penggunaan Penggabungan Selectors:**
     ```css
     /* Menargetkan elemen dengan class .menu yang merupakan anak pertama dalam parent */
     .menu li:first-child {
         background-color: gray;
    

 }

     /* Menargetkan link dengan class .active dan menambahkan gaya ketika dihover */
     a.active:hover {
         color: white;
         background-color: green;
     }
     ```
     - **Penjelasan:**
       - `.menu li:first-child` akan memberi latar belakang abu-abu pada elemen `li` pertama dalam elemen dengan class `menu`.
       - `a.active:hover` akan mengubah warna teks menjadi putih dan latar belakang menjadi hijau ketika pengguna mengarahkan kursor di atas link dengan class `active`.

#### **Praktikum Lengkap:**

1. **Latihan 1: Menggunakan Element dan Class Selectors**
   - Buatlah halaman HTML yang menggunakan element selectors untuk mengatur gaya dasar, dan gunakan class selectors untuk menambahkan gaya khusus pada elemen tertentu.

   **Contoh Praktik:**
   ```css
   p {
       font-size: 16px;
       color: black;
   }

   .highlight {
       background-color: yellow;
       font-weight: bold;
   }
   ```

   **HTML:**
   ```html
   <p>Ini adalah paragraf biasa.</p>
   <p class="highlight">Ini adalah paragraf yang di-highlight.</p>
   ```

2. **Latihan 2: Menulis ID dan Attribute Selectors**
   - Buatlah halaman HTML dengan elemen yang memiliki ID unik dan atribut tertentu, lalu gunakan ID dan attribute selectors untuk mengatur gaya elemen tersebut.

   **Contoh Praktik:**
   ```css
   #header {
       background-color: blue;
       color: white;
   }

   a[href^="https"] {
       color: green;
   }
   ```

   **HTML:**
   ```html
   <div id="header">Ini adalah header halaman.</div>
   <a href="https://www.example.com">Link ke HTTPS</a>
   ```

3. **Latihan 3: Menggunakan Pseudo-class dan Pseudo-element Selectors**
   - Cobalah buat halaman HTML yang menggunakan pseudo-class untuk mengatur gaya elemen saat dihover, dan gunakan pseudo-element untuk menambahkan konten sebelum dan sesudah elemen.

   **Contoh Praktik:**
   ```css
   a:hover {
       background-color: lightblue;
   }

   .note::before {
       content: "📝 ";
       font-size: 20px;
   }
   ```

   **HTML:**
   ```html
   <a href="#">Hover di sini</a>
   <p class="note">Ini adalah catatan penting.</p>
   ```

#### **Diskusi dan Review:**

- **Bagaimana Menggunakan Selectors dengan Efisien?**
  - Diskusikan pentingnya menggunakan selectors yang tepat untuk memastikan gaya diterapkan secara efisien tanpa konflik dan dengan mempertimbangkan kinerja halaman.

- **Apa Saja Tantangan dalam Menggunakan Pseudo-classes dan Pseudo-elements?**
  - Diskusikan bagaimana mengatasi tantangan seperti kompatibilitas browser dan pengaturan gaya yang kompleks dengan menggunakan pseudo-classes dan pseudo-elements.