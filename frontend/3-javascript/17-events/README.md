### **Bab 41: Events**

#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Memahami berbagai jenis event yang ada dalam JavaScript dan bagaimana cara menanganinya.
- Menambahkan event listener untuk menangani event seperti **click**, **submit**, **load**, **change**, **focus**, dan **blur**.
- Memahami dan mengendalikan **event propagation** melalui bubbling dan capturing.

#### **Materi:**

1. **Apa Itu Event dalam JavaScript?**
   - **Definisi Event:**
     - Event adalah tindakan atau kejadian yang terjadi di halaman web, seperti pengguna mengklik tombol, mengisi formulir, atau memuat halaman. JavaScript dapat digunakan untuk mendeteksi dan merespons event ini, memungkinkan interaksi dinamis dengan pengguna.
   - **Mengapa Event Penting?**
     - Event penting karena mereka memungkinkan halaman web menjadi interaktif dan responsif terhadap tindakan pengguna, yang sangat penting dalam pengalaman pengguna modern.

2. **Menambahkan Event Listener**
   - **Penjelasan:**
     - Event listener adalah function yang dijalankan ketika event tertentu terjadi. Event listener dapat ditambahkan menggunakan metode `addEventListener`.
   - **Sintaks Dasar:**
     ```javascript
     element.addEventListener('event', function, useCapture);
     ```
   - **Contoh Penggunaan:**
     ```javascript
     let button = document.querySelector("button");
     button.addEventListener("click", function() {
         alert("Tombol diklik!");
     });
     ```
     - **Penjelasan:**
       - Event listener ditambahkan ke elemen tombol (`button`) yang akan menampilkan pesan saat tombol diklik.

3. **Jenis-jenis Event yang Umum Digunakan**

   - **Click Event:**
     - **Penjelasan:**
       - Event `click` terjadi ketika pengguna mengklik elemen, seperti tombol, tautan, atau gambar.
     - **Contoh Penggunaan:**
       ```javascript
       let button = document.querySelector("button");
       button.addEventListener("click", function() {
           console.log("Tombol diklik.");
       });
       ```

   - **Submit Event:**
     - **Penjelasan:**
       - Event `submit` terjadi ketika formulir dikirimkan. Ini biasanya digunakan untuk memvalidasi input sebelum dikirim ke server.
     - **Contoh Penggunaan:**
       ```javascript
       let form = document.querySelector("form");
       form.addEventListener("submit", function(event) {
           event.preventDefault(); // Mencegah pengiriman formulir
           console.log("Formulir dikirimkan.");
       });
       ```

   - **Load Event:**
     - **Penjelasan:**
       - Event `load` terjadi ketika seluruh halaman atau elemen seperti gambar atau script selesai dimuat.
     - **Contoh Penggunaan:**
       ```javascript
       window.addEventListener("load", function() {
           console.log("Halaman selesai dimuat.");
       });
       ```

   - **Change Event:**
     - **Penjelasan:**
       - Event `change` terjadi ketika nilai elemen form seperti input, textarea, atau select berubah.
     - **Contoh Penggunaan:**
       ```javascript
       let select = document.querySelector("select");
       select.addEventListener("change", function() {
           console.log("Pilihan berubah menjadi: " + select.value);
       });
       ```

   - **Focus dan Blur Events:**
     - **Penjelasan:**
       - Event `focus` terjadi ketika elemen form seperti input atau textarea mendapatkan fokus, sementara `blur` terjadi ketika elemen kehilangan fokus.
     - **Contoh Penggunaan:**
       ```javascript
       let input = document.querySelector("input");
       input.addEventListener("focus", function() {
           console.log("Input mendapatkan fokus.");
       });

       input.addEventListener("blur", function() {
           console.log("Input kehilangan fokus.");
       });
       ```

