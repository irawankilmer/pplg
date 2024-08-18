# **Bab 1 - Pengantar Teknologi Web dan Backend**

## **Tujuan Pembelajaran**
Pada akhir pertemuan ini, kalian diharapkan mampu:
- Memahami dasar-dasar teknologi web dan bagaimana frontend dan backend saling berinteraksi.
- Mengenal peran PHP dalam pengembangan aplikasi backend.
- Menjelaskan dengan mudah alur kerja dari permintaan HTTP hingga respon yang diterima oleh pengguna.

## **Materi yang Akan Dibahas**
1. Apa Itu Teknologi Web?
2. Perbedaan antara Frontend dan Backend
3. Pengenalan PHP sebagai Bahasa Pemrograman Backend
4. Alur Kerja Permintaan HTTP hingga Respon

---

## **1. Apa Itu Teknologi Web?**

Bayangkan kalian sedang berjalan-jalan di halaman sekolah, SMK Assalam Samarang. Setiap ruangan kelas adalah bagian dari sekolah yang kalian bisa lihat, sentuh, dan masuk ke dalamnya. Di dalam kelas, ada papan tulis, meja, kursi, dan alat belajar lainnya. Nah, ini mirip dengan **Frontend**—bagian dari teknologi web yang bisa kalian lihat dan berinteraksi langsung.

Di sisi lain, ada banyak hal yang kalian mungkin tidak lihat secara langsung, seperti bagaimana listrik bekerja untuk menyalakan lampu kelas, atau bagaimana sistem keamanan sekolah menjaga semua tetap aman. Bagian-bagian yang bekerja di belakang layar ini bisa kita ibaratkan sebagai **Backend**—meskipun tidak terlihat, perannya sangat penting untuk memastikan semuanya berjalan lancar.

### **Definisi Teknologi Web**
Teknologi web adalah sekumpulan alat dan metode yang kita gunakan untuk membuat, mengelola, dan menjalankan aplikasi atau situs web. Setiap kali kalian membuka website sekolah untuk melihat jadwal pelajaran atau nilai, kalian sedang berinteraksi dengan teknologi web.

Di dunia teknologi web, ada dua komponen utama yang harus kalian kenal:
- **Frontend**: Bagian yang kalian lihat dan gunakan langsung, seperti tampilan halaman login, menu navigasi, atau halaman informasi.
- **Backend**: Bagian yang bekerja di balik layar untuk memastikan semua data diolah dengan benar, seperti ketika kalian memasukkan data login dan sistem memverifikasinya di database.

## **2. Perbedaan antara Frontend dan Backend**

### **Frontend: Wajah dari Sebuah Aplikasi**
Frontend adalah bagian dari aplikasi web yang kalian lihat dan gunakan. Setiap kali kalian klik tombol, isi formulir, atau melihat gambar di halaman web, kalian sedang berinteraksi dengan frontend. 

**Teknologi yang Digunakan di Frontend:**
- **HTML** (Hypertext Markup Language) untuk membuat struktur halaman.
- **CSS** (Cascading Style Sheets) untuk mengatur tampilan, seperti warna dan tata letak.
- **JavaScript** untuk menambah interaktivitas, seperti animasi atau validasi form.

Contoh sederhananya adalah ketika kalian membuka halaman login di website sekolah, bagian yang kalian lihat dan isi adalah frontend.

### **Backend: Mesin Penggerak di Balik Layar**
Backend adalah otak dari aplikasi web, yang mengatur bagaimana data diproses dan disimpan. Ketika kalian memasukkan data login dan mengklik "Masuk," backend akan menerima data tersebut, memeriksanya di database, dan mengirimkan kembali hasilnya ke frontend.

**Teknologi yang Digunakan di Backend:**
- **Bahasa Pemrograman Server-Side** seperti PHP, Python, atau Ruby.
- **Database** seperti MySQL atau PostgreSQL untuk menyimpan dan mengelola data.
- **Server** (misalnya, Apache atau Nginx) untuk mengelola permintaan dan respon antara pengguna dan server.

Analoginya, bayangkan kalian sedang berbelanja di kantin sekolah. Kalian (frontend) memesan makanan kepada ibu kantin (backend). Ibu kantin kemudian mengambil makanan dari dapur (database) dan memberikannya kepada kalian setelah memproses pesanan tersebut.

