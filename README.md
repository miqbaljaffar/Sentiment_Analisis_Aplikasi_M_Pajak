Analisis Sentimen Aplikasi M-Pajak/CoreTax
Proyek ini bertujuan untuk menganalisis sentimen pengguna terhadap aplikasi M-Pajak (juga dikenal sebagai CoreTax DJP) berdasarkan ulasan yang diberikan di Google Play Store. Analisis ini menggunakan teknik Natural Language Processing (NLP) dan Machine Learning untuk mengklasifikasikan ulasan ke dalam sentimen positif, negatif, atau netral.

Insight Utama
Berdasarkan analisis terhadap lebih dari 4.600 ulasan pengguna, ditemukan beberapa insight penting:

Sentimen Mayoritas Negatif: Sebagian besar ulasan (sekitar 83%) menunjukkan sentimen negatif. Hal ini mengindikasikan adanya masalah signifikan yang dihadapi pengguna saat menggunakan aplikasi.

Isu Utama Pengguna (Sentimen Negatif): Dari visualisasi Word Cloud, keluhan utama pengguna berpusat pada kata-kata seperti "susah", "error", "ribet", "verif" (verifikasi), dan "npwp". Ini menunjukkan bahwa masalah utama terkait dengan proses verifikasi yang sulit, aplikasi yang sering mengalami kesalahan teknis, dan alur penggunaan yang dianggap rumit, terutama dalam hal pendaftaran NPWP.

Apresiasi Pengguna (Sentimen Positif): Meskipun jumlahnya lebih sedikit, ulasan positif umumnya mengandung kata-kata seperti "mudah", "bantu", dan "bagus". Ini menandakan bahwa sebagian pengguna merasa aplikasi ini membantu dan mudah digunakan ketika berfungsi dengan baik.

Performa Model: Model Deep Learning dengan arsitektur Bidirectional LSTM (BiLSTM) menunjukkan performa terbaik dalam mengklasifikasikan sentimen dengan akurasi pengujian mencapai ~88%. Ini membuktikan bahwa model mampu memahami konteks ulasan pengguna dengan cukup baik.

Metodologi
Proses analisis dilakukan melalui beberapa tahapan:

Pengumpulan Data: Data ulasan diambil (scraping) dari Google Play Store untuk aplikasi dengan ID id.go.pajak.djp menggunakan pustaka google-play-scraper.

Preprocessing Teks: Teks ulasan dibersihkan melalui serangkaian proses untuk mempersiapkannya sebelum masuk ke model, meliputi:

Case Folding: Mengubah semua teks menjadi huruf kecil.

Cleaning: Menghapus URL, mention, hashtag, angka, dan tanda baca.

Slang Word Normalization: Mengubah kata-kata tidak baku menjadi baku (contoh: "gak" -> "tidak").

Stopword Removal: Menghapus kata-kata umum yang tidak memiliki makna sentimen (contoh: "yang", "di", "dan").

Stemming: Mengubah kata berimbuhan menjadi kata dasar menggunakan pustaka Sastrawi (contoh: "membantu" -> "bantu").

Pelabelan Sentimen: Ulasan diberi label sentimen berdasarkan peringkat bintang yang diberikan pengguna:

Negatif: 1-2 Bintang

Netral: 3 Bintang

Positif: 4-5 Bintang

Pemodelan: Beberapa model machine learning dan deep learning dilatih dan dievaluasi, termasuk:

Logistic Regression

Support Vector Machine (SVM)

Random Forest

Bidirectional LSTM (BiLSTM)

Kesimpulan dan Rekomendasi
Secara keseluruhan, aplikasi M-Pajak/CoreTax masih memiliki banyak ruang untuk perbaikan. Sentimen yang didominasi oleh ulasan negatif menunjukkan adanya kendala teknis dan fungsional yang signifikan.

Rekomendasi untuk Pengembang:

Prioritaskan Perbaikan Proses Verifikasi: Sederhanakan dan percepat alur verifikasi yang sering dikeluhkan pengguna.

Stabilitas Aplikasi: Fokus pada perbaikan bug dan error untuk meningkatkan keandalan aplikasi.

Penyederhanaan Antarmuka (UI/UX): Desain ulang alur penggunaan agar lebih intuitif dan tidak "ribet", terutama untuk layanan krusial seperti pendaftaran NPWP.

Cara Menjalankan Proyek
Prasyarat:

Python 3.x

Jupyter Notebook atau lingkungan Python lainnya

Instalasi Dependensi:
Pastikan semua pustaka yang dibutuhkan telah terinstal dengan menjalankan perintah berikut di terminal:

pip install -r requirements.txt

Menjalankan Analisis:

Buka dan jalankan file Sentiment_Analisis_Aplikasi_M_Pajak.ipynb di Jupyter Notebook.

Notebook akan secara otomatis melakukan scraping data jika file pajak_reviews_min10k.csv tidak ditemukan.
