
# Prediksi Dropout dan Keberhasilan Akademik Mahasiswa Menggunakan Machine Learning

## 1. Deskripsi Proyek

Proyek ini membahas penerapan *Machine Learning* untuk memprediksi status akademik mahasiswa menggunakan Python dan Google Colab. Proyek ini disusun berdasarkan materi webinar 4, yaitu *Introduction to Machine Learning*, khususnya penerapan algoritma pembelajaran mesin untuk menyelesaikan permasalahan klasifikasi berdasarkan data.

Studi kasus yang diangkat adalah klasifikasi status mahasiswa berdasarkan data akademik, demografi, dan sosial-ekonomi. Model yang dibangun bertujuan untuk mengklasifikasikan mahasiswa ke dalam tiga kategori, yaitu *Dropout*, *Enrolled*, dan *Graduate*, menggunakan algoritma *Logistic Regression* dan *Random Forest Classifier*.

Kedua algoritma tersebut diterapkan dan dibandingkan untuk mengetahui perbedaan performanya dalam mengklasifikasikan status mahasiswa. Evaluasi dilakukan menggunakan beberapa metrik, seperti *accuracy*, *precision*, *recall*, dan *F1-score*, serta visualisasi *confusion matrix* untuk memahami hasil prediksi model.

Implementasi dilakukan menggunakan Google Colab agar seluruh proses pengolahan data, pelatihan model, evaluasi, dan visualisasi dapat dijalankan dalam lingkungan berbasis cloud tanpa memerlukan instalasi Python secara lokal.

## 2. Tujuan

- Memahami penerapan konsep *Machine Learning* dalam permasalahan klasifikasi.
- Menganalisis karakteristik dataset mahasiswa yang tersedia secara publik.
- Mengeksplorasi distribusi status mahasiswa berdasarkan kategori *Dropout*, *Enrolled*, dan *Graduate*.
- Melakukan preprocessing data sebelum digunakan dalam proses pelatihan model.
- Membangun model klasifikasi menggunakan algoritma *Logistic Regression* dan *Random Forest Classifier*.
- Membandingkan performa kedua model berdasarkan *accuracy*, *precision*, *recall*, dan *F1-score*.
- Mengevaluasi hasil klasifikasi menggunakan *classification report* dan *confusion matrix*.
- Mengidentifikasi fitur yang berkontribusi terhadap prediksi model Random Forest.
- Memahami tahapan implementasi *Machine Learning* menggunakan Python dan Google Colab.

## 3. Dataset

**Nama dataset:** Predict Students' Dropout and Academic Success

**Sumber:** UCI Machine Learning Repository

Tautan dataset:  
https://archive.ics.uci.edu/dataset/697/predict+students+dropout+and+academic+success

**Atribusi dataset:** Realinho, V., Vieira Martins, M., Machado, J., & Baptista, L. (2021). *Predict Students' Dropout and Academic Success* [Dataset]. UCI Machine Learning Repository.

DOI: https://doi.org/10.24432/C5MC89

Dataset ini berisi 4.424 data mahasiswa dengan 36 fitur masukan dan satu kolom target. Informasi yang tersedia mencakup karakteristik demografi, kondisi sosial-ekonomi, serta data yang berkaitan dengan aktivitas dan performa akademik mahasiswa.

Pada proyek ini, kolom `Target` digunakan sebagai variabel target yang ingin diprediksi, sedangkan kolom lainnya digunakan sebagai fitur masukan model.

Variabel target memiliki tiga kategori, yaitu:

- `Dropout`: mahasiswa yang berhenti dari program studi.
- `Enrolled`: mahasiswa yang masih terdaftar atau menjalani pendidikan.
- `Graduate`: mahasiswa yang telah menyelesaikan pendidikan.

Dataset diambil dari UCI Machine Learning Repository menggunakan Python dan pustaka Pandas. Data kemudian diperiksa untuk memahami struktur, tipe data, distribusi kelas, dan kemungkinan nilai kosong sebelum digunakan dalam pemodelan.

