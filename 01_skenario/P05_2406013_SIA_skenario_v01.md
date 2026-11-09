## 1. Deskripsi Skenario
Tugas ini MELANJUTKAN kasus SIA Pertemuan 4, bukan kasus baru.Diagram acuannya adalah diagram SIA Pertemuan 4, dan kebutuhan acuannya adalah SIA-R07 sampai SIA-R12 (lihat Jobsheet Pertemuan 4, Tabel 4.6). Keterampilan baru pada tugas ini adalah penulisan skenario, bukan perancangan kasus baru, sehingga mahasiswa tidak menambah use case, aktor, atau kebutuhan di luar diagram SIA Pertemuan 4. Tidak ada contoh jawaban SIA di dalam jobsheet ini.

## 2. Kebutuhan Tugas
| ID Kebutuhan | Kebutuhan |
================================================================================================================================================================
| SIA-R07      | Mahasiswa dan Dosen, sebagai Civitas Akademika, dapat melihat kalender akademik.                                                              |
| SIA-R08      | Dosen dapat menginput nilai mata kuliah yang diampunya setelah masa perkuliahan berakhir.                                                     |
| SIA-R09      | Mahasiswa dapat melihat KHS untuk semester yang dipilih dengan hanya menampilkan nilai yang sudah dipublikasikan.                             |
| SIA-R10      | Admin Akademik dapat mengelola data mahasiswa.                                                                                                |
| SIA-R11      | Pengelolaan data mahasiswa terdiri dari tiga bentuk khusus, yaitu tambah, ubah, dan hapus data mahasiswa.                                     |
| SIA-R12      | Model menunjukkan collaboration yang merealisasikan use case Input Nilai Mata Kuliah dan collaboration yang merealisasikan use case Lihat KHS.|

## 3. Batas dan Asumsi
• Kode kebutuhan dimulai dari SIA-R07 agar SIA-R01 dan SIA-R02 (Pertemuan 2) serta SIA-R03 sampai SIA-R06 (Pertemuan 3) tetap empunyai identitas berbeda.
• Pengguna telah terautentikasi dan memiliki hak akses sesuai peran.
• Kalender akademik pada tugas ini adalah agenda resmi institusi (awal semester, batas KRS, masa ujian, dan sejenisnya); jangan menyamakannya dengan jadwal kuliah pada Pertemuan 2.
• Nilai hanya dapat diinput oleh dosen pengampu mata kuliah tersebut. Nilai yang diinput belum terpublikasi sebelum dinyatakan resmi oleh ketentuan tugas ini: KHS hanya menampilkan nilai yang sudah dipublikasikan.
• Hapus Data Mahasiswa hanya untuk mahasiswa yang tidak memiliki dataakademik aktif. Ketentuan ini fiktif untuk latihan.
• Pengajuan KRS tetap digambar sebagai bagian diagram kumulatif dari Pertemuan 3. Pembayaran dan perancangan basis data berada di luar tugas ini.


## 4. Identifikasi Aktor

| Nama Aktor | Deskripsi Peran |
=======================================================================================================================================================================
| Mahasiswa | Melihat jadwal kuliah, mengajukan KRS, mengunduh bukti pengajuan jika tersedia, melihat kalender akademik, dan melihat KHS yang memuat nilai yang telah dipublikasikan. |
| Admin Akademik | Mengelola jadwal kuliah dan mengelola data mahasiswa melalui penambahan, perubahan, serta penghapusan sesuai ketentuan. |
| Dosen | Melihat kalender akademik dan menginput nilai mata kuliah yang diampunya. Menyetujui atau menolak pengajuan KRS mahasiswa bimbingannya pada lingkup Pertemuan|
| Civitas Akademika | Aktor umum yang mewakili perilaku bersama Mahasiswa dan Dosen dalam melihat kalender akademik. |


## 5. Identifikasi Use Case SIA

ID kebutuhan menggunakan awalan `SIA-R`, sedangkan ID use case
menggunakan awalan `SIA-UC`.

Satu kebutuhan dapat dipenuhi oleh lebih dari satu use case.

