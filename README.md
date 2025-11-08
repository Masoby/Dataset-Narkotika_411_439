# 🧾 Dokumentasi Dataset Narkotika dan Overview Putusan Pengadilan

## 1. Latar Belakang
Peredaran dan penyalahgunaan narkotika merupakan salah satu permasalahan serius di Indonesia. Dataset ini disusun untuk mendukung kegiatan **analisis data hukum dan kriminalitas**, khususnya dalam mempelajari pola, kecenderungan, serta keputusan hukum terkait tindak pidana narkotika.  

Dataset ini merupakan bagian dari penelitian eksploratif yang bertujuan untuk:
- Melakukan analisis deskriptif terhadap data kasus narkotika;
- Mengidentifikasi pola putusan pengadilan;
- Menyediakan bahan uji untuk sistem berbasis *Case-Based Reasoning* (CBR), *Text Mining*, maupun *Natural Language Processing* (NLP) dalam konteks hukum.

---

## 2. Struktur Direktori
Dataset/
└── Narkotika.zip → Dataset mentah (berisi data kasus dan bukti narkotika)
Overview/
└── Overview.xlsx → Rekapitulasi putusan pengadilan


---

## 3. Deskripsi Dataset

### a. Dataset `Overview.xlsx`
Berisi 51 data putusan pengadilan terkait tindak pidana narkotika dari **Pengadilan Negeri Banjarmasin (PN BANJARMASIN)**.  
Data ini bersumber dari hasil scraping dan pengolahan dokumen putusan yang tersedia untuk umum.

| No | Nama Kolom | Tipe Data | Keterangan |
|----|-------------|------------|-------------|
| 1 | **NO** | Integer | Nomor urut data |
| 2 | **NO PUTUSAN** | String | Nomor perkara pengadilan (mis. *295/Pid.Sus/2025/PN Bjm*) |
| 3 | **LEMBAGA PERADILAN** | String | Nama pengadilan tempat perkara disidangkan |
| 4 | **BARANG BUKTI** | Text | Deskripsi barang bukti yang disita (mis. jumlah paket sabu, alat bukti, dll.) |
| 5 | **AMAR PUTUSAN** | Text | Ringkasan hasil putusan terhadap terdakwa (mis. lama hukuman, vonis, denda, dll.) |

---

## 4. Tujuan Penggunaan
Dataset ini dapat digunakan untuk:
- **Analisis hukum berbasis teks** – memahami pola bahasa hukum dan isi putusan;
- **Pembuatan sistem CBR (Case-Based Reasoning)** untuk rekomendasi putusan berdasarkan kasus serupa;
- **Pelatihan model klasifikasi teks hukum** (misalnya dengan metode SVM, Naïve Bayes, atau Transformer);
- **Evaluasi kecenderungan putusan** (misalnya lama hukuman rata-rata untuk jenis barang bukti tertentu);
- **Eksperimen deteksi anomali atau ketidakwajaran putusan.**

---

## 5. Contoh Penggunaan (Python)

```python
import pandas as pd

# Membaca file Excel
df = pd.read_excel("Overview/Overview.xlsx")

# Melihat 5 baris pertama
print(df.head())

# Contoh analisis sederhana:
# Menghitung jumlah putusan per lembaga peradilan
print(df['LEMBAGA PERADILAN'].value_counts())
