# **Bab 3 - Instalasi dan Administrasi Dasar Basis Data**

## **Tujuan Pembelajaran**
Setelah pertemuan ini, kalian akan:
- Paham apa itu RDBMS dan perannya dalam pengelolaan basis data.
- Mengetahui jenis-jenis sistem manajemen basis data selain RDBMS.
- Mampu menginstal RDBMS seperti MySQL atau PostgreSQL di komputer kalian.
- Mampu melakukan administrasi dasar seperti membuat user, mengelola hak akses, dan mengatur penyimpanan.
- Familiar dengan perintah dasar SQL yang digunakan dalam administrasi basis data.

## **Materi yang Akan Dibahas**
1. Pengertian RDBMS dan Sistem Manajemen Basis Data Lainnya
2. Instalasi RDBMS (MySQL/PostgreSQL)
3. Pengelolaan User dan Hak Akses
4. Pengelolaan Ruang Penyimpanan
5. Pengenalan Perintah Dasar SQL untuk Administrasi

---

## **1. Pengertian RDBMS dan Sistem Manajemen Basis Data Lainnya**

### **Apa Itu RDBMS?**
RDBMS, atau **Relational Database Management System**, adalah perangkat lunak yang digunakan untuk mengelola basis data yang terstruktur dalam bentuk tabel yang saling berhubungan. Di dalam RDBMS, data disimpan dalam tabel (juga dikenal sebagai relasi), yang diorganisir dalam baris (record) dan kolom (field).

### **Fungsi Utama RDBMS:**
- **Penyimpanan Data:** Menyimpan data secara terstruktur dan terorganisir.
- **Manipulasi Data:** Memungkinkan pengguna untuk menambah, menghapus, memperbarui, dan mengelola data.
- **Pengambilan Data:** Memungkinkan pengguna untuk mengambil data dengan menggunakan perintah SQL (Structured Query Language).
- **Keamanan Data:** Mengatur hak akses pengguna dan menjaga integritas data.

### **Contoh RDBMS yang Populer:**
- **MySQL:** Salah satu RDBMS yang paling banyak digunakan, open-source, dan sering digunakan dalam pengembangan web.
- **PostgreSQL:** RDBMS open-source yang dikenal dengan kemampuan tingkat lanjut seperti dukungan untuk tipe data kompleks dan compliance dengan standar SQL.
- **Oracle Database:** RDBMS komersial yang banyak digunakan oleh perusahaan besar dengan kebutuhan basis data yang kompleks.
- **Microsoft SQL Server:** RDBMS yang dikembangkan oleh Microsoft, sering digunakan dalam lingkungan bisnis dan aplikasi enterprise.

### **Apakah Ada Sistem Manajemen Basis Data Lainnya?**
Selain RDBMS, ada juga jenis sistem manajemen basis data lainnya yang digunakan untuk kebutuhan yang berbeda:

1. **NoSQL (Not Only SQL):**
   - **Penggunaan:** Digunakan untuk mengelola basis data yang tidak terstruktur atau semi-terstruktur, seperti dokumen, graf, dan data yang berhubungan dengan big data.
   - **Contoh:** MongoDB (dokumen), Cassandra (key-value store), Neo4j (graf).
   - **Kelebihan:** Fleksibilitas dalam menyimpan berbagai jenis data dan skalabilitas yang tinggi.

2. **Object-Oriented Database (OODBMS):**
   - **Penggunaan:** Mengelola data sebagai objek, seperti dalam pemrograman berorientasi objek.
   - **Contoh:** db4o, ObjectDB.
   - **Kelebihan:** Memungkinkan penyimpanan objek secara langsung tanpa perlu konversi ke format relasional.

3. **Hierarchical Database:**
   - **Penggunaan:** Menyimpan data dalam struktur hierarki seperti pohon.
   - **Contoh:** IBM Information Management System (IMS).
   - **Kelebihan:** Cepat dalam mengambil data yang mengikuti hierarki, seperti dalam aplikasi sistem operasi.

4. **Network Database:**
   - **Penggunaan:** Memungkinkan data memiliki beberapa jalur hubungan, lebih fleksibel daripada model hierarki.
   - **Contoh:** Integrated Data Store (IDS).
   - **Kelebihan:** Mengelola hubungan kompleks antara data, berguna dalam aplikasi jaringan telekomunikasi.

### **Kesimpulan:**
RDBMS adalah pilihan yang umum digunakan karena kemampuannya untuk mengelola data terstruktur dengan baik dan dukungan luas untuk berbagai aplikasi. Namun, untuk kebutuhan khusus seperti big data atau data yang tidak terstruktur, sistem seperti NoSQL mungkin lebih cocok.

## **2. Instalasi RDBMS (MySQL/PostgreSQL)**

### **Kenapa Perlu Instalasi?**
Sebelum kalian bisa mulai mengelola data, kalian butuh alat yang bisa mengatur dan menyimpannya dengan rapi. Di sini, kita akan menginstal RDBMS seperti MySQL atau PostgreSQL. Keduanya populer dan banyak digunakan dalam pengembangan aplikasi.

