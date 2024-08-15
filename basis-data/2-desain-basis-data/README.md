# **Bab 2 - Desain Basis Data**

## **Tujuan Pembelajaran**
Pada akhir pertemuan ini, kalian diharapkan mampu:
- Memahami berbagai jenis relasi antar tabel dalam basis data dan bagaimana merancangnya.
- Menguasai konsep normalisasi data untuk meningkatkan efisiensi dan integritas data.
- Mampu menerapkan normalisasi hingga bentuk normal ketiga (3NF) pada desain basis data yang kalian buat.

## **Materi yang Akan Dibahas**
1. Desain Relasi Antar Tabel
2. Contoh Penerapan Relasi dalam Skenario Nyata
3. Normalisasi Basis Data
4. Contoh Normalisasi Data

---

## **1. Desain Relasi Antar Tabel**

### **One-to-One Relationship**
- **Pengertian:** Hubungan one-to-one adalah ketika satu record di tabel A berhubungan dengan tepat satu record di tabel B.
- **Penggunaan:** Biasanya digunakan ketika data di tabel B jarang digunakan atau memiliki aturan keamanan yang berbeda.
- **Contoh:** Dalam sistem HR (Human Resources), informasi karyawan mungkin disimpan dalam tabel utama, sedangkan informasi sensitif seperti gaji atau data medis disimpan di tabel terpisah yang berhubungan secara one-to-one dengan tabel karyawan.

**Diagram Relasi:**
```
Karyawan
--------
ID_Karyawan (PK)
Nama
...

Gaji
--------
ID_Karyawan (PK, FK)
Jumlah_Gaji
...
```

### **One-to-Many Relationship**
- **Pengertian:** Hubungan one-to-many adalah ketika satu record di tabel A dapat berhubungan dengan banyak record di tabel B, namun satu record di tabel B hanya berhubungan dengan satu record di tabel A.
- **Penggunaan:** Sangat umum, digunakan misalnya ketika satu entitas berperan sebagai “parent” yang memiliki banyak “children”.
- **Contoh:** Dalam sistem penjualan, satu pelanggan dapat memiliki banyak pesanan, tetapi satu pesanan hanya berhubungan dengan satu pelanggan.

**Diagram Relasi:**
```
Pelanggan
---------
ID_Pelanggan (PK)
Nama
...

Pesanan
---------
ID_Pesanan (PK)
Tanggal
ID_Pelanggan (FK)
...
```

### **Many-to-Many Relationship**
- **Pengertian:** Hubungan many-to-many adalah ketika banyak record di tabel A bisa berhubungan dengan banyak record di tabel B. Biasanya, ini diimplementasikan dengan membuat tabel penghubung (junction table).
- **Penggunaan:** Umum digunakan untuk hubungan yang kompleks, seperti siswa yang bisa mengambil banyak mata kuliah dan setiap mata kuliah bisa diikuti oleh banyak siswa.
- **Contoh:** Di perpustakaan, satu buku bisa dipinjam oleh banyak anggota, dan satu anggota bisa meminjam banyak buku.

**Diagram Relasi:**
```
Anggota
---------
ID_Anggota (PK)
Nama
...

Buku
---------
ID_Buku (PK)
Judul
...

Peminjaman
---------
ID_Anggota (FK)
ID_Buku (FK)
Tanggal_Peminjaman
...
```

## **2. Contoh Penerapan Relasi dalam Skenario Nyata**

Mari kita bahas bagaimana relasi-relasi ini diterapkan dalam skenario nyata, misalnya dalam **sistem manajemen sekolah**:

- **Entitas:**
    - **Siswa**: Menyimpan informasi pribadi siswa.
    - **Kelas**: Menyimpan informasi tentang kelas.
    - **Mata Pelajaran**: Menyimpan detail mata pelajaran.
    - **Pengajar**: Menyimpan informasi tentang pengajar.

- **Relasi:**
    - **One-to-Many:** Satu kelas memiliki banyak siswa, tetapi satu siswa hanya terdaftar di satu kelas.
    - **Many-to-Many:** Banyak siswa bisa mengambil banyak mata pelajaran, dan setiap mata pelajaran bisa diikuti oleh banyak siswa. Ini memerlukan tabel penghubung seperti “Pendaftaran_MataPelajaran”.

**Diagram Relasi:**
```
Siswa
-----
ID_Siswa (PK)
Nama
ID_Kelas (FK)
...

Kelas
-----
ID_Kelas (PK)
Nama_Kelas
...

Mata_Pelajaran
-----
ID_MataPelajaran (PK)
Nama_MataPelajaran
...

Pengajar
-----
ID_Pengajar (PK)
Nama_Pengajar
...

Pendaftaran_MataPelajaran
-----
ID_Siswa (FK)
ID_MataPelajaran (FK)
ID_Pengajar (FK)
...
```

