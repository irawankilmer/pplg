### **Bab 18: Flexbox**

#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Memahami konsep dasar Flexbox dan bagaimana ia bekerja dalam CSS.
- Menggunakan properti-properti Flexbox seperti `justify-content`, `align-items`, `flex-direction`, dan `flex-wrap` untuk membuat tata letak yang fleksibel dan responsif.
- Menerapkan Flexbox untuk mengatur elemen dalam kontainer secara efektif, baik dalam baris maupun kolom.

#### **Materi:**

1. **Apa Itu Flexbox?**
   - **Definisi Flexbox:**
     - Flexbox, atau Flexible Box Layout, adalah model tata letak satu dimensi dalam CSS yang dirancang untuk membuat tata letak yang lebih fleksibel dan efisien dalam menyusun elemen dalam baris (row) atau kolom (column). Flexbox sangat berguna untuk membuat tata letak yang responsif dan mudah disesuaikan dengan berbagai ukuran layar.
   - **Mengapa Flexbox Penting?**
     - Flexbox memungkinkan kalian mengontrol perataan, distribusi ruang, dan urutan elemen di dalam kontainer dengan lebih mudah dibandingkan model tata letak tradisional. Ini membuat pengembangan tata letak yang kompleks menjadi lebih sederhana dan intuitif.

2. **Konsep Dasar Flexbox**

   - **Flex Container dan Flex Items:**
     - Flexbox bekerja dengan dua entitas utama:
       - **Flex Container:** Elemen induk yang memiliki properti `display: flex`. Semua elemen anak dari flex container menjadi flex items.
       - **Flex Items:** Elemen-elemen di dalam flex container yang akan diatur menggunakan properti-properti Flexbox.

   - **Cara Mengaktifkan Flexbox:**
     - Untuk mengaktifkan Flexbox pada suatu elemen, kalian hanya perlu menambahkan `display: flex` pada elemen tersebut.
     - **Contoh:**
       ```css
       .container {
           display: flex;
           background-color: lightgray;
           padding: 10px;
       }
       ```
       - **HTML:**
         ```html
         <div class="container">
             <div>Item 1</div>
             <div>Item 2</div>
             <div>Item 3</div>
         </div>
         ```

