# **Bab 9 - Kasus Penggunaan Nyata dan Pengenalan NoSQL**

## **Tujuan Pembelajaran**
Setelah pertemuan ini, kalian diharapkan:
- Memahami bagaimana basis data relasional diterapkan dalam proyek nyata.
- Mengerti kapan dan mengapa NoSQL digunakan sebagai alternatif dari RDBMS.
- Memahami perbedaan utama antara RDBMS dan NoSQL, serta mengetahui beberapa jenis NoSQL yang umum digunakan.

## **Materi yang Akan Dibahas**
1. Kasus Penggunaan Nyata Basis Data Relasional
2. Pengenalan NoSQL dan Perbedaannya dengan RDBMS
3. Jenis-Jenis Basis Data NoSQL
4. Contoh Implementasi NoSQL dalam Skenario Nyata

---

## **1. Kasus Penggunaan Nyata Basis Data Relasional**

### **Implementasi Basis Data dalam Proyek Nyata**
Basis data relasional (RDBMS) digunakan di berbagai bidang untuk mengelola data yang terstruktur dan terhubung. Beberapa contoh implementasi dalam proyek nyata meliputi:

1. **Sistem Manajemen Inventaris:**
    - Menggunakan tabel untuk menyimpan informasi produk, pemasok, pesanan, dan stok.
    - Relasi antara tabel memungkinkan manajemen stok yang efisien, memudahkan pelacakan produk dari pemasok hingga ke pelanggan.

2. **Sistem Informasi Akademik:**
    - Tabel siswa, mata pelajaran, jadwal, dan nilai yang saling berhubungan.
    - Memudahkan pencarian data siswa, pengelolaan jadwal, serta perekaman dan penilaian hasil akademik.

3. **E-commerce:**
    - Menyimpan data produk, pelanggan, pesanan, dan pembayaran dalam tabel terpisah.
    - Memungkinkan penelusuran pesanan dan stok secara real-time serta pengelolaan data pelanggan untuk keperluan pemasaran.

### **Mengapa RDBMS Dipilih?**
RDBMS dipilih dalam skenario ini karena:
- **Data Terstruktur:** Data yang terorganisir dalam tabel dengan hubungan yang jelas.
- **Konsistensi dan Integritas:** Menjamin bahwa data tetap konsisten dan akurat melalui constraints dan transaksi ACID.
- **Query yang Kuat:** SQL memungkinkan untuk query yang kompleks, agregasi data, dan pengelolaan data yang terhubung.

## **2. Pengenalan NoSQL dan Perbedaannya dengan RDBMS**

### **Apa Itu NoSQL?**
NoSQL adalah jenis sistem basis data yang dirancang untuk menangani data yang tidak terstruktur atau semi-terstruktur. Tidak seperti RDBMS yang menggunakan tabel dan relasi, NoSQL menawarkan fleksibilitas lebih dalam penyimpanan dan pengelolaan data.

### **Perbedaan Utama antara NoSQL dan RDBMS:**

1. **Struktur Data:**
    - **RDBMS:** Menggunakan tabel dengan baris dan kolom, sangat terstruktur.
    - **NoSQL:** Menggunakan dokumen, key-value, kolom lebar, atau graf, lebih fleksibel dalam menangani data yang tidak terstruktur.

2. **Skalabilitas:**
    - **RDBMS:** Skalabilitas vertikal (menambah kapasitas dengan meningkatkan hardware).
    - **NoSQL:** Skalabilitas horizontal (menambah kapasitas dengan menambah server).

3. **Transaksi:**
    - **RDBMS:** Mendukung transaksi ACID yang menjamin konsistensi.
    - **NoSQL:** Beberapa sistem NoSQL mungkin tidak mendukung ACID penuh, tetapi mendukung BASE (Basically Available, Soft state, Eventual consistency).

### **Kapan Menggunakan NoSQL?**
NoSQL cocok digunakan ketika:
- Data yang dikelola sangat besar (big data) dan tidak terstruktur.
- Aplikasi memerlukan skalabilitas tinggi dan performa cepat.
- Skema data sering berubah atau tidak tetap.

## **3. Jenis-Jenis Basis Data NoSQL**

### **1. Key-Value Stores:**
- **Contoh:** Redis, DynamoDB.
- **Penggunaan:** Menyimpan data dalam pasangan key-value sederhana, cocok untuk cache dan sesi pengguna.

### **2. Document Stores:**
- **Contoh:** MongoDB, CouchDB.
- **Penggunaan:** Menyimpan data dalam format dokumen (seperti JSON), cocok untuk data semi-terstruktur yang sering berubah.

### **3. Column-Family Stores:**
- **Contoh:** Cassandra, HBase.
- **Penggunaan:** Menyimpan data dalam kolom yang sangat terdistribusi, cocok untuk analisis big data.

### **4. Graph Databases:**
- **Contoh:** Neo4j, ArangoDB.
- **Penggunaan:** Menyimpan dan mengelola data yang saling terhubung melalui graf, cocok untuk analisis jaringan sosial dan rekomendasi.

## **4. Contoh Implementasi NoSQL dalam Skenario Nyata**

### **Skenario: Aplikasi Media Sosial**

**Dokumen Database (MongoDB):**
- **Penggunaan:** Menyimpan profil pengguna, postingan, komentar, dan interaksi dalam dokumen terpisah.
- **Keuntungan:** Fleksibilitas dalam menyimpan data dengan skema yang berbeda, skalabilitas tinggi untuk menangani jutaan pengguna dan interaksi mereka.

**Graf Database (Neo4j):**
- **Penggunaan:** Menyimpan hubungan antara pengguna (misalnya, pertemanan, pengikut) dan interaksi mereka (misalnya, like, share).
- **Keuntungan:** Sangat efisien dalam memproses query yang melibatkan hubungan kompleks, seperti rekomendasi teman atau analisis jaringan.

### **Mengapa Implementasi Ini Penting?**
NoSQL sangat penting untuk aplikasi yang membutuhkan fleksibilitas tinggi dalam penyimpanan data, serta performa dan skalabilitas yang dapat diandalkan, terutama dalam lingkungan dengan pertumbuhan data yang cepat dan tidak terstruktur.

---

### **Aktivitas**

1. **Diskusi Kelompok:**
    - **Topik:** Kapan kalian harus memilih NoSQL dibandingkan RDBMS dalam proyek nyata?
    - **Tujuan:** Memahami situasi di mana NoSQL lebih unggul dari RDBMS, dan bagaimana mengintegrasikan NoSQL dalam sistem basis data yang sudah ada.

2. **Latihan:**
    - **Tugas:** Buat skenario aplikasi yang memerlukan NoSQL. Pilih jenis NoSQL yang tepat dan desain skema data untuk aplikasi tersebut. Bandingkan kelebihan dan kekurangan dengan skema RDBMS tradisional.
    - **Output:** Deskripsi skenario, pilihan NoSQL, dan skema data yang diusulkan, serta analisis perbandingan dengan RDBMS.

---
[⏮ Stored Procedures dan Triggers](../8-stored-procedures-and-triggers/README.md) || [Home 🏘](../README.md) || [Monitoring ⏭](../10-monitoring/README.md)