### **Bab 8: Tables dalam HTML**

#### **Tujuan Pembelajaran**
Pada akhir sesi ini, kalian akan mampu:
- Memahami bagaimana cara membuat tabel dengan dan tanpa menggunakan elemen `<thead>`, `<tbody>`, dan `<tfoot>`.
- Menggunakan elemen-elemen tabel seperti `<table>`, `<tr>`, `<th>`, dan `<td>` secara efektif.
- Menggabungkan sel dalam tabel dengan menggunakan atribut `colspan` dan `rowspan`.

#### **Materi:**

1. **Membuat Tabel dengan `<table>`**
   - **Tag `<table>`** adalah fondasi dari pembuatan tabel di HTML. Dengan tag ini, kalian bisa mulai membangun tabel yang menampung data dalam format baris dan kolom. Tabel bisa digunakan untuk menampilkan data seperti daftar nilai, jadwal pelajaran, atau daftar presensi.

2. **Mengatur Tabel Tanpa `<thead>`, `<tbody>`, dan `<tfoot>`**
   - Kalian bisa membuat tabel sederhana tanpa menggunakan `<thead>`, `<tbody>`, atau `<tfoot>`. Tabel semacam ini berguna untuk data yang sederhana atau ketika kalian tidak perlu memisahkan bagian tabel secara eksplisit.

   **Contoh Tabel Tanpa `<thead>`, `<tbody>`, dan `<tfoot>`:**
   ```html
   <table border="1">
       <tr>
           <th>Nama Siswa</th>
           <th>Matematika</th>
           <th>Bahasa Inggris</th>
           <th>Bahasa Indonesia</th>
       </tr>
       <tr>
           <td>Alya Salsabila</td>
           <td>85</td>
           <td>90</td>
           <td>88</td>
       </tr>
       <tr>
           <td>Anggie Maryani</td>
           <td>78</td>
           <td>82</td>
           <td>80</td>
       </tr>
   </table>
   ```

   - **Catatan:**
     - Pada contoh di atas, tabel tidak dibagi menjadi bagian-bagian terpisah. Semua baris, baik header maupun data, ditulis langsung dalam elemen `<table>` tanpa pembagian lebih lanjut.

3. **Mengatur Tabel dengan `<thead>`, `<tbody>`, dan `<tfoot>`**
   - **`<thead>`**, **`<tbody>`**, dan **`<tfoot>`** membantu kalian mengatur tabel menjadi bagian-bagian yang lebih terstruktur:
     - **`<thead>`**: Bagian ini berisi header tabel, seperti judul kolom.
     - **`<tbody>`**: Di sini adalah tempat semua baris data ditempatkan.
     - **`<tfoot>`**: Bagian ini biasanya digunakan untuk menampilkan ringkasan atau total di bagian bawah tabel.

   **Contoh Tabel dengan `<thead>`, `<tbody>`, dan `<tfoot>`:**
   ```html
   <table border="1">
       <thead>
           <tr>
               <th>Nama Siswa</th>
               <th>Matematika</th>
               <th>Bahasa Inggris</th>
               <th>Bahasa Indonesia</th>
           </tr>
       </thead>
       <tbody>
           <tr>
               <td>Alya Salsabila</td>
               <td>85</td>
               <td>90</td>
               <td>88</td>
           </tr>
           <tr>
               <td>Anggie Maryani</td>
               <td>78</td>
               <td>82</td>
               <td>80</td>
           </tr>
       </tbody>
       <tfoot>
           <tr>
               <td colspan="3">Rata-rata</td>
               <td>85.5</td>
           </tr>
       </tfoot>
   </table>
   ```

   - **Catatan:**
     - Pada contoh ini, tabel dibagi menjadi tiga bagian utama, yang membantu dalam pengorganisasian data dan memungkinkan pengguna untuk dengan mudah memahami struktur tabel.

4. **Baris dan Sel dengan `<tr>`, `<th>`, dan `<td>`**
   - **`<tr>`** digunakan untuk mendefinisikan baris dalam tabel. Setiap baris baru dimulai dengan tag ini.
   - **`<th>`** digunakan untuk membuat header tabel. Sel ini secara default ditampilkan dengan teks tebal dan sejajar di tengah.
   - **`<td>`** digunakan untuk mendefinisikan sel data biasa dalam tabel.

   **Contoh Penggunaan:**
   ```html
   <tr>
       <td>Haikal Mubarok</td>
       <td>92</td>
       <td>89</td>
       <td>91</td>
   </tr>
   ```

