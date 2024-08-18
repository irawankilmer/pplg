### **Bab 23: Transitions and Animations**

#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Memahami konsep dasar dan perbedaan antara **transition** dan **animation** dalam CSS.
- Menggunakan properti seperti `transition`, `transform`, dan `animation` untuk menciptakan efek animasi yang menarik dan interaktif di halaman web.
- Menerapkan teknik-teknik animasi CSS untuk membuat halaman web lebih dinamis dan interaktif, dengan cara yang tidak mengganggu pengalaman pengguna.

#### **Materi:**

1. **Apa Itu Transitions dalam CSS?**
   - **Definisi Transitions:**
     - Transition dalam CSS adalah cara untuk mengubah properti CSS secara bertahap dari satu nilai ke nilai lainnya dalam periode waktu tertentu. Misalnya, kalian bisa membuat warna latar belakang tombol berubah perlahan saat pengguna mengarahkan kursor di atasnya.
   - **Mengapa Transitions Penting?**
     - Transitions memberikan pengalaman yang lebih halus dan menyenangkan bagi pengguna, serta menambah interaktivitas ke halaman web tanpa memerlukan JavaScript. Efek transisi juga dapat membantu pengguna memahami interaksi di halaman, seperti perubahan visual saat tombol diklik atau link dihover.

2. **Properti-Properti Utama dalam Transitions**

   - **`transition-property`**
     - **Penjelasan:**
       - Properti `transition-property` menentukan properti CSS mana yang akan mengalami transisi. Kalian bisa menentukan satu atau lebih properti yang ingin diubah.
     - **Contoh Penggunaan:**
       ```css
       button {
           transition-property: background-color, transform;
       }
       ```
       - **Penjelasan:**
         - Transisi akan terjadi pada perubahan warna latar belakang dan transformasi elemen.

   - **`transition-duration`**
     - **Penjelasan:**
       - Properti `transition-duration` menentukan berapa lama transisi akan berlangsung. Nilainya bisa dalam detik (`s`) atau milidetik (`ms`).
     - **Contoh Penggunaan:**
       ```css
       button {
           transition-duration: 0.5s;
       }
       ```
       - **Penjelasan:**
         - Transisi akan berlangsung selama 0,5 detik (500 milidetik).

   - **`transition-timing-function`**
     - **Penjelasan:**
       - Properti `transition-timing-function` mengontrol kecepatan transisi. Nilai umum termasuk `ease`, `linear`, `ease-in`, `ease-out`, dan `ease-in-out`.
     - **Contoh Penggunaan:**
       ```css
       button {
           transition-timing-function: ease-in-out;
       }
       ```
       - **Penjelasan:**
         - Transisi akan dimulai dan berakhir dengan kecepatan yang lebih lambat, dan lebih cepat di tengah-tengah.

   - **`transition-delay`**
     - **Penjelasan:**
       - Properti `transition-delay` menentukan jeda waktu sebelum transisi dimulai. Ini juga bisa dalam detik atau milidetik.
     - **Contoh Penggunaan:**
       ```css
       button {
           transition-delay: 0.2s;
       }
       ```
       - **Penjelasan:**
         - Transisi akan dimulai setelah jeda 0,2 detik.

   - **Contoh Lengkap Penggunaan Transitions:**
     ```css
     button {
         background-color: #4CAF50;
         color: white;
         padding: 15px 32px;
         font-size: 16px;
         transition: background-color 0.3s ease-in-out, transform 0.3s ease-in-out;
     }

     button:hover {
         background-color: #45a049;
         transform: scale(1.1);
     }
     ```
     - **Penjelasan:**
       - Tombol akan berubah warna latar belakangnya dan sedikit membesar (scale) saat pengguna mengarahkan kursor di atasnya, dengan durasi transisi 0,3 detik.

3. **Apa Itu Animations dalam CSS?**
   - **Definisi Animations:**
     - Animation dalam CSS adalah cara untuk membuat elemen berubah dari satu kondisi ke kondisi lain secara bertahap dan berulang. Animasi ini bisa lebih kompleks daripada transisi, karena kalian bisa mengontrol banyak langkah dan properti yang berubah seiring waktu.
   - **Mengapa Animations Penting?**
     - Animations memungkinkan kalian membuat efek visual yang dinamis dan menarik tanpa memerlukan JavaScript. Kalian bisa membuat animasi yang berjalan otomatis ketika halaman dimuat atau dipicu oleh interaksi pengguna, seperti ketika tombol diklik.

