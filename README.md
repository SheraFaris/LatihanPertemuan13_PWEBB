# **LAPORAN PRAKTIKUM**

## **IMPLEMENTASI ARSITEKTUR APLIKASI WEB 3-LAYER PADA APLIKASI CRUD DATA SISWA**

---

### **Identitas Mahasiswa**

| Keterangan    | Data                                       |
| ------------- | ------------------------------------------ |
| Nama          | **Ananda Faris Ghazi Ramadhan**            |
| NRP           | **5025231280**                             |
| Program Studi | Teknik Informatika                         |
| Fakultas      | FTEIC                                      |
| Institusi     | Institut Teknologi Sepuluh Nopember        |
| Mata Kuliah   | Arsitektur Aplikasi Web                    |
| Topik         | Three-Tier Architecture pada Aplikasi CRUD |

**Link Github CRUD: https://github.com/SheraFaris/LatihanPertemuan12_PWEBB.git**

---

## **1. Pendahuluan**

Arsitektur aplikasi web merupakan aspek penting dalam pengembangan sistem berbasis web agar aplikasi dapat berjalan secara terstruktur, aman, dan mudah dikembangkan. Tanpa arsitektur yang jelas, aplikasi cenderung sulit dipelihara, rawan kesalahan, serta tidak scalable.

Pada praktikum ini, dilakukan pengembangan **aplikasi web CRUD (Create, Read, Update, Delete) data siswa** menggunakan **PHP dan MySQL** dengan menerapkan **Arsitektur 3-Layer (Three-Tier Architecture)**. Arsitektur ini membagi aplikasi menjadi tiga lapisan utama, yaitu **Presentation Layer**, **Application Layer**, dan **Data Layer**, sehingga setiap komponen memiliki tanggung jawab yang jelas.

---

## **2. Tujuan Praktikum**

Tujuan dari praktikum ini adalah:

1. Memahami konsep **Arsitektur Aplikasi Web**
2. Menerapkan **Arsitektur 3-Layer (Three-Tier Architecture)**
3. Memisahkan logika tampilan, proses aplikasi, dan akses data
4. Menghasilkan aplikasi web yang rapi, terstruktur, dan mudah dikembangkan
5. Mengimplementasikan CRUD dengan pengelolaan file upload secara aman

---

## **3. Konsep Arsitektur 3-Layer (Three-Tier Architecture)**

Arsitektur 3-Layer membagi sistem aplikasi menjadi tiga lapisan utama:

### **1. Presentation Layer**

Lapisan ini bertanggung jawab terhadap **antarmuka pengguna (user interface)**.

Contoh pada aplikasi:

* `index.php`
* `tambah.php`
* `edit.php`
* HTML & CSS (`style.css`)

Fungsi:

* Menampilkan data ke pengguna
* Menerima input dari form
* Tidak langsung berinteraksi dengan database

---

### **2. Application Layer**

Lapisan ini berisi **logika bisnis dan pengolahan data**.

Contoh pada aplikasi:

* Proses validasi input
* Logika CRUD (insert, update, delete)
* Logika upload dan penghapusan file foto
* Query database melalui PHP

Fungsi:

* Menjembatani tampilan dengan database
* Mengontrol alur aplikasi
* Menjaga keamanan dan konsistensi data

---

### **3. Data Layer**

Lapisan ini bertanggung jawab terhadap **penyimpanan dan pengelolaan data**.

Contoh pada aplikasi:

* Database MySQL (`sekolah_crud`)
* Tabel `siswa`
* File konfigurasi koneksi (`config.php`)
* Folder `uploads/` untuk file foto

Fungsi:

* Menyimpan data siswa
* Menyimpan nama file foto
* Menyediakan data ke application layer

---

## **4. Struktur File Berdasarkan Arsitektur**

```
crud-siswa/
│── index.php        → Presentation Layer
│── tambah.php       → Presentation Layer
│── edit.php         → Presentation Layer
│── hapus.php        → Application Layer
│── config.php       → Data Layer
│── style.css        → Presentation Layer
└── uploads/         → Data Layer (file storage)
```

Struktur ini menunjukkan pemisahan tanggung jawab antar lapisan sesuai prinsip **separation of concerns**.

---

## **5. Perancangan Database (Data Layer)**

Database yang digunakan bernama **`sekolah_crud`** dengan tabel **`siswa`**.

| Field      | Tipe Data | Keterangan        |
| ---------- | --------- | ----------------- |
| id         | INT       | Primary Key       |
| nis        | VARCHAR   | Nomor Induk Siswa |
| nama       | VARCHAR   | Nama siswa        |
| kelas      | VARCHAR   | Kelas             |
| alamat     | TEXT      | Alamat            |
| foto       | VARCHAR   | Nama file foto    |
| created_at | TIMESTAMP | Waktu input       |

Database hanya menyimpan **data teks dan nama file**, sedangkan file foto disimpan secara fisik di folder `uploads`.

---

## **6. Implementasi CRUD dalam Arsitektur 3-Layer**

### **Create**

* User mengisi form pada Presentation Layer
* Application Layer memvalidasi dan memproses data
* Data disimpan ke Data Layer

### **Read**

* Data diambil dari database
* Application Layer memproses hasil query
* Presentation Layer menampilkan data dalam tabel

### **Update**

* Data lama diambil dari database
* User mengubah data melalui form
* Foto lama dihapus jika diganti

### **Delete**

* Data siswa dihapus dari database
* File foto dihapus dari folder `uploads`

---

## **7. Keamanan dan Kerapian Arsitektur**

Dengan arsitektur 3-Layer:

* Query database tidak ditulis sembarangan
* File upload tidak bercampur dengan logic tampilan
* Kode lebih mudah dirawat dan dikembangkan
* Risiko kesalahan dan redundansi kode berkurang

---

## **8. Hasil dan Evaluasi**

Aplikasi berhasil:

* Menerapkan Arsitektur 3-Layer dengan baik
* Menjalankan CRUD secara lengkap
* Mengelola file upload secara terstruktur
* Memisahkan tanggung jawab antar komponen

Struktur ini memudahkan pengembangan lanjutan seperti autentikasi pengguna, pagination, dan API integration.

---

## **9. Kesimpulan**

Dari praktikum ini dapat disimpulkan bahwa:

1. Arsitektur aplikasi web sangat penting dalam pengembangan sistem
2. Arsitektur 3-Layer membantu menciptakan aplikasi yang rapi dan scalable
3. Pemisahan Presentation, Application, dan Data Layer meningkatkan maintainability
4. PHP dan MySQL cocok untuk implementasi arsitektur web dasar

