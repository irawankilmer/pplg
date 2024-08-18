### **Bab 39: Asynchronous**

#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Memahami konsep dasar asinkron dalam JavaScript dan mengapa asinkronitas penting dalam pengembangan web.
- Menggunakan **Promises** untuk menangani operasi asinkron.
- Menggunakan **async/await** untuk menulis kode asinkron yang lebih mudah dibaca.
- Menggunakan **callbacks** dan memahami konsep **callback hell** serta cara menghindarinya.

#### **Materi:**

1. **Apa Itu Asynchronous JavaScript?**
   - **Definisi Asynchronous:**
     - Asynchronous atau asinkron dalam JavaScript berarti bahwa beberapa operasi dapat berjalan di latar belakang dan tidak akan memblokir eksekusi kode lainnya. Hal ini memungkinkan program JavaScript untuk tetap responsif meskipun sedang menjalankan operasi yang memakan waktu, seperti pengambilan data dari server.
   - **Mengapa Asynchronous Penting?**
     - Asynchronous penting karena memungkinkan aplikasi web untuk tetap interaktif dan responsif, terutama saat berhadapan dengan operasi yang memerlukan waktu lama, seperti permintaan jaringan atau pemrosesan data besar.

2. **Callbacks**
   - **Penjelasan:**
     - Callback adalah function yang dilewatkan sebagai argumen ke function lain dan dipanggil setelah operasi tertentu selesai. Ini adalah cara tradisional untuk menangani operasi asinkron di JavaScript.
   - **Sintaks Dasar:**
     ```javascript
     function getData(callback) {
         setTimeout(() => {
             console.log("Data diambil dari server.");
             callback();
         }, 1000);
     }

     function displayData() {
         console.log("Data ditampilkan di layar.");
     }

     getData(displayData);
     ```
   - **Penjelasan:**
     - `getData` adalah function asinkron yang menerima callback. Setelah data "diambil", callback `displayData` dipanggil untuk menampilkan data.

3. **Callback Hell**
   - **Penjelasan:**
     - Callback hell terjadi ketika kalian memiliki banyak callback bersarang, membuat kode sulit dibaca dan dipelihara.
   - **Contoh Callback Hell:**
     ```javascript
     getData(function(result) {
         processResult(result, function(processed) {
             saveResult(processed, function(saved) {
                 console.log("Data berhasil diproses dan disimpan.");
             });
         });
     });
     ```
     - **Penjelasan:**
       - Pada contoh di atas, callback bersarang satu sama lain, yang membuat kode menjadi kompleks dan sulit dipahami. Ini dikenal sebagai callback hell.

4. **Promises**
   - **Penjelasan:**
     - Promises adalah cara modern untuk menangani operasi asinkron di JavaScript. Promise adalah objek yang mewakili penyelesaian (atau kegagalan) dari operasi asinkron. Promise memiliki tiga status: **pending** (sedang berlangsung), **fulfilled** (berhasil), dan **rejected** (gagal).
   - **Sintaks Dasar:**
     ```javascript
     let promise = new Promise((resolve, reject) => {
         let success = true; // Contoh kondisi
         if (success) {
             resolve("Operasi berhasil.");
         } else {
             reject("Operasi gagal.");
         }
     });

     promise.then(result => {
         console.log(result);
     }).catch(error => {
         console.log(error);
     });
     ```
   - **Penjelasan:**
     - Pada contoh di atas, sebuah Promise dibuat yang akan menyelesaikan (resolve) atau gagal (reject) berdasarkan kondisi tertentu. Kode yang dijalankan ketika Promise berhasil diletakkan dalam `then`, sementara yang gagal ditangani dalam `catch`.

5. **Chaining Promises**
   - **Penjelasan:**
     - Kalian dapat menghubungkan beberapa `then` untuk melakukan beberapa operasi secara berurutan.
   - **Contoh Penggunaan:**
     ```javascript
     let promise = new Promise((resolve, reject) => {
         resolve(5);
     });

     promise.then(result => {
         console.log(result); // Output: 5
         return result * 2;
     }).then(result => {
         console.log(result); // Output: 10
         return result * 3;
     }).then(result => {
         console.log(result); // Output: 30
     }).catch(error => {
         console.log(error);
     });
     ```
     - **Penjelasan:**
       - Pada contoh di atas, hasil dari setiap `then` diteruskan ke `then` berikutnya, memungkinkan operasi berantai yang lebih mudah dibaca dan dipelihara.

