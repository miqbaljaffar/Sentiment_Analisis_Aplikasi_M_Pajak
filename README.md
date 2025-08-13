# 📊 Analisis Sentimen Aplikasi M-Pajak / CoreTax DJP

Proyek ini bertujuan untuk **menganalisis sentimen pengguna** terhadap aplikasi **M-Pajak** (juga dikenal sebagai CoreTax DJP) berdasarkan ulasan yang diambil dari **Google Play Store**.  
Analisis ini menggunakan **Natural Language Processing (NLP)** dan **Machine Learning** untuk mengklasifikasikan ulasan ke dalam **sentimen positif, negatif, atau netral**.

---

## 📌 Insight Utama

> Berdasarkan analisis terhadap **4.600+ ulasan pengguna**, ditemukan beberapa poin penting:

- **🚨 Sentimen Mayoritas Negatif**  
  ±83% ulasan bernada negatif — indikasi adanya masalah signifikan yang dihadapi pengguna.

- **⚠ Isu Utama Pengguna** (Negatif)  
  Berdasarkan Word Cloud, keluhan dominan berkaitan dengan:  
  `"susah"`, `"error"`, `"ribet"`, `"verif"` (verifikasi), `"npwp"`.  
  Masalah paling sering muncul:  
  - Proses verifikasi yang rumit  
  - Error teknis yang sering terjadi  
  - Alur penggunaan yang membingungkan (terutama pendaftaran NPWP)

- **✅ Apresiasi Pengguna** (Positif)  
  Ulasan positif biasanya mengandung kata: `"mudah"`, `"bantu"`, `"bagus"`.  
  Artinya, ketika aplikasi berjalan dengan baik, pengguna menganggapnya **membantu** dan **mudah digunakan**.

- **🤖 Performa Model**  
  Model Deep Learning **Bidirectional LSTM (BiLSTM)** memberikan akurasi tertinggi: **±88%**.  
  Ini membuktikan kemampuan model memahami konteks ulasan dengan baik.

---

## 🛠 Metodologi Analisis

### 1. **Pengumpulan Data**
- Data diambil dari **Google Play Store** menggunakan pustaka [`google-play-scraper`](https://pypi.org/project/google-play-scraper/)  
- Target aplikasi: `id.go.pajak.djp`

### 2. **Preprocessing Teks**
- **Case Folding** → semua huruf menjadi lowercase  
- **Cleaning** → hapus URL, mention, hashtag, angka, tanda baca  
- **Slang Normalization** → ubah kata tidak baku (contoh: *gak* → *tidak*)  
- **Stopword Removal** → hapus kata umum tanpa makna sentimen (contoh: *yang*, *di*, *dan*)  
- **Stemming** → ubah kata berimbuhan menjadi kata dasar (contoh: *membantu* → *bantu*) dengan pustaka **Sastrawi**

### 3. **Pelabelan Sentimen**
- **Negatif**: ⭐ 1–2  
- **Netral**: ⭐ 3  
- **Positif**: ⭐ 4–5

### 4. **Pemodelan**
Model yang diuji:
- Logistic Regression
- Support Vector Machine (SVM)
- Random Forest
- **Bidirectional LSTM (BiLSTM)** → performa terbaik

---

## 📈 Kesimpulan & Rekomendasi

- **Dominasi Sentimen Negatif** → aplikasi butuh perbaikan signifikan
- **Masalah utama**: proses verifikasi, stabilitas, UI/UX

**Rekomendasi untuk Pengembang:**
1. **Sederhanakan Proses Verifikasi**  
2. **Perbaiki Stabilitas Aplikasi** (bug & error)  
3. **Redesign UI/UX** agar lebih intuitif dan tidak “ribet”

---

## 🚀 Cara Menjalankan Proyek

### **Prasyarat**
- Python 3.x  
- Jupyter Notebook / lingkungan Python lain

### **Instalasi Dependensi**
```bash
pip install -r requirements.txt
````

### **Menjalankan Analisis**

1. Buka file:

   ```bash
   Sentiment_Analisis_Aplikasi_M_Pajak.ipynb
   ```
2. Jalankan di Jupyter Notebook
3. Jika `pajak_reviews_min10k.csv` tidak ditemukan → proses scraping data akan otomatis dilakukan

---

## 📂 Struktur Folder

```
📦 m-pajak-sentiment-analysis
 ┣ 📜 Sentiment_Analisis_Aplikasi_M_Pajak.ipynb
 ┣ 📜 requirements.txt
 ┣ 📜 pajak_reviews_min10k.csv (opsional)
 ┗ 📜 README.md
```

---

💡 *Analisis ini diharapkan dapat menjadi bahan evaluasi untuk meningkatkan pengalaman pengguna aplikasi M-Pajak / CoreTax.*
