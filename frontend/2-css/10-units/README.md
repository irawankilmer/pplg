### **Bab 22: Units**

#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Memahami berbagai jenis satuan (units) dalam CSS dan kapan menggunakan masing-masing.
- Menggunakan satuan seperti `px`, `em`, `rem`, `percent (%)`, `vh`, dan `vw` untuk mengatur ukuran elemen, margin, padding, dan lainnya di halaman web.
- Menerapkan satuan-satuan ini untuk membuat tata letak yang responsif dan fleksibel di berbagai ukuran layar.

#### **Materi:**

1. **Apa Itu CSS Units?**
   - **Definisi CSS Units:**
     - CSS Units adalah ukuran yang digunakan untuk menentukan ukuran berbagai elemen dalam CSS, seperti lebar, tinggi, margin, padding, font-size, dan lainnya. Satuan-satuan ini membantu kalian mengontrol ukuran dan tata letak elemen dengan presisi.
   - **Mengapa Memilih Units yang Tepat Penting?**
     - Memilih units yang tepat sangat penting karena mempengaruhi bagaimana halaman web ditampilkan di berbagai perangkat dan ukuran layar. Menggunakan units yang benar memungkinkan kalian membuat desain yang konsisten dan responsif.

2. **Jenis-Jenis CSS Units**

   - **Pixel (px)**
     - **Penjelasan:**
       - Pixel (`px`) adalah unit absolut yang mengukur ukuran elemen berdasarkan piksel layar. Satuan ini sering digunakan untuk mengatur ukuran elemen yang harus memiliki dimensi tetap dan tidak tergantung pada ukuran layar atau konteks.
     - **Contoh Penggunaan:**
       ```css
       h1 {
           font-size: 24px;
       }

       .box {
           width: 300px;
           height: 200px;
       }
       ```
       - **Penjelasan:**
         - `24px` menetapkan ukuran teks heading menjadi 24 piksel, dan `300px` x `200px` menetapkan ukuran elemen kotak dengan lebar dan tinggi tetap.

   - **Em (em)**
     - **Penjelasan:**
       - Em (`em`) adalah unit relatif yang mengukur ukuran elemen relatif terhadap ukuran font dari elemen induknya. 1em setara dengan ukuran font elemen induk. Satuan ini berguna untuk membuat ukuran elemen yang berskala sesuai dengan konteksnya.
     - **Contoh Penggunaan:**
       ```css
       p {
           font-size: 1.5em; /* 1.5 kali ukuran font dari elemen induk */
       }

       .nested {
           font-size: 2em; /* 2 kali ukuran font dari elemen induk */
       }
       ```
       - **Penjelasan:**
         - `1.5em` menetapkan ukuran font paragraf menjadi 1,5 kali ukuran font dari elemen induk. `2em` menetapkan ukuran font elemen nested menjadi dua kali ukuran font dari elemen induk.

   - **Rem (rem)**
     - **Penjelasan:**
       - Rem (`rem`) adalah unit relatif yang mengukur ukuran elemen relatif terhadap ukuran font dari root element (`<html>`). Rem sering digunakan untuk menciptakan skala yang konsisten di seluruh halaman.
     - **Contoh Penggunaan:**
       ```css
       html {
           font-size: 16px;
       }

       p {
           font-size: 1.5rem; /* 1.5 kali ukuran font dari root element */
       }
       ```
       - **Penjelasan:**
         - `1.5rem` menetapkan ukuran font paragraf menjadi 1,5 kali ukuran font dari root element (`<html>`), yang di sini adalah 16px.

   - **Persen (%)**
     - **Penjelasan:**
       - Persen (`%`) adalah unit relatif yang mengukur ukuran elemen berdasarkan persentase dari elemen induknya. Satuan ini sangat berguna untuk membuat elemen yang skalanya relatif terhadap elemen lain.
     - **Contoh Penggunaan:**
       ```css
       .container {
           width: 80%;
       }

       .child {
           width: 50%; /* 50% dari lebar elemen induk */
       }
       ```
       - **Penjelasan:**
         - `80%` menetapkan lebar container menjadi 80% dari lebar elemen induk, dan `50%` menetapkan lebar elemen anak menjadi 50% dari lebar container.

   - **Viewport Width (vw) dan Viewport Height (vh)**
     - **Penjelasan:**
       - `vw` dan `vh` adalah units relatif yang mengukur ukuran elemen berdasarkan persentase dari lebar viewport (`vw`) atau tinggi viewport (`vh`). Satuan ini sangat berguna untuk membuat elemen yang responsif terhadap ukuran layar.
     - **Contoh Penggunaan:**
       ```css
       .fullscreen {
           width: 100vw; /* 100% lebar viewport */
           height: 100vh; /* 100% tinggi viewport */
       }
       ```
       - **Penjelasan:**
         - `100vw` menetapkan lebar elemen menjadi 100% dari lebar viewport, dan `100vh` menetapkan tinggi elemen menjadi 100% dari tinggi viewport, membuat elemen tersebut mengisi seluruh layar.

