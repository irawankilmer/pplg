# **Bab 9 - Kasus Penggunaan Nyata dan Pengenalan NoSQL**
#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Menerapkan konsep basis data dalam kasus penggunaan nyata yang relevan dengan dunia industri.
- Memahami konsep dasar basis data NoSQL dan bagaimana mereka berbeda dari basis data relasional.
- Mengidentifikasi skenario di mana penggunaan basis data NoSQL lebih cocok daripada basis data relasional.

#### **Materi yang Akan Dibahas**

1. **Kasus Penggunaan Nyata dalam Basis Data**
   - **Pengertian Kasus Penggunaan Nyata:**
     - Kasus penggunaan nyata merujuk pada aplikasi praktis dari konsep basis data dalam situasi kehidupan nyata atau dunia industri. Ini membantu kalian untuk memahami bagaimana teori yang dipelajari di kelas dapat diterapkan dalam konteks profesional.
   - **Contoh Kasus Penggunaan:**
     - **Sistem Manajemen Siswa**: Basis data untuk mengelola informasi siswa, kelas, dan penilaian di sekolah.
     - **Sistem E-commerce**: Basis data yang digunakan untuk mengelola produk, pesanan, pelanggan, dan transaksi dalam platform e-commerce.
     - **Sistem Perbankan**: Mengelola informasi akun, transaksi, pinjaman, dan nasabah.
     - **Sistem Pemesanan Tiket**: Basis data yang digunakan untuk mengelola pemesanan tiket penerbangan, bioskop, atau transportasi publik.

2. **Pengenalan NoSQL**
   - **Apa itu NoSQL?**
     - NoSQL (Not Only SQL) adalah jenis basis data yang tidak menggunakan model tabel relasional seperti basis data SQL tradisional. NoSQL dirancang untuk menangani sejumlah besar data terdistribusi dan tidak terstruktur, seperti data yang dihasilkan oleh aplikasi web dan mobile modern.
   - **Jenis-jenis Basis Data NoSQL:**
     - **Document Stores**: Menggunakan format dokumen (misalnya JSON) untuk menyimpan data, contoh: MongoDB.
     - **Key-Value Stores**: Menyimpan data sebagai pasangan kunci-nilai, contoh: Redis.
     - **Column Stores**: Menyimpan data dalam kolom-kolom, bukan baris, yang memungkinkan akses data yang sangat cepat, contoh: Apache Cassandra.
     - **Graph Databases**: Menyimpan data dalam bentuk grafis, ideal untuk data yang saling terkait seperti jaringan sosial, contoh: Neo4j.
   - **Kapan Menggunakan NoSQL?**
     - **Skalabilitas Horizontal**: Ketika aplikasi membutuhkan skalabilitas yang tinggi dengan data terdistribusi.
     - **Data Tidak Terstruktur**: Ketika data tidak sesuai dengan model tabel relasional tradisional.
     - **Kecepatan Akses**: Ketika aplikasi membutuhkan kecepatan akses data yang sangat tinggi, seperti dalam cache atau aplikasi real-time.

3. **Perbandingan SQL dan NoSQL**
   - **SQL (Relational Databases):**
     - Menggunakan skema yang terstruktur dan tabel-tabel yang saling berhubungan.
     - Cocok untuk aplikasi yang membutuhkan konsistensi data dan integritas referensial.
     - Kurang fleksibel dalam menangani data tidak terstruktur atau data dalam jumlah sangat besar yang tersebar di banyak lokasi.
   - **NoSQL (Non-Relational Databases):**
     - Tidak memiliki skema yang kaku, lebih fleksibel dalam menangani data tidak terstruktur.
     - Didesain untuk mendukung skalabilitas horizontal, cocok untuk aplikasi modern yang menangani data dalam jumlah besar.
     - Kurang cocok untuk aplikasi yang memerlukan konsistensi data yang ketat.

4. **Studi Kasus Penggunaan NoSQL**
   - **MongoDB dalam E-commerce:**
     - MongoDB sering digunakan dalam platform e-commerce untuk mengelola katalog produk yang memiliki berbagai macam atribut dan variasi. Keuntungan utama MongoDB adalah kemampuannya untuk menyimpan data dalam format JSON, yang memudahkan penanganan data tidak terstruktur atau semi-terstruktur.
   - **Redis sebagai Cache:**
     - Redis, sebagai key-value store, sering digunakan sebagai cache untuk meningkatkan kecepatan akses data di aplikasi yang membutuhkan performa tinggi. Data yang sering diakses disimpan di Redis untuk mengurangi beban pada basis data utama.
   - **Apache Cassandra untuk Big Data:**
     - Apache Cassandra digunakan oleh perusahaan besar yang menangani data dalam skala besar, seperti Facebook dan Netflix. Karena arsitektur terdistribusinya, Cassandra dapat menangani replikasi data lintas banyak pusat data, menjadikannya ideal untuk aplikasi yang membutuhkan ketersediaan data yang tinggi.
   - **Neo4j dalam Jaringan Sosial:**
     - Neo4j digunakan dalam aplikasi yang memerlukan pemodelan relasi yang kompleks antar entitas, seperti dalam jaringan sosial. Misalnya, untuk memodelkan hubungan pertemanan dan rekomendasi dalam sebuah platform sosial.

5. **Praktikum Lengkap**

   - **Latihan 1: Kasus Penggunaan Nyata dalam Basis Data Relasional**
     - Buatlah sebuah model basis data untuk sistem manajemen siswa yang mencakup tabel `Siswa`, `Kelas`, dan `Nilai`. Tulis query untuk menampilkan laporan nilai siswa berdasarkan kelas.

   - **Latihan 2: Penggunaan NoSQL**
     - Pilih salah satu basis data NoSQL (misalnya MongoDB) dan buat contoh skema untuk sistem e-commerce yang mengelola produk dan pesanan. Tulis perintah untuk menambahkan data dan melakukan pencarian berdasarkan kriteria tertentu.

6. **Diskusi dan Review**

- **Kapan Menggunakan SQL vs NoSQL?**
  - **Diskusi:** Dalam skenario apa kalian lebih memilih basis data relasional seperti SQL dan kapan kalian akan memilih NoSQL? Diskusikan pro dan kontra masing-masing jenis basis data berdasarkan kebutuhan aplikasi.

- **Bagaimana Studi Kasus Membantu Memahami NoSQL?**
  - **Diskusi:** Mengapa penting untuk memahami contoh penggunaan nyata dalam memilih jenis basis data yang tepat? Bagaimana MongoDB, Redis, Cassandra, dan Neo4j digunakan dalam industri? Diskusikan bagaimana skenario ini dapat diterapkan dalam proyek kalian sendiri.

---
[⏮ Stored Procedures dan Triggers](../8-stored-procedures-and-triggers/README.md) || [Home 🏘](../README.md) || [Monitoring ⏭](../10-monitoring/README.md)