5. **Menggabungkan Sel dengan `colspan` dan `rowspan`**
   - **`colspan`** digunakan untuk menggabungkan beberapa kolom menjadi satu sel yang lebih besar. Misalnya, kalian bisa menggunakannya untuk menggabungkan beberapa kolom di header atau footer.
   - **`rowspan`** digunakan untuk menggabungkan beberapa baris menjadi satu sel yang lebih tinggi, sangat berguna untuk data yang berlaku untuk beberapa baris.

   **Contoh Penggunaan `colspan`:**
   ```html
   <tr>
       <th colspan="3">Total Nilai</th>
       <td>265</td>
   </tr>
   ```

   **Contoh Penggunaan `rowspan`:**
   ```html
   <tr>
       <td rowspan="2">Siti Salma</td>
       <td>Matematika: 88</td>
       <td>Bahasa Inggris: 87</td>
   </tr>
   <tr>
       <td>Bahasa Indonesia: 85</td>
       <td>IPA: 90</td>
   </tr>
   ```

#### **Praktikum Lengkap:**

1. **Latihan Membuat Tabel Sederhana Tanpa `<thead>`, `<tbody>`, dan `<tfoot>`**
   - Buatlah tabel sederhana yang menampilkan daftar nilai beberapa siswa dalam beberapa mata pelajaran. Gunakan elemen `<tr>`, `<th>`, dan `<td>` tanpa memisahkannya menjadi bagian-bagian terpisah.

   **Contoh Praktik:**
   ```html
   <!DOCTYPE html>
   <html>
   <head>
       <title>Nilai Siswa XI PPLG 1</title>
   </head>
   <body>
       <h2>Daftar Nilai Siswa Kelas XI PPLG 1</h2>
       <table border="1">
           <tr>
               <th>Nama Siswa</th>
               <th>Matematika</th>
               <th>Bahasa Inggris</th>
               <th>Bahasa Indonesia</th>
           </tr>
           <tr>
               <td>Laelatul Mukarromah</td>
               <td>88</td>
               <td>90</td>
               <td>87</td>
           </tr>
           <tr>
               <td>Mulyana</td>
               <td>82</td>
               <td>85</td>
               <td>80</td>
           </tr>
       </table>
   </body>
   </html>
   ```

2. **Latihan Membuat Tabel dengan `<thead>`, `<tbody>`, dan `<tfoot>`**
   - Buatlah tabel yang menampilkan data yang lebih kompleks dengan membaginya menjadi bagian header, body, dan footer. Gunakan atribut `colspan` untuk menggabungkan sel di footer jika diperlukan.

   **Contoh Praktik:**
   ```html
   <!DOCTYPE html>
   <html>
   <head>
       <title>Rapor Siswa XI PPLG 1</title>
   </head>
   <body>
       <h2>Rapor Siswa Kelas XI PPLG 1</h2>
       <table border="1">
           <thead>
               <tr>
                   <th>Nama Siswa</th>
                   <th>Matematika</th>
                   <th>Bahasa Inggris</th>
                   <th>Bahasa Indonesia</th>
               </tr>
           </thead>
           <tbody>
               <tr>
                   <td>Laelatul Mukarromah</td>
                   <td>88</td>
                   <td>90</td>
                   <td>87</td>
               </tr>
               <tr>
                   <td>Mulyana</td>
                   <td>82</td>
                   <td>85</td>
                   <td>80</td>
               </tr>
           </tbody>
           <tfoot>
               <tr>
                   <td colspan="3">Rata-rata</td>
                   <td>85.3</td>
               </tr>
           </tfoot>
       </table>
   </body>
   </html>
   ```

#### **Diskusi dan Review:**

- **Mengapa Terkadang Tidak Perlu Menggunakan `<thead>`, `<tbody>`, dan `<tfoot>`?**
  - Diskusikan kapan tabel sederhana lebih baik tanpa pembagian ini, terutama jika tabel tersebut hanya memiliki sedikit data atau jika pembagian tersebut tidak menambah nilai

 pada pemahaman data.

- **Bagaimana Penggunaan `colspan` dan `rowspan` Dapat Meningkatkan Tata Letak Tabel?**
  - Diskusikan bagaimana menggabungkan sel-sel dapat membantu dalam menyajikan data yang lebih kompleks atau membuat tampilan tabel lebih ringkas.