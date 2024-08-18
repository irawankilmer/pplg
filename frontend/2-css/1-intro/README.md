### **Bab 13: Berkenalan dengan CSS**

#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Memahami apa itu CSS dan peran pentingnya dalam pengembangan web.
- Mengetahui cara menulis dan menerapkan CSS dalam berbagai cara, termasuk inline, internal, dan eksternal.
- Menggunakan CSS untuk mengatur tampilan dan layout halaman web dengan lebih efektif.

#### **Materi:**

1. **Apa Itu CSS?**
   - **Definisi CSS:**
     - **CSS (Cascading Style Sheets)** adalah bahasa yang digunakan untuk mendesain dan mengatur tampilan elemen-elemen di halaman web. Dengan CSS, kalian bisa mengontrol warna, font, tata letak, dan banyak aspek lain dari tampilan halaman web.
   - **Mengapa CSS Penting?**
     - CSS memisahkan konten dari tampilan, memungkinkan kalian untuk mengatur gaya halaman web secara terpisah dari struktur HTML. Ini membuat halaman lebih mudah dikelola dan diupdate, serta memastikan tampilan yang konsisten di seluruh situs.

2. **Cara Kerja CSS**
   - **CSS bekerja dengan mengaplikasikan gaya pada elemen HTML yang ditentukan.**
   - **Cascading**: Istilah "cascading" berarti bahwa gaya diterapkan berdasarkan urutan prioritas tertentu. Jika ada beberapa aturan yang berlaku untuk elemen yang sama, urutan ini akan menentukan gaya mana yang digunakan.
   - **Specificity**: CSS juga menggunakan sistem prioritas (specificity) untuk menentukan gaya mana yang diterapkan ketika ada konflik antara beberapa aturan CSS.

3. **Cara Menulis CSS**
   - Ada tiga cara utama untuk menulis dan menerapkan CSS: **inline**, **internal**, dan **eksternal**. Setiap metode memiliki kegunaannya masing-masing.

   - **Inline CSS**
     - CSS ditulis langsung pada elemen HTML menggunakan atribut `style`. Ini berguna untuk perubahan cepat atau styling yang sangat spesifik.
     - **Contoh Penggunaan:**
       ```html
       <p style="color: blue; font-size: 18px;">Ini adalah teks berwarna biru.</p>
       ```

   - **Internal CSS**
     - CSS ditulis dalam tag `<style>` di dalam bagian `<head>` dari dokumen HTML. Ini digunakan untuk mendesain halaman web tunggal dengan aturan CSS yang spesifik.
     - **Contoh Penggunaan:**
       ```html
       <head>
           <style>
               body {
                   background-color: #f0f0f0;
               }
               h1 {
                   color: #333;
                   text-align: center;
               }
           </style>
       </head>
       ```

   - **Eksternal CSS**
     - CSS ditulis dalam file terpisah dengan ekstensi `.css`. Ini adalah metode terbaik untuk mengelola gaya untuk situs web yang besar dan kompleks, karena memungkinkan pemisahan konten dan tampilan yang jelas.
     - **Contoh Penggunaan:**
       - **File HTML:**
         ```html
         <head>
             <link rel="stylesheet" href="styles.css">
         </head>
         ```
       - **File CSS (styles.css):**
         ```css
         body {
             background-color: #f0f0f0;
         }
         h1 {
             color: #333;
             text-align: center;
         }
         ```

4. **CSS Cascade dan Specificity**
   - **CSS Cascade**: Aturan yang ditulis lebih dekat ke elemen (misalnya, inline) akan memiliki prioritas lebih tinggi daripada yang ditulis lebih jauh (misalnya, dalam file eksternal), kecuali ada aturan yang lebih spesifik.
   - **Specificity**: Aturan yang lebih spesifik (misalnya, berdasarkan ID) akan mengalahkan aturan yang lebih umum (misalnya, berdasarkan tag atau class).
     - **Contoh Specificity:**
       ```css
       /* Aturan umum untuk semua paragraf */
       p {
           color: black;
       }

       /* Aturan lebih spesifik untuk paragraf dengan class 'highlight' */
       .highlight {
           color: red;
       }

       /* Aturan paling spesifik untuk paragraf dengan ID 'unique' */
       #unique {
           color: blue;
       }
       ```