## **3. Normalisasi Basis Data**

### **Apa itu Normalisasi?**
Normalisasi adalah proses pengaturan data dalam basis data untuk mengurangi redundansi dan meningkatkan integritas data. Normalisasi dilakukan dengan membagi data menjadi beberapa tabel yang lebih kecil, masing-masing dengan fokus tertentu, dan menghubungkannya dengan relasi.

### **Tahapan Normalisasi:**

1. **First Normal Form (1NF):**
    - Menghapus duplikasi kolom dalam tabel.
    - Setiap kolom harus berisi nilai atomic (satu nilai per kolom).
    - **Contoh:** Jika ada kolom yang berisi daftar produk terjual dalam satu pesanan, ini harus dipecah ke dalam baris yang terpisah.

2. **Second Normal Form (2NF):**
    - Memastikan bahwa setiap kolom bukan kunci bergantung penuh pada kunci utama (Primary Key).
    - **Contoh:** Jika ada kolom yang hanya bergantung pada sebagian dari kunci utama, ini harus dipindahkan ke tabel terpisah.

3. **Third Normal Form (3NF):**
    - Menghapus kolom yang tidak bergantung langsung pada kunci utama.
    - **Contoh:** Jika ada informasi seperti nama kota dan kode pos, kode pos harus berada di tabel terpisah yang memiliki relasi ke tabel utama berdasarkan kota, bukan disimpan langsung dalam tabel utama.

## **4. Contoh Normalisasi Data**

### **Skenario: Tabel Pesanan**

**Tabel Awal:**
```
Pesanan
-------
ID_Pesanan | Pelanggan_Nama | Pelanggan_Alamat | Produk_Nama | Produk_Harga
---------------------------------------------------------------------------
1          | Andi           | Jl. Merdeka 123  | Laptop      | 10,000,000
1          | Andi           | Jl. Merdeka 123  | Mouse       | 150,000
2          | Budi           | Jl. Sudirman 45  | Laptop      | 10,000,000
```

**1NF:**
- Pisahkan kolom "Pelanggan_Nama" dan "Pelanggan_Alamat" ke tabel Pelanggan.
- Pisahkan kolom "Produk_Nama" dan "Produk_Harga" ke tabel Produk.

**2NF:**
- Buat tabel Pesanan yang hanya berisi "ID_Pesanan", "Tanggal_Pesanan", dan referensi ke "ID_Pelanggan".
- Pindahkan "ID_Produk" dan "Jumlah" ke tabel Detail_Pesanan yang berisi "ID_Pesanan" dan "ID_Produk".

**3NF:**
- Pastikan "Harga_Produk" disimpan di tabel Produk, bukan di Detail_Pesanan, untuk menghindari ketergantungan transitif.

**Hasil Akhir:**
```
Pelanggan
---------
ID_Pelanggan | Nama    | Alamat
--------------------------------
1            | Andi    | Jl. Merdeka 123
2            | Budi    | Jl. Sudirman 45

Produk
------
ID_Produk | Nama   | Harga
--------------------------
1         | Laptop | 10,000,000
2         | Mouse  | 150,000

Pesanan
-------
ID_Pesanan | Tanggal | ID_Pelanggan
-----------------------------------
1          | 01-08-2024 | 1
2          | 02-08-2024 | 2

Detail_Pesanan
--------------
ID_Pesanan | ID_Produk | Jumlah
--------------------------------
1          | 1         | 1
1          | 2         | 2
2          | 1         | 1
```

---

### **Aktivitas**

1. **Diskusi Kelompok:**
    - **Topik:** Mengapa normalisasi penting dalam pengelolaan basis data?
    - **Tujuan:** Memahami pentingnya normalisasi untuk menghindari duplikasi data dan menjaga integritas data dalam basis data.

2. **Latihan:**
    - **Tugas:** Desain basis data sederhana untuk aplikasi penjualan online. Identifikasi entitas, atribut, dan relasi antar tabel. Lakukan normalisasi hingga 3NF.
    - **Output:** Diagram relasi tabel yang mencerminkan penerapan berbagai jenis hubungan dan hasil normalisasi hingga 3NF.

---

[⏮ Pengenalan Basis Data](../1-pengenalan-basis-data/README.md) || [Home 🏘](../README.md) || [Installasi ⏭](../3-installasi/README.md)