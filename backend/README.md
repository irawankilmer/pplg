## Pembahasan
1. [Pengantar](./1-pengantar/README.md)
2. [Konfigurasi](./2-konfigurasi/README.md)
3. [Variable](./3-variable/README.md)
4. [Tipe Data](./4-tipe-data/README.md)
5. [Operator](./5-operator/README.md)
6. [Control Flow](./6-control-flow/README.md)
7. [Function](./7-function/README.md)
8. [Array](./8-array/README.md)
9. [Super Globals](./9-super-globals/README.md)
10. [Form Handling](./10-form-handling/README.md)
11. [Database Driver Intro](./11-database-driver-intro/README.md)
12. [Database Driver PDO](./12-database-driver-pdo/README.md)
13. [Database Driver MySqli - Prosedural](./13-database-driver-mysqli-prosedural/README.md)
14. [Database Driver MySqli - Object Oriented Programming](./14-database-driver-mysqli-oop/README.md)


Benar, **`$_SESSION` dan `$_COOKIE`** termasuk bagian dari *Super Globals*, tapi pembahasan tentang **Session & Cookie** idealnya **dipisahkan menjadi subtopik tersendiri**, karena:

* Perlu konfigurasi dan pemahaman lifecycle (mulai, simpan, hapus)
* Penting untuk autentikasi dan manajemen user

---

**Soal `Variable Scope`**, itu memang **penting dan sebaiknya dibahas setelah Variable**, karena:

* Menjelaskan perbedaan **global**, **local**, **static**
* Jadi jembatan ke topik Function (karena sering bentrok scope-nya)

---

### ✅ Saran Susunan Revisi Roadmap

1. **Pengantar**
2. **Konfigurasi**
3. **Variable**
4. **Variable Scope** ✅ *tambahkan di sini*
5. **Tipe Data**
6. **Operator**
7. **Control Flow**
8. **Function**
9. **Array**
10. **Super Globals**

    * (hanya pengenalan singkat semua: `$_GET`, `$_POST`, `$_SESSION`, dll)
11. **Form Handling**
12. **Session & Cookie** ✅ *pisahkan di sini*
13. **Validasi Data** *(optional tapi penting)*
14. **Database Driver Intro**
15. **PDO**
16. **MySQLi - Prosedural**
17. **MySQLi - OOP**
18. **CRUD Lengkap**
19. **Keamanan Dasar**
20. **Mini Project (statis ke dinamis)**

Dengan alur ini, siswa belajar secara **bertahap** dari dasar ke praktik nyata. Mau roadmap-nya saya rapiin jadi format tabel atau outline juga bisa.
