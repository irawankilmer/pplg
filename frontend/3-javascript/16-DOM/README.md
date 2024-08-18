### **Bab 40: DOM Manipulation**

#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Memahami apa itu DOM (Document Object Model) dan bagaimana DOM memungkinkan interaksi antara JavaScript dan HTML.
- Menggunakan metode untuk memilih elemen HTML menggunakan JavaScript.
- Mengubah konten, atribut, dan gaya elemen HTML menggunakan DOM manipulation.
- Menambahkan, menghapus, dan memanipulasi elemen HTML secara dinamis.

#### **Materi:**

1. **Apa Itu DOM (Document Object Model)?**
   - **Definisi DOM:**
     - DOM adalah representasi berbasis objek dari dokumen HTML yang memungkinkan JavaScript untuk mengakses dan memanipulasi konten, struktur, dan gaya halaman web.
   - **Mengapa DOM Penting?**
     - DOM penting karena memungkinkan kalian untuk membuat halaman web interaktif dengan mengubah elemen-elemen HTML secara dinamis berdasarkan input pengguna atau kondisi tertentu.

2. **Memilih Elemen dalam DOM**
   - **Penjelasan:**
     - Untuk memanipulasi elemen HTML, kalian perlu memilih elemen tersebut terlebih dahulu. JavaScript menyediakan beberapa metode untuk memilih elemen berdasarkan id, kelas, tag, atau selector CSS.
   - **Metode Memilih Elemen:**
     - **`document.getElementById()`**: Memilih elemen berdasarkan id.
       ```javascript
       let header = document.getElementById("header");
       console.log(header.innerHTML); // Output: konten dari elemen dengan id 'header'
       ```
     - **`document.getElementsByClassName()`**: Memilih elemen berdasarkan kelas (class). Mengembalikan HTMLCollection.
       ```javascript
       let items = document.getElementsByClassName("item");
       console.log(items[0].innerHTML); // Output: konten dari elemen pertama dengan class 'item'
       ```
     - **`document.getElementsByTagName()`**: Memilih elemen berdasarkan nama tag. Mengembalikan HTMLCollection.
       ```javascript
       let paragraphs = document.getElementsByTagName("p");
       console.log(paragraphs[0].innerHTML); // Output: konten dari paragraf pertama
       ```
     - **`document.querySelector()`**: Memilih elemen pertama yang cocok dengan selector CSS yang diberikan.
       ```javascript
       let firstItem = document.querySelector(".item");
       console.log(firstItem.innerHTML); // Output: konten dari elemen pertama dengan class 'item'
       ```
     - **`document.querySelectorAll()`**: Memilih semua elemen yang cocok dengan selector CSS yang diberikan. Mengembalikan NodeList.
       ```javascript
       let allItems = document.querySelectorAll(".item");
       console.log(allItems.length); // Output: jumlah elemen dengan class 'item'
       ```

3. **Mengubah Konten dan Atribut Elemen**
   - **Penjelasan:**
     - Setelah memilih elemen, kalian bisa mengubah konten atau atributnya menggunakan JavaScript.
   - **Mengubah Konten Elemen:**
     - **`innerHTML`**: Mengubah konten HTML dalam elemen.
       ```javascript
       let header = document.getElementById("header");
       header.innerHTML = "Selamat Datang di SMK Assalam Samarang";
       ```
     - **`textContent`**: Mengubah teks dalam elemen tanpa mempengaruhi tag HTML di dalamnya.
       ```javascript
       let paragraph = document.querySelector("p");
       paragraph.textContent = "Ini adalah teks baru.";
       ```
   - **Mengubah Atribut Elemen:**
     - **`setAttribute()`**: Menetapkan nilai baru untuk atribut elemen.
       ```javascript
       let link = document.querySelector("a");
       link.setAttribute("href", "https://www.example.com");
       ```
     - **`getAttribute()`**: Mengambil nilai atribut dari elemen.
       ```javascript
       let linkHref = link.getAttribute("href");
       console.log(linkHref); // Output: https://www.example.com
       ```

4. **Mengubah Gaya (CSS) Elemen**
   - **Penjelasan:**
     - Kalian bisa mengubah gaya elemen secara dinamis menggunakan properti `style`.
   - **Mengubah Gaya Elemen:**
     ```javascript
     let header = document.getElementById("header");
     header.style.color = "blue";
     header.style.fontSize = "24px";
     header.style.backgroundColor = "#f0f0f0";
     ```
     - **Penjelasan:**
       - Dengan menggunakan properti `style`, kalian dapat mengubah berbagai properti CSS seperti warna teks (`color`), ukuran font (`fontSize`), dan warna latar belakang (`backgroundColor`).