Dataset ini berasal dari institusi pendidikan tinggi di Portugal. Oleh karena itu, hasil analisis dan prediksi tidak dapat langsung dianggap mewakili kondisi mahasiswa di Indonesia. Proyek ini ditujukan untuk pembelajaran dan eksperimen Machine Learning, bukan untuk menentukan keputusan akademik nyata terhadap individu.

## 4. Metode dan Tahapan Analisis

1. **Pengambilan data**  
   Mengambil dataset Predict Students' Dropout and Academic Success dari UCI Machine Learning Repository menggunakan Python dan Pandas.

2. **Pemeriksaan dan pemahaman data**  
   Memeriksa ukuran dataset, nama kolom, tipe data, jumlah nilai kosong, data duplikat, dan beberapa sampel data untuk memahami struktur dataset.

3. **Analisis eksploratif**  
   Menggunakan statistik deskriptif dan visualisasi untuk mempelajari distribusi status mahasiswa pada kategori *Dropout*, *Enrolled*, dan *Graduate*.

4. **Penentuan fitur dan target**  
   Memisahkan kolom `Target` sebagai variabel yang akan diprediksi, sedangkan kolom lainnya digunakan sebagai fitur masukan.

5. **Pembagian data**  
   Membagi dataset menjadi 80% data pelatihan dan 20% data pengujian menggunakan `train_test_split`. Parameter `stratify=y` digunakan untuk mempertahankan proporsi kelas pada kedua bagian data.

6. **Preprocessing data**  
   Menggunakan `SimpleImputer` untuk menangani kemungkinan nilai kosong. Pada model Logistic Regression, `StandardScaler` digunakan untuk melakukan standardisasi fitur. Proses preprocessing ditempatkan dalam pipeline agar transformasi dipelajari dari data pelatihan.

7. **Pembuatan model Machine Learning**  
   Membangun dua model klasifikasi, yaitu *Logistic Regression* sebagai model klasifikasi dasar dan *Random Forest Classifier* untuk mempelajari pola hubungan yang lebih kompleks pada data.

8. **Pelatihan model**  
   Melatih kedua algoritma menggunakan data pelatihan yang telah disiapkan. Parameter model ditentukan melalui konfigurasi pada kode notebook.

9. **Evaluasi model**  
   Mengukur performa klasifikasi menggunakan *accuracy*, *macro precision*, *macro recall*, dan *macro F1-score*. Evaluasi tambahan dilakukan menggunakan *classification report* untuk melihat performa pada setiap kelas.

10. **Visualisasi hasil**  
    Menampilkan distribusi kelas, *confusion matrix*, dan grafik perbandingan performa kedua model untuk membantu memahami hasil klasifikasi.

11. **Analisis fitur penting**  
    Menggunakan *feature importance* dari Random Forest untuk mengidentifikasi fitur yang memiliki kontribusi relatif besar terhadap prediksi model. Hasil ini tidak menunjukkan hubungan sebab-akibat.

12. **Pengujian prediksi**  
    Menggunakan satu sampel dari data pengujian untuk memperlihatkan cara model menghasilkan prediksi status mahasiswa.

13. **Penyimpanan hasil**  
    Menyimpan model yang telah dilatih, tabel evaluasi, dan hasil analisis fitur ke dalam folder `hasil_proyek` agar dapat digunakan kembali atau didokumentasikan.

14. **Analisis dan kesimpulan**  
    Membandingkan hasil evaluasi kedua algoritma untuk mengetahui model dengan performa terbaik berdasarkan nilai *macro F1-score* pada pembagian data pengujian yang digunakan.

## 5. Teknologi yang Digunakan

- **Python** — bahasa pemrograman untuk pengolahan data dan implementasi Machine Learning.
- **Google Colab** — lingkungan berbasis cloud untuk menjalankan notebook Python.
- **Pandas** — membaca, mengolah, dan memeriksa dataset.
- **NumPy** — mendukung operasi numerik.
- **Matplotlib** — membuat grafik dan visualisasi hasil eksperimen.
- **Seaborn** — membantu membuat visualisasi statistik, termasuk distribusi kelas dan confusion matrix.
- **Scikit-learn** — menyediakan preprocessing, pembagian data, algoritma klasifikasi, pipeline, dan metrik evaluasi.
- **Joblib** — menyimpan model Machine Learning yang telah dilatih.

## 6. Implementasi Machine Learning

