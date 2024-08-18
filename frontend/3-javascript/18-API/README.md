### **Bab 42: API**

#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Memahami konsep API (Application Programming Interface) dan bagaimana API digunakan untuk berkomunikasi antara client dan server.
- Menggunakan metode **fetch** untuk membuat permintaan HTTP ke API.
- Menangani respons dari API, termasuk parsing data JSON dan menangani kesalahan.
- Membuat permintaan HTTP GET dan POST dengan JavaScript.

#### **Materi:**

1. **Apa Itu API?**
   - **Definisi API:**
     - API (Application Programming Interface) adalah antarmuka yang memungkinkan aplikasi berkomunikasi satu sama lain. API sering digunakan untuk mengakses layanan atau data dari server secara asinkron.
   - **Mengapa API Penting?**
     - API penting karena memungkinkan aplikasi untuk berinteraksi dengan layanan eksternal, seperti mengambil data dari server, mengirimkan data ke server, atau berinteraksi dengan berbagai platform dan layanan lain.

2. **Menggunakan `fetch` untuk Membuat Permintaan HTTP**
   - **Penjelasan:**
     - `fetch` adalah metode modern yang digunakan untuk membuat permintaan HTTP ke server. `fetch` mengembalikan Promise yang menyelesaikan respons dari server.
   - **Sintaks Dasar:**
     ```javascript
     fetch(url)
       .then(response => {
           // Mengembalikan hasil sebagai Promise
       })
       .catch(error => {
           // Menangani kesalahan
       });
     ```
   - **Contoh Penggunaan:**
     ```javascript
     fetch("https://api.example.com/data")
       .then(response => response.json())
       .then(data => {
           console.log(data);
       })
       .catch(error => {
           console.error("Terjadi kesalahan:", error);
       });
     ```

3. **Membuat Permintaan HTTP GET**
   - **Penjelasan:**
     - Permintaan GET digunakan untuk mengambil data dari server tanpa mengubah data pada server.
   - **Contoh Penggunaan GET:**
     ```javascript
     fetch("https://jsonplaceholder.typicode.com/posts")
       .then(response => {
           if (!response.ok) {
               throw new Error("Jaringan bermasalah.");
           }
           return response.json();
       })
       .then(data => {
           console.log(data); // Menampilkan data yang diterima dari server
       })
       .catch(error => {
           console.error("Terjadi kesalahan:", error);
       });
     ```
     - **Penjelasan:**
       - Dalam contoh ini, permintaan GET dibuat ke URL API publik, dan respons JSON diambil menggunakan `response.json()` dan kemudian diproses.

4. **Membuat Permintaan HTTP POST**
   - **Penjelasan:**
     - Permintaan POST digunakan untuk mengirim data ke server. POST biasanya digunakan untuk mengirimkan data formulir atau data yang harus disimpan di server.
   - **Contoh Penggunaan POST:**
     ```javascript
     fetch("https://jsonplaceholder.typicode.com/posts", {
         method: "POST",
         headers: {
             "Content-Type": "application/json"
         },
         body: JSON.stringify({
             title: "Judul Baru",
             body: "Konten dari postingan baru.",
             userId: 1
         })
     })
     .then(response => {
         if (!response.ok) {
             throw new Error("Jaringan bermasalah.");
         }
         return response.json();
     })
     .then(data => {
         console.log("Data yang disimpan:", data);
     })
     .catch(error => {
         console.error("Terjadi kesalahan:", error);
     });
     ```
     - **Penjelasan:**
       - Permintaan POST dikirim ke API untuk membuat data baru. Header `Content-Type: application/json` digunakan untuk memberi tahu server bahwa data yang dikirim adalah JSON. Data yang dikirimkan dikonversi menjadi string JSON menggunakan `JSON.stringify()`.

5. **Menangani Respons dari API**
   - **Penjelasan:**
     - Respons dari API biasanya berupa data dalam format JSON. `fetch` menyediakan cara mudah untuk mengonversi respons menjadi objek JavaScript menggunakan `response.json()`.
   - **Contoh Penggunaan:**
     ```javascript
     fetch("https://jsonplaceholder.typicode.com/posts/1")
       .then(response => {
           if (!response.ok) {
               throw new Error("Jaringan bermasalah.");
           }
           return response.json();
       })
       .then(data => {
           console.log("Data dari server:", data);
       })
       .catch(error => {
           console.error("Terjadi kesalahan:", error);
       });
     ```
     - **Penjelasan:**
       - Pada contoh ini, data JSON yang diambil dari API diubah menjadi objek JavaScript menggunakan `response.json()` dan kemudian ditampilkan di konsol.