4. **Event Propagation: Bubbling dan Capturing**
   - **Penjelasan:**
     - Event propagation adalah cara event ditangani dalam DOM. Ada dua fase utama dalam event propagation: **bubbling** dan **capturing**.
     - **Bubbling**: Event ditangani pertama kali oleh elemen target, kemudian naik ke elemen induk.
     - **Capturing**: Event ditangani pertama kali oleh elemen induk, kemudian turun ke elemen target.
   - **Menangani Event Bubbling:**
     - **Contoh Penggunaan:**
       ```javascript
       document.querySelector("#child").addEventListener("click", function() {
           console.log("Child diklik");
       });

       document.querySelector("#parent").addEventListener("click", function() {
           console.log("Parent diklik");
       });
       ```
     - **Penjelasan:**
       - Jika elemen `#child` diklik, pesan "Child diklik" akan muncul terlebih dahulu, diikuti oleh "Parent diklik" karena event bubbling.
   - **Menangani Event Capturing:**
     - **Contoh Penggunaan:**
       ```javascript
       document.querySelector("#parent").addEventListener("click", function() {
           console.log("Parent diklik");
       }, true); // Menambahkan event listener pada fase capturing

       document.querySelector("#child").addEventListener("click", function() {
           console.log("Child diklik");
       });
       ```
     - **Penjelasan:**
       - Jika `#child` diklik, pesan "Parent diklik" akan muncul terlebih dahulu karena capturing, diikuti oleh "Child diklik".

   - **Menghentikan Event Propagation:**
     - **Penjelasan:**
       - `stopPropagation` digunakan untuk menghentikan propagation event lebih lanjut, baik di fase bubbling maupun capturing.
     - **Contoh Penggunaan:**
       ```javascript
       document.querySelector("#child").addEventListener("click", function(event) {
           event.stopPropagation();
           console.log("Child diklik, propagation dihentikan.");
       });

       document.querySelector("#parent").addEventListener("click", function() {
           console.log("Parent diklik");
       });
       ```

5. **Delegasi Event**
   - **Penjelasan:**
     - Delegasi event adalah teknik di mana event listener ditempatkan pada elemen induk untuk menangani event pada elemen anak, memungkinkan pengelolaan event yang lebih efisien.
   - **Contoh Penggunaan:**
     ```javascript
     document.querySelector("#parent").addEventListener("click", function(event) {
         if (event.target && event.target.matches("button")) {
             console.log("Tombol diklik: " + event.target.textContent);
         }
     });
     ```

#### **Praktikum Lengkap:**

1. **Latihan 1: Menambahkan Event Listener ke Tombol**
   - Buat event listener untuk tombol yang menampilkan pesan di konsol saat tombol diklik.
   **Contoh Praktik:**
   ```javascript
   let button = document.querySelector("button");
   button.addEventListener("click", function() {
       console.log("Tombol diklik.");
   });
   ```

2. **Latihan 2: Menggunakan Event `submit` untuk Validasi Formulir**
   - Buat event listener untuk menangani pengiriman formulir dan mencegah pengiriman jika validasi gagal.
   **Contoh Praktik:**
   ```javascript
   let form = document.querySelector("form");
   form.addEventListener("submit", function(event) {
       let input = document.querySelector("input").value;
       if (input === "") {
           event.preventDefault();
           console.log("Formulir tidak boleh kosong.");
       }
   });
   ```

3. **Latihan 3: Menangani Event Propagation dengan Bubbling**
   - Tambahkan event listener pada elemen induk dan anak, dan perhatikan bagaimana event bubbling bekerja.
   **Contoh Praktik:**
   ```javascript
   document.querySelector("#parent").addEventListener("click", function() {
       console.log("Parent diklik.");
   });

   document.querySelector("#child").addEventListener("click", function() {
       console.log("Child diklik.");
   });
   ```

4. **Latihan 4: Menggunakan Event Delegation**
   - Gunakan delegasi event untuk menangani klik pada beberapa tombol di dalam elemen induk yang sama.
   **Contoh Praktik:**
   ```javascript
   document.querySelector("#button-container").addEventListener("click", function(event) {
       if (event.target && event.target.matches("button")) {
           console.log("Tombol diklik: " + event.target.textContent);
       }
   });
   ```

#### **Diskusi dan Review:**

- **Mengapa Event Bubbling dan Capturing Penting untuk Dipahami?**
  - **Diskusi:**
    - Memahami event bubbling dan capturing penting karena mereka mempengaruhi cara event ditangani di dalam DOM. Pengetahuan ini memungkinkan kalian untuk mengontrol bagaimana dan kapan event ditangani, yang berguna dalam pengembangan aplikasi web yang kompleks.

- **Kapan Sebaiknya Menggunakan Delegasi Event?**
  - **Diskusi:**
    - Delegasi event sangat berguna ketika kalian memiliki banyak elemen anak yang memerlukan event listener. Ini memungkinkan kalian untuk menempatkan satu event listener pada elemen induk dan menangani event dari elemen anak, yang lebih efisien daripada menambahkan event listener ke setiap elemen

 anak.

- **Bagaimana `stopPropagation` Membantu Mengendalikan Event Propagation?**
  - **Diskusi:**
    - `stopPropagation` digunakan untuk menghentikan propagasi event lebih lanjut, baik di fase bubbling maupun capturing. Ini memberikan kontrol lebih besar dalam menangani event, terutama ketika kalian tidak ingin event menyebar ke elemen induk.