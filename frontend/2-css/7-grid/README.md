### **Bab 19: CSS Grid**

#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Memahami konsep dasar CSS Grid dan bagaimana cara kerjanya dalam mengatur tata letak halaman web.
- Menggunakan properti-properti seperti `grid-template-columns`, `grid-template-rows`, `gap`, dan `grid-area` untuk membuat tata letak grid yang kompleks dan responsif.
- Menerapkan CSS Grid untuk mengatur elemen dalam baris dan kolom dengan cara yang fleksibel dan presisi.

#### **Materi:**

1. **Apa Itu CSS Grid?**
   - **Definisi CSS Grid:**
     - CSS Grid adalah model tata letak dua dimensi yang memungkinkan kalian untuk membuat tata letak yang kompleks dengan baris (rows) dan kolom (columns). Dengan Grid, kalian dapat mengatur elemen-elemen di halaman web dengan lebih presisi dan fleksibel.
   - **Mengapa CSS Grid Penting?**
     - CSS Grid sangat berguna untuk membuat tata letak halaman yang responsif dan dapat disesuaikan dengan berbagai ukuran layar. Grid memungkinkan kalian untuk mengontrol tata letak secara keseluruhan, baik secara horizontal maupun vertikal.

2. **Konsep Dasar CSS Grid**

   - **Grid Container dan Grid Items:**
     - CSS Grid bekerja dengan dua entitas utama:
       - **Grid Container:** Elemen induk yang memiliki properti `display: grid`. Semua elemen anak dari grid container menjadi grid items.
       - **Grid Items:** Elemen-elemen di dalam grid container yang akan diatur menggunakan properti-properti Grid.

   - **Cara Mengaktifkan Grid:**
     - Untuk mengaktifkan CSS Grid pada suatu elemen, kalian hanya perlu menambahkan `display: grid` pada elemen tersebut.
     - **Contoh:**
       ```css
       .container {
           display: grid;
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

3. **Properti-Properti Utama dalam CSS Grid**

   - **`grid-template-columns` dan `grid-template-rows`**
     - **Penjelasan:**
       - Properti `grid-template-columns` dan `grid-template-rows` digunakan untuk menentukan jumlah dan ukuran kolom dan baris dalam grid. Kalian dapat menentukan ukuran dengan nilai absolut (seperti `px` atau `em`), persen (`%`), atau unit fraksi (`fr`).
     - **Contoh Penggunaan:**
       ```css
       .container {
           display: grid;
           grid-template-columns: 1fr 2fr 1fr;
           grid-template-rows: 100px 200px;
       }
       ```
       - **HTML:**
         ```html
         <div class="container">
             <div>Item 1</div>
             <div>Item 2</div>
             <div>Item 3</div>
             <div>Item 4</div>
         </div>
         ```

   - **`gap` (sebelumnya dikenal sebagai `grid-gap`)**
     - **Penjelasan:**
       - Properti `gap` digunakan untuk mengatur jarak antara baris dan kolom di dalam grid. Kalian dapat mengatur jarak horizontal (`column-gap`), jarak vertikal (`row-gap`), atau keduanya sekaligus (`gap`).
     - **Contoh Penggunaan:**
       ```css
       .container {
           display: grid;
           grid-template-columns: repeat(3, 1fr);
           gap: 10px 20px; /* 10px untuk row-gap, 20px untuk column-gap */
       }
       ```
       - **HTML:**
         ```html
         <div class="container">
             <div>Item 1</div>
             <div>Item 2</div>
             <div>Item 3</div>
             <div>Item 4</div>
             <div>Item 5</div>
             <div>Item 6</div>
         </div>
         ```

   - **`grid-area`**
     - **Penjelasan:**
       - Properti `grid-area` digunakan untuk menggabungkan pengaturan grid-row-start, grid-column-start, grid-row-end, dan grid-column-end dalam satu pernyataan. Kalian juga bisa menggunakan nama area grid yang didefinisikan dalam `grid-template-areas`.
     - **Contoh Penggunaan:**
       ```css
       .container {
           display: grid;
           grid-template-columns: 1fr 1fr 1fr;
           grid-template-rows: auto;
           gap: 10px;
       }

       .item1 {
           grid-area: 1 / 1 / 2 / 3; /* Mulai dari baris 1, kolom 1, berakhir di baris 2, kolom 3 */
       }

       .item2 {
           grid-area: 2 / 1 / 3 / 4;
       }
       ```
       - **HTML:**
         ```html
         <div class="container">
             <div class="item1">Item 1</div>
             <div class="item2">Item 2</div>
             <div>Item 3</div>
             <div>Item 4</div>
         </div>
         ```

   - **`grid-template-areas`**
     - **Penjelasan:**
       - Properti `grid-template-areas` digunakan untuk memberi nama area tertentu di dalam grid dan menempatkan grid items ke dalam area tersebut. Ini memungkinkan kalian untuk membuat tata letak yang lebih jelas dan terstruktur.
     - **Contoh Penggunaan:**
       ```css
       .container {
           display: grid;
           grid-template-columns: 1fr 2fr 1fr;
           grid-template-rows: auto;
           grid-template-areas: 
               "header header header"
               "sidebar content content"
               "footer footer footer";
           gap: 10px;
       }

       .header {
           grid-area: header;
           background-color: lightblue;
       }

       .sidebar {
           grid-area: sidebar;
           background-color: lightgreen;
       }

       .content {
           grid-area: content;
           background-color: lightcoral;
       }

       .footer {
           grid-area: footer;
           background-color: lightyellow;
       }
       ```
       - **HTML:**
         ```html
         <div class="container">
             <div class="header">Header</div>
             <div class="sidebar">Sidebar</div>
             <div class="content">Content</div>
             <div class="footer">Footer</div>
         </div>
         ```

4. **Penggunaan Lanjutan CSS Grid**

   - **`repeat()`**
     - **Penjelasan:**
       - Fungsi `repeat()` digunakan untuk mengatur template kolom atau baris dengan pola berulang. Ini sangat berguna ketika kalian ingin membuat grid dengan banyak kolom atau baris dengan ukuran yang seragam.
     - **Contoh Penggunaan:**
       ```css
       .container {
           display: grid;
           grid-template-columns: repeat(4, 1fr);
           grid-template-rows: repeat(2, 100px);
           gap: 10px;
       }
       ```
       - **HTML:**
         ```html
         <div class="container">
             <div>Item 1</div>
             <div>Item 2</div>
             <div>Item 3</div>
             <div>Item 4</div>
             <div>Item 5</div>
             <div>Item 6</div>
             <div>Item 7</div>
             <div>Item 8</div>
         </div>
         ```

   - **`minmax()`**
     - **Penjelasan:**
       - Fungsi `minmax()` digunakan untuk menetapkan ukuran minimum dan maksimum untuk kolom atau baris. Ini membantu memastikan bahwa elemen-elemen di grid tidak menjadi terlalu kecil atau terlalu besar.
     - **Contoh Penggunaan:**
       ```css
       .container {
           display: grid;
           grid-template-columns: repeat(3, minmax(100px, 1fr));
           grid-template-rows: 200px;
           gap: 10px;
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

5. **Contoh Penggunaan CSS Grid dalam Tata Letak Halaman**

   - **Contoh Praktik Grid Layout:**
     ```css
     .container {
         display: grid;
         grid-template-columns: 1fr 3fr;
         grid-template-rows: auto;
         gap: 20px;
         grid-template-areas: 
             "header header"
             "sidebar content"
             "footer footer";
     }

     .header {
         grid-area: header;
         background-color: #333;
         color: white;
         padding: 10px;
         text-align: center;
     }

     .sidebar {
         grid-area: sidebar;
         background-color: #f4f4f

4;
         padding: 10px;
     }

     .content {
         grid-area: content;
         background-color: #e4e4e4;
         padding: 20px;
     }

     .footer {
         grid-area: footer;
         background-color: #333;
         color: white;
         padding: 10px;
         text-align: center;
     }
     ```

   **HTML:**
   ```html
   <div class="container">
       <div class="header">Header</div>
       <div class="sidebar">Sidebar</div>
       <div class="content">Content</div>
       <div class="footer">Footer</div>
   </div>
   ```

#### **Praktikum Lengkap:**

1. **Latihan 1: Menggunakan Grid Template Columns dan Rows**
   - Buatlah grid dengan beberapa kolom dan baris menggunakan `grid-template-columns` dan `grid-template-rows`.

   **Contoh Praktik:**
   ```css
   .container {
       display: grid;
       grid-template-columns: 1fr 2fr 1fr;
       grid-template-rows: 100px 200px;
       gap: 15px;
   }

   .item {
       background-color: lightblue;
       padding: 20px;
       text-align: center;
   }
   ```

   **HTML:**
   ```html
   <div class="container">
       <div class="item">Item 1</div>
       <div class="item">Item 2</div>
       <div class="item">Item 3</div>
       <div class="item">Item 4</div>
   </div>
   ```

2. **Latihan 2: Membuat Tata Letak Halaman dengan Grid Template Areas**
   - Buatlah tata letak halaman dengan header, sidebar, konten, dan footer menggunakan `grid-template-areas`.

   **Contoh Praktik:**
   ```css
   .container {
       display: grid;
       grid-template-columns: 1fr 3fr;
       grid-template-rows: auto;
       gap: 20px;
       grid-template-areas: 
           "header header"
           "sidebar content"
           "footer footer";
   }

   .header {
       grid-area: header;
       background-color: #333;
       color: white;
       padding: 10px;
       text-align: center;
   }

   .sidebar {
       grid-area: sidebar;
       background-color: #f4f4f4;
       padding: 10px;
   }

   .content {
       grid-area: content;
       background-color: #e4e4e4;
       padding: 20px;
   }

   .footer {
       grid-area: footer;
       background-color: #333;
       color: white;
       padding: 10px;
       text-align: center;
   }
   ```

   **HTML:**
   ```html
   <div class="container">
       <div class="header">Header</div>
       <div class="sidebar">Sidebar</div>
       <div class="content">Content</div>
       <div class="footer">Footer</div>
   </div>
   ```

#### **Diskusi dan Review:**

- **Bagaimana CSS Grid Dapat Mempermudah Tata Letak yang Kompleks?**
  - Diskusikan bagaimana CSS Grid memungkinkan kalian untuk membuat tata letak halaman yang kompleks dengan lebih mudah dan fleksibel dibandingkan metode lain seperti float atau Flexbox.

- **Apa Keuntungan Menggunakan `grid-template-areas`?**
  - Diskusikan bagaimana penggunaan `grid-template-areas` dapat membuat tata letak menjadi lebih jelas dan mudah dimengerti, terutama saat bekerja dengan tim.