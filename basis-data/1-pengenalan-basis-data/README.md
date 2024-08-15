# **Bab 1 - Pengenalan Basis Data**

## **Tujuan Pembelajaran**
Pada akhir pertemuan ini, kalian diharapkan mampu:
- Memahami konsep dasar dan manfaat dari basis data.
- Mengidentifikasi elemen-elemen utama dalam struktur basis data, seperti entitas, atribut, dan hubungan.
- Memahami hierarki data dalam basis data, termasuk konsep file, record, dan field.
- Memahami aturan dasar dalam desain basis data, termasuk konsep normalisasi, primary key, dan foreign key.

## **Materi yang Akan Dibahas**
1. Pengertian dan Manfaat Basis Data
2. Konsep Dasar Struktur Basis Data: Entitas, Atribut, dan Hubungan
3. Hierarki Basis Data: File, Record, Field
4. Aturan Dasar dalam Desain Basis Data

---

## **1. Pengertian dan Manfaat Basis Data**
### Pengertian
Basis data adalah kumpulan data yang terstruktur dan tersimpan dalam sistem komputer yang memungkinkan untuk dikelola dan diakses secara efisien. Sistem manajemen basis data (DBMS) adalah perangkat lunak yang mengatur dan mengelola basis data, sehingga data dapat disimpan, diperbarui, dan diakses dengan mudah.

### Manfaat Basis Data
- **Rapi dan Teratur:** Data disimpan dengan struktur yang jelas, memudahkan pengelolaan dan pencarian.
- **Akses Cepat:** Memungkinkan pengguna untuk dengan mudah mengakses data yang dibutuhkan.
- **Keamanan Data:** Pengaturan hak akses dan proteksi untuk data sensitif.
- **Hemat Ruang Penyimpanan:** Menghindari pengulangan data yang tidak perlu.
- **Pengambilan Keputusan:** Data yang terorganisir membantu dalam pengambilan keputusan yang lebih baik.

**Contoh:**
Sebuah perpustakaan menggunakan basis data untuk menyimpan informasi tentang buku, anggota, dan peminjaman. Dengan basis data, staf perpustakaan dapat dengan mudah mencari informasi buku yang dipinjam oleh anggota tertentu.

## **2. Konsep Dasar Struktur Basis Data: Entitas, Atribut, dan Hubungan**
### Entitas
Entitas adalah objek atau "sesuatu" yang ingin kita simpan datanya. Dalam konteks basis data, entitas bisa berupa orang, barang, atau konsep. Misalnya, di dalam basis data sekolah, entitas bisa berupa "Siswa", "Guru", atau "Mata Pelajaran".

### Atribut
Atribut adalah karakteristik atau informasi yang menggambarkan entitas. Misalnya, untuk entitas "Siswa", atributnya bisa berupa Nama, Nomor Induk Siswa, Alamat, dan Tanggal Lahir.

### Hubungan
Hubungan adalah koneksi antara dua atau lebih entitas. Hubungan menunjukkan bagaimana data dalam satu entitas terhubung dengan data dalam entitas lain. Misalnya, hubungan antara entitas "Siswa" dan "Kelas" bisa menunjukkan bahwa satu siswa dapat terdaftar di beberapa kelas.

**Contoh:**
Dalam basis data sistem perpustakaan, entitas "Buku" mungkin memiliki atribut seperti "Judul", "Penulis", dan "Tahun Terbit". Entitas "Anggota" mungkin memiliki atribut seperti "Nama" dan "Nomor Anggota". Hubungan antara "Buku" dan "Anggota" bisa berupa peminjaman, di mana satu anggota dapat meminjam banyak buku.

## **3. Hierarki Basis Data: File, Record, Field**
### Field
Field adalah unit data terkecil dalam basis data, biasanya mewakili satu atribut dari entitas. Misalnya, field "Nama_Pelanggan" menyimpan nama dari pelanggan dalam sebuah tabel.

### Record
Record adalah kumpulan field yang terkait, yang menggambarkan satu entitas dalam basis data. Misalnya, satu record di tabel Pelanggan akan berisi Nama, Alamat, dan Nomor Telepon untuk satu pelanggan.

### File
File adalah kumpulan record yang berhubungan satu sama lain dan disimpan dalam satu tempat penyimpanan. Misalnya, file Pelanggan yang berisi semua data pelanggan dari sebuah perusahaan.

**Contoh:**
Sebuah tabel dalam basis data yang menyimpan data pelanggan mungkin memiliki field seperti "Nama", "Alamat", dan "Nomor Telepon". Setiap baris (record) dalam tabel tersebut mewakili satu pelanggan, dan tabel ini secara keseluruhan disebut sebagai file.

## **4. Aturan Dasar dalam Desain Basis Data**
### Normalisasi
Normalisasi adalah proses pengorganisasian data untuk mengurangi redundansi dan meningkatkan integritas data. Proses ini dilakukan dengan membagi data ke dalam beberapa tabel yang lebih kecil dan menghubungkannya dengan relasi yang jelas. Normalisasi biasanya dilakukan hingga bentuk normal ketiga (3NF).

### Primary Key
Primary Key adalah kolom atau sekelompok kolom yang unik untuk setiap record dalam tabel, digunakan untuk mengidentifikasi setiap record secara unik. Misalnya, "ID_Pelanggan" bisa menjadi Primary Key untuk tabel Pelanggan.

### Foreign Key
Foreign Key adalah kolom yang digunakan untuk menciptakan hubungan antara dua tabel, biasanya merujuk pada Primary Key di tabel lain. Misalnya, di tabel Pesanan, "ID_Pelanggan" bisa menjadi Foreign Key yang merujuk ke "ID_Pelanggan" di tabel Pelanggan.

### Integritas Data
Integritas data adalah aturan untuk memastikan data selalu akurat dan konsisten. Ini termasuk integritas entitas (setiap record harus unik), integritas referensial (hubungan antara tabel harus valid), dan integritas domain (nilai data harus sesuai dengan tipe data yang diharapkan).

**Contoh:**
Misalnya, sebuah perusahaan memiliki tabel "Karyawan" dengan Primary Key "ID_Karyawan". Tabel lain, seperti "Proyek", dapat memiliki Foreign Key "ID_Karyawan" untuk menunjukkan karyawan mana yang terlibat dalam proyek tertentu.

---

### **Aktivitas**

1. **Diskusi Kelompok:**
    - **Topik:** Mengapa basis data penting untuk mengelola informasi?
    - **Tujuan:** Memahami peran basis data dalam berbagai situasi kehidupan sehari-hari, seperti di perpustakaan, toko online, atau institusi pendidikan.

2. **Latihan:**
    - **Tugas:** Buat diagram entitas dan atribut sederhana untuk sistem perpustakaan. Gambarkan entitas seperti Buku, Anggota, dan Peminjaman, serta atribut yang terkait dengan setiap entitas.
    - **Output:** Diagram yang menunjukkan entitas, atribut, dan hubungan antara entitas.

---

[Home 🏘](../README.md) || [Desain Basis Data ⏭](../2-desain-basis-data/README.md)