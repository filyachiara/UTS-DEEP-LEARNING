# Klasifikasi Penyebab Deforestasi Menggunakan Convolutional Neural Network (CNN)

## 1. Deskripsi Proyek

Proyek ini membahas penerapan *Machine Learning* menggunakan algoritma *Convolutional Neural Network* (CNN) untuk mempelajari proses klasifikasi citra yang berkaitan dengan penyebab deforestasi. Proyek ini disusun berdasarkan materi Studi Kasus Webinar 6 dengan menggunakan Python, TensorFlow/Keras, dan Google Colab.

Studi kasus ini mengangkat permasalahan deforestasi, yaitu hilangnya tutupan hutan akibat aktivitas manusia maupun faktor alam. Sistem pemantauan kehilangan tutupan pohon seperti RADD dan GLAD dapat membantu menunjukkan lokasi gangguan hutan, tetapi tidak selalu menjelaskan penyebab langsung kehilangan tersebut.

Dalam proyek ini, CNN digunakan untuk mempelajari tahapan dasar klasifikasi citra, mulai dari persiapan data, pembentukan model, pelatihan, hingga evaluasi hasil klasifikasi.

**Catatan:** notebook menggunakan dataset sintetis yang dibuat secara artifisial untuk keperluan pembelajaran. Data tersebut bukan citra Sentinel-1 atau Sentinel-2 asli dan tidak mewakili karakteristik ilmiah penyebab deforestasi yang telah tervalidasi. Oleh karena itu, hasil model tidak dapat digunakan sebagai bukti untuk menentukan penyebab deforestasi di dunia nyata.

## 2. Tujuan

- Memahami penerapan *Deep Learning* untuk permasalahan klasifikasi citra.
- Memahami konsep dasar *Convolutional Neural Network* (CNN).
- Mempelajari persiapan dataset dan pembentukan label klasifikasi.
- Membangun model CNN menggunakan TensorFlow/Keras.
- Melakukan pelatihan model berdasarkan dataset yang tersedia.
- Menghasilkan prediksi kelas beserta probabilitasnya.
- Mengevaluasi performa model menggunakan *Overall Accuracy* dan *Macro-F1*.
- Menampilkan visualisasi hasil prediksi dan *confusion matrix*.
- Memahami keterbatasan penggunaan data sintetis untuk merepresentasikan fenomena deforestasi yang sebenarnya.

## 3. Dataset

**Nama dataset:** Dataset Sintetis Klasifikasi Penyebab Deforestasi

**Sumber:** Data sintetis yang dibuat langsung melalui kode Python di dalam notebook.

**Format data:** Citra berbentuk *patch* berukuran 32 × 32 piksel dengan 3 kanal.

**Jumlah data:** 2.000 sampel sintetis.

**Jumlah kelas:** 8 kelas.

Dataset dibuat secara otomatis menggunakan NumPy sehingga pengguna tidak perlu mengunggah file dataset secara manual. Setiap kelas memiliki pola buatan yang berbeda untuk membantu demonstrasi proses klasifikasi menggunakan CNN.

Kelas yang digunakan dalam eksperimen adalah:

- `Pertanian skala besar`
- `Pertanian skala kecil`
- `Pertambangan`
- `Pembangunan jalan`
- `Penebangan selektif`
- `Kebakaran hutan`
- `Banjir`
- `Faktor alam lainnya`

Setiap kelas terdiri atas 250 sampel sintetis. Pola citra dibuat menggunakan kombinasi bentuk geometris, garis, area dengan nilai kanal berbeda, dan variasi acak.

Dataset ini hanya digunakan untuk demonstrasi teknis. Label dan pola citra dibuat berdasarkan aturan dalam kode, bukan berdasarkan hasil interpretasi citra satelit atau data observasi lapangan. Dengan demikian, model hanya mempelajari pola sintetis tersebut dan belum membuktikan kemampuan mengidentifikasi penyebab deforestasi yang sebenarnya.

## 4. Metode dan Tahapan Analisis

1. **Impor pustaka**

   Mengimpor pustaka NumPy, Matplotlib, TensorFlow/Keras, dan Scikit-learn yang digunakan untuk pengolahan data, pembangunan model, visualisasi, serta evaluasi.

2. **Penentuan parameter eksperimen**

   Menentukan nilai *random seed*, ukuran citra, jumlah kanal, jumlah sampel setiap kelas, dan nama kelas untuk menjaga konsistensi eksperimen.

3. **Pembuatan dataset sintetis**

   Membuat 2.000 citra sintetis berukuran 32 × 32 piksel dengan 3 kanal. Setiap kelas memiliki pola buatan yang berbeda.