3. **Properti-Proporsi Flexbox**

   - **`flex-direction`**
     - **Penjelasan:**
       - Properti `flex-direction` menentukan arah utama (main axis) di mana flex items diatur di dalam flex container. Nilai defaultnya adalah `row`, yang berarti flex items akan diatur dalam satu baris dari kiri ke kanan.
     - **Nilai yang Mungkin:**
       - `row`: Mengatur flex items dalam baris dari kiri ke kanan.
       - `row-reverse`: Mengatur flex items dalam baris dari kanan ke kiri.
       - `column`: Mengatur flex items dalam kolom dari atas ke bawah.
       - `column-reverse`: Mengatur flex items dalam kolom dari bawah ke atas.
     - **Contoh Penggunaan:**
       ```css
       .container {
           display: flex;
           flex-direction: row;
       }
       ```
       - **HTML:**
         ```html
         <div class="container">
             <div>Item 1</div>
             <div>Item 2</div>
             <div>Item 3</div>
         </div>
         ```

   - **`justify-content`**
     - **Penjelasan:**
       - Properti `justify-content` mengontrol perataan flex items sepanjang sumbu utama (main axis). Ini menentukan bagaimana ruang kosong didistribusikan antara dan di sekitar flex items.
     - **Nilai yang Mungkin:**
       - `flex-start`: Flex items disejajarkan ke awal flex container.
       - `flex-end`: Flex items disejajarkan ke akhir flex container.
       - `center`: Flex items disejajarkan di tengah flex container.
       - `space-between`: Flex items didistribusikan secara merata dengan ruang di antara mereka.
       - `space-around`: Flex items didistribusikan secara merata dengan ruang di sekitar mereka.
       - `space-evenly`: Flex items didistribusikan secara merata dengan ruang yang sama di antara dan di sekitar mereka.
     - **Contoh Penggunaan:**
       ```css
       .container {
           display: flex;
           justify-content: space-between;
       }
       ```
       - **HTML:**
         ```html
         <div class="container">
             <div>Item 1</div>
             <div>Item 2</div>
             <div>Item 3</div>
         </div>
         ```

   - **`align-items`**
     - **Penjelasan:**
       - Properti `align-items` mengontrol perataan flex items sepanjang sumbu silang (cross axis). Ini menentukan bagaimana flex items disejajarkan secara vertikal dalam kontainer.
     - **Nilai yang Mungkin:**
       - `flex-start`: Flex items disejajarkan ke awal cross axis (atas untuk `row`, kiri untuk `column`).
       - `flex-end`: Flex items disejajarkan ke akhir cross axis (bawah untuk `row`, kanan untuk `column`).
       - `center`: Flex items disejajarkan di tengah cross axis.
       - `baseline`: Flex items disejajarkan berdasarkan baseline teks mereka.
       - `stretch`: Flex items akan meregang untuk memenuhi tinggi kontainer (jika tidak ditentukan tinggi).
     - **Contoh Penggunaan:**
       ```css
       .container {
           display: flex;
           align-items: center;
           height: 200px;
           background-color: lightgray;
       }
       ```
       - **HTML:**
         ```html
         <div class="container">
             <div>Item 1</div>
             <div>Item 2</div>
             <div>Item 3</div>
         </div>
         ```

   - **`flex-wrap`**
     - **Penjelasan:**
       - Secara default, flex items akan tetap berada di satu baris atau kolom, terlepas dari ukurannya. Properti `flex-wrap` memungkinkan flex items untuk membungkus ke baris atau kolom baru jika diperlukan.
     - **Nilai yang Mungkin:**
       - `nowrap`: Flex items tidak akan membungkus; semua tetap dalam satu baris atau kolom (default).
       - `wrap`: Flex items akan membungkus ke baris atau kolom baru jika tidak cukup ruang.
       - `wrap-reverse`: Flex items akan membungkus ke baris atau kolom baru dalam urutan terbalik.
     - **Contoh Penggunaan:**
       ```css
       .container {
           display: flex;
           flex-wrap: wrap;
       }

       .item {
           width: 150px;
           height: 100px;
           background-color: lightblue;
           margin: 10px;
       }
       ```
       - **HTML:**
         ```html
         <div class="container">
             <div class="item">Item 1</div>
             <div class="item">Item 2</div>
             <div class="item">Item 3</div>
             <div class="item">Item 4</div>
             <div class="item">Item 5</div>
         </div>
         ```

4. **Pengaturan Flex Items dengan Properti Flexbox Tambahan**

   - **`align-self`**
     - **Penjelasan:**
       - Properti `align-self` memungkinkan pengaturan perataan individual untuk flex items, yang akan menimpa pengaturan `align-items` dari flex container.
     - **Nilai yang Mungkin:** Sama seperti `align-items`.
     - **Contoh Penggunaan:**
       ```css
       .item-2 {
           align-self: flex-end;
       }
       ```
       - **HTML:**
         ```html
         <div class="container">
             <div class="item">Item 1</div>
             <div class="item item-2">Item 2 (align-self: flex-end)</div>
             <div class="item">Item 3</div>
         </div>
         ```

   - **`order`**
     - **Penjelasan:**
       - Properti `order` menentukan urutan tampilan dari flex items. Nilai defaultnya adalah `0`, tetapi kalian bisa mengubah urutan dengan memberikan nilai numerik yang berbeda.
     - **Contoh Penggunaan:**
       ```css
       .item-1 {
           order: 2;
       }

       .item-3 {
           order: 1;
       }
       ```
       - **HTML:**
         ```html
         <div class="container">
             <div class="item item-1">Item 1 (order: 2)</div>
             <div class="item item-2">Item 2</div>
             <div class="item item-3">Item 3 (order: 1)</div>
         </div>
         ```

   - **`flex-grow`, `flex-shrink`, dan `flex-basis`**
     - **Penjelasan:**
       - Properti `flex-grow` menentukan seberapa besar flex items akan tumbuh relatif terhadap flex items lainnya jika ada ruang ekstra.
       - Properti `flex-shrink` menentukan seberapa besar flex items akan menyusut relatif terhadap flex items lainnya jika ada kekurangan

 ruang.
       - Properti `flex-basis` menentukan ukuran dasar dari flex items sebelum ruang tambahan dialokasikan.
     - **Contoh Penggunaan:**
       ```css
       .item-1 {
           flex-grow: 2;
       }

       .item-2 {
           flex-shrink: 1;
       }

       .item-3 {
           flex-basis: 200px;
       }
       ```
       - **HTML:**
         ```html
         <div class="container">
             <div class="item item-1">Item 1 (flex-grow: 2)</div>
             <div class="item item-2">Item 2 (flex-shrink: 1)</div>
             <div class="item item-3">Item 3 (flex-basis: 200px)</div>
         </div>
         ```

