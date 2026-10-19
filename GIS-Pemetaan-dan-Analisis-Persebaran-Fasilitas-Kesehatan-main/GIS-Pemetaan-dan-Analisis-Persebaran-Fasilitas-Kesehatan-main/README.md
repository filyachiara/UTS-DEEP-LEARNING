# Pemetaan dan Analisis Persebaran Fasilitas Kesehatan di Kota Bengkulu Menggunakan GIS

## 1. Deskripsi Proyek

Proyek ini membahas pemetaan dan analisis persebaran fasilitas kesehatan di sekitar Kota Bengkulu menggunakan *Geographic Information System* (GIS). Proyek ini disusun berdasarkan materi Webinar 3 tentang GIS, khususnya pemanfaatan data geografis untuk memahami persebaran suatu objek dan menyajikan informasi lokasi dalam bentuk visual.

Analisis dilakukan menggunakan data fasilitas kesehatan yang tersedia pada OpenStreetMap (OSM). Data tersebut diambil melalui Overpass API, kemudian diolah menggunakan Python di Google Colab. Tahapan proyek meliputi pengambilan data, pemeriksaan dan pembersihan data, pengelompokan fasilitas berdasarkan jenis, pembuatan peta interaktif, serta visualisasi konsentrasi titik menggunakan *heatmap*.

Peta dasar (*basemap*) menggunakan Esri WorldStreetMap untuk membantu menampilkan lokasi fasilitas kesehatan pada konteks geografis. Penggunaan basemap Esri tidak mengubah sumber data fasilitas kesehatan yang tetap berasal dari OpenStreetMap.

Hasil proyek diharapkan dapat membantu memahami cara GIS digunakan untuk menyajikan informasi lokasi fasilitas kesehatan secara lebih mudah dipahami. Namun, hasil pemetaan ini merupakan eksplorasi awal berdasarkan data OpenStreetMap, bukan inventaris resmi fasilitas kesehatan dari pemerintah.

## 2. Tujuan

- Memahami penerapan konsep GIS dalam pemetaan fasilitas kesehatan.
- Mengambil data lokasi fasilitas kesehatan dari OpenStreetMap menggunakan Overpass API.
- Mengolah data geografis yang terdiri dari koordinat latitude dan longitude.
- Mengelompokkan objek fasilitas kesehatan berdasarkan jenis atau tag yang tersedia.
- Membuat peta interaktif untuk menampilkan lokasi fasilitas kesehatan.
- Memvisualisasikan konsentrasi titik menggunakan *heatmap*.
- Memahami manfaat dan keterbatasan data spasial dalam mendukung analisis persebaran fasilitas kesehatan.

## 3. Dataset

**Nama dataset:** Data Fasilitas Kesehatan OpenStreetMap

**Sumber data:** OpenStreetMap

Tautan OpenStreetMap:  
https://www.openstreetmap.org/

Tautan Overpass API:  
https://overpass-api.de/

Berbeda dengan dataset statis yang sudah tersedia dalam bentuk CSV, proyek ini mengambil data secara langsung melalui Overpass API berdasarkan tag yang berkaitan dengan fasilitas kesehatan.

Tag yang digunakan mencakup `hospital`, `clinic`, `doctors`, `dentist`, `pharmacy`, serta objek yang memiliki tag `healthcare`.

Data yang diperoleh dapat mencakup informasi seperti:

- Nama fasilitas kesehatan, jika tersedia.
- Jenis atau kategori fasilitas berdasarkan tag OpenStreetMap.
- Koordinat latitude dan longitude.
- Nama operator, jika tercantum.
- ID objek OpenStreetMap sebagai identitas data.

Area pengambilan data menggunakan *bounding box* atau kotak koordinat perkiraan di sekitar Kota Bengkulu. Batas pencarian tersebut digunakan untuk membatasi wilayah pengambilan data dan bukan merupakan batas administrasi resmi Kota Bengkulu.

Data OpenStreetMap bersifat kolaboratif. Oleh karena itu, kelengkapan, ketepatan, dan kebaruan data bergantung pada informasi yang telah dimasukkan oleh kontributor. Jumlah objek dan hasil analisis dapat berubah ketika notebook dijalankan pada waktu yang berbeda.

Atribusi sumber data dicantumkan untuk menghargai penyedia data. Jika data atau hasil turunannya dibagikan kembali, ketentuan atribusi dan lisensi OpenStreetMap, termasuk Open Database License (ODbL), perlu diperhatikan.

## 4. Metode dan Tahapan Analisis

1. **Pengambilan data**

   Mengambil data fasilitas kesehatan yang tersedia di OpenStreetMap melalui Overpass API berdasarkan tag yang berkaitan dengan layanan kesehatan dan wilayah pencarian yang ditentukan.

2. **Pemeriksaan struktur data**

   Memeriksa jumlah objek yang berhasil diperoleh, atribut yang tersedia, serta struktur data sebelum dilakukan pengolahan lebih lanjut.

3. **Pembersihan dan pengolahan data**

   Menyusun data ke dalam tabel yang berisi ID objek, nama fasilitas, jenis fasilitas, latitude, longitude, operator, dan sumber data. Objek yang tidak memiliki koordinat yang dapat digunakan akan dilewati, kemudian data diperiksa berdasarkan wilayah pencarian dan duplikasi ID.

4. **Pengelompokan fasilitas kesehatan**

   Mengelompokkan objek berdasarkan jenis atau tag yang tersedia, kemudian menghitung jumlah objek pada setiap kategori untuk melihat komposisi data fasilitas kesehatan yang berhasil diperoleh.

