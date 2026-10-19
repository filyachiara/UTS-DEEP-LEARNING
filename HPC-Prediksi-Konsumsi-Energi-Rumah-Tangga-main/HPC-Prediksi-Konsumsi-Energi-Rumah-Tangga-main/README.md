# Prediksi Konsumsi Energi Rumah Tangga Menggunakan Machine Learning dan High Performance Computing (HPC)

## 1. Deskripsi Proyek

Proyek ini membahas prediksi konsumsi energi peralatan rumah tangga menggunakan Python dan Google Colab. Proyek ini terinspirasi dari materi webinar 2, yaitu *Bridging Global Infrastructure to Address Local Challenge with HPC*, khususnya pemanfaatan komputasi dan teknologi untuk membantu menyelesaikan permasalahan nyata.

Studi kasus yang diangkat adalah penggunaan data energi rumah tangga untuk membangun model prediksi menggunakan algoritma *Random Forest Regressor*. Selain melakukan analisis data dan pemodelan, proyek ini juga membandingkan waktu pelatihan model menggunakan konfigurasi komputasi serial dan paralel.

Perbandingan tersebut dilakukan untuk memahami bagaimana pemanfaatan komputasi paralel dapat membantu meningkatkan efisiensi proses pelatihan model. Implementasi dilakukan di Google Colab sebagai demonstrasi konsep komputasi paralel yang berkaitan dengan High Performance Computing (HPC).

## 2. Tujuan

- Menganalisis pola konsumsi energi peralatan rumah tangga berdasarkan data pengukuran.
- Mengeksplorasi hubungan antara konsumsi energi, waktu, suhu, kelembapan, dan variabel lingkungan lainnya.
- Membangun model prediksi konsumsi energi menggunakan *Random Forest Regressor*.
- Membandingkan waktu pelatihan model dengan konfigurasi komputasi serial dan paralel.
- Mengevaluasi performa model menggunakan MAE, RMSE, dan R².
- Memahami penerapan konsep komputasi paralel dalam proses pemodelan *machine learning*.
- Mengidentifikasi potensi pemanfaatan komputasi yang lebih efisien untuk mendukung analisis energi.

## 3. Dataset

**Nama dataset:** Appliances Energy Prediction

**Sumber:** UCI Machine Learning Repository

Tautan dataset:  
https://archive.ics.uci.edu/dataset/374/appliances+energy+prediction

**Atribusi dataset:** Candanedo, L. (2017). *Appliances Energy Prediction* [Dataset]. UCI Machine Learning Repository.

DOI: https://doi.org/10.24432/C5VC8G

Dataset ini berisi pengukuran konsumsi energi peralatan rumah tangga, penggunaan lampu, suhu, kelembapan, dan beberapa variabel lingkungan lainnya. Data dikumpulkan selama sekitar 4,5 bulan dengan interval pencatatan 10 menit.

Dataset diambil langsung dari UCI Machine Learning Repository menggunakan pustaka `ucimlrepo`. Data kemudian diperiksa dan diolah sebelum digunakan untuk analisis dan pemodelan.

Pada proyek ini, kolom `Appliances` digunakan sebagai target prediksi, sedangkan variabel sensor dan variabel waktu yang dipilih digunakan sebagai masukan model.

Dataset ini bukan data konsumsi energi gedung di Bengkulu, sehingga hasil analisis menggambarkan data pengukuran pada sumber tersebut dan tidak dapat langsung dianggap mewakili kondisi bangunan di Indonesia.

## 4. Metode dan Tahapan Analisis

1. **Pengambilan data**  
   Mengambil dataset Appliances Energy Prediction dari UCI Machine Learning Repository menggunakan Python.

2. **Pemeriksaan dan pembersihan data**  
   Memeriksa struktur dataset, tipe data, nilai kosong, dan format tanggal untuk memastikan data dapat digunakan dalam analisis.

3. **Pengolahan variabel waktu**  
   Mengubah kolom tanggal menjadi format waktu serta membuat variabel seperti jam, hari dalam minggu, dan bulan.

4. **Analisis eksploratif**  
   Menggunakan statistik deskriptif dan visualisasi untuk mempelajari pola konsumsi energi berdasarkan waktu dan variabel lingkungan.

5. **Persiapan data**  
   Menentukan variabel masukan dan target prediksi. Kolom `Appliances` digunakan sebagai target yang ingin diprediksi.

6. **Pembagian data**  
   Membagi data berdasarkan urutan waktu menjadi 80% data pelatihan dan 20% data pengujian. Pembagian ini dilakukan agar data pengujian berasal dari periode waktu yang lebih akhir.

