# PN STABAT - NARKOTIKA DAN PSIKOTROPIKA

## Deskripsi Dataset
Dataset ini merupakan kumpulan 50 dokumen putusan pengadilan dari Pengadilan Negeri (PN) Stabat dalam kategori **Pidana Khusus** dengan klasifikasi **Narkotika dan Psikotropika**. Dataset dikumpulkan sebagai bagian dari tugas mata kuliah **Temu Kembali Informasi (TKI)** untuk mendukung analisis, penelitian, dan pengembangan model TKI berbasis dokumen hukum terbuka.

Dokumen putusan ini bersifat publik dan tidak terikat Hak atas Kekayaan Intelektual (HaKI), sesuai dengan kebijakan Direktori Putusan Mahkamah Agung Republik Indonesia. Dataset difokuskan pada putusan tahun **2023-2025** dan **tidak termasuk** putusan dengan status **Berkekuatan Hukum Tetap** untuk memastikan relevansi dan kelengkapan data untuk tujuan analisis.

- **Jumlah Dokumen**: 50 putusan (dalam format PDF)
- **Sumber**: Direktori Putusan Mahkamah Agung RI (https://putusan3.mahkamahagung.go.id)
- **Klasifikasi**: Pidana Khusus > Narkotika dan Psikotropika
- **Pengadilan**: PN Stabat (unik antar kelompok, terdaftar di grup WA kelas TKI)
- **Ukuran Dataset**: ~71 MB (setelah kompresi ZIP)

Dataset ini dapat digunakan untuk:
- Ekstraksi informasi otomatis (e.g., entitas bernama, relasi barang bukti).
- Pelatihan model machine learning untuk retrieval informasi hukum.
- Analisis tren kasus narkotika di PN Stabat.

## Struktur Direktori
Repository ini mengikuti struktur direktori sebagai berikut:
```
Dataset-Narkotika_264_265/
├── Dataset/
│   └── Narkotika.zip          # Arsip 50 file PDF putusan (ekstrak untuk akses individu)
├── Overview/
│   └── Overview.xlsx          # Summary metadata 50 putusan (format Excel)
└── README.md                  
```

- **Narkotika.zip**: Berisi 50 file PDF PN STABAT > Pidana Khusus > Narkotika dan Psikotropika. Ekstrak ZIP untuk mengakses file individu.
- **Overview.xlsx**: File Excel dengan sheet "Overview" berisi ringkasan data.

## Deskripsi Kolom Overview.xlsx
File Excel memiliki struktur kolom sederhana sebagai berikut:

| No | No Putusan          | Lembaga Peradilan | Barang Bukti                                                                 | Amar Putusan                                                                 |
|----|---------------------|-------------------|------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| 1  | 622/Pid.Sus/2025/PN Stb | PN STABAT      | 7 bungkus plastik yang berisi plastik klip Narkotika jenis Sabu dengan total 119 (serratus Sembilan belas) plastik klip Narkotika jenis sabu dengan berat kotor total + 83,44 (delapan puluh tiga koma empat puluh empat) gram dan berat netto 57,741 (lima puluh tujuh koma tujuh ratus empat puluh satu) gram; 2 (dua) buah korek api; 1 (satu) buah sedotan plastik; 1 (satu) buah sendok plastik; 1 (satu) buah sendok plastik dari sedotan; 1 (satu) bungkus rokok; 2 (dua) buah isolasi; 1 (satu) buah plastic wrapping; 1 (satu) buah tas slempang; 1 (satu) buah Hp merk oppo warna biru 1 (satu) buah Hp merk VIVO Warna Coklat dengan nomor simcard 085857430552; Dimusnahkan; | [Teks lengkap amar putusan dari Catatan Amar, termasuk ketentuan hukuman dan perintah pengadilan] |
| 2  | ...                | ...              | ...                                                                          | ...                                                                          |
| ...| ...                | ...              | ...                                                                          | ...                                                                          |
| 50 | ...                | ...              | ...                                                                          | ...                                                                          |

- **No**: Nomor urut otomatis (1-50).
- **No Putusan**: Nomor resmi putusan (e.g., 622/Pid.Sus/2025/PN Stb).
- **Lembaga Peradilan**: PN STABAT.
- **Barang Bukti**: Deskripsi barang bukti narkotika (e.g., sabu, alat bantu) yang diekstrak dari "Catatan Amar".
- **Amar Putusan**: Teks lengkap amar putusan dari "Catatan Amar", mencakup vonis, biaya, dan instruksi (e.g., pemusnahan barang bukti).

## Contoh Penggunaan
Untuk memproses dataset:
1. Ekstrak `Narkotika.zip` ke folder `Dataset/Narkotika/`.
2. Buka `Overview.xlsx` di Excel atau Python (dengan pandas):
   ```python
   import pandas as pd
   df = pd.read_excel('Overview/Overview.xlsx')
   print(df['Barang Bukti'].value_counts())  # Analisis frekuensi barang bukti
   ```
3. Untuk TKI: Gunakan teks dari PDF (ekstrak dengan PyPDF2 atau pdfminer) sebagai korpus query.

## Lisensi dan Catatan
- **Lisensi**: Public Domain (data asli dari situs pemerintah RI, bebas digunakan untuk tujuan non-komersial/pendidikan).
- **Catatan**:
  - Data dikumpulkan pada November 2025.
  - Hubungi pemilik repository untuk pertanyaan: [alfitranurr@gmail.com].
  - Sumber lengkap: https://putusan3.mahkamahagung.go.id.


Terima kasih atas kunjungan! Dataset ini dibuat oleh [Al Fitra Nur Ramadhani (202210370311264) & Muhammad Hanif (202210370311265)].
