# Studi Kasus Enam Sesi Webinar

Repositori ini berisi dokumentasi dan implementasi enam proyek studi kasus yang dikembangkan berdasarkan materi webinar. Setiap proyek menerapkan konsep komputasi, analisis data, *Machine Learning*, *Deep Learning*, *Geographic Information System* (GIS), serta *Human-Computer Interaction* (HCI) untuk mempelajari penerapan teknologi dalam menyelesaikan permasalahan tertentu.

Seluruh proyek dikembangkan menggunakan Python dan Google Colab, dengan pustaka serta teknologi pendukung yang disesuaikan dengan kebutuhan setiap studi kasus.

## Daftar Isi

1. [Sesi 1 — Prediksi Customer Churn](#1-sesi-1--prediksi-customer-churn-menggunakan-machine-learning)
2. [Sesi 2 — Prediksi Konsumsi Energi dan HPC](#2-sesi-2--prediksi-konsumsi-energi-rumah-tangga-dan-high-performance-computing-hpc)
3. [Sesi 3 — Pemetaan Fasilitas Kesehatan Menggunakan GIS](#3-sesi-3--pemetaan-dan-analisis-persebaran-fasilitas-kesehatan-menggunakan-gis)
4. [Sesi 4 — Prediksi Dropout dan Keberhasilan Akademik](#4-sesi-4--prediksi-dropout-dan-keberhasilan-akademik-mahasiswa)
5. [Sesi 5 — Dashboard Interaktif Layanan Perpustakaan](#5-sesi-5--dashboard-interaktif-layanan-perpustakaan-kampus)
6. [Sesi 6 — Klasifikasi Penyebab Deforestasi Menggunakan CNN](#6-sesi-6--klasifikasi-penyebab-deforestasi-menggunakan-cnn)
7. [Teknologi yang Digunakan](#teknologi-yang-digunakan)
8. [Cara Menjalankan Proyek](#cara-menjalankan-proyek)

---

## 1. Sesi 1 — Prediksi Customer Churn Menggunakan Machine Learning

### Deskripsi

Proyek ini menerapkan konsep *predictive analytics* dan *Machine Learning* untuk memprediksi kemungkinan pelanggan berhenti berlangganan atau melakukan *customer churn*. Prediksi dilakukan berdasarkan karakteristik pelanggan pada layanan telekomunikasi.

Tujuan utamanya adalah memahami pola pelanggan, membangun model klasifikasi, dan mengidentifikasi informasi yang dapat membantu perusahaan merencanakan strategi retensi pelanggan.

### Tujuan

- Memahami karakteristik pelanggan melalui eksplorasi data.
- Melakukan pemeriksaan dan prapemrosesan data.
- Membangun serta membandingkan model klasifikasi.
- Mengevaluasi model menggunakan beberapa metrik.
- Mengidentifikasi insight yang berpotensi mendukung pengambilan keputusan bisnis.

### Dataset

**IBM Telco Customer Churn**

Sumber: IBM Telco Customer Churn Dataset, tersedia melalui sumber publik.

Variabel target adalah `Churn`, yang menunjukkan apakah pelanggan berhenti berlangganan (`Yes`) atau tetap menggunakan layanan (`No`).

### Metode dan Tahapan

1. Memuat dan memeriksa dataset.
2. Melakukan eksplorasi data dan visualisasi.
3. Memeriksa nilai kosong, duplikasi, dan distribusi kelas.
4. Memisahkan fitur dan variabel target.
5. Membagi data menjadi data pelatihan, validasi, dan pengujian sesuai implementasi notebook.
6. Melakukan prapemrosesan fitur numerik dan kategorikal menggunakan pipeline.
7. Melatih model Logistic Regression dan Random Forest.
8. Membandingkan performa model menggunakan metrik evaluasi.
9. Meninjau hasil prediksi dan merumuskan insight bisnis.

### Algoritma dan Evaluasi

- **Logistic Regression:** model klasifikasi sebagai baseline.
- **Random Forest:** model berbasis kumpulan pohon keputusan yang mampu mempelajari pola hubungan nonlinier.

Metrik evaluasi meliputi Accuracy, Precision, Recall, F1-score, dan ROC-AUC. Confusion matrix dan kurva ROC digunakan untuk membantu memahami hasil klasifikasi.

### Teknologi

Python, Google Colab, Pandas, NumPy, Matplotlib, Seaborn, dan Scikit-learn.

### Notebook

`studi_kasus_customer_churn_webinar1.ipynb`

---

## 2. Sesi 2 — Prediksi Konsumsi Energi Rumah Tangga dan High Performance Computing (HPC)

### Deskripsi

Proyek ini menerapkan Machine Learning untuk memprediksi konsumsi energi peralatan rumah tangga. Selain membangun model prediksi, proyek ini memperkenalkan konsep komputasi paralel melalui perbandingan waktu pelatihan model dalam konfigurasi serial dan paralel.

Eksperimen menggunakan Random Forest Regressor dan dijalankan di Google Colab untuk mempelajari hubungan antara pemodelan data, efisiensi komputasi, dan penerapan konsep HPC.

### Tujuan

- Menganalisis pola konsumsi energi dan variabel lingkungan.
- Membangun model prediksi konsumsi energi.
- Membandingkan waktu pelatihan dalam konfigurasi serial dan paralel.
- Mengevaluasi kualitas prediksi menggunakan metrik regresi.
- Memahami penerapan dasar komputasi paralel dalam Machine Learning.

### Dataset

**Appliances Energy Prediction**

Sumber: [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/374/appliances+energy+prediction)

DOI: [10.24432/C5VC8G](https://doi.org/10.24432/C5VC8G)

Dataset berisi pengukuran konsumsi energi peralatan rumah tangga, penggunaan lampu, suhu, kelembapan, dan variabel lingkungan lainnya. Data dikumpulkan selama sekitar 4,5 bulan dengan interval pencatatan 10 menit.

Variabel target yang digunakan adalah `Appliances`.

### Metode dan Tahapan

1. Mengambil dataset dari UCI Machine Learning Repository.
2. Memeriksa struktur, tipe data, dan nilai kosong.
3. Mengolah variabel waktu, seperti jam, hari dalam minggu, dan bulan.
4. Melakukan eksplorasi data dan visualisasi.
5. Menentukan fitur masukan dan target prediksi.
6. Membagi data berdasarkan urutan waktu menjadi 80% data pelatihan dan 20% data pengujian.
7. Melatih model Random Forest Regressor.
8. Membandingkan konfigurasi serial (`n_jobs=1`) dan paralel (`n_jobs=-1`).
9. Mengukur performa prediksi dan waktu pelatihan.
10. Menganalisis hasil eksperimen.

### Evaluasi dan Implementasi HPC

Performa prediksi dievaluasi menggunakan:

- **MAE:** rata-rata kesalahan absolut.
- **RMSE:** akar rata-rata kuadrat kesalahan.
- **R²:** ukuran kemampuan model menjelaskan variasi target.

Waktu pelatihan kedua konfigurasi juga dicatat untuk mengetahui perbedaan efisiensi komputasi.

Perlu diperhatikan bahwa eksperimen ini merupakan demonstrasi paralelisasi pada CPU, bukan implementasi pada klaster HPC sungguhan. Waktu pelatihan dapat berbeda bergantung pada jumlah core, spesifikasi perangkat, dan kondisi lingkungan eksekusi.

### Teknologi

Python, Google Colab, Pandas, NumPy, Matplotlib, Scikit-learn, dan ucimlrepo.

### Notebook

`Studi_Kasus_Webinar_2_HPC_Energi.ipynb`

---

## 3. Sesi 3 — Pemetaan dan Analisis Persebaran Fasilitas Kesehatan Menggunakan GIS

### Deskripsi

Proyek ini menerapkan *Geographic Information System* (GIS) untuk memetakan dan mengeksplorasi persebaran fasilitas kesehatan di sekitar Kota Bengkulu.

Data lokasi diperoleh dari OpenStreetMap melalui Overpass API, kemudian diolah menggunakan Python untuk menghasilkan tabel, grafik, peta interaktif, dan heatmap.

Proyek ini bertujuan menunjukkan bagaimana data geografis dapat digunakan untuk menyajikan informasi lokasi secara visual dan membantu pengguna mengamati pola persebaran objek.

### Tujuan

- Memahami penerapan GIS dalam pemetaan fasilitas kesehatan.
- Mengambil dan membersihkan data geografis.
- Mengelompokkan fasilitas berdasarkan jenis atau tag.
- Menampilkan lokasi dalam peta interaktif.
- Membuat heatmap untuk mengeksplorasi konsentrasi titik.
- Memahami keterbatasan data spasial yang bersumber dari OpenStreetMap.

### Dataset

**Data Fasilitas Kesehatan OpenStreetMap**

Sumber:

- [OpenStreetMap](https://www.openstreetmap.org/)
- [Overpass API](https://overpass-api.de/)

Data diambil berdasarkan tag yang berkaitan dengan fasilitas kesehatan, seperti `hospital`, `clinic`, `doctors`, `dentist`, `pharmacy`, dan `healthcare`.

Atribut yang dapat diperoleh meliputi nama fasilitas, jenis fasilitas, koordinat latitude dan longitude, operator, serta ID objek OpenStreetMap jika tersedia.

Wilayah pencarian menggunakan bounding box atau kotak koordinat perkiraan di sekitar Kota Bengkulu, sehingga tidak otomatis merepresentasikan batas administrasi resmi kota.

### Metode dan Tahapan

1. Mengambil data fasilitas kesehatan melalui Overpass API.
2. Memeriksa struktur dan atribut data.
3. Membersihkan data serta memeriksa koordinat dan duplikasi ID.
4. Mengelompokkan fasilitas berdasarkan kategori.
5. Menghitung jumlah objek setiap kategori.
6. Membuat grafik batang untuk merangkum komposisi fasilitas.
7. Membuat peta interaktif menggunakan Folium.
8. Menambahkan MarkerCluster untuk mengelompokkan titik yang berdekatan.
9. Membuat heatmap berdasarkan koordinat fasilitas.
10. Menyimpan hasil pengolahan dalam CSV dan peta HTML jika fitur penyimpanan tersedia.
11. Menginterpretasikan hasil dengan mempertimbangkan keterbatasan data.

### Hasil yang Diharapkan

- Tabel data fasilitas kesehatan.
- Ringkasan jumlah fasilitas berdasarkan kategori.
- Grafik distribusi fasilitas kesehatan.
- Peta interaktif dengan penanda lokasi.
- Heatmap konsentrasi titik.
- File CSV dan HTML sesuai keluaran notebook.

Heatmap hanya menggambarkan konsentrasi lokasi yang tercatat dalam data, bukan ukuran langsung kecukupan atau aksesibilitas layanan kesehatan.

### Teknologi

Python, Google Colab, Pandas, Requests, Folium, MarkerCluster, HeatMap, Matplotlib, dan Esri WorldStreetMap sebagai basemap.

### Notebook

`Studi_Kasus_Webinar_3_GIS_Fasilitas_Kesehatan_Bengkulu.ipynb`

---

## 4. Sesi 4 — Prediksi Dropout dan Keberhasilan Akademik Mahasiswa

### Deskripsi

Proyek ini menerapkan Machine Learning untuk mengklasifikasikan status akademik mahasiswa berdasarkan data demografi, sosial-ekonomi, dan akademik.

Model memprediksi status mahasiswa ke dalam tiga kategori, yaitu `Dropout`, `Enrolled`, dan `Graduate`. Dua algoritma klasifikasi digunakan untuk membandingkan performa model pada dataset yang sama.

### Tujuan

- Memahami penerapan Machine Learning dalam klasifikasi.
- Mengeksplorasi karakteristik dan distribusi status mahasiswa.
- Melakukan prapemrosesan data.
- Membangun dan membandingkan dua algoritma klasifikasi.
- Mengevaluasi performa setiap kelas.
- Mengidentifikasi fitur yang berkontribusi terhadap prediksi model.

### Dataset

**Predict Students' Dropout and Academic Success**

Sumber: [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/697/predict+students+dropout+and+academic+success)

DOI: [10.24432/C5MC89](https://doi.org/10.24432/C5MC89)

Dataset berisi 4.424 data mahasiswa dengan 36 fitur masukan dan satu variabel target bernama `Target`.

Kategori target:

- `Dropout`: mahasiswa yang berhenti dari program studi.
- `Enrolled`: mahasiswa yang masih terdaftar atau menjalani pendidikan.
- `Graduate`: mahasiswa yang telah menyelesaikan pendidikan.

Dataset berasal dari institusi pendidikan tinggi di Portugal, sehingga hasil eksperimen tidak dapat langsung digeneralisasikan ke mahasiswa di Indonesia.

### Metode dan Tahapan

1. Mengambil dan memeriksa dataset.
2. Memeriksa tipe data, nilai kosong, duplikasi, dan distribusi kelas.
3. Melakukan eksplorasi data dan visualisasi.
4. Memisahkan fitur dan variabel target.
5. Membagi data menjadi 80% data pelatihan dan 20% data pengujian dengan stratifikasi kelas.
6. Melakukan preprocessing menggunakan SimpleImputer dan pipeline.
7. Menerapkan StandardScaler pada Logistic Regression.
8. Melatih Logistic Regression dan Random Forest Classifier.
9. Mengevaluasi performa menggunakan beberapa metrik klasifikasi.
10. Membuat confusion matrix dan visualisasi perbandingan model.
11. Menganalisis feature importance dari Random Forest.
12. Menampilkan contoh prediksi dan menyimpan hasil jika fitur tersebut tersedia pada notebook.

### Algoritma dan Evaluasi

- **Logistic Regression:** model klasifikasi dasar dengan standardisasi fitur.
- **Random Forest Classifier:** model ensemble berbasis pohon keputusan.

Metrik yang digunakan adalah Accuracy, Macro Precision, Macro Recall, dan Macro F1-score. Classification report digunakan untuk meninjau performa pada setiap kelas, sedangkan confusion matrix menunjukkan pola kesalahan klasifikasi.

Macro F1-score digunakan sebagai acuan utama perbandingan karena memberikan bobot yang sama kepada setiap kelas.

Feature importance menunjukkan kontribusi relatif fitur terhadap prediksi model dan tidak membuktikan hubungan sebab-akibat.

### Teknologi

Python, Google Colab, Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn, dan Joblib.

### Notebook

`Studi_Kasus_Prediksi_Dropout_Mahasiswa.ipynb`

---

## 5. Sesi 5 — Dashboard Interaktif Layanan Perpustakaan Kampus

### Deskripsi

Proyek ini menerapkan konsep *Human-Computer Interaction* (HCI) dan *Data Visualization* melalui pengembangan dashboard interaktif untuk menyajikan informasi layanan perpustakaan kampus.

Dashboard menampilkan indikator utama, grafik, filter interaktif, dan tabel rincian kunjungan. Antarmuka dibuat menggunakan HTML, CSS, dan JavaScript, sedangkan Python dan Pandas digunakan untuk menyiapkan data serta menghasilkan file dashboard HTML.

### Tujuan

- Memahami penerapan HCI dalam perancangan antarmuka.
- Menyajikan informasi melalui visualisasi data.
- Mengembangkan dashboard yang interaktif dan responsif.
- Membuat filter untuk mengeksplorasi data.
- Menerapkan prinsip konsistensi, hierarki visual, dan umpan balik interaksi.
- Mendokumentasikan proyek agar dapat dibagikan melalui GitHub.

### Dataset

**Data Dummy Layanan Perpustakaan Kampus**

Sumber: data sintetis yang dibuat menggunakan Python dan NumPy.

Jumlah data: 800 catatan kunjungan.

Variabel utama meliputi:

- `date`: tanggal kunjungan.
- `service`: jenis layanan.
- `faculty`: fakultas pengunjung.
- `time_slot`: rentang waktu kunjungan.
- `wait`: waktu tunggu dalam menit.
- `duration`: durasi pelayanan dalam menit.
- `satisfaction`: tingkat kepuasan pada skala 1–5.

Data merupakan simulasi untuk demonstrasi teknis, bukan data resmi perpustakaan atau hasil survei pengunjung nyata.

### Metode dan Tahapan

1. Membuat dataset sintetis menggunakan Python, NumPy, dan Pandas.
2. Memeriksa struktur dan tipe data.
3. Mengolah variabel yang dibutuhkan untuk visualisasi.
4. Menghitung indikator utama dashboard.
5. Merancang struktur halaman dengan HTML.
6. Mengatur tampilan menggunakan CSS.
7. Membuat grafik interaktif menggunakan Plotly.js.
8. Mengembangkan filter layanan, fakultas, dan rentang tanggal menggunakan JavaScript.
9. Memperbarui indikator, grafik, dan tabel berdasarkan filter.
10. Menerapkan prinsip desain responsif dan aksesibilitas dasar.
11. Menguji fungsi filter dan tampilan dashboard.
12. Menghasilkan file HTML untuk digunakan melalui browser.

### Fitur Dashboard

**Indikator utama (KPI):**
- Total kunjungan.
- Rata-rata waktu tunggu.
- Rata-rata tingkat kepuasan.
- Layanan paling banyak digunakan.

**Visualisasi:**
- Grafik garis tren kunjungan harian.
- Grafik batang jumlah kunjungan per layanan.
- Grafik sebar hubungan waktu tunggu dan kepuasan.
- Grafik batang rata-rata durasi pelayanan.

**Interaksi:**
- Filter berdasarkan jenis layanan.
- Filter berdasarkan fakultas.
- Filter berdasarkan rentang tanggal.
- Tombol Terapkan Filter dan Reset.
- Tabel rincian kunjungan yang menyesuaikan filter.

### Penerapan HCI

Prinsip HCI yang diterapkan meliputi hierarki visual, konsistensi komponen, kejelasan label, umpan balik setelah interaksi, desain responsif, dan dukungan fokus keyboard.

Penerapan tersebut merupakan bagian dari rancangan teknis. Pengujian usability formal dengan pengguna nyata masih diperlukan untuk mengukur efektivitas dan kemudahan penggunaan secara empiris.

### Teknologi

Python, Google Colab, HTML, CSS, JavaScript, Pandas, NumPy, Plotly.js, dan GitHub.

### Keluaran dan Notebook

- `Studi_Kasus_HCI_Visualisasi_Layanan_Perpustakaan_HTML.ipynb`
- `dashboard_perpustakaan.html`
- Dataset CSV jika dihasilkan oleh notebook.

Dashboard dapat dibuka menggunakan Google Chrome atau browser lainnya setelah file HTML berhasil dibuat.

---

## 6. Sesi 6 — Klasifikasi Penyebab Deforestasi Menggunakan CNN

### Deskripsi

Proyek ini menerapkan konsep *Deep Learning* menggunakan *Convolutional Neural Network* (CNN) untuk mempelajari klasifikasi citra yang berkaitan dengan penyebab deforestasi.

Proyek berfokus pada tahapan dasar klasifikasi citra, mulai dari pembuatan dataset, pemberian label, pelatihan model, hingga evaluasi prediksi.

**Penting:** eksperimen menggunakan citra sintetis yang dibuat secara artifisial, bukan citra satelit Sentinel-1 atau Sentinel-2 asli. Oleh karena itu, model ini merupakan demonstrasi pembelajaran dan belum dapat digunakan untuk menentukan penyebab deforestasi di dunia nyata.

### Tujuan

- Memahami dasar Deep Learning dan CNN.
- Mempelajari persiapan dataset citra dan label.
- Membangun model klasifikasi menggunakan TensorFlow/Keras.
- Melatih dan menguji model.
- Mengevaluasi hasil menggunakan metrik klasifikasi.
- Memahami keterbatasan penggunaan dataset sintetis.

### Dataset

**Dataset Sintetis Klasifikasi Penyebab Deforestasi**

Sumber: data sintetis yang dibuat menggunakan NumPy di dalam notebook.

Spesifikasi:

- Jumlah sampel: 2.000 citra sintetis.
- Ukuran citra: 32 × 32 piksel.
- Kanal citra: 3.
- Jumlah kelas: 8.
- Jumlah sampel per kelas: 250.

Kelas yang digunakan:

1. Pertanian skala besar.
2. Pertanian skala kecil.
3. Pertambangan.
4. Pembangunan jalan.
5. Penebangan selektif.
6. Kebakaran hutan.
7. Banjir.
8. Faktor alam lainnya.

Pola citra dibuat menggunakan bentuk geometris, garis, area dengan nilai kanal berbeda, dan variasi acak. Label diberikan berdasarkan kelas sintetis yang telah ditentukan dalam kode.

### Metode dan Tahapan

1. Mengimpor pustaka yang diperlukan.
2. Menentukan parameter eksperimen dan random seed.
3. Membuat dataset citra sintetis.
4. Memberikan label numerik pada setiap kelas.
5. Menampilkan contoh citra untuk memahami pola sintetis.
6. Membagi dataset menjadi data pelatihan dan pengujian.
7. Membangun arsitektur CNN menggunakan TensorFlow/Keras.
8. Melatih model menggunakan data pelatihan.
9. Menghasilkan prediksi kelas dan probabilitas.
10. Mengevaluasi hasil klasifikasi.
11. Membuat confusion matrix dan visualisasi prediksi.
12. Menganalisis hasil berdasarkan karakteristik dataset sintetis.

### Algoritma dan Evaluasi

**Convolutional Neural Network (CNN)** digunakan untuk mempelajari pola spasial dalam citra melalui operasi konvolusi dan lapisan jaringan lainnya.

Evaluasi menggunakan:

- **Overall Accuracy:** proporsi seluruh prediksi yang benar.
- **Macro-F1:** rata-rata F1-score dari setiap kelas dengan bobot yang sama.
- **Confusion matrix:** menunjukkan jumlah prediksi benar dan kesalahan pada setiap kelas.

Nilai evaluasi yang tinggi hanya menunjukkan kemampuan model pada data dan pola sintetis yang digunakan. Nilai tersebut tidak membuktikan kemampuan mengenali penyebab deforestasi pada citra satelit asli.

### Teknologi

Python, Google Colab, NumPy, Matplotlib, TensorFlow/Keras, dan Scikit-learn.

### Notebook

Notebook proyek klasifikasi penyebab deforestasi sesuai file yang tersedia pada repositori.

---

## Teknologi yang Digunakan

| Teknologi | Penggunaan |
|---|---|
| Python | Bahasa pemrograman utama untuk pengolahan data dan pemodelan. |
| Google Colab | Lingkungan berbasis cloud untuk menjalankan notebook. |
| Pandas dan NumPy | Pengolahan data tabular dan operasi numerik. |
| Matplotlib dan Seaborn | Visualisasi data dan hasil evaluasi. |
| Scikit-learn | Preprocessing, pemodelan Machine Learning, dan evaluasi. |
| TensorFlow/Keras | Pembangunan dan pelatihan model CNN. |
| Requests dan Folium | Pengambilan data geografis dan pembuatan peta interaktif. |
| HTML, CSS, dan JavaScript | Pengembangan antarmuka dashboard. |
| Plotly.js | Pembuatan grafik interaktif. |
| ucimlrepo | Pengambilan dataset dari UCI Machine Learning Repository. |
| GitHub | Dokumentasi dan pengelolaan kode sumber proyek. |

Tidak semua teknologi digunakan pada setiap proyek. Pustaka yang digunakan bergantung pada kebutuhan dan tujuan masing-masing sesi.

## Cara Menjalankan Proyek

Secara umum, langkah menjalankan proyek adalah sebagai berikut.

1. Buka [Google Colab](https://colab.research.google.com/).
2. Pilih notebook sesuai sesi webinar yang ingin dijalankan.
3. Unggah notebook melalui menu **File → Upload notebook**, atau buka notebook langsung dari repositori GitHub jika tersedia.
4. Pastikan koneksi internet tersedia untuk mengunduh dataset, mengakses API, atau memasang pustaka jika diperlukan.
5. Jalankan setiap sel secara berurutan dari atas ke bawah atau gunakan menu **Runtime → Run all**.
6. Tunggu proses pengambilan data, preprocessing, pelatihan model, evaluasi, atau pembuatan dashboard hingga selesai.
7. Periksa tabel, grafik, metrik evaluasi, peta, atau dashboard yang dihasilkan.
8. Simpan notebook dan keluaran proyek jika diperlukan untuk dokumentasi.

## Penutup

Enam proyek ini memberikan pengalaman pembelajaran yang beragam, mulai dari analisis data dan prediksi menggunakan Machine Learning, pengenalan komputasi paralel, pemetaan geografis, pengembangan dashboard interaktif, hingga klasifikasi citra menggunakan Deep Learning.

Setiap proyek dirancang untuk membantu memahami alur kerja pengembangan solusi berbasis data, mulai dari pengumpulan dan persiapan data hingga pemodelan, evaluasi, visualisasi, serta interpretasi hasil.

Repositori ini diharapkan dapat menjadi dokumentasi pembelajaran, referensi implementasi, dan dasar untuk pengembangan proyek lanjutan dengan dataset nyata, metode yang lebih beragam, serta evaluasi yang lebih mendalam.