### **Langkah Instalasi MySQL:**
1. **Unduh Installer:** Kalian bisa download MySQL dari [situs resminya](https://dev.mysql.com/downloads/).
2. **Jalankan Installer:** Ikuti langkah-langkah instalasi. Pilih "Server only" jika hanya butuh server database.
3. **Konfigurasi Awal:** Setelah instalasi, atur root password (jangan sampai lupa, karena ini kunci akses utama kalian).
4. **Verifikasi Instalasi:** Cek instalasi dengan command prompt. Ketik `mysql -u root -p` dan masukkan password kalian untuk masuk.

### **Langkah Instalasi PostgreSQL:**
1. **Unduh Installer:** Download PostgreSQL dari [situs resminya](https://www.postgresql.org/download/).
2. **Jalankan Installer:** Ikuti petunjuk instalasi, pilih direktori, dan atur password untuk user `postgres`.
3. **Konfigurasi Database:** Gunakan pgAdmin atau psql (command line) untuk mulai membuat dan mengelola database.
4. **Verifikasi Instalasi:** Buka pgAdmin atau jalankan `psql -U postgres` di command prompt untuk memverifikasi bahwa PostgreSQL sudah siap digunakan.

## **3. Pengelolaan User dan Hak Akses**

### **Apa itu User dan Hak Akses?**
Setiap orang yang mengakses basis data harus punya akun (user). Sebagai admin, kalian bertugas untuk membuat akun ini dan mengatur apa yang boleh dan tidak boleh mereka lakukan di dalam basis data.

### **Perintah Dasar untuk Mengelola User:**
- **Membuat User:** `CREATE USER 'username'@'host' IDENTIFIED BY 'password';`
- **Memberikan Hak Akses:** `GRANT ALL PRIVILEGES ON database_name.* TO 'username'@'host';`
- **Melihat Hak Akses:** `SHOW GRANTS FOR 'username'@'host';`
- **Menghapus User:** `DROP USER 'username'@'host';`

**Contoh:**
Misalnya, kalian mau buat akun untuk tim pengembangan yang hanya boleh mengakses data dari tabel tertentu:
```sql
CREATE USER 'developer'@'localhost' IDENTIFIED BY 'devpassword';
GRANT SELECT, INSERT ON my_database.my_table TO 'developer'@'localhost';
```

## **4. Pengelolaan Ruang Penyimpanan**

### **Kenapa Ini Penting?**
Pikirkan basis data seperti lemari penyimpanan di rumah. Kalau nggak diatur, lama-lama penuh dan berantakan. Sama halnya dengan basis data. Kalian perlu mengelola ruang penyimpanan supaya data tetap rapi dan efisien.

### **Hal-Hal yang Perlu Diperhatikan:**
- **Ukuran Database:** Cek ukuran basis data kalian secara berkala untuk memastikan tidak ada yang terlalu besar tanpa alasan.
- **Partisi:** Pertimbangkan untuk mempartisi tabel yang sangat besar agar lebih mudah dikelola.
- **Backup:** Selalu pastikan kalian punya cadangan (backup) dari basis data untuk menghindari kehilangan data.

**Perintah SQL terkait:**
- **Cek Ukuran Database:** `SELECT table_schema "DB Name", SUM( data_length + index_length ) / 1024 / 1024 "DB Size in MB" FROM information_schema.TABLES GROUP BY table_schema;`
- **Membuat Partisi Tabel:** Ini biasanya membutuhkan perencanaan dan konfigurasi yang lebih mendalam, jadi mungkin kalian perlu berkonsultasi dengan DBA.

## **5. Pengenalan Perintah Dasar SQL untuk Administrasi**

### **Perintah Dasar yang Harus Kalian Tahu:**
- **Cek Daftar Database:** `SHOW DATABASES;`
- **Membuat Database Baru:** `CREATE DATABASE nama_database;`
- **Menghapus Database:** `DROP DATABASE nama_database;`
- **Mengganti Nama Database:** `ALTER DATABASE nama_database RENAME TO nama_baru;`

**Contoh:**
Misalnya kalian ingin membuat basis data baru untuk proyek kalian:
```sql
CREATE DATABASE toko_online;
USE toko_online;
```

---

### **Aktivitas**

1. **Diskusi Kelompok:**
   - **Topik:** Bagaimana cara memastikan basis data tetap aman dan efisien?
   - **Tujuan:** Memahami pentingnya pengelolaan user, hak akses, dan penyimpanan dalam menjaga kinerja dan keamanan basis data.

2. **Latihan:**
   - **Tugas:** Instal MySQL atau PostgreSQL di komputer kalian. Buat beberapa user dengan hak akses yang berbeda, dan coba buat serta hapus basis data

   - **Output:** Screenshot atau catatan dari proses instalasi dan pengelolaan user yang kalian lakukan.

---
[⏮ Desin Basis Data](../2-desain-basis-data/README.md) || [Home 🏘](../README.md) || [DDL ⏭](../4-ddl/README.md)