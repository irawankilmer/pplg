# **Bab 1 – Pengantar Teknologi Web dan Backend**

## **🎯 Tujuan Pembelajaran**

Pada akhir pembelajaran ini, kalian diharapkan mampu:

* Memahami dasar-dasar teknologi web dan bagaimana frontend dan backend saling berinteraksi.
* Menjelaskan konsep client-server dalam dunia web.
* Mengenal peran PHP dalam pengembangan aplikasi backend.
* Menjelaskan alur kerja permintaan HTTP hingga respon yang diterima oleh pengguna.

---

## **📚 Materi yang Akan Dibahas**

1. Apa Itu Teknologi Web?
2. Perbedaan antara Frontend dan Backend
3. Konsep Client dan Server
4. Apa Itu HTTP dan URL?
5. Pengenalan PHP sebagai Bahasa Pemrograman Backend
6. Alur Kerja Permintaan HTTP hingga Respon

---

## **1. Apa Itu Teknologi Web?**

Bayangkan kalian sedang berada di SMK Assalam Samarang. Setiap ruangan kelas adalah bagian dari sekolah yang bisa kalian lihat, sentuh, dan gunakan. Ada papan tulis, meja, kursi, dan alat pembelajaran lainnya. Inilah analogi **Frontend**—bagian dari teknologi web yang dapat dilihat dan digunakan langsung oleh pengguna.

Tapi di balik itu, ada hal-hal yang tidak terlihat: jaringan listrik, sistem keamanan, pengelolaan jadwal oleh staf TU, dan server sekolah. Ini menggambarkan **Backend**—bagian yang bekerja di balik layar untuk memastikan semuanya berjalan lancar.

### **🧾 Definisi Teknologi Web**

Teknologi web adalah kumpulan alat, bahasa pemrograman, dan sistem yang memungkinkan kita untuk membuat, menjalankan, dan mengakses aplikasi atau situs web melalui internet.

Setiap kali kalian membuka situs web—seperti website sekolah, marketplace, atau media sosial—kalian sedang menggunakan teknologi web.

Dua komponen utama:

* **Frontend**: Tampilan dan antarmuka yang digunakan oleh pengguna.
* **Backend**: Mesin di balik layar yang memproses data dan logika aplikasi.

---

## **2. Perbedaan antara Frontend dan Backend**

### **Frontend: Wajah dari Sebuah Aplikasi**

Frontend adalah bagian dari aplikasi web yang terlihat oleh pengguna dan digunakan untuk berinteraksi, seperti formulir login, menu, gambar, atau teks.

#### Teknologi Umum yang Digunakan:

* **HTML** – struktur dasar halaman.
* **CSS** – tampilan, warna, tata letak.
* **JavaScript** – interaktivitas (seperti klik tombol, validasi form, efek animasi).

**Contoh**: Ketika kalian membuka halaman login website sekolah, tampilan form itulah bagian dari frontend.

---

### **Backend: Otak dan Mesin Penggerak di Balik Aplikasi**

Backend adalah bagian dari aplikasi web yang tidak terlihat, tetapi menjalankan logika dan mengelola data. Ia memproses permintaan dari frontend, berinteraksi dengan database, lalu mengirimkan respon kembali.

#### Teknologi Umum yang Digunakan:

* Bahasa pemrograman seperti PHP, Python, Node.js, atau Ruby.
* Database seperti MySQL, PostgreSQL, MongoDB.
* Web server seperti Apache, Nginx.

**Analogi**: Kalian (frontend) memesan makanan ke ibu kantin (backend). Ibu kantin mengambil makanan dari dapur (database), memproses pesanan, lalu memberikan makanan ke kalian.

---

## **3. Konsep Client dan Server**

### **Client**

Client adalah perangkat atau aplikasi yang digunakan oleh pengguna untuk mengakses web—biasanya melalui browser seperti Chrome, Firefox, atau Edge.

### **Server**

Server adalah komputer yang menyimpan dan menjalankan aplikasi web. Ia menerima permintaan (request) dari client dan mengirimkan balasan (response).

**Contoh**: Saat kalian membuka browser dan mengakses `https://sekolahku.sch.id`, browser (client) mengirim permintaan ke server sekolah. Server akan memproses permintaan dan mengirimkan tampilan halaman kembali ke browser kalian.

---

## **4. Apa Itu HTTP dan URL?**

### **HTTP (Hypertext Transfer Protocol)**

Adalah protokol (aturan komunikasi) yang digunakan untuk mengirim dan menerima data antara browser dan server.

* HTTP digunakan untuk permintaan seperti "tolong tampilkan halaman profil saya" atau "simpan data pendaftaran ini."
* Sekarang, mayoritas web menggunakan versi aman: **HTTPS** (dengan enkripsi data).