| ID Use Case | Nama Use Case            | Aktor Terkait  | Peran dalam Model | Acuan Kebutuhan |
===================================================================================================================================
| SIA-UC01    | Melihat Jadwal Kuliah    | Mahasiswa      | Fungsi utama mahasiswa pada Pertemuan | SIA-R01 |
| SIA-UC02    | Mengelola Jadwal Kuliah  | Admin Akademik | Fungsi utama admin pada Pertemuan     | SIA-R02 |
| SIA-UC03    | Mengajukan KRS           | Mahasiswa      | Fungsi utama mahasiswa pada Pertemuan | SIA-R03 |
| SIA-UC04    | Memvalidasi KRS          | Mahasiswa melalui Mengajukan KRS | Perilaku wajib yang disertakan dalam Mengajukan KRS. | SIA-R04 |
| SIA-UC05    | Mengunduh Bukti Pengajuan| Mahasiswa      | Perilaku tambahan bersyarat pada Mengajukan KRS. | SIA-R05 |
| SIA-UC06    | Menyetujui/Menolak KRS   | Dosen Wali     | Fungsi utama dosen wali pada Pertemuan  | SIA-R06 |
| SIA-UC07    | Melihat Kalender Akademik| Civitas Akademika | Fungsi umum yang diwarisi oleh Mahasiswa dan Dosen. | SIA-R07 |
| SIA-UC08    | Input Nilai Mata Kuliah  | Dosen          | Fungsi utama untuk memasukkan nilai mahasiswa. | SIA-R08 |
| SIA-UC09    | Lihat KHS                | Mahasiswa      | Fungsi utama untuk melihat hasil studi yang telah dipublikasikan. | SIA-R09 |
| SIA-UC10    | Mengelola Data Mahasiswa | Admin Akademik | Use case umum pengelolaan data mahasiswa. | SIA-R10 |
| SIA-UC11    | Tambah Data Mahasiswa    | Admin Akademik | Spesialisasi dari Mengelola Data Mahasiswa. | SIA-R11 |
| SIA-UC12    | Ubah Data Mahasiswa      | Admin Akademik | Spesialisasi dari Mengelola Data Mahasiswa. | SIA-R11 |
| SIA-UC13    | Hapus Data Mahasiswa     | Admin Akademik | Spesialisasi dari Mengelola Data Mahasiswa. | SIA-R11 |


## 6. Identifikasi Collaboration
| ID Collaboration | Nama Collaboration | Use Case yang Direalisasikan | Acuan Kebutuhan |
|---|---|---|---|
| SIA-CO01 | Realisasi Input Nilai Mata Kuliah | SIA-UC08 Input Nilai Mata Kuliah | SIA-R12 |
| SIA-CO02 | Realisasi Lihat KHS | SIA-UC09 Lihat KHS | SIA-R12 |

7. Relasi Include dan Extend
 7.1 Relasi Include
    Relasi
`SIA-UC03 Mengajukan KRS «include» SIA-UC04 Memvalidasi KRS`
    Arah panah
Dari Mengajukan KRS menuju Memvalidasi KRS.
    Alasan
Validasi merupakan perilaku wajib dalam pengajuan KRS.
Sistem memeriksa pengajuan sebelum proses pengajuan dinyatakan
berhasil.
    Notasi
Garis putus-putus dengan panah terbuka menuju use case yang
disertakan, disertai label `«include»`.

### 7.2 Relasi Extend
    Relasi
`SIA-UC05 Mengunduh Bukti Pengajuan «extend» SIA-UC03 Mengajukan KRS`
    Arah panah
Dari Mengunduh Bukti Pengajuan menuju Mengajukan KRS.
    Extension point
Setelah pengajuan berhasil dan bukti pengajuan tersedia.
    Kondisi
`[Mahasiswa memilih mengunduh bukti pengajuan]`
    Alasan
Mengunduh bukti merupakan tindakan tambahan yang bersifat opsional.
Pengajuan KRS tetap berhasil meskipun mahasiswa tidak mengunduh bukti.
    Notasi
Garis putus-putus dengan panah terbuka menuju use case dasar,
disertai label `«extend»`.

8. Generalization Aktor
 8.1 Relasi
- Mahasiswa → Civitas Akademika.
- Dosen → Civitas Akademika.


9. Generalization Use Case
 9.1 Relasi
- SIA-UC11 Tambah Data Mahasiswa → SIA-UC10 Mengelola Data Mahasiswa.
- SIA-UC12 Ubah Data Mahasiswa → SIA-UC10 Mengelola Data Mahasiswa.
- SIA-UC13 Hapus Data Mahasiswa → SIA-UC10 Mengelola Data Mahasiswa.