5. **Mengapa Menggunakan Eksternal CSS?**
   - **Keuntungan Eksternal CSS:**
     - **Pemeliharaan Mudah:** Satu file CSS dapat mengontrol banyak halaman, sehingga perubahan desain dapat dilakukan dengan lebih cepat dan efisien.
     - **Konsistensi:** Semua halaman di situs dapat berbagi gaya yang sama, sehingga tampilan menjadi konsisten.
     - **Kinerja:** Browser dapat menyimpan file CSS eksternal dalam cache, sehingga halaman web bisa dimuat lebih cepat.

6. **Contoh Penggunaan CSS untuk Halaman Web Sederhana:**
   - **File HTML:**
     ```html
     <!DOCTYPE html>
     <html lang="id">
     <head>
         <meta charset="UTF-8">
         <meta name="viewport" content="width=device-width, initial-scale=1.0">
         <link rel="stylesheet" href="styles.css">
         <title>Halaman Web Sederhana</title>
     </head>
     <body>
         <h1>Selamat Datang di Halaman Kelas XI PPLG 1</h1>
         <p>Kelas ini berfokus pada pemrograman dan desain web.</p>
     </body>
     </html>
     ```
   - **File CSS (styles.css):**
     ```css
     body {
         font-family: Arial, sans-serif;
         background-color: #f0f0f0;
         margin: 0;
         padding: 20px;
     }

     h1 {
         color: #333;
         text-align: center;
     }

     p {
         font-size: 16px;
         color: #555;
     }
     ```

#### **Praktikum Lengkap:**

1. **Latihan 1: Menggunakan Inline CSS**
   - Cobalah mengubah warna dan ukuran font dari beberapa elemen di halaman web menggunakan inline CSS.

   **Contoh Praktik:**
   ```html
   <p style="color: green; font-size: 20px;">Teks ini berwarna hijau dan berukuran besar.</p>
   ```

2. **Latihan 2: Menulis Internal CSS**
   - Buatlah halaman HTML yang menggunakan internal CSS untuk mengatur latar belakang halaman dan gaya teks.

   **Contoh Praktik:**
   ```html
   <!DOCTYPE html>
   <html lang="id">
   <head>
       <meta charset="UTF-8">
       <title>Halaman dengan Internal CSS</title>
       <style>
           body {
               background-color: lightblue;
           }
           h1 {
               color: navy;
               text-align: center;
           }
       </style>
   </head>
   <body>
       <h1>Ini adalah Judul dengan Internal CSS</h1>
       <p>Halaman ini menggunakan internal CSS untuk mengatur gaya.</p>
   </body>
   </html>
   ```

3. **Latihan 3: Menggunakan Eksternal CSS**
   - Buatlah dua halaman HTML yang menggunakan file CSS eksternal yang sama untuk mengatur gaya.

   **Contoh Praktik:**
   - **File HTML 1:**
     ```html
     <!DOCTYPE html>
     <html lang="id">
     <head>
         <meta charset="UTF-8">
         <link rel="stylesheet" href="styles.css">
         <title>Halaman 1</title>
     </head>
     <body>
         <h1>Halaman Pertama</h1>
         <p>Ini adalah halaman pertama yang menggunakan CSS eksternal.</p>
     </body>
     </html>
     ```
   - **File HTML 2:**
     ```html
     <!DOCTYPE html>
     <html lang="id">
     <head>
         <meta charset="UTF-8">
         <link rel="stylesheet" href="styles.css">
         <title>Halaman 2</title>
     </head>
     <body>
         <h1>Halaman Kedua</h1>
         <p>Ini adalah halaman kedua yang menggunakan CSS eksternal yang sama.</p>
     </body>
     </html>
     ```
   - **File CSS (styles.css):**
     ```css
     body {
         font-family: Arial, sans-serif;
         background-color: #e0e0e0;
         margin: 0;
         padding: 20px;
     }

     h1 {
         color: #333;
         text-align: center;
     }

     p {
         font-size: 16px;
         color: #555;
     }
     ```

#### **Diskusi dan Review:**

- **Mengapa Memisahkan CSS dari HTML Itu Penting?**
  - Diskusikan bagaimana pemisahan ini memudahkan pemeliharaan situs web, membuat kode lebih bersih, dan memungkinkan desain yang lebih konsisten di seluruh situs.

- **Bagaimana Mengelola Konflik Gaya dengan CSS Cascade dan Specificity?**
  - Diskusikan bagaimana cara mengelola prioritas gaya ketika ada konflik antara beberapa aturan CSS, dan pentingnya memahami sistem cascading dan specificity.