6. **Menangani Kesalahan dalam `fetch`**
   - **Penjelasan:**
     - Ketika bekerja dengan API, penting untuk menangani kesalahan jaringan atau kesalahan lain yang mungkin terjadi. Hal ini dilakukan menggunakan `catch`.
   - **Contoh Penggunaan:**
     ```javascript
     fetch("https://api.example.com/data")
       .then(response => {
           if (!response.ok) {
               throw new Error("Gagal mengambil data.");
           }
           return response.json();
       })
       .then(data => {
           console.log(data);
       })
       .catch(error => {
           console.error("Terjadi kesalahan:", error.message);
       });
     ```
     - **Penjelasan:**
       - `catch` menangani kesalahan yang terjadi selama proses fetch, baik karena kegagalan jaringan maupun kesalahan server lainnya.

7. **Menggunakan `async/await` untuk Permintaan Asinkron**
   - **Penjelasan:**
     - `async/await` memberikan cara yang lebih bersih dan mudah dibaca untuk menulis kode asinkron, termasuk bekerja dengan `fetch`.
   - **Contoh Penggunaan `async/await`:**
     ```javascript
     async function getData() {
         try {
             let response = await fetch("https://jsonplaceholder.typicode.com/posts");
             if (!response.ok) {
                 throw new Error("Jaringan bermasalah.");
             }
             let data = await response.json();
             console.log("Data dari server:", data);
         } catch (error) {
             console.error("Terjadi kesalahan:", error.message);
         }
     }

     getData();
     ```
     - **Penjelasan:**
       - Pada contoh ini, `async/await` digunakan untuk membuat kode asinkron lebih sederhana dan mirip dengan kode sinkron, sehingga lebih mudah dipahami dan dikelola.

#### **Praktikum Lengkap:**

1. **Latihan 1: Membuat Permintaan GET ke API**
   - Buat permintaan GET ke API publik dan tampilkan hasilnya di konsol.
   **Contoh Praktik:**
   ```javascript
   fetch("https://jsonplaceholder.typicode.com/posts")
       .then(response => response.json())
       .then(data => {
           console.log("Data yang diterima:", data);
       })
       .catch(error => {
           console.error("Terjadi kesalahan:", error);
       });
   ```

2. **Latihan 2: Mengirim Data dengan Permintaan POST**
   - Buat permintaan POST ke API publik untuk mengirimkan data baru dan tampilkan responsnya.
   **Contoh Praktik:**
   ```javascript
   fetch("https://jsonplaceholder.typicode.com/posts", {
       method: "POST",
       headers: {
           "Content-Type": "application/json"
       },
       body: JSON.stringify({
           title: "Belajar API",
           body: "Ini adalah konten dari postingan baru.",
           userId: 1
       })
   })
   .then(response => response.json())
   .then(data => {
       console.log("Data yang disimpan:", data);
   })
   .catch(error => {
       console.error("Terjadi kesalahan:", error);
   });
   ```

3. **Latihan 3: Menangani Kesalahan pada Permintaan API**
   - Buat permintaan GET ke API yang salah dan tangani kesalahannya dengan `catch`.
   **Contoh Praktik:**
   ```javascript
   fetch("https://api.example.com/wrong-url")
       .then(response => {
           if (!response.ok) {
               throw new Error("Gagal mengambil data.");
           }
           return response.json();
       })
       .then(data => {
           console.log("Data:", data);
       })
       .catch(error => {
           console.error("Terjadi kesalahan:", error.message);
       });
   ```

4. **Latihan 4: Menggunakan `async/await` untuk Permintaan Asinkron**
   - Gunakan `async/await` untuk membuat permintaan GET dan tampilkan data yang diterima.
   **Contoh Praktik:**
   ```javascript
   async function ambilData() {
       try {
           let response = await fetch("https://jsonplaceholder.typicode.com/posts/1");
           if (!response.ok) {
               throw new Error("Gagal mengambil data.");
           }
           let data = await response.json();
           console.log("Data yang diterima:", data);
       } catch (error) {
           console.error("Terjadi kesalahan:", error.message);
       }
   }

   ambilData();
   ```

#### **Diskusi dan Review:**

- **Apa Kelebihan Menggunakan `fetch` Dibandingkan dengan Metode Lama Seperti `XMLHttpRequest`?**
 

 - **Diskusi:**
    - `fetch` menawarkan sintaks yang lebih sederhana dan lebih bersih dibandingkan dengan `XMLHttpRequest`. `fetch` juga lebih mudah diintegrasikan dengan Promises dan `async/await`, membuat pengelolaan operasi asinkron lebih efisien.

- **Bagaimana Cara Menangani Kesalahan pada Permintaan API?**
  - **Diskusi:**
    - Kesalahan pada permintaan API bisa terjadi karena berbagai alasan, seperti masalah jaringan atau kesalahan server. Menggunakan `catch` untuk menangani kesalahan ini adalah cara yang efektif untuk memastikan aplikasi tetap berjalan dengan lancar meskipun terjadi masalah.

- **Mengapa `async/await` Lebih Disukai dalam Menulis Kode Asinkron?**
  - **Diskusi:**
    - `async/await` memungkinkan penulisan kode asinkron yang lebih mirip dengan kode sinkron, sehingga lebih mudah dibaca dan dipahami. Ini juga mempermudah penanganan kesalahan dengan `try...catch`, membuat kode lebih bersih dan dapat dipelihara.