5. **Analisis eksploratif**

   Menampilkan ringkasan jumlah fasilitas berdasarkan jenis menggunakan tabel dan grafik batang. Tahap ini digunakan untuk memahami komposisi data yang berhasil dikumpulkan.

6. **Pembuatan peta interaktif**

   Menggunakan Folium untuk menampilkan titik lokasi fasilitas kesehatan pada peta. Basemap Esri WorldStreetMap digunakan sebagai latar peta, sedangkan fitur *MarkerCluster* digunakan untuk mengelompokkan penanda yang berdekatan agar peta lebih mudah dibaca.

7. **Visualisasi heatmap**

   Membuat *heatmap* berdasarkan koordinat fasilitas untuk melihat area dengan konsentrasi titik yang relatif lebih tinggi pada data yang terpetakan. Visualisasi ini digunakan untuk mengamati konsentrasi lokasi, bukan untuk mengukur kecukupan layanan kesehatan.

8. **Penyimpanan hasil**

   Menyimpan data yang telah diolah dalam format CSV serta menyimpan peta interaktif dalam format HTML agar hasilnya dapat diperiksa kembali dan didokumentasikan, sesuai dengan keluaran yang dihasilkan notebook.

9. **Interpretasi hasil**

   Mengamati pola persebaran titik dan komposisi fasilitas berdasarkan hasil aktual. Interpretasi dilakukan dengan memperhatikan keterbatasan sumber data agar konsentrasi titik tidak langsung dianggap sebagai ukuran kecukupan layanan kesehatan.

## 5. Teknologi yang Digunakan

- **Python** — bahasa pemrograman untuk pengambilan, pengolahan, dan analisis data.
- **Google Colab** — lingkungan berbasis cloud untuk menjalankan notebook Python.
- **Pandas** — pengolahan data dalam bentuk tabel, pembersihan data, dan pengelompokan kategori.
- **Requests** — mengirim permintaan ke Overpass API untuk mengambil data OpenStreetMap.
- **Folium** — pembuatan peta interaktif berbasis data koordinat.
- **Esri WorldStreetMap** — penyedia basemap untuk menampilkan konteks geografis dan lokasi fasilitas kesehatan.
- **MarkerCluster** — pengelompokan penanda lokasi yang berdekatan pada peta.
- **HeatMap** — visualisasi konsentrasi titik lokasi.
- **Matplotlib** — pembuatan grafik jumlah objek berdasarkan jenis fasilitas.

## 6. Cara Menjalankan Proyek

1. Buka notebook `Studi_Kasus_Webinar_3_GIS_Fasilitas_Kesehatan_Bengkulu.ipynb` melalui Google Colab.
2. Jalankan setiap sel secara berurutan dari awal hingga akhir. Alternatifnya, pilih menu **Runtime → Run all**.
3. Pastikan koneksi internet tersedia karena notebook mengambil data dari Overpass API dan memuat basemap dari layanan Esri.
4. Tunggu hingga proses pengambilan data, pembersihan data, pengelompokan kategori, dan visualisasi selesai.
5. Periksa tabel data, grafik jumlah objek berdasarkan jenis, peta interaktif, dan *heatmap* yang dihasilkan.
6. Periksa folder `hasil_gis` untuk melihat file CSV hasil pengolahan dan peta interaktif berformat HTML, jika notebook telah menghasilkan dan menyimpan file tersebut.
7. Jika pengambilan data gagal karena layanan API sedang sibuk atau mengalami gangguan, coba jalankan kembali sel pengambilan data setelah beberapa saat.


## 7. Hasil yang Dihasilkan

Notebook dirancang untuk menghasilkan beberapa keluaran, antara lain:

- Tabel data fasilitas kesehatan yang berhasil diambil dari OpenStreetMap.
- Informasi nama, jenis, koordinat, operator, dan ID objek jika tersedia.
- Ringkasan jumlah objek berdasarkan jenis atau tag fasilitas kesehatan.
- Grafik batang yang menunjukkan jumlah objek pada setiap kategori.
- Peta interaktif yang menampilkan lokasi fasilitas kesehatan dengan basemap Esri WorldStreetMap.
- Fitur *MarkerCluster* untuk membantu menampilkan titik yang berdekatan.
- *Heatmap* untuk mengeksplorasi konsentrasi lokasi fasilitas kesehatan.
- File CSV hasil pengolahan data.
- File HTML peta interaktif, jika fitur penyimpanan tersebut dijalankan dalam notebook.

## 8. Kesimpulan

Proyek ini menunjukkan penerapan konsep *Geographic Information System* (GIS) untuk mengolah dan memvisualisasikan data lokasi fasilitas kesehatan di sekitar Kota Bengkulu. Dengan menggunakan Python dan Google Colab, data dari OpenStreetMap dapat diambil, dibersihkan, dikelompokkan, dan ditampilkan dalam bentuk tabel, grafik, peta interaktif, serta *heatmap*.

Visualisasi tersebut membantu pengguna memahami pola persebaran fasilitas kesehatan yang tercatat pada sumber data. Penggunaan basemap Esri WorldStreetMap membantu menampilkan konteks geografis, sedangkan data fasilitas kesehatan tetap berasal dari OpenStreetMap.

Meskipun demikian, hasil pemetaan tidak dapat langsung dianggap sebagai gambaran lengkap kondisi fasilitas kesehatan di Kota Bengkulu. Pengembangan berikutnya dapat dilakukan dengan menggunakan data resmi pemerintah, batas administrasi yang lebih akurat, data jumlah penduduk, serta analisis jarak atau waktu tempuh untuk memperoleh pemahaman yang lebih baik mengenai aksesibilitas layanan kesehatan.
