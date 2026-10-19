# Prediksi Customer Churn Menggunakan Machine Learning

Proyek ini merupakan studi kasus analisis data dan *machine learning* untuk memprediksi kemungkinan pelanggan berhenti berlangganan (*customer churn*). Proyek dibuat sebagai implementasi konsep *predictive analytics* menggunakan dataset publik IBM Telco Customer Churn.

## Latar Belakang

Customer churn adalah kondisi ketika pelanggan berhenti menggunakan layanan suatu perusahaan. Prediksi churn dapat membantu perusahaan mengenali pelanggan yang berpotensi berhenti berlangganan sehingga strategi retensi dapat direncanakan dengan lebih tepat.

Pada proyek ini, data pelanggan dianalisis dan digunakan untuk membangun model klasifikasi yang memperkirakan apakah pelanggan akan melakukan churn.

## Tujuan

- Memahami karakteristik pelanggan berdasarkan data.
- Melakukan pemeriksaan dan prapemrosesan data.
- Membangun dan membandingkan model klasifikasi.
- Mengevaluasi hasil model menggunakan beberapa metrik, bukan hanya akurasi.
- Mengidentifikasi insight yang dapat mendukung pengambilan keputusan bisnis.

## Dataset

Dataset yang digunakan adalah **IBM Telco Customer Churn**, yang berisi informasi pelanggan layanan telekomunikasi dan status churn mereka.

Dataset diakses melalui sumber publik berikut:

- [IBM Telco Customer Churn Dataset (CSV)](https://raw.githubusercontent.com/IBM/telco-customer-churn-on-icp4d/master/data/Telco-Customer-Churn.csv)

Kolom target yang diprediksi adalah `Churn`, yang menunjukkan apakah pelanggan berhenti berlangganan (`Yes`) atau tidak (`No`).

> Catatan: notebook mengunduh dataset dari URL publik. Ketersediaan dataset bergantung pada sumber tersebut.

## Metode

Proyek membandingkan dua algoritma klasifikasi:

1. **Logistic Regression** — model klasifikasi yang digunakan sebagai baseline.
2. **Random Forest** — model berbasis kumpulan pohon keputusan yang dapat menangkap hubungan nonlinier pada data.

Prapemrosesan dilakukan melalui pipeline agar transformasi fitur numerik dan kategorikal diterapkan secara konsisten pada data pelatihan dan evaluasi.

## Alur Analisis

1. Memuat dataset.
2. Memeriksa struktur data, tipe kolom, nilai kosong, duplikasi, dan distribusi target.
3. Melakukan eksplorasi data dan visualisasi.
4. Memisahkan fitur dan target.
5. Membagi data menjadi data latih, validasi, dan data uji.
6. Melakukan prapemrosesan fitur numerik dan kategorikal.
7. Melatih Logistic Regression dan Random Forest.
8. Membandingkan kinerja model.
9. Meninjau contoh prediksi dan merumuskan insight bisnis.

## Evaluasi Model

Kinerja model dievaluasi menggunakan metrik berikut:

- **Accuracy**: proporsi prediksi yang benar secara keseluruhan.
- **Precision**: proporsi prediksi churn yang benar-benar churn.
- **Recall**: proporsi pelanggan churn yang berhasil dikenali model.
- **F1-score**: keseimbangan antara precision dan recall.
- **ROC-AUC**: kemampuan model membedakan kelas berdasarkan skor prediksi.

Confusion matrix dan kurva ROC digunakan untuk membantu memahami pola kesalahan dan kemampuan pemisahan kelas. Nilai evaluasi yang sebenarnya akan dihasilkan ketika notebook dijalankan.

## Insight Bisnis

Hasil analisis dapat digunakan sebagai bahan pertimbangan untuk:
- mengenali kelompok pelanggan yang berisiko churn;
- merancang strategi retensi yang lebih terarah;
- menentukan pelanggan yang perlu ditinjau lebih lanjut oleh tim layanan.

Prediksi model bukan keputusan final untuk memperlakukan pelanggan. Hasilnya perlu dipertimbangkan bersama konteks bisnis dan pemeriksaan manusia.

## Teknologi yang Digunakan

- Python
- Google Colab / Jupyter Notebook
- pandas dan NumPy
- Matplotlib dan Seaborn
- scikit-learn

## Cara Menjalankan

1. Buka notebook `studi_kasus_customer_churn_webinar1.ipynb` di Google Colab.
2. Jalankan setiap sel secara berurutan dari atas ke bawah.
3. Pastikan koneksi internet tersedia saat notebook mengunduh dataset.
4. Tinjau visualisasi, metrik evaluasi, dan insight yang dihasilkan.

Sebagian besar proses menggunakan CPU; GPU tidak diperlukan untuk model yang digunakan dalam proyek ini.