Implementasi Machine Learning pada proyek ini dilakukan dengan membandingkan dua algoritma klasifikasi, yaitu *Logistic Regression* dan *Random Forest Classifier*.

Kedua algoritma menggunakan data pelatihan dan data pengujian yang sama agar hasil evaluasi dapat dibandingkan secara lebih adil.

- **Logistic Regression**  
  Digunakan sebagai model klasifikasi dasar untuk mempelajari hubungan antara fitur masukan dan kategori status mahasiswa. Standardisasi fitur diterapkan melalui `StandardScaler` sebelum proses klasifikasi.

- **Random Forest Classifier**  
  Menggunakan kumpulan pohon keputusan untuk menghasilkan prediksi kelas. Algoritma ini juga digunakan untuk melihat nilai *feature importance* dari fitur yang tersedia.

Performa kedua model dibandingkan menggunakan *accuracy*, *macro precision*, *macro recall*, dan *macro F1-score*. Penggunaan metrik macro membantu memberikan bobot yang sama kepada setiap kelas, sehingga performa pada kelas yang jumlah datanya lebih sedikit tetap diperhatikan.

Selain membandingkan skor evaluasi, proyek ini menggunakan *confusion matrix* untuk melihat kelas yang berhasil diprediksi dengan benar dan kelas yang masih sering tertukar.

Model dengan nilai *macro F1-score* tertinggi ditampilkan sebagai model terbaik pada eksperimen tersebut. Kesimpulan ini hanya berlaku untuk konfigurasi dan pembagian data yang digunakan, sehingga belum menjamin performa yang sama pada dataset lain.

## 7. Cara Menjalankan Proyek

1. Buka Google Colab melalui https://colab.research.google.com/.
2. Unduh notebook `Studi_Kasus_Prediksi_Dropout_Mahasiswa.ipynb` dari repositori GitHub atau file proyek yang disediakan.
3. Unggah notebook melalui menu **File → Upload notebook**.
4. Pastikan koneksi internet tersedia karena dataset diambil dari UCI Machine Learning Repository.
5. Jalankan sel notebook secara berurutan atau pilih menu **Runtime → Run all**.
6. Pastikan dataset berhasil dimuat dan kolom `Target` terbaca dengan benar sebelum melanjutkan analisis.
7. Tunggu sampai proses preprocessing, pelatihan model, evaluasi, dan visualisasi selesai.
8. Periksa tabel perbandingan performa model, *classification report*, *confusion matrix*, dan hasil analisis fitur penting.
9. Periksa folder `hasil_proyek` untuk melihat file model dan hasil evaluasi yang telah disimpan.
10. Simpan perubahan notebook jika terdapat modifikasi atau hasil eksperimen yang ingin didokumentasikan.

## 8. Kesimpulan

Proyek ini menerapkan konsep *Machine Learning* untuk mengklasifikasikan status akademik mahasiswa menggunakan dataset publik dari UCI Machine Learning Repository. Algoritma *Logistic Regression* dan *Random Forest Classifier* digunakan untuk mempelajari pola pada data dan menghasilkan prediksi ke dalam tiga kategori, yaitu *Dropout*, *Enrolled*, dan *Graduate*.

Evaluasi menggunakan *accuracy*, *precision*, *recall*, *F1-score*, dan *confusion matrix* membantu mengetahui kemampuan masing-masing model dalam melakukan klasifikasi. Perbandingan tersebut juga memberikan gambaran mengenai kelebihan dan keterbatasan algoritma yang digunakan pada dataset yang sama.

Melalui studi kasus ini, tahapan dasar Machine Learning dapat dipelajari mulai dari pengambilan data, eksplorasi, preprocessing, pembagian data, pelatihan model, hingga evaluasi dan penyimpanan hasil.

Pengembangan selanjutnya dapat dilakukan dengan menguji algoritma lain, melakukan penyesuaian parameter model, mengevaluasi pengaruh ketidakseimbangan kelas, dan menguji model pada dataset dari institusi pendidikan yang berbeda. Penggunaan model untuk mendukung keputusan akademik nyata memerlukan validasi lebih lanjut, evaluasi keadilan, serta pertimbangan etis dan privasi.