7. **Pembuatan model Machine Learning**  
   Menggunakan algoritma *Random Forest Regressor* untuk mempelajari pola hubungan antara variabel masukan dan konsumsi energi.

8. **Implementasi komputasi serial dan paralel**  
   Membandingkan proses pelatihan model menggunakan `n_jobs=1` sebagai konfigurasi serial dan `n_jobs=-1` untuk memanfaatkan seluruh core CPU yang tersedia pada lingkungan eksekusi.

9. **Evaluasi model**  
   Mengukur performa prediksi menggunakan MAE, RMSE, dan R² serta mencatat waktu pelatihan masing-masing konfigurasi.

10. **Visualisasi hasil**  
    Menampilkan perbandingan waktu pelatihan, metrik evaluasi, serta nilai aktual dan prediksi untuk membantu memahami hasil eksperimen.

11. **Analisis dan kesimpulan**  
    Menafsirkan hasil eksperimen untuk mengetahui performa model dan perbedaan waktu pelatihan pada konfigurasi komputasi yang diuji.

## 5. Teknologi yang Digunakan

- **Python** — bahasa pemrograman untuk pengolahan data dan pemodelan.
- **Google Colab** — lingkungan berbasis cloud untuk menjalankan notebook.
- **Pandas** — pengolahan dan pemeriksaan data.
- **NumPy** — operasi numerik.
- **Matplotlib** — pembuatan grafik dan visualisasi hasil.
- **Scikit-learn** — pembuatan model Random Forest dan evaluasi performa.
- **ucimlrepo** — mengambil dataset dari UCI Machine Learning Repository.

## 6. Implementasi Konsep HPC

Konsep HPC pada proyek ini diperkenalkan melalui pengujian komputasi paralel dalam pelatihan model *Random Forest Regressor*.

Eksperimen membandingkan dua konfigurasi:

- **Komputasi serial (`n_jobs=1`)**: proses pelatihan Random Forest menggunakan satu pekerjaan pada satu waktu.
- **Komputasi paralel (`n_jobs=-1`)**: Random Forest memanfaatkan seluruh core CPU yang tersedia dan didukung oleh proses pelatihan model.

Waktu pelatihan dari kedua konfigurasi dicatat dan dibandingkan untuk mengamati pengaruh paralelisasi terhadap efisiensi komputasi. Metrik prediksi juga diperiksa untuk memastikan bahwa perbandingan tidak hanya berfokus pada kecepatan.

Pengujian ini merupakan demonstrasi konsep komputasi paralel yang relevan dengan HPC, bukan implementasi pada klaster HPC sungguhan. Hasil waktu pelatihan dapat berbeda bergantung pada spesifikasi CPU, jumlah core, beban sistem, dan kondisi lingkungan Google Colab.

## 7. Cara Menjalankan Proyek

1. Buka Google Colab melalui https://colab.research.google.com/.
2. Unggah notebook `Studi_Kasus_Webinar_2_HPC_Energi.ipynb`.
3. Pastikan koneksi internet tersedia karena dataset diambil dari UCI Machine Learning Repository.
4. Jalankan seluruh sel notebook secara berurutan atau pilih menu **Runtime → Run all**.
5. Tunggu sampai proses pengambilan data, pengolahan data, pelatihan model, dan evaluasi selesai.
6. Periksa tabel hasil, grafik, metrik evaluasi, dan perbandingan waktu pelatihan.
7. Simpan perubahan notebook jika terdapat modifikasi atau hasil eksperimen yang ingin didokumentasikan.

## 8. Kesimpulan

Proyek ini menerapkan analisis data dan *machine learning* untuk memprediksi konsumsi energi peralatan rumah tangga menggunakan algoritma *Random Forest Regressor*. Evaluasi menggunakan MAE, RMSE, dan R² digunakan untuk menilai performa prediksi, sedangkan perbandingan waktu pelatihan digunakan untuk mengamati perbedaan antara konfigurasi komputasi serial dan paralel.

Melalui studi kasus ini, konsep komputasi paralel yang berkaitan dengan High Performance Computing (HPC) dapat dipelajari melalui eksperimen yang sederhana dan dapat dijalankan menggunakan Google Colab.

Proyek ini diharapkan dapat menjadi contoh penerapan komputasi untuk membantu menganalisis permasalahan energi. Pengembangan selanjutnya dapat dilakukan dengan menggunakan data gedung kampus atau bangunan di wilayah lokal, menguji algoritma lain, serta melakukan eksperimen pada infrastruktur komputasi dengan sumber daya yang lebih besar.