4. **Properti-Properti Utama dalam Animations**

   - **`@keyframes`**
     - **Penjelasan:**
       - `@keyframes` adalah aturan yang digunakan untuk menentukan langkah-langkah animasi. Kalian mendefinisikan `keyframes` untuk menentukan bagaimana elemen akan berubah pada berbagai tahap animasi.
     - **Contoh Penggunaan:**
       ```css
       @keyframes example {
           0% { background-color: red; }
           50% { background-color: yellow; }
           100% { background-color: green; }
       }
       ```
       - **Penjelasan:**
         - Animasi ini akan mengubah warna latar belakang dari merah, ke kuning, dan akhirnya menjadi hijau.

   - **`animation-name`**
     - **Penjelasan:**
       - Properti `animation-name` menentukan nama animasi yang akan digunakan pada elemen. Nama ini harus sesuai dengan nama `@keyframes` yang telah ditentukan.
     - **Contoh Penggunaan:**
       ```css
       div {
           animation-name: example;
       }
       ```

   - **`animation-duration`**
     - **Penjelasan:**
       - Properti `animation-duration` menentukan berapa lama animasi akan berlangsung. Nilainya bisa dalam detik (`s`) atau milidetik (`ms`).
     - **Contoh Penggunaan:**
       ```css
       div {
           animation-duration: 4s;
       }
       ```

   - **`animation-timing-function`**
     - **Penjelasan:**
       - Properti `animation-timing-function` mengontrol kecepatan animasi. Nilai yang umum termasuk `ease`, `linear`, `ease-in`, `ease-out`, dan `ease-in-out`, sama seperti pada `transition-timing-function`.
     - **Contoh Penggunaan:**
       ```css
       div {
           animation-timing-function: ease-in-out;
       }
       ```

   - **`animation-delay`**
     - **Penjelasan:**
       - Properti `animation-delay` menentukan jeda waktu sebelum animasi dimulai.
     - **Contoh Penggunaan:**
       ```css
       div {
           animation-delay: 2s;
       }
       ```

   - **`animation-iteration-count`**
     - **Penjelasan:**
       - Properti `animation-iteration-count` menentukan berapa kali animasi akan diulang. Nilai `infinite` akan membuat animasi berulang terus-menerus.
     - **Contoh Penggunaan:**
       ```css
       div {
           animation-iteration-count: infinite;
       }
       ```

   - **Contoh Lengkap Penggunaan Animations:**
     ```css
     @keyframes move {
         0% { transform: translateX(0); }
         50% { transform: translateX(100px); }
         100% { transform: translateX(0); }
     }

     .box {
         width: 100px;
         height: 100px;
         background-color: blue;
         animation: move 3s ease-in-out infinite;
     }
     ```
     - **Penjelasan:**
       - Kotak akan bergerak dari kiri ke kanan dan kembali lagi dalam 3 detik, dan animasi akan terus berulang tanpa henti.

5. **Menggabungkan Transitions dan Animations untuk Efek yang Lebih Menarik**

   - **Menggunakan Transitions dengan Animations:**
     - Kalian bisa menggabungkan transition dengan animation untuk membuat interaksi pengguna yang lebih halus. Misalnya, animasi dapat dimulai setelah transisi selesai, atau transisi digunakan untuk menambah efek pada animasi yang berjalan.
     - **Contoh Penggunaan:**
       ```css
       .hover-box {
           width: 100px;
           height: 100px;
           background-color: red;
           transition: transform 0.5s ease-in-out;
           animation: pulse 2s infinite;
       }

       .hover-box:hover {
           transform: scale(1.2);
       }

       @keyframes pulse {
           0% { background-color: red; }
           50% { background-color: pink; }
           100% { background-color: red; }
       }
       ```
       - **Penjelasan:**
         - Kotak akan berdenyut (pulse) dengan animasi warna, dan ketika pengguna mengarahkan kursor di atasnya, kotak tersebut akan membesar dengan transisi yang halus.

