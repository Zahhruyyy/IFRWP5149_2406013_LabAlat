Langkah 2: Katalog Use Case Gabungan (Kumulatif)

| ID Use Case | Nama Use Case | Aktor Terkait | Sumber Kebutuhan | Status |
|--------------|-------------------------------|--------------------------------------|------------------|--------|
| SIA-UC01 | Melihat Jadwal Kuliah | Mahasiswa | SIA-R01 | Tetap |
| SIA-UC02 | Kelola Jadwal Kuliah | Admin Akademik | SIA-R02 | Tetap |
| SIA-UC03 | Ajukan KRS | Mahasiswa | SIA-R03 | Tetap |
| SIA-UC04 | Validasi KRS | Sistem (include SIA-UC03) | SIA-R04 | Tetap |
| SIA-UC05 | Unduh Bukti Pengajuan KRS | Mahasiswa | SIA-R05 (extend SIA-UC03) | Tetap |
| SIA-UC06 | Proses Keputusan KRS | Dosen Wali | SIA-R06 | Tetap |
| SIA-UC07 | Lihat Kalender Akademik | Civitas Akademika | SIA-R07 | Baru |
| SIA-UC08 | Input Nilai Mata Kuliah | Dosen | SIA-R08 | Baru |
| SIA-UC09 | Lihat KHS | Mahasiswa | SIA-R09 | Baru |
| SIA-UC10 | Kelola Data Mahasiswa | Admin Akademik | SIA-R10 | Baru |
| SIA-UC11 | Tambah Data Mahasiswa | Admin Akademik | SIA-R11 (via SIA-UC10) | Baru |
| SIA-UC12 | Ubah Data Mahasiswa | Admin Akademik | SIA-R11 (via SIA-UC10) | Baru |
| SIA-UC13 | Hapus Data Mahasiswa | Admin Akademik | SIA-R11 (via SIA-UC10) | Baru |

Langkah 3: Generalization Aktor

### Hierarki

**Aktor Umum**
- Civitas Akademika

**Aktor Khusus**
- Mahasiswa
- Dosen

Kedua aktor tersebut merupakan spesialisasi dari **Civitas Akademika**.

### Fungsi yang Diwarisi

- SIA-UC07 – Lihat Kalender Akademik

### Alasan Pemodelan

Penggunaan generalization bertujuan menghindari penggandaan hubungan asosiasi pada diagram. Karena Mahasiswa dan Dosen sama-sama memiliki hak untuk melihat Kalender Akademik, maka fungsi tersebut cukup dihubungkan ke aktor umum **Civitas Akademika**, sedangkan Mahasiswa dan Dosen mewarisi fungsi tersebut melalui relasi **Generalization**.

---

# Langkah 4: Generalization Use Case

### Use Case Umum

**SIA-UC10 – Kelola Data Mahasiswa**

### Use Case Khusus

- SIA-UC11 – Tambah Data Mahasiswa
- SIA-UC12 – Ubah Data Mahasiswa
- SIA-UC13 – Hapus Data Mahasiswa

### Perilaku Pembeda

**SIA-UC11 – Tambah Data Mahasiswa**

Menambahkan data mahasiswa baru beserta identitasnya ke dalam sistem akademik.

**SIA-UC12 – Ubah Data Mahasiswa**

Memperbarui informasi mahasiswa yang telah terdaftar apabila terdapat perubahan data.

**SIA-UC13 – Hapus Data Mahasiswa**

Menghapus data mahasiswa dari sistem dengan ketentuan mahasiswa tersebut tidak memiliki data akademik yang masih aktif.

---

# Langkah 5: Collaboration

### Collaboration ID

**SIA-CO01**

### Nama Collaboration

**Input Nilai Mata Kuliah**

### Realizes Use Case

**SIA-UC08 – Input Nilai Mata Kuliah**

---

### Collaboration ID

**SIA-CO02**

### Nama Collaboration

**Lihat KHS**

### Realizes Use Case

**SIA-UC09 – Lihat KHS**

---

# Langkah 6: Use Case Description

## Deskripsi Lengkap

### SIA-UC08 – Input Nilai Mata Kuliah

**ID & Nama Use Case**

SIA-UC08 – Input Nilai Mata Kuliah

**Collaboration**

SIA-CO01 – Input Nilai Mata Kuliah

**Aktor Utama**

Dosen

**Deskripsi Singkat**

Dosen menginput nilai mahasiswa pada mata kuliah yang diampunya setelah proses perkuliahan selesai.

### Prasyarat

- Dosen telah terautentikasi ke dalam sistem.
- Dosen merupakan pengampu mata kuliah tersebut.
- Data mahasiswa pada mata kuliah tersedia.

### Alur Utama (Main Success Scenario)

1. Dosen memilih menu **Input Nilai Mata Kuliah**.
2. Sistem menampilkan daftar mata kuliah yang diampu.
3. Dosen memilih mata kuliah dan kelas.
4. Sistem menampilkan daftar mahasiswa.
5. Dosen menginput nilai setiap mahasiswa.
6. Sistem memvalidasi data nilai yang dimasukkan.
7. Dosen menyimpan data nilai.
8. Sistem menyimpan nilai mahasiswa.

### Alur Alternatif

**6a. Data nilai tidak valid**

Sistem menampilkan pesan kesalahan dan meminta dosen memperbaiki data nilai sebelum disimpan.

### Pascakondisi Berhasil

Data nilai mahasiswa berhasil disimpan ke dalam sistem.

### Pascakondisi Gagal

Data nilai tidak tersimpan sehingga perubahan nilai tidak dilakukan.

---

# Deskripsi Lengkap

## SIA-UC09 – Lihat KHS

**ID & Nama Use Case**

SIA-UC09 – Lihat KHS

**Collaboration**

SIA-CO02 – Lihat KHS

**Aktor Utama**

Mahasiswa

**Deskripsi Singkat**

Mahasiswa melihat Kartu Hasil Studi (KHS) untuk semester yang nilai mata kuliahnya telah dipublikasikan.

### Prasyarat

- Mahasiswa telah login ke sistem.
- Nilai semester yang dipilih telah dipublikasikan.

### Alur Utama (Main Success Scenario)

1. Mahasiswa memilih menu **Lihat KHS**.
2. Sistem menampilkan daftar semester.
3. Mahasiswa memilih semester.
4. Sistem mengambil data nilai yang telah dipublikasikan.
5. Sistem menghitung IP Semester apabila diperlukan.
6. Sistem menampilkan KHS kepada mahasiswa.

### Alur Alternatif

**4a. Nilai belum dipublikasikan**

Sistem menampilkan informasi bahwa nilai semester tersebut belum tersedia.

### Pascakondisi Berhasil

Mahasiswa dapat melihat KHS semester yang dipilih.

### Pascakondisi Gagal

KHS tidak dapat ditampilkan karena nilai belum dipublikasikan atau data tidak tersedia.

---

Versi ini sudah konsisten dengan skenario yang kamu berikan, termasuk penggunaan **generalization**, **include**, **extend**, serta **collaboration** tanpa menambahkan aturan yang tidak ada pada skenario.