## **3. Pengenalan PHP sebagai Bahasa Pemrograman Backend**

PHP adalah bahasa pemrograman yang sangat populer dan sering digunakan untuk mengembangkan bagian backend dari sebuah aplikasi web.

### **Mengapa Memilih PHP?**
- **Mudah Dipelajari**: PHP dirancang agar mudah dipahami, terutama untuk pemula. Kalian tidak perlu memiliki latar belakang teknis yang mendalam untuk mulai belajar PHP.
- **Banyak Sumber Belajar**: Karena banyak digunakan, kalian bisa dengan mudah menemukan tutorial, forum, dan komunitas yang siap membantu.
- **Populer dan Andal**: Banyak situs web besar yang menggunakan PHP, seperti Facebook dan WordPress, menunjukkan bahwa PHP bisa diandalkan untuk aplikasi yang besar dan kompleks.

### **Peran PHP dalam Backend**
PHP bertindak sebagai penghubung antara frontend dan database. Misalnya, ketika kalian mengisi formulir di halaman pendaftaran siswa baru dan menekan tombol "Kirim", PHP akan mengambil data tersebut, memeriksanya, menyimpannya di database, dan kemudian memberikan pesan konfirmasi ke frontend.

**Contoh Nyata di SMK Assalam Samarang:**
Misalnya, Hani Fuziyani dari kelas XI PPLG A ingin melihat hasil ujian. Hani masuk ke situs sekolah, memasukkan nomor ujian, dan menekan tombol "Lihat Nilai." Di sini, PHP akan memproses permintaan Hani, mengambil data nilai dari database, dan mengirimkan hasilnya kembali ke browser Hani.

## **4. Alur Kerja Permintaan HTTP hingga Respon**

Ketika kalian mengetik URL di browser dan menekan Enter, ada serangkaian proses yang terjadi sebelum halaman yang kalian inginkan muncul di layar. Mari kita lihat bagaimana alur kerja ini terjadi secara sederhana:

1. **Permintaan HTTP (HTTP Request)**: Browser kalian mengirimkan permintaan ke server, meminta halaman yang kalian inginkan.
2. **Pemrosesan di Server**: Server menerima permintaan ini dan mengirimkannya ke aplikasi backend (misalnya PHP) untuk diproses.
3. **Interaksi dengan Database**: Jika data diperlukan (misalnya, untuk menampilkan nilai atau informasi siswa), PHP akan berkomunikasi dengan database untuk mendapatkan data yang dibutuhkan.
4. **Respon HTTP (HTTP Response)**: Setelah diproses, PHP mengirimkan hasilnya kembali ke server, yang kemudian mengirimkannya ke browser kalian sebagai respon.
5. **Tampilan di Browser**: Browser menerima respon ini dan menampilkan halaman yang kalian minta, seperti halaman profil siswa atau hasil ujian.

**Contoh Nyata:**
Misalnya, Ahmad Zaki Aprizal dari kelas XI PPLG B ingin melihat jadwal pelajarannya. Dia membuka browser, mengetik URL website sekolah, dan menekan Enter. Browsernya mengirimkan permintaan ke server sekolah, PHP memproses permintaan tersebut, mengambil data jadwal dari database, dan menampilkan jadwal Ahmad di browser.

---

### **Aktivitas**

1. **Diskusi Kelompok:**
   - **Topik:** Mengapa backend penting dalam aplikasi web?
   - **Tujuan:** Memahami peran kritis backend dalam menjaga kelancaran aplikasi, terutama dalam hal keamanan dan keandalan.

2. **Latihan:**
   - **Tugas:** Identifikasi teknologi frontend dan backend yang digunakan dalam aplikasi web yang kalian gunakan sehari-hari. Buat diagram sederhana yang menggambarkan alur kerja permintaan hingga respon.
   - **Output:** Diagram yang menunjukkan bagaimana frontend berinteraksi dengan backend dalam aplikasi tersebut.

---
### Navigasi
[Home 🏘](../README.md) || [Konfigurasi ⏭](../2-konfigurasi/README.md)