| Use Case Khusus | Perilaku Pembeda |
==========================================================================
| Tambah Data Mahasiswa | Membuat dan menyimpan data mahasiswa baru. |
| Ubah Data Mahasiswa | Memperbarui data mahasiswa yang telah tersimpan. |
| Hapus Data Mahasiswa | Menghapus data mahasiswa yang memenuhi ketentuan penghapusan. |


10. Collaboration/Realization
 10.1 Realisasi Input Nilai Mata Kuliah
    Relasi
`SIA-CO01 Realisasi Input Nilai Mata Kuliah → SIA-UC08 Input Nilai Mata Kuliah`
    Penjelasan
Collaboration SIA-CO01 merealisasikan perilaku Input Nilai Mata Kuliah,
yang mencakup pemeriksaan dosen pengampu, penerimaan isian nilai,
validasi nilai, dan penyimpanan nilai.

Hasil penyimpanan nilai belum otomatis dipublikasikan.

 10.2 Realisasi Lihat KHS
    Relasi
`SIA-CO02 Realisasi Lihat KHS → SIA-UC09 Lihat KHS`
    Penjelasan
Collaboration SIA-CO02 merealisasikan perilaku Lihat KHS,
yang mencakup pengambilan data hasil studi mahasiswa,
pemeriksaan status publikasi nilai, dan penampilan KHS.

Nilai yang belum dipublikasikan tidak ditampilkan sebagai hasil
studi yang telah resmi tersedia.

 10.3 Arah Panah dan Notasi
- Collaboration digambarkan sebagai elips bergaris putus-putus.
- Relasi realization digambarkan sebagai garis putus-putus dengan
  kepala panah segitiga kosong.
- Arah panah berasal dari collaboration menuju use case yang
  direalisasikannya.

 10.4 Hubungan Data antara Input Nilai dan Lihat KHS
Nilai yang disimpan melalui Input Nilai Mata Kuliah dapat digunakan
oleh Lihat KHS setelah nilai tersebut dipublikasikan.

Hubungan pemanfaatan data tersebut tidak berarti bahwa Input Nilai
Mata Kuliah merealisasikan Lihat KHS.

Karena itu, jangan menggambar relasi realization langsung:

`Input Nilai Mata Kuliah → Lihat KHS`

Gunakan dua collaboration yang masing-masing merealisasikan
use case terkait.


| Jenis Relasi | Sumber | Tujuan | Keterangan |
|---|---|---|---|
| Association | Mahasiswa | Melihat Jadwal Kuliah | Akses mahasiswa ke jadwal kuliah. |
| Association | Admin Akademik | Mengelola Jadwal Kuliah | Akses admin ke pengelolaan jadwal. |
| Association | Mahasiswa | Mengajukan KRS | Akses mahasiswa ke pengajuan KRS. |
| Association | Dosen Wali | Menyetujui/Menolak KRS | Akses dosen wali sesuai penugasan. |
| Include | Mengajukan KRS | Memvalidasi KRS | Validasi wajib dijalankan dalam pengajuan. |
| Extend | Mengunduh Bukti Pengajuan | Mengajukan KRS | Pengunduhan bersifat opsional. |
| Generalization aktor | Mahasiswa | Civitas Akademika | Mahasiswa merupakan aktor khusus. |
| Generalization aktor | Dosen | Civitas Akademika | Dosen merupakan aktor khusus. |
| Association | Civitas Akademika | Melihat Kalender Akademik | Perilaku umum Mahasiswa dan Dosen. |
| Association | Dosen | Input Nilai Mata Kuliah | Akses dibatasi kepada dosen pengampu. |
| Association | Mahasiswa | Lihat KHS | Akses terhadap hasil studi sendiri. |
| Association | Admin Akademik | Mengelola Data Mahasiswa | Akses pengelolaan data mahasiswa. |
| Generalization use case | Tambah Data Mahasiswa | Mengelola Data Mahasiswa | Bentuk khusus penambahan data. |
| Generalization use case | Ubah Data Mahasiswa | Mengelola Data Mahasiswa | Bentuk khusus perubahan data. |
| Generalization use case | Hapus Data Mahasiswa | Mengelola Data Mahasiswa | Bentuk khusus penghapusan data. |
| Realization | SIA-CO01 | Input Nilai Mata Kuliah | Collaboration merealisasikan penginputan nilai. |
| Realization | SIA-CO02 | Lihat KHS | Collaboration merealisasikan penampilan KHS. |