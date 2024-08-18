### **Bab 2: Perkenalan HTML**
**Apa Itu HTML?**

Oke, kalian mungkin sering dengar tentang HTML, tapi apa sih sebenarnya HTML itu? HTML, atau **HyperText Markup Language**, adalah bahasa yang digunakan untuk membuat halaman web. Kalian bisa bayangkan HTML seperti cetak biru atau kerangka bangunan. Tanpa kerangka ini, rumah (atau halaman web) nggak akan bisa berdiri dengan baik. Jadi, HTML ini adalah dasar yang memberi struktur pada semua konten yang nanti akan kalian tampilkan di halaman web.

**Kenapa HTML Itu Penting?**

Coba bayangkan kalian sedang membangun rumah. Kalian butuh fondasi yang kuat, kan? Nah, HTML itu adalah fondasi untuk setiap situs web. Tanpa HTML, browser seperti Chrome atau Firefox nggak akan tahu gimana caranya menampilkan teks, gambar, video, dan elemen lainnya yang ada di web. Jadi, HTML ini adalah bahasa yang pertama kali harus kalian pelajari kalau ingin membuat halaman web.

**Cara Kerja HTML**

HTML bekerja dengan apa yang disebut "tag". Tag ini dikelilingi oleh tanda kurung sudut `< >`. Ada dua jenis tag yang biasanya dipakai: **tag pembuka** dan **tag penutup**. Misalnya, kalau kalian ingin membuat paragraf teks, kalian pakai tag `<p>` untuk membuka paragraf dan `</p>` untuk menutupnya. Jadi, semua teks yang ingin kalian masukkan dalam paragraf harus berada di antara tag pembuka dan penutup ini.

Contohnya kayak gini:

```html
<p>Ini adalah sebuah paragraf sederhana.</p>
```

Di sini, `<p>` adalah tag pembuka, dan `</p>` adalah tag penutup. Teks "Ini adalah sebuah paragraf sederhana." akan tampil di browser sebagai sebuah paragraf.

**Struktur Dasar HTML**

Setiap halaman web memiliki struktur dasar yang mirip-mirip, seperti tubuh kita yang punya kepala, badan, dan kaki. Di HTML, ada beberapa bagian utama yang selalu ada di setiap halaman web:

- **`<!DOCTYPE html>`**: Ini seperti pengumuman ke browser, "Hei, ini dokumen HTML5, ya!"
- **`<html>`**: Semua isi halaman web dibungkus dalam tag ini, ibaratnya ini adalah tubuh utama dari halaman web kalian.
- **`<head>`**: Di sini tempatnya informasi-informasi penting tentang halaman kalian, seperti judul dan link ke file CSS.
- **`<body>`**: Nah, ini bagian di mana semua konten yang bakal dilihat oleh pengguna berada. Mulai dari teks, gambar, hingga video, semuanya ada di dalam tag `<body>`.

Berikut ini adalah contoh struktur HTML yang sangat sederhana:

```html
<!DOCTYPE html>
<html>
<head>
    <title>Halaman Web Pertama Saya</title>
</head>
<body>
    <h1>Halo, Dunia!</h1>
    <p>Selamat datang di halaman web pertama saya. Ini adalah contoh paragraf yang dibuat menggunakan HTML.</p>
</body>
</html>
```

Di contoh ini, kita bikin halaman sederhana yang punya judul "Halaman Web Pertama Saya", sebuah judul besar "Halo, Dunia!" di dalam tag `<h1>`, dan paragraf yang menyapa pengunjung dengan teks "Selamat datang di halaman web pertama saya." dalam tag `<p>`.

---
### Navigasi
[⏮Intro HTML](../1-pembukaan/README.md) || [Home🏠](../../README.md) || [Tag Dasar HTML⏭](../3-tag-dasar-html/README.md)