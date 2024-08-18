### **Bab 44: Modules**

#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Memahami konsep modul dalam JavaScript dan mengapa modul penting untuk mengorganisasi kode.
- Menggunakan **CommonJS** dan **ECMAScript Modules (ESM)** untuk mengimpor dan mengekspor modul.
- Memahami perbedaan antara **CommonJS** dan **ESM**.
- Mengorganisasi kode JavaScript menjadi beberapa modul yang dapat digunakan kembali.

#### **Materi:**

1. **Apa Itu Modul dalam JavaScript?**
   - **Definisi Modul:**
     - Modul adalah file JavaScript yang memiliki ruang lingkup sendiri dan dapat mengekspor nilai (seperti variabel, fungsi, atau kelas) yang dapat diimpor oleh file lain. Modul membantu mengorganisasi kode dengan memisahkan fungsionalitas ke dalam file yang lebih kecil dan lebih fokus.
   - **Mengapa Modul Penting?**
     - Modul penting karena mereka memungkinkan pengembangan kode yang lebih terstruktur, modular, dan dapat digunakan kembali. Dengan menggunakan modul, kalian bisa memecah aplikasi besar menjadi bagian-bagian yang lebih kecil, yang membuat kode lebih mudah dipahami, dikelola, dan diuji.

2. **CommonJS Modules**
   - **Penjelasan:**
     - CommonJS adalah standar modul yang paling sering digunakan dalam lingkungan Node.js. Dalam CommonJS, modul diekspor menggunakan `module.exports` atau `exports`, dan diimpor menggunakan `require`.
   - **Sintaks Dasar CommonJS:**
     - **Ekspor Modul:**
       ```javascript
       // math.js
       function tambah(a, b) {
           return a + b;
       }

       module.exports = tambah;
       ```
     - **Impor Modul:**
       ```javascript
       // app.js
       const tambah = require('./math');

       console.log(tambah(2, 3)); // Output: 5
       ```
     - **Penjelasan:**
       - Pada contoh di atas, fungsi `tambah` diekspor dari `math.js` menggunakan `module.exports`, dan kemudian diimpor ke `app.js` menggunakan `require`. Ini adalah cara dasar bekerja dengan modul di lingkungan Node.js.

3. **ECMAScript Modules (ESM)**
   - **Penjelasan:**
     - ECMAScript Modules (ESM) adalah standar modul yang diperkenalkan dalam ES6 (ECMAScript 2015) dan didukung oleh sebagian besar browser modern. ESM menggunakan sintaks `export` untuk mengekspor modul dan `import` untuk mengimpor modul.
   - **Sintaks Dasar ESM:**
     - **Ekspor Modul:**
       ```javascript
       // math.js
       export function tambah(a, b) {
           return a + b;
       }
       ```
     - **Impor Modul:**
       ```javascript
       // app.js
       import { tambah } from './math.js';

       console.log(tambah(2, 3)); // Output: 5
       ```
     - **Penjelasan:**
       - Pada contoh di atas, fungsi `tambah` diekspor dari `math.js` menggunakan `export`, dan kemudian diimpor ke `app.js` menggunakan `import`. ESM memungkinkan kalian untuk menggunakan sintaks yang lebih intuitif dan mendukung pengelolaan modul yang lebih fleksibel.

4. **Perbedaan antara CommonJS dan ECMAScript Modules**
   - **Ekspor dan Impor:**
     - **CommonJS** menggunakan `module.exports` dan `require` untuk mengekspor dan mengimpor modul.
     - **ESM** menggunakan `export` dan `import`.
   - **Waktu Eksekusi:**
     - **CommonJS** dieksekusi secara sinkron, artinya modul diimpor dan dieksekusi ketika `require` dipanggil.
     - **ESM** dieksekusi secara asinkron, artinya modul diimpor dan dieksekusi setelah parsing selesai.
   - **Dukungan Lingkungan:**
     - **CommonJS** terutama digunakan di Node.js.
     - **ESM** didukung di browser modern dan Node.js (dengan beberapa penyesuaian).
   - **Flexibilitas Ekspor:**
     - **CommonJS** mendukung ekspor tunggal dan multiple dengan `module.exports`.
     - **ESM** mendukung ekspor tunggal (`export default`) dan multiple (`export {}`).

5. **Ekspor dan Impor dengan ESM**
   - **Penjelasan:**
     - ESM memungkinkan berbagai cara untuk mengekspor dan mengimpor modul, termasuk ekspor default dan named exports.
   - **Ekspor Default:**
     - **Contoh:**
       ```javascript
       // math.js
       export default function tambah(a, b) {
           return a + b;
       }
       ```
     - **Impor Default:**
       ```javascript
       // app.js
       import tambah from './math.js';

       console.log(tambah(2, 3)); // Output: 5
       ```
   - **Named Exports:**
     - **Contoh:**
       ```javascript
       // math.js
       export function tambah(a, b) {
           return a + b;
       }

       export function kurang(a, b) {
           return a - b;
       }
       ```
     - **Impor Named Exports:**
       ```javascript
       // app.js
       import { tambah, kurang } from './math.js';

       console.log(tambah(5, 3)); // Output: 8
       console.log(kurang(5, 3)); // Output: 2
       ```