3. **Penggunaan Kombinasi Units**

   - **Menggabungkan Units untuk Efek Responsif:**
     - Kalian bisa menggabungkan berbagai units dalam satu elemen untuk mencapai efek desain yang lebih dinamis dan responsif.
     - **Contoh Penggunaan:**
       ```css
       .responsive-box {
           width: 50%;
           padding: 1em;
           font-size: 2vw;
           margin: 10px;
       }
       ```
       - **Penjelasan:**
         - Lebar elemen ditetapkan menjadi 50% dari elemen induk, padding ditetapkan dengan `em`, font-size menggunakan `vw` untuk membuatnya berskala dengan lebar layar, dan margin ditetapkan dengan `px` untuk memberikan jarak tetap antar elemen.

4. **Kapan Menggunakan Units Tertentu**

   - **Kapan Menggunakan `px`:**
     - Gunakan `px` untuk elemen yang harus memiliki ukuran tetap, seperti border atau margin yang tidak berubah ukurannya berdasarkan konteks atau perangkat.
   - **Kapan Menggunakan `em` dan `rem`:**
     - Gunakan `em` dan `rem` untuk elemen yang harus berskala dengan ukuran font, seperti font-size, padding, dan margin. `rem` lebih stabil karena hanya bergantung pada root element, sedangkan `em` bergantung pada elemen induk langsung.
   - **Kapan Menggunakan `%`, `vw`, dan `vh`:**
     - Gunakan `%` untuk ukuran yang harus berskala dengan elemen induk, dan gunakan `vw` serta `vh` untuk elemen yang harus berskala dengan lebar dan tinggi layar.

5. **Contoh Penggunaan Units dalam Desain Halaman Web**

   - **Contoh Praktik Units:**
     ```css
     body {
         font-size: 16px;
     }

     .container {
         width: 80%;
         max-width: 1200px;
         margin: 0 auto;
     }

     .header {
         font-size: 2rem;
         padding: 20px;
         background-color: #333;
         color: white;
         text-align: center;
     }

     .box {
         width: 50%;
         padding: 1em;
         font-size: 1.5rem;
         margin: 2vh 0;
         background-color: #f4f4f4;
     }
     ```

   **HTML:**
   ```html
   <body>
       <div class="container">
           <div class="header">Header Halaman</div>
           <div class="box">Ini adalah konten dengan ukuran yang fleksibel.</div>
           <div class="box">Ini adalah konten lain yang juga fleksibel.</div>
       </div>
   </body>
   ```

#### **Praktikum Lengkap:**

1. **Latihan 1: Menggunakan Units untuk Responsivitas**
   - Buatlah tata letak dengan menggunakan kombinasi units untuk membuat elemen yang berskala secara responsif berdasarkan ukuran layar dan elemen induk.

   **Contoh Praktik:**
   ```css
   .container {
       width: 90%;
       max-width: 1000px;
       margin: 0 auto;
   }

   .responsive-text {
       font-size: 2vw;
       padding: 1em;
       background-color: lightblue;
   }

   .fixed-box {
       width: 300px;
       height: 200px;
       margin: 10px;
       background-color: lightcoral;
   }
   ```

   **HTML:**
   ```html
   <div class="container">
       <div class="responsive-text">Teks ini responsif terhadap lebar layar.</div>
       <div class="fixed-box">Ini adalah kotak dengan ukuran tetap.</div>
   </div>
   ```

2. **Latihan 2: Menggunakan `em` dan `rem` untuk Konsistensi Ukuran**
   - Buatlah halaman dengan teks dan elemen yang menggunakan `em` dan `rem` untuk ukuran font, padding, dan margin, sehingga skala elemen menjadi konsisten dan responsif.

   **Contoh Praktik:**
   ```

css
   html {
       font-size: 18px;
   }

   h1 {
       font-size: 2.5rem;
   }

   p {
       font-size: 1rem;
       padding: 1.5em;
       margin-bottom: 2em;
       background-color: #f0f0f0;
   }
   ```

   **HTML:**
   ```html
   <h1>Judul Besar</h1>
   <p>Paragraf ini memiliki padding dan margin yang berskala dengan ukuran font, membuatnya lebih konsisten.</p>
   <p>Ini adalah paragraf lain dengan pengaturan yang sama.</p>
   ```

#### **Diskusi dan Review:**

- **Bagaimana Menggunakan Units untuk Meningkatkan Responsivitas?**
  - Diskusikan bagaimana menggabungkan berbagai units untuk membuat tata letak halaman yang lebih responsif dan fleksibel di berbagai perangkat.

- **Apa Tantangan dalam Menggunakan Units Relatif?**
  - Diskusikan tantangan dalam menggunakan units relatif seperti `em` dan `rem`, terutama dalam menjaga konsistensi ukuran dan memastikan kompatibilitas di berbagai perangkat.