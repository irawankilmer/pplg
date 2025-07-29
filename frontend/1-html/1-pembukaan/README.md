### **Bab 1: Teknologi Internet untuk Front-End Developer**

---

#### **1.1. Apa Itu Internet?**

**Definisi:**
Internet adalah jaringan komputer global yang saling terhubung melalui berbagai media komunikasi dan protokol standar, yang memungkinkan pertukaran data dan layanan secara real-time di seluruh dunia.

**Sejarah Singkat:**

* **1960-an:** ARPANET oleh Departemen Pertahanan AS.
* **1980-an:** Protokol TCP/IP distandarisasi.
* **1990-an:** WWW ditemukan oleh Tim Berners-Lee → lahirnya web browser.
* **2000-an hingga sekarang:** Perkembangan broadband, 4G/5G, Cloud, IoT.

**Manfaat Internet:**

* Komunikasi (email, pesan instan)
* Informasi (pencarian, berita)
* Transaksi (e-commerce, perbankan)
* Hiburan (streaming, game)
* Kolaborasi (Google Docs, GitHub)

---

#### **1.2. Internet vs Web (WWW)**

* **Internet:** Infrastruktur jaringan global.
* **Web (WWW):** Layanan berbasis internet yang menggunakan HTTP(S), terdiri dari halaman web yang diakses melalui browser.

**Perbedaan HTTP & HTTPS:**

* HTTP: Hypertext Transfer Protocol (tanpa enkripsi)
* HTTPS: HTTP + SSL/TLS (data dienkripsi, lebih aman)

**URL:** Uniform Resource Locator — alamat dari suatu resource (gambar, halaman, file) di web.
Contoh: `https://www.contoh.com/produk?id=123`

**Struktur URL:**

* `https:` → skema/protokol
* `www.contoh.com` → domain
* `/produk` → path
* `?id=123` → query string

---

#### **1.3. Bagaimana Internet Bekerja**

**1. Alamat IP:**
Setiap perangkat memiliki alamat IP unik (IPv4 atau IPv6).

**2. DNS (Domain Name System):**
Menerjemahkan domain menjadi IP address. Misalnya, `google.com` → `142.250.196.46`

**3. Client - Server:**

* **Client (Browser)** mengirim permintaan HTTP ke **Server Web**
* Server mengirim **respon HTTP** berisi konten (HTML, CSS, JS)

**4. Protokol TCP/IP:**

* **TCP:** Memecah data menjadi paket dan menyusun ulang.
* **IP:** Mengirimkan paket ke tujuan.

**5. Routing:**
Router meneruskan paket melalui jalur tercepat hingga sampai ke alamat tujuan.

---

#### **1.4. Komponen Internet**

* **Perangkat Keras:**

  * Komputer, server, router, switch, modem, kabel serat optik
* **Perangkat Lunak:**

  * Browser (Chrome, Firefox), protokol (HTTP, FTP), server (Apache, Nginx)
* **Protokol:**

  * TCP/IP, HTTP/HTTPS, FTP, WebSocket

---

#### **1.5. Peran Internet dalam Front-End Web Development**

* Menyediakan akses ke **library eksternal** (CDN)
* Mengakses data melalui **API (REST/JSON/GraphQL)**
* Menghosting file di server agar dapat diakses melalui URL
* Integrasi layanan pihak ketiga (Google Fonts, Maps, Firebase, dll)

**Contoh Proses:**

1. User mengakses `https://tokoku.com`
2. Browser melakukan DNS lookup
3. Request dikirim ke server
4. Server mengirim HTML → Browser render halaman
5. Browser juga mengambil CSS, JS, gambar via URL

---

#### **1.6. Keamanan dan Infrastruktur Internet**

* **SSL/TLS:** Enkripsi koneksi (ditandai dengan ikon gembok di browser)
* **Firewall:** Menyaring lalu lintas berbahaya
* **VPN:** Mengamankan koneksi dan menyembunyikan identitas
* **CDN (Content Delivery Network):** Mempercepat pengiriman konten dari lokasi server terdekat

---

#### **1.7. Teknologi Terkait Internet**

* **Cloud Computing:** Akses aplikasi/data via internet (contoh: Google Drive, AWS)
* **Internet of Things (IoT):** Perangkat pintar yang terhubung internet (sensor, CCTV, smart home)
* **WebSocket:** Komunikasi dua arah real-time (digunakan pada chat, game online)

---

#### **1.8. Alat Bantu Developer Web**

* **Developer Tools (DevTools):** Debugging HTML, CSS, JS
* **Network Tools:** Ping, traceroute, DNS lookup
* **F12 Tools (di browser):** Melihat permintaan dan respon HTTP
* **Lighthouse:** Audit performa dan aksesibilitas website

---

#### **1.9. Perkembangan Teknologi Internet (terkini)**

* **5G:** Koneksi lebih cepat, mendukung aplikasi real-time
* **Progressive Web Apps (PWA):** Aplikasi web yang bisa berjalan offline
* **HTTP/3:** Protokol web generasi baru yang lebih cepat dan aman
* **Edge Computing:** Memproses data di dekat pengguna (di "edge") untuk latensi rendah

---

#### **Aktivitas dan Latihan**

1. **Diskusi Kelas:**

   * Apa perbedaan internet dan web?
   * Bagaimana protokol HTTP bekerja?

2. **Tugas Individu:**

   * Gambar dan jelaskan alur permintaan dari browser ke server sampai halaman tampil.

3. **Latihan:**

   * Gunakan DevTools untuk memeriksa URL gambar, CSS, dan JS dari suatu situs.

---

### **Navigasi**

[🏠 Home](../../README.md) | [⏭ Bab 2: Pengenalan HTML](../2-perkenalan-html/README.md)
