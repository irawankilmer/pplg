### **Bab 17: Display**

#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Memahami berbagai nilai properti `display` dalam CSS dan bagaimana mereka mempengaruhi tata letak elemen di halaman web.
- Menggunakan `display` untuk mengontrol bagaimana elemen ditampilkan, baik sebagai blok, inline, atau kombinasi keduanya.
- Menerapkan konsep `display: flex` dan `display: grid` untuk membuat tata letak yang fleksibel dan responsif.

#### **Materi:**

1. **Apa Itu CSS Display?**
   - **Definisi Display:**
     - Properti `display` dalam CSS menentukan bagaimana elemen HTML ditampilkan di halaman web. Ini mengontrol apakah elemen ditampilkan sebagai blok, inline, kombinasi dari keduanya, atau bahkan tidak ditampilkan sama sekali.
   - **Mengapa Display Penting?**
     - Pemahaman tentang `display` sangat penting karena ini menentukan bagaimana elemen diatur dan berinteraksi satu sama lain di dalam aliran dokumen. Dengan mengubah nilai `display`, kalian dapat mengubah tata letak halaman secara drastis.

2. **Jenis-Jenis Nilai Display dalam CSS**

   - **`display: block`**
     - **Penjelasan:**
       - Elemen dengan `display: block` akan menempati seluruh lebar kontainer induknya dan selalu memulai baris baru. Contoh elemen blok adalah `<div>`, `<h1>`, `<p>`, `<section>`.
       - Elemen blok dapat memiliki `width`, `height`, `margin`, dan `padding` yang diatur.
     - **Contoh Penggunaan:**
       ```css
       .block {
           display: block;
           width: 100%;
           background-color: lightblue;
           padding: 10px;
           margin-bottom: 10px;
       }
       ```
       - **HTML:**
         ```html
         <div class="block">Ini adalah elemen blok.</div>
         <div class="block">Ini juga elemen blok lain.</div>
         ```

   - **`display: inline`**
     - **Penjelasan:**
       - Elemen dengan `display: inline` akan menempati hanya lebar kontennya dan tidak memulai baris baru, melainkan mengikuti elemen sebelumnya. Contoh elemen inline adalah `<span>`, `<a>`, `<strong>`.
       - Elemen inline tidak bisa memiliki `width` dan `height` yang diatur, dan margin atau padding hanya akan mempengaruhi elemen di satu sisi.
     - **Contoh Penggunaan:**
       ```css
       .inline {
           display: inline;
           color: red;
       }
       ```
       - **HTML:**
         ```html
         <span class="inline">Ini adalah elemen inline.</span>
         <span class="inline">Ini juga elemen inline lain.</span>
         ```

   - **`display: inline-block`**
     - **Penjelasan:**
       - `display: inline-block` menggabungkan karakteristik dari `inline` dan `block`. Elemen dengan `display: inline-block` akan berada dalam aliran dokumen seperti elemen inline, tetapi bisa memiliki `width`, `height`, `margin`, dan `padding` seperti elemen blok.
     - **Contoh Penggunaan:**
       ```css
       .inline-block {
           display: inline-block;
           width: 150px;
           height: 100px;
           background-color: lightgreen;
           margin: 5px;
       }
       ```
       - **HTML:**
         ```html
         <div class="inline-block">Elemen 1</div>
         <div class="inline-block">Elemen 2</div>
         <div class="inline-block">Elemen 3</div>
         ```

   - **`display: none`**
     - **Penjelasan:**
       - `display: none` akan menghilangkan elemen dari tampilan sepenuhnya, tidak hanya membuatnya tidak terlihat tetapi juga menghapus elemen tersebut dari aliran dokumen. Elemen dengan `display: none` tidak akan mempengaruhi tata letak halaman.
     - **Contoh Penggunaan:**
       ```css
       .hidden {
           display: none;
       }
       ```
       - **HTML:**
         ```html
         <div class="hidden">Elemen ini disembunyikan.</div>
         ```

3. **Penggunaan `display: flex` untuk Tata Letak Fleksibel**

   - **Penjelasan Flexbox:**
     - Flexbox adalah model tata letak yang digunakan untuk membuat tata letak fleksibel dan responsif. Dengan `display: flex`, kalian dapat mengatur elemen dalam baris atau kolom dan mengontrol bagaimana elemen tersebut didistribusikan dalam kontainer.
   - **Properti Flexbox yang Umum Digunakan:**
     - `flex-direction`: Menentukan arah aliran elemen (row, column).
     - `justify-content`: Mengatur distribusi ruang di antara elemen pada sumbu utama (main axis).
     - `align-items`: Mengatur perataan elemen pada sumbu silang (cross axis).
   - **Contoh Penggunaan Flexbox:**
     ```css
     .flex-container {
         display: flex;
         flex-direction: row;
         justify-content: space-between;
         align-items: center;
         background-color: lightgray;
         padding: 10px;
     }

     .flex-item {
         background-color: lightblue;
         padding: 20px;
         margin: 5px;
         flex: 1;
     }
     ```
     - **HTML:**
       ```html
       <div class="flex-container">
           <div class="flex-item">Item 1</div>
           <div class="flex-item">Item 2</div>
           <div class="flex-item">Item 3</div>
       </div>
       ```

