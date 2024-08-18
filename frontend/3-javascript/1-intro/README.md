### **Bab 25: Pengenalan JavaScript**

#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Memahami apa itu JavaScript dan peran pentingnya dalam pengembangan web.
- Mengetahui bagaimana JavaScript bekerja di dalam browser.
- Mengerti konsep dasar pemrograman dengan JavaScript dan bagaimana menggunakannya untuk membuat halaman web yang interaktif.

#### **Materi:**

1. **Apa Itu JavaScript?**
   - **Definisi JavaScript:**
     - JavaScript adalah bahasa pemrograman yang digunakan untuk membuat halaman web menjadi dinamis dan interaktif. Berbeda dengan HTML dan CSS yang digunakan untuk struktur dan tampilan, JavaScript memungkinkan kalian untuk mengubah konten halaman web secara langsung, merespons tindakan pengguna, dan banyak lagi.
   - **Sejarah Singkat JavaScript:**
     - JavaScript pertama kali dikembangkan oleh Brendan Eich pada tahun 1995 dan menjadi bagian dari Netscape Navigator, salah satu browser pertama yang populer. Awalnya, JavaScript dikenal dengan nama Mocha, kemudian berubah menjadi LiveScript sebelum akhirnya diberi nama JavaScript.
   - **Mengapa JavaScript Penting?**
     - JavaScript adalah bahasa yang membuat web lebih hidup. Tanpa JavaScript, situs web akan menjadi statis dan kurang interaktif. Misalnya, animasi, validasi form, dan manipulasi DOM semuanya dimungkinkan oleh JavaScript.

2. **Bagaimana JavaScript Bekerja di Browser?**
   - **Peran Browser:**
     - Browser memiliki mesin JavaScript yang mengeksekusi kode JavaScript. Setiap browser modern seperti Chrome, Firefox, dan Safari memiliki mesin JavaScript sendiri, seperti V8 untuk Chrome dan SpiderMonkey untuk Firefox.
   - **Interaksi dengan HTML dan CSS:**
     - JavaScript bekerja bersama HTML dan CSS. HTML memberikan struktur, CSS memberikan gaya, dan JavaScript menambahkan interaktivitas. JavaScript dapat mengubah elemen HTML dan CSS secara dinamis untuk menciptakan pengalaman pengguna yang lebih baik.
   - **Cara Kerja JavaScript:**
     - JavaScript dieksekusi di sisi klien (client-side), yang berarti kode dijalankan langsung di browser pengguna. Ini membuat halaman web lebih responsif karena tidak perlu mengirim permintaan kembali ke server untuk setiap interaksi kecil.

3. **Contoh Penggunaan JavaScript**
   - **Manipulasi DOM:**
     - Salah satu kegunaan paling umum dari JavaScript adalah manipulasi DOM (Document Object Model). Kalian bisa menambah, menghapus, atau mengubah elemen di halaman web secara langsung.
     - **Contoh:**
       ```html
       <button onclick="changeText()">Klik Saya</button>
       <p id="text">Teks ini akan berubah.</p>

       <script>
           function changeText() {
               document.getElementById("text").innerHTML = "Teks telah berubah!";
           }
       </script>
       ```
       - **Penjelasan:**
         - Ketika tombol diklik, teks pada paragraf akan berubah menjadi "Teks telah berubah!".

   - **Validasi Form:**
     - JavaScript sering digunakan untuk memvalidasi data yang dimasukkan pengguna sebelum data tersebut dikirim ke server.
     - **Contoh:**
       ```html
       <form onsubmit="return validateForm()">
           Nama: <input type="text" id="name">
           <input type="submit" value="Submit">
       </form>

       <script>
           function validateForm() {
               var name = document.getElementById("name").value;
               if (name == "") {
                   alert("Nama harus diisi!");
                   return false;
               }
               return true;
           }
       </script>
       ```
       - **Penjelasan:**
         - Jika pengguna mencoba mengirim form tanpa mengisi nama, JavaScript akan menampilkan pesan peringatan dan menghentikan pengiriman form.

   - **Interaktivitas:**
     - JavaScript memungkinkan halaman web untuk merespons tindakan pengguna seperti klik, hover, atau input.
     - **Contoh:**
       ```html
       <input type="text" oninput="showValue(this.value)">
       <p id="output"></p>

       <script>
           function showValue(val) {
               document.getElementById("output").innerText = "Kamu mengetik: " + val;
           }
       </script>
       ```
       - **Penjelasan:**
         - Saat pengguna mengetik di dalam input, teks pada paragraf akan berubah sesuai dengan apa yang mereka ketik.

4. **Kapan Menggunakan JavaScript?**
   - **Validasi Data:**
     - JavaScript sangat berguna untuk validasi data di sisi klien sebelum data dikirim ke server. Ini membantu mengurangi beban server dan memberikan umpan balik langsung kepada pengguna.
   - **Interaktivitas Halaman:**
     - JavaScript memungkinkan kalian untuk membuat halaman web yang interaktif, seperti dropdown menu, slider gambar, dan modals.
   - **Manipulasi Konten:**
     - Jika kalian perlu mengubah konten halaman tanpa memuat ulang seluruh halaman, JavaScript adalah alat yang tepat.

5. **Memulai dengan JavaScript**
   - **Menyisipkan JavaScript di HTML:**
     - Kalian bisa menyisipkan JavaScript langsung di dalam tag `<script>` pada file HTML, atau merujuk ke file JavaScript eksternal.
     - **Contoh:**
       ```html
       <script src="script.js"></script>
       ```
     - **Penjelasan:**
       - Kode ini akan memuat dan mengeksekusi file JavaScript eksternal bernama `script.js`.

   - **Menggunakan Console untuk Belajar:**
     - Saat memulai belajar JavaScript, kalian bisa menggunakan console di browser (biasanya bisa diakses dengan menekan `F12` atau `Ctrl+Shift+I` dan memilih tab "Console") untuk menulis dan menguji kode JavaScript secara langsung.

#### **Diskusi dan Review:**

- **Mengapa JavaScript Penting untuk Dipelajari?**
  - Diskusikan peran penting JavaScript dalam pengembangan web modern dan bagaimana ini berbeda dari HTML dan CSS.
  
- **Bagaimana JavaScript Membantu Membuat Halaman Web Interaktif?**
  - Diskusikan contoh-contoh bagaimana JavaScript bisa digunakan untuk menambahkan interaktivitas ke halaman web, seperti menampilkan atau menyembunyikan konten, dan merespons input pengguna.