6. **Async/Await**
   - **Penjelasan:**
     - `async` dan `await` adalah sintaks modern untuk menulis kode asinkron yang terlihat lebih seperti kode sinkron. `async` digunakan untuk mendefinisikan function asinkron, dan `await` digunakan untuk menunggu penyelesaian Promise di dalam function asinkron tersebut.
   - **Sintaks Dasar:**
     ```javascript
     async function fetchData() {
         try {
             let response = await fetch("https://api.example.com/data");
             let data = await response.json();
             console.log(data);
         } catch (error) {
             console.log("Terjadi kesalahan: " + error.message);
         }
     }

     fetchData();
     ```
   - **Penjelasan:**
     - Pada contoh di atas, `fetchData` adalah function asinkron yang menggunakan `await` untuk menunggu hasil dari `fetch` dan `response.json()`. Jika terjadi kesalahan, itu ditangani dalam blok `catch`.

7. **Menggunakan Async/Await untuk Menghindari Callback Hell**
   - **Penjelasan:**
     - `async/await` memungkinkan kalian untuk menulis kode yang terlihat lebih linier dan menghindari callback hell.
   - **Contoh Penggunaan:**
     ```javascript
     async function processData() {
         try {
             let data = await getData();
             let processed = await processResult(data);
             await saveResult(processed);
             console.log("Data berhasil diproses dan disimpan.");
         } catch (error) {
             console.log("Kesalahan: " + error.message);
         }
     }

     processData();
     ```

#### **Praktikum Lengkap:**

1. **Latihan 1: Menggunakan Callbacks**
   - Buat function dengan callback yang mensimulasikan pengambilan data dan menampilkan hasilnya.
   **Contoh Praktik:**
   ```javascript
   function ambilData(callback) {
       setTimeout(() => {
           console.log("Data diambil dari server.");
           callback();
       }, 1000);
   }

   function tampilkanData() {
       console.log("Data ditampilkan di layar.");
   }

   ambilData(tampilkanData);
   ```

2. **Latihan 2: Membuat dan Menggunakan Promises**
   - Buat sebuah Promise yang mensimulasikan operasi asinkron dan tangani hasil atau kesalahannya.
   **Contoh Praktik:**
   ```javascript
   let janji = new Promise((resolve, reject) => {
       let sukses = true; // Ganti ini untuk melihat hasil yang berbeda
       if (sukses) {
           resolve("Operasi berhasil.");
       } else {
           reject("Operasi gagal.");
       }
   });

   janji.then(result => {
       console.log(result);
   }).catch(error => {
       console.log(error);
   });
   ```

3. **Latihan 3: Chaining Promises**
   - Gunakan chaining untuk melakukan beberapa operasi secara berurutan dengan Promises.
   **Contoh Praktik:**
   ```javascript
   let janji = new Promise((resolve) => {
       resolve(2);
   });

   janji.then(result => {
       console.log(result); // Output: 2
       return result + 2;
   }).then(result => {
       console.log(result); // Output: 4
       return result * 3;
   }).then(result => {
       console.log(result); // Output: 12
   }).catch(error => {
       console.log(error);
   });
   ```

4. **Latihan 4: Menggunakan Async/Await untuk Kode yang Lebih Mudah Dibaca**
   - Buat function asinkron yang menggunakan `async/await` untuk menangani operasi asinkron secara berurutan.
   **Contoh Praktik:**
   ```javascript
   async function prosesData() {
       try {
           let data = await ambilDataDariServer();
           let hasil = await prosesHasil(data);
           console.log("Proses selesai dengan hasil:", hasil);
       } catch (error) {
           console.log("Terjadi kesalahan:", error.message);
       }
   }

   async function ambilDataDariServer() {
       return new Promise((resolve) => {
           setTimeout(() => {
               resolve("Data diambil");
           }, 1000);
       });
   }

   async function prosesHasil(data) {
       return `Hasil dari ${data}`;
   }

   prosesData();
   ```

#### **Diskusi dan Review:**

- **Apa Keuntungan Menggunakan Promises Dibandingkan Callbacks?**
  - **Diskusi:**
    - Promises menawarkan cara yang lebih bersih dan lebih dapat diprediksi untuk menangani operasi asinkron dibandingkan dengan callbacks. Mereka menghindari callback hell dan membuat kode lebih mudah diikuti dengan chaining `then`.

- **Bagaimana Async/Await Mempermudah Penul

isan Kode Asinkron?**
  - **Diskusi:**
    - `async/await` memungkinkan kalian untuk menulis kode asinkron yang terlihat lebih seperti kode sinkron, membuatnya lebih mudah dibaca dan dipahami. Ini juga memungkinkan kalian untuk menangani kesalahan dengan lebih efisien menggunakan `try...catch`.

- **Apa Itu Callback Hell dan Bagaimana Cara Menghindarinya?**
  - **Diskusi:**
    - Callback hell terjadi ketika kalian memiliki terlalu banyak callback bersarang, membuat kode sulit dibaca dan dipelihara. Ini bisa dihindari dengan menggunakan Promises atau `async/await`.