### **URL (Uniform Resource Locator)**

URL adalah alamat web yang kalian ketik di browser, misalnya `https://www.google.com`. URL menunjukkan **lokasi** sumber daya (halaman web, gambar, file, dll) di internet.

**Struktur URL:**

```
https://      www.sekolahku.sch.id       /jadwal
 protokol        domain situs             path
```

---

## **5. Pengenalan PHP sebagai Bahasa Pemrograman Backend**

### **Apa itu PHP?**

PHP (Hypertext Preprocessor) adalah bahasa pemrograman server-side yang digunakan untuk membuat aplikasi web dinamis. Artinya, halaman web dapat berubah-ubah sesuai dengan data yang dikirim atau diterima.

### **Sejarah Singkat**

PHP pertama kali dibuat oleh Rasmus Lerdorf pada tahun 1994. Awalnya hanya digunakan untuk keperluan pribadi, tetapi berkembang menjadi bahasa backend paling populer dan digunakan oleh jutaan website.

### **Mengapa PHP Populer?**

* Mudah dipelajari untuk pemula.
* Banyak dokumentasi dan komunitas aktif.
* Digunakan oleh berbagai CMS besar seperti WordPress.
* Gratis dan open source.

### **Peran PHP dalam Backend**

PHP bertindak sebagai "penghubung" antara frontend dan database.

**Contoh:**
Saat Hani Fuziyani dari kelas XI PPLG A ingin melihat hasil ujian, ia memasukkan nomor ujian di halaman web. PHP mengambil data tersebut, mencocokkannya ke database, lalu menampilkan nilainya ke layar browser.

---

## **6. Alur Kerja Permintaan HTTP hingga Respon**

Untuk memahami bagaimana aplikasi web bekerja, mari kita pelajari alurnya dari awal sampai akhir:

### **Langkah-langkah Alur Request–Response:**

1. **Client Mengirim HTTP Request**
   Pengguna membuka browser dan mengetik URL lalu menekan Enter. Browser mengirimkan permintaan ke server.

2. **Server Menerima dan Memproses**
   Web server (seperti Apache) menerima permintaan tersebut dan mengarahkan ke file PHP terkait.

3. **PHP Mengeksekusi Logika Backend**
   PHP memproses permintaan: apakah perlu memeriksa database? Apakah perlu menampilkan halaman khusus?

4. **Akses ke Database (Jika Diperlukan)**
   Jika dibutuhkan, PHP mengirimkan perintah SQL ke database (MySQL, misalnya) untuk mengambil atau menyimpan data.

5. **Server Mengirim HTTP Response**
   Hasil akhir dikirim kembali ke browser berupa HTML, CSS, dan JavaScript.

6. **Browser Menampilkan Hasil ke Pengguna**
   Browser menampilkan halaman atau data sesuai dengan hasil respon dari server.

---

### **Contoh Kasus**

> Ahmad Zaki Aprizal ingin melihat jadwal pelajarannya. Dia membuka browser dan mengetik URL website sekolah, lalu menekan Enter. Browser mengirim permintaan ke server sekolah. PHP memproses permintaan tersebut, mengambil data dari database, lalu menampilkan jadwal Ahmad di browsernya.

---

### **🖼 Ilustrasi Alur Kerja (Text Diagram)**

```
[Browser Pengguna]
      |
      | 1. HTTP Request (GET/POST)
      v
[Web Server (Apache/Nginx)]
      |
      | 2. Kirim ke PHP
      v
[PHP Backend Script]
      |
      | 3. Query ke Database
      v
[Database MySQL]
      |
      | 4. Data Dikirim Kembali
      v
[PHP Memproses dan Kembalikan Respon]
      |
      | 5. HTTP Response (HTML)
      v
[Browser Menampilkan Halaman]
```

---

## **🧠 Aktivitas dan Latihan**

### **Diskusi Kelompok:**

* **Topik:** Mengapa backend sangat penting dalam aplikasi web?
* **Panduan Diskusi:** Fokuskan pada peran backend dalam keamanan data, kecepatan pemrosesan, dan interaksi dengan database.

### **Latihan Individu:**

1. Pilih salah satu aplikasi web yang kalian sering gunakan (misalnya Shopee, Instagram Web, atau website sekolah).
2. Identifikasi komponen frontend dan backend dari aplikasi tersebut.
3. Buat diagram alur request-respon dari salah satu fitur (misalnya login atau menampilkan data).

---

### 🧭 Navigasi

[🏘 Home](../README.md) | [⏭ Bab 2 - Konfigurasi](../2-konfigurasi/README.md)