4. **Penggunaan `display: grid` untuk Tata Letak Grid**

   - **Penjelasan Grid Layout:**
     - CSS Grid adalah model tata letak dua dimensi yang memungkinkan kalian membuat tata letak berdasarkan baris dan kolom. Dengan `display: grid`, kalian dapat membuat grid kompleks yang mengatur elemen dalam layout yang sangat presisi.
   - **Properti Grid yang Umum Digunakan:**
     - `grid-template-columns`: Menentukan jumlah dan ukuran kolom.
     - `grid-template-rows`: Menentukan jumlah dan ukuran baris.
     - `gap`: Mengatur jarak antara baris dan kolom.
   - **Contoh Penggunaan Grid Layout:**
     ```css
     .grid-container {
         display: grid;
         grid-template-columns: 1fr 1fr 1fr;
         grid-template-rows: auto;
         gap: 10px;
         background-color: lightyellow;
         padding: 10px;
     }

     .grid-item {
         background-color: lightcoral;
         padding: 20px;
         text-align: center;
     }
     ```
     - **HTML:**
       ```html
       <div class="grid-container">
           <div class="grid-item">Item 1</div>
           <div class="grid-item">Item 2</div>
           <div class="grid-item">Item 3</div>
           <div class="grid-item">Item 4</div>
           <div class="grid-item">Item 5</div>
           <div class="grid-item">Item 6</div>
       </div>
       ```

5. **Kombinasi Display dengan Positioning dan Box Model**
   - **Menggabungkan Display dengan Positioning:**
     - Kalian bisa menggabungkan properti `display` dengan positioning (`position: relative`, `absolute`, dll.) dan Box Model (`padding`, `margin`, `border`) untuk membuat tata letak yang lebih kompleks dan responsif.
   - **Contoh Penggunaan Kombinasi:**
     ```css
     .container {
         display: flex;
         justify-content: center;
         align-items: center;
         height: 100vh;
         background-color: lightgray;
     }

     .box {
         position: relative;
         display: inline-block;
         padding: 20px;
         margin: 10px;
         background-color: lightgreen;
         border: 2px solid #333;
     }
     ```
     - **HTML:**
       ```html
       <div class="container">
           <div class="box">Box 1</div>
           <div class="box">Box 2</div>
       </div>
       ```

#### **Praktikum Lengkap:**

1. **Latihan 1: Menggunakan Display Block dan Inline-block**
   - Buatlah dua set elemen, satu menggunakan `display: block` dan yang lain menggunakan `display: inline-block`, dan amati perbedaannya.

   **Contoh Praktik:**
   ```css
   .block {
       display: block;
       width: 100%;
       background-color: lightblue;
       padding: 10px;
       margin-bottom: 10px;
   }

   .inline-block {
       display: inline-block;
       width: 150px;
       height: 100px;
       background-color: lightgreen;
       margin: 5px;
   }
   ```

   **HTML:**
   ```html
   <div class="block">Elemen Blok 1</div>
   <div class

="block">Elemen Blok 2</div>

   <div class="inline-block">Elemen Inline-block 1</div>
   <div class="inline-block">Elemen Inline-block 2</div>
   <div class="inline-block">Elemen Inline-block 3</div>
   ```

2. **Latihan 2: Menggunakan Flexbox untuk Tata Letak Responsif**
   - Buatlah tata letak fleksibel menggunakan Flexbox dengan elemen yang disusun dalam baris dan terdistribusi secara merata.

   **Contoh Praktik:**
   ```css
   .flex-container {
       display: flex;
       justify-content: space-between;
       align-items: center;
       background-color: lightgray;
       padding: 10px;
   }

   .flex-item {
       background-color: lightblue;
       padding: 20px;
       margin: 5px;
       flex: 1;
   }
   ```

   **HTML:**
   ```html
   <div class="flex-container">
       <div class="flex-item">Item 1</div>
       <div class="flex-item">Item 2</div>
       <div class="flex-item">Item 3</div>
   </div>
   ```

3. **Latihan 3: Menggunakan Grid Layout untuk Tata Letak Grid**
   - Buatlah tata letak grid sederhana menggunakan Grid Layout dengan beberapa kolom dan baris, dan atur jarak antar elemen.

   **Contoh Praktik:**
   ```css
   .grid-container {
       display: grid;
       grid-template-columns: 1fr 1fr 1fr;
       grid-template-rows: auto;
       gap: 10px;
       background-color: lightyellow;
       padding: 10px;
   }

   .grid-item {
       background-color: lightcoral;
       padding: 20px;
       text-align: center;
   }
   ```

   **HTML:**
   ```html
   <div class="grid-container">
       <div class="grid-item">Item 1</div>
       <div class="grid-item">Item 2</div>
       <div class="grid-item">Item 3</div>
       <div class="grid-item">Item 4</div>
       <div class="grid-item">Item 5</div>
       <div class="grid-item">Item 6</div>
   </div>
   ```

#### **Diskusi dan Review:**

- **Bagaimana Memilih Nilai Display yang Tepat?**
  - Diskusikan bagaimana memilih nilai `display` yang sesuai berdasarkan kebutuhan tata letak halaman, seperti kapan menggunakan `block`, `inline`, `inline-block`, atau `flex` dan `grid`.

- **Apa Tantangan dalam Menggunakan Flexbox dan Grid?**
  - Diskusikan tantangan umum seperti pengaturan tata letak yang kompleks atau responsif, dan bagaimana cara mengatasi masalah tersebut dengan Flexbox dan Grid.