6. **Mengorganisasi Kode dengan Modul**
   - **Penjelasan:**
     - Modul memungkinkan kalian untuk mengorganisasi kode dengan lebih baik, memisahkan fungsionalitas ke dalam file yang berbeda sesuai dengan tugas atau tujuan tertentu.
   - **Contoh Struktur Proyek:**
     - **Struktur Direktori:**
       ```
       /project
       ├── /modules
       │   ├── math.js
       │   └── string.js
       ├── app.js
       └── index.html
       ```
     - **Contoh Penggunaan:**
       ```javascript
       // math.js
       export function tambah(a, b) {
           return a + b;
       }

       // string.js
       export function uppercase(str) {
           return str.toUpperCase();
       }

       // app.js
       import { tambah } from './modules/math.js';
       import { uppercase } from './modules/string.js';

       console.log(tambah(2, 3)); // Output: 5
       console.log(uppercase("hello")); // Output: HELLO
       ```

7. **Menggunakan Modul di Browser**
   - **Penjelasan:**
     - Untuk menggunakan ESM di browser, kalian harus memastikan bahwa file HTML kalian mengacu pada file JavaScript sebagai modul dengan menambahkan atribut `type="module"`.
   - **Contoh Penggunaan:**
     ```html
     <!-- index.html -->
     <!DOCTYPE html>
     <html lang="en">
     <head>
         <meta charset="UTF-8">
         <meta name="viewport" content="width=device-width, initial-scale=1.0">
         <title>Modul dalam JavaScript</title>
     </head>
     <body>
         <script type="module" src="./app.js"></script>
     </body>
     </html>
     ```

8. **Modul dalam Node.js**
   - **Penjelasan:**
     - Node.js mendukung CommonJS secara default tetapi juga mendukung ESM dengan beberapa konfigurasi tambahan.
   - **Menggunakan ESM di Node.js:**
     - Untuk menggunakan ESM di Node.js, kalian bisa:
       - Menggunakan ekstensi file `.mjs`.
       - Atau menambahkan `"type": "module"` di file `package.json`.
     - **Contoh `package.json`:**
       ```json
       {
           "name": "project-name",
           "version": "1.0.0",
           "type": "module"
       }
       ```
     - **Menggunakan Modul ESM di Node.js:**
       ```javascript
       // math.mjs
       export function tambah(a, b) {
           return a + b;
       }

       // app.mjs
       import { tambah } from './math.mjs';

       console.log(tambah(5, 3)); // Output: 8
       ```

#### **Praktikum Lengkap:**

1. **Latihan 1: Menggunakan CommonJS di Node.js**
   - Buat dua file: `math.js` yang mengekspor fungsi `tambah` dan `app.js` yang mengimpor dan menggunakan fungsi tersebut.
   **Contoh Praktik:**
   ```javascript
   // math.js
   function tambah(a, b) {
       return a + b;
   }

   module.exports = tambah;

   // app.js
   const tambah = require('./math');

   console.log(tambah(10, 5)); // Output: 15
   ```

2. **Latihan 2: Menggunakan ESM di Browser**
   - Buat dua file modul `math.js` dan `app.js` dan gunakan dalam file HTML.
   **Contoh Praktik:**
   ```javascript
   // math.js
   export function tambah(a, b) {
       return a + b;
   }

   // app.js


   import { tambah } from './math.js';

   console.log(tambah(7, 2)); // Output: 9
   ```
   ```html
   <!-- index.html -->
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <title>JavaScript Modules</title>
   </head>
   <body>
       <script type="module" src="./app.js"></script>
   </body>
   </html>
   ```

3. **Latihan 3: Menggunakan Ekspor Default dan Named Exports**
   - Buat modul dengan ekspor default dan beberapa named exports, lalu impor dan gunakan dalam file lain.
   **Contoh Praktik:**
   ```javascript
   // math.js
   export default function tambah(a, b) {
       return a + b;
   }

   export function kurang(a, b) {
       return a - b;
   }

   // app.js
   import tambah, { kurang } from './math.js';

   console.log(tambah(6, 4)); // Output: 10
   console.log(kurang(10, 3)); // Output: 7
   ```

4. **Latihan 4: Menggunakan Modul di Node.js dengan ESM**
   - Buat proyek Node.js yang menggunakan ESM dengan mengonfigurasi `package.json`.
   **Contoh Praktik:**
   ```json
   {
       "name": "esm-example",
       "version": "1.0.0",
       "type": "module"
   }
   ```
   ```javascript
   // math.mjs
   export function kali(a, b) {
       return a * b;
   }

   // app.mjs
   import { kali } from './math.mjs';

   console.log(kali(5, 5)); // Output: 25
   ```

#### **Diskusi dan Review:**

- **Mengapa Modul Penting untuk Mengorganisasi Kode dalam Proyek JavaScript?**
  - **Diskusi:**
    - Modul membantu mengorganisasi kode dengan memisahkan fungsionalitas ke dalam file yang lebih kecil dan fokus. Ini membuat kode lebih mudah dipahami, diuji, dan dikelola, terutama dalam proyek yang besar.

- **Apa Perbedaan Utama antara CommonJS dan ESM?**
  - **Diskusi:**
    - CommonJS adalah standar modul yang digunakan di Node.js dan menggunakan `require` untuk mengimpor modul. ESM adalah standar yang lebih modern, mendukung sintaks `import` dan `export`, dan didukung oleh browser modern serta Node.js dengan beberapa konfigurasi.

- **Bagaimana Cara Menggunakan ESM di Node.js dan Browser?**
  - **Diskusi:**
    - Di Node.js, kalian bisa menggunakan ESM dengan ekstensi `.mjs` atau dengan menambahkan `"type": "module"` di `package.json`. Di browser, ESM bisa digunakan dengan menambahkan `type="module"` pada tag `<script>` dalam file HTML.