6. **Contoh Penggunaan Transitions dan Animations dalam Desain Halaman Web**

   - **Contoh Praktik Transitions dan Animations:**
     ```css
     .menu-item {
         padding: 10px 20px;
         background-color: #3498db;
         color: white;
         text-align: center;
         transition: background-color 0.3s ease-in-out, transform 0.3s ease-in-out;
         animation: fadeIn 1s ease-in;
     }

     .menu-item:hover {
         background-color: #2980b9;
         transform: translateY(-5px);
     }

     @keyframes fadeIn {
         from {
             opacity: 0;
         }
         to {
             opacity: 1;
         }
     }
     ```

     **Penjelasan:**
     - Elemen `.menu-item` akan muncul dengan efek fade-in saat halaman dimuat, berkat animasi `fadeIn`. Ketika pengguna mengarahkan kursor di atasnya, warna latar belakang akan berubah, dan elemen akan sedikit terangkat ke atas dengan transisi yang halus.

   **HTML:**
   ```html
   <div class="menu-item">Home</div>
   <div class="menu-item">About</div>
   <div class="menu-item">Contact</div>
   ```

7. **Tips dan Praktik Terbaik dalam Menggunakan Transitions dan Animations**

   - **Gunakan dengan Bijak:**
     - Terlalu banyak animasi atau transisi dapat mengganggu pengguna. Pastikan untuk hanya menggunakan efek yang mendukung fungsi dan estetika halaman.
   - **Perhatikan Performa:**
     - Animasi yang kompleks dapat mempengaruhi performa halaman, terutama pada perangkat dengan sumber daya terbatas. Uji animasi pada berbagai perangkat untuk memastikan performa yang optimal.
   - **Jangan Lupakan Aksesibilitas:**
     - Pastikan animasi tidak mengganggu pengguna dengan kebutuhan khusus, seperti mereka yang menderita sensitivitas terhadap gerakan. Pertimbangkan untuk menambahkan opsi untuk menonaktifkan animasi jika diperlukan.

#### **Praktikum Lengkap:**

1. **Latihan 1: Membuat Animasi Hover pada Tombol**
   - Cobalah membuat tombol yang berubah warna dan ukurannya saat dihover menggunakan kombinasi transitions dan animations.

   **Contoh Praktik:**
   ```css
   .hover-button {
       padding: 15px 30px;
       background-color: #e74c3c;
       color: white;
       border: none;
       cursor: pointer;
       transition: background-color 0.3s ease, transform 0.3s ease;
       animation: grow 1s infinite alternate;
   }

   .hover-button:hover {
       background-color: #c0392b;
       transform: scale(1.1);
   }

   @keyframes grow {
       from {
           transform: scale(1);
       }
       to {
           transform: scale(1.05);
       }
   }
   ```

   **HTML:**
   ```html
   <button class="hover-button">Klik Saya</button>
   ```

2. **Latihan 2: Membuat Animasi Berulang pada Background**
   - Buatlah elemen yang memiliki latar belakang dengan warna yang berubah-ubah secara terus menerus menggunakan CSS animations.

   **Contoh Praktik:**
   ```css
   .animated-bg {
       width: 100%;
       height: 200px;
       background-color: #3498db;
       animation: colorChange 5s infinite;
   }

   @keyframes colorChange {
       0% { background-color: #3498db; }
       25% { background-color: #9b59b6; }
       50% { background-color: #e74c3c; }
       75% { background-color: #f1c40f; }
       100% { background-color: #3498db; }
   }
   ```

   **HTML:**
   ```html
   <div class="animated-bg"></div>
   ```

#### **Diskusi dan Review:**

- **Kapan Menggunakan Transitions vs. Animations?**
  - Diskusikan kapan sebaiknya menggunakan transitions (untuk efek sederhana pada perubahan state) dan kapan menggunakan animations (untuk efek yang lebih kompleks dan berulang).
  
- **Bagaimana Menjaga Keseimbangan dalam Animasi?**
  - Diskusikan pentingnya keseimbangan dalam penggunaan animasi untuk memastikan bahwa efek visual mendukung pengalaman pengguna tanpa mengganggu.