4. **Pemberian label**

   Memberikan label numerik pada setiap citra berdasarkan kelas yang telah ditentukan.

5. **Visualisasi dataset**

   Menampilkan contoh citra dari setiap kelas untuk memahami perbedaan pola yang dibuat dalam dataset sintetis.

6. **Pembagian data**

   Membagi data menjadi data pelatihan dan data pengujian menggunakan `train_test_split`. Pembagian data digunakan untuk memisahkan sampel yang digunakan dalam pelatihan dan evaluasi.

7. **Pembangunan model CNN**

   Menggunakan TensorFlow/Keras untuk membangun arsitektur CNN yang mempelajari pola spasial pada citra sintetis.

8. **Pelatihan model**

   Melatih model menggunakan data pelatihan agar model mempelajari hubungan antara pola citra sintetis dan label kelas.

9. **Prediksi kelas**

   Menggunakan model yang telah dilatih untuk menghasilkan prediksi kelas dan probabilitas pada data pengujian atau sampel yang dipilih.

10. **Evaluasi model**

    Mengevaluasi hasil klasifikasi menggunakan *Overall Accuracy*, *Macro-F1*, dan metrik tambahan yang tersedia pada notebook.

11. **Visualisasi hasil evaluasi**

    Menampilkan *confusion matrix* dan contoh hasil prediksi untuk melihat kelas yang berhasil diprediksi serta kelas yang masih tertukar.

12. **Analisis hasil**

    Membahas hasil eksperimen berdasarkan dataset sintetis, konfigurasi model, dan metrik evaluasi yang diperoleh.

## 5. Teknologi yang Digunakan

- **Python** — bahasa pemrograman untuk pengolahan data dan implementasi model.
- **Google Colab** — lingkungan berbasis cloud untuk menjalankan notebook tanpa instalasi Python lokal.
- **NumPy** — membuat dan mengolah data numerik serta citra sintetis.
- **Matplotlib** — menampilkan visualisasi citra dan hasil evaluasi.
- **TensorFlow/Keras** — membangun dan melatih model CNN.
- **Scikit-learn** — membantu pembagian dataset dan evaluasi hasil klasifikasi.

## 6. Implementasi Deep Learning

Implementasi *Deep Learning* pada proyek ini menggunakan *Convolutional Neural Network* (CNN). CNN dipilih karena mampu mempelajari pola spasial dalam data berbentuk citra melalui operasi konvolusi dan lapisan jaringan lainnya.

Pada eksperimen ini, citra sintetis berukuran 32 × 32 piksel dengan 3 kanal digunakan sebagai masukan model. Label kelas menjadi target yang dipelajari selama pelatihan.

Evaluasi dilakukan menggunakan metrik klasifikasi untuk mengetahui seberapa baik model memprediksi label pada data pengujian. *Overall Accuracy* menggambarkan proporsi prediksi yang benar, sedangkan *Macro-F1* menghitung rata-rata F1-score setiap kelas dengan bobot yang sama.

Nilai evaluasi yang tinggi pada dataset sintetis tidak otomatis menunjukkan bahwa model dapat mengenali penyebab deforestasi pada citra satelit asli. Model dapat saja mempelajari pola buatan yang sengaja ditanamkan ke dalam dataset.

Untuk pengembangan lebih lanjut, dataset sintetis dapat diganti dengan citra satelit asli yang memiliki label penyebab kehilangan hutan yang tepercaya. Proses tersebut membutuhkan sumber data publik yang sesuai, keselarasan spasial dan temporal antara citra dan label, serta pemeriksaan kualitas data sebelum model dilatih.

## 7. Cara Menjalankan Proyek

1. Buka Google Colab melalui [https://colab.research.google.com/](https://colab.research.google.com/).
2. Buka notebook proyek klasifikasi penyebab deforestasi.
3. Pastikan koneksi internet tersedia untuk mengakses Google Colab dan memasang pustaka jika diperlukan.
4. Jalankan sel notebook secara berurutan atau pilih **Runtime → Run all**.
5. Periksa hasil impor pustaka dan informasi ketersediaan GPU.
6. Jalankan pembuatan dataset sintetis secara otomatis.
7. Perhatikan contoh citra sintetis yang ditampilkan untuk setiap kelas.
8. Lanjutkan proses pembagian data, pelatihan CNN, prediksi, dan evaluasi sesuai urutan notebook.
9. Periksa metrik evaluasi, *confusion matrix*, dan contoh hasil prediksi yang dihasilkan.
10. Simpan notebook jika ingin mendokumentasikan hasil eksperimen atau melakukan perubahan.