5. **Menambahkan dan Menghapus Elemen**
   - **Penjelasan:**
     - Kalian bisa menambahkan atau menghapus elemen dalam DOM secara dinamis menggunakan JavaScript.
   - **Menambahkan Elemen:**
     - **`createElement()`**: Membuat elemen HTML baru.
     - **`appendChild()`**: Menambahkan elemen baru ke dalam DOM sebagai anak dari elemen yang dipilih.
       ```javascript
       let newParagraph = document.createElement("p");
       newParagraph.textContent = "Ini adalah paragraf baru.";
       document.body.appendChild(newParagraph);
       ```
     - **`insertBefore()`**: Menyisipkan elemen baru sebelum elemen tertentu.
       ```javascript
       let header = document.getElementById("header");
       document.body.insertBefore(newParagraph, header);
       ```
   - **Menghapus Elemen:**
     - **`removeChild()`**: Menghapus elemen anak dari elemen induknya.
       ```javascript
       let parent = document.getElementById("parent");
       let child = document.getElementById("child");
       parent.removeChild(child);
       ```

6. **Mengelola Kelas (Class) Elemen**
   - **Penjelasan:**
     - Mengelola kelas elemen memungkinkan kalian untuk menambahkan atau menghapus kelas CSS dari elemen secara dinamis.
   - **Metode Mengelola Kelas:**
     - **`classList.add()`**: Menambahkan satu atau lebih kelas ke elemen.
       ```javascript
       let header = document.getElementById("header");
       header.classList.add("highlight");
       ```
     - **`classList.remove()`**: Menghapus satu atau lebih kelas dari elemen.
       ```javascript
       header.classList.remove("highlight");
       ```
     - **`classList.toggle()`**: Menambahkan kelas jika tidak ada, atau menghapusnya jika ada.
       ```javascript
       header.classList.toggle("highlight");
       ```
     - **`classList.contains()`**: Mengecek apakah elemen memiliki kelas tertentu.
       ```javascript
       console.log(header.classList.contains("highlight")); // Output: true atau false
       ```

7. **Event Handling (Menangani Event)**
   - **Penjelasan:**
     - Event handling memungkinkan kalian untuk merespon interaksi pengguna seperti klik, input, atau pengguliran.
   - **Menambahkan Event Listener:**
     - **`addEventListener()`**: Menambahkan event listener ke elemen.
       ```javascript
       let button = document.querySelector("button");
       button.addEventListener("click", function() {
           alert("Tombol diklik!");
       });
       ```
     - **Penjelasan:**
       - `addEventListener` mengikat event handler ke elemen, yang akan dipanggil ketika event tertentu terjadi, seperti klik pada tombol.

#### **Praktikum Lengkap:**

1. **Latihan 1: Memilih dan Mengubah Konten Elemen**
   - Buat sebuah elemen dengan id "header" dan ubah kontennya menggunakan JavaScript.
   **Contoh Praktik:**
   ```javascript
   let header = document.getElementById("header");
   header.innerHTML = "Selamat Datang di SMK Assalam Samarang";
   ```

2. **Latihan 2: Mengubah Gaya Elemen Secara Dinamis**
   - Ubah warna dan ukuran font elemen dengan kelas "judul" ketika tombol diklik.
   **Contoh Praktik:**
   ```javascript
   let button = document.querySelector("button");
   button.addEventListener("click", function() {
       let judul = document.querySelector(".judul");
       judul.style.color = "red";
       judul.style.fontSize = "30px";
   });
   ```

3. **Latihan 3: Menambahkan dan Menghapus Elemen dalam DOM**
   - Tambahkan paragraf baru ke dalam halaman ketika tombol diklik, lalu hapus paragraf tersebut setelah beberapa detik.
   **Contoh Praktik:**
   ```javascript
   let button = document.querySelector("button");
   button.addEventListener("click", function() {
       let newParagraph = document.createElement("p");
       newParagraph.textContent = "Ini adalah paragraf yang baru ditambahkan.";
       document.body.appendChild(newParagraph);

       setTimeout(function() {
           document.body.removeChild(newParagraph);
       }, 3000); // Paragraf dihapus setelah 3 detik
   });
   ```

4. **Latihan 4: Mengelola Kelas Elemen dengan `classList`**
   - Tambahkan kelas "aktif" ke elemen dengan id "menu" ketika tombol diklik, dan

 hapus kelas tersebut ketika diklik lagi.
   **Contoh Praktik:**
   ```javascript
   let button = document.querySelector("button");
   button.addEventListener("click", function() {
       let menu = document.getElementById("menu");
       menu.classList.toggle("aktif");
   });
   ```

#### **Diskusi dan Review:**

- **Mengapa Penting Memahami dan Menggunakan DOM Manipulation?**
  - **Diskusi:**
    - Memahami dan menggunakan DOM manipulation memungkinkan kalian untuk membuat halaman web yang interaktif dan responsif. Ini adalah keterampilan penting dalam pengembangan web modern, di mana pengalaman pengguna sangat diprioritaskan.

- **Apa Perbedaan Antara `innerHTML` dan `textContent`?**
  - **Diskusi:**
    - `innerHTML` mengembalikan atau mengatur konten HTML di dalam elemen, yang berarti bisa menyertakan tag HTML. `textContent` hanya mengembalikan atau mengatur teks di dalam elemen tanpa mempengaruhi tag HTML.

- **Bagaimana Event Handling Membantu dalam Pengembangan Web Interaktif?**
  - **Diskusi:**
    - Event handling memungkinkan kalian untuk merespon tindakan pengguna seperti klik, input, atau pengguliran, yang sangat penting untuk menciptakan pengalaman pengguna yang interaktif dan dinamis.