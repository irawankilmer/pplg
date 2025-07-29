## Peran Modeling dalam SDLC (berdasarkan ISO/IEC/IEEE 12207 & SWEBOK)

---

### 1. Tentang ISO/IEC/IEEE 12207: Life Cycle Processes

* ISO 12207 (diperbarui 2017) mendefinisikan proses hidup perangkat lunak (software life cycle), bukan fase waktu, melainkan **activity/process** yang mendukung pengembangan & pemeliharaan perangkat lunak. ([Wikipedia][1], [Wikipedia][2])
* Standar ini bersifat modular, dapat di-*tailor* untuk setiap proyek dengan memilih proses yang relevan (proses dasar, pendukung, organisasi).

---

### 2. Di Mana Modeling Berperan dalam ISO 12207?

Modeling mendukung beberapa proses penting:

* **Persiapan dan spesifikasi kebutuhan**
* **Desain arsitektur dan desain detil**
* **Validasi & verifikasi model**
* **Manajemen konfigurasi & dokumentasi**
  Model (baik diagram UML, ERD, atau dokumentasi arsitektur) menjadi *work product* utama dari proses desain dan review.

---

### 3. SWEBOK v4 – Area Knowledge “Software Engineering Models & Methods”

Menurut SWEBOK KA–9:

* Modeling adalah teknik untuk menyampaikan abstraksi sistem untuk komunikasi, analisis, dan pengambilan keputusan.
* Ada prinsip modeling:

  * **Abstraction**: fokus pada aspek penting, tinggalkan yang tidak relevan.
  * **Viewpoint & View**: representasi sistem dari sudut kepentingan stakeholder yang berbeda.
* Tipikal tipe model:

  * *Information Modeling* (misal conceptual model, ERD)
  * *Structure Modeling* (UML class, component, deployment)
  * *Behavior Modeling* (state machines, activity, data flow)
* Teknik analisis model mencakup validasi **completeness**, **consistency**, **correctness**, **traceability**, dan **interaction analysis**.

---

### 4. Relasi ISO 12207 ↔ SWEBOK

| ISO/IEC/IEEE 12207 Process Features | SWEBOK KA–9 Role of Modeling                                                                |
| ----------------------------------- | ------------------------------------------------------------------------------------------- |
| Proses termasuk desain & verifikasi | Modeling menghasilkan produk desain & analisis                                              |
| Output berupa artefak dokumentasi   | Modeling menyediakan produk seperti diagram UML, ERD                                        |
| Konfigurasi & traceability penting  | SWEBOK menggariskan traceability antar model, kebutuhan, test ([Wikipedia][8], [GitHub][9]) |

---

### 5. Manfaat Modeling dalam SDLC

* Mengurangi risiko kesalahan sejak awal
* Memudahkan review dan keterlibatan stakeholder
* Mendukung traceability hingga pengujian dan pemeliharaan
* Menyediakan artefak yang dapat di-*reuse* untuk dokumentasi dan migrasi sistem

---

### 6. Studi Kasus Mini

**Contoh**: Sebuah startup ingin membangun sistem inventaris dengan pendekatan ISO 12207.

1. Proses *requirements elicitation* → membuat model kebutuhan (*use case*, *domain model*).
2. Proses *design* → menghasilkan arsitektur sistem (*component UML*, *deployment diagram*).
3. Proses *verification* → review model & uji traceability match dengan kebutuhan.
4. Proses *configuration management* → model-model tersebut menjadi artefak versi kontrol.

---

### 7. Ringkasan:

* **Modeling** merupakan bagian integral dari SDLC menurut standar ISO 12207 dan definisi kita di SWEBOK.
* Modeling diarahkan bukan hanya membuat diagram, tapi memastikan kualitas, konsistensi, dan traceability dari kebutuhan hingga testing.
* Penerapan modeling standar membantu memastikan perangkat lunak **tepat guna, aman, dan dikelola dengan baik**.

---

### Aktivitas Diskusi & Latihan:

1. **Diskusi Grup**

   > Identifikasi di SDLC (berdasarkan ISO 12207) di mana modeling berperan; jelaskan output yang dihasilkan.

2. **Latihan Individu**

   > Buatlah diagram *domain model* dan *sequence* sederhana dari sistem pemesanan siswa → gunakan teknik traceability untuk memetakan koneksi model ke kebutuhan fungsional.