5. **Contoh Penggunaan Flexbox dalam Tata Letak Halaman**

   - **Contoh Praktik Flexbox:**
     ```css
     .navbar {
         display: flex;
         justify-content: space-between;
         align-items: center;
         background-color: #333;
         color: white;
         padding: 10px;
     }

     .nav-item {
         margin: 0 10px;
     }

     .main-content {
         display: flex;
         flex-wrap: wrap;
         gap: 10px;
         margin-top: 20px;
     }

     .content-box {
         flex: 1 1 200px;
         padding: 20px;
         background-color: lightgray;
         text-align: center;
     }
     ```

   **HTML:**
   ```html
   <div class="navbar">
       <div class="nav-item">Logo</div>
       <div class="nav-item">Home</div>
       <div class="nav-item">About</div>
       <div class="nav-item">Contact</div>
   </div>

   <div class="main-content">
       <div class="content-box">Content 1</div>
       <div class="content-box">Content 2</div>
       <div class="content-box">Content 3</div>
   </div>
   ```

#### **Praktikum Lengkap:**

1. **Latihan 1: Menggunakan Flexbox untuk Membuat Header dan Footer Fleksibel**
   - Buatlah tata letak halaman dengan header dan footer yang menggunakan Flexbox untuk mendistribusikan item secara merata.

   **Contoh Praktik:**
   ```css
   .header, .footer {
       display: flex;
       justify-content: space-between;
       padding: 10px;
       background-color: #333;
       color: white;
   }

   .header div, .footer div {
       margin: 0 10px;
   }
   ```

   **HTML:**
   ```html
   <div class="header">
       <div>Logo</div>
       <div>Navigation</div>
       <div>Profile</div>
   </div>

   <div class="footer">
       <div>Links</div>
       <div>Contact</div>
       <div>Privacy Policy</div>
   </div>
   ```

2. **Latihan 2: Membuat Tata Letak Produk Menggunakan Flexbox**
   - Cobalah buat tata letak produk menggunakan Flexbox yang menampilkan produk dalam baris, dan produk bisa dibungkus jika ruang tidak cukup.

   **Contoh Praktik:**
   ```css
   .product-container {
       display: flex;
       flex-wrap: wrap;
       gap: 20px;
   }

   .product-item {
       flex: 1 1 200px;
       padding: 15px;
       background-color: lightcoral;
       text-align: center;
   }
   ```

   **HTML:**
   ```html
   <div class="product-container">
       <div class="product-item">Produk 1</div>
       <div class="product-item">Produk 2</div>
       <div class="product-item">Produk 3</div>
       <div class="product-item">Produk 4</div>
   </div>
   ```

#### **Diskusi dan Review:**

- **Bagaimana Menggunakan Flexbox untuk Tata Letak yang Kompleks?**
  - Diskusikan bagaimana Flexbox dapat digunakan untuk membuat tata letak yang kompleks namun tetap fleksibel dan mudah disesuaikan dengan berbagai ukuran layar.

- **Apa Tantangan dalam Menggunakan Flexbox?**
  - Diskusikan tantangan umum seperti kompatibilitas browser dan penataan flex items yang tidak diinginkan, serta bagaimana cara mengatasi masalah tersebut.