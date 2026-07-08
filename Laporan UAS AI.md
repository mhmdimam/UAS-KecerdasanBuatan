\# Laporan UAS Kecerdasan Buatan



1\. Judul Proyek

&#x20;  Judul: Prediksi Kelayakan Air Minum (Water Potability) Menggunakan Algoritma Machine Learning

&#x20;  Nama Kelompok: Muhamad Imam Assidiq

&#x20;  Domain Proyek: Lingkungan dan Kesehatan Masyarakat (Kualitas Air)



2\. Business Understanding

* Permasalahan dunia nyata dan literatur review: Akses terhadap air minum yang aman adalah kebutuhan dasar manusia, namun pencemaran lingkungan membuat sumber air seringkali tidak layak konsumsi. Pengujian kualitas air secara manual di laboratorium memakan waktu dan biaya.
* Tujuan proyek: Membangun model Machine Learning yang dapat memprediksi kelayakan air minum (aman/tidak aman) secara otomatis berdasarkan parameter kimia dan fisika air.
* Siapa user/pengguna sistem: Perusahaan daerah air minum (PDAM), dinas kesehatan, atau peneliti lingkungan.
* Solusi dan manfaat implementasi AI: AI memberikan solusi berupa deteksi dini kelayakan air yang lebih cepat dan efisien untuk mencegah penyakit akibat air yang terkontaminasi.



3\. Data Understanding

* Sumber data: Dataset diunduh dari Kaggle dengan judul "Water Potability".
* Deskripsi fitur utama: Terdapat 9 fitur kimiawi air yaitu ph, Hardness (kesadahan), Solids (padatan terlarut), Chloramines, Sulfate, Conductivity, Organic\_carbon, Trihalomethanes, dan Turbidity (kekeruhan).
* Target klasifikasi: Kolom Potability dengan kategori 0 (Tidak Aman) dan 1 (Aman).
* Ukuran dan format data: Dataset bertipe `.csv` dengan total 3.276 baris data dan 10 kolom.
* Tipe data: Seluruh fitur pengujian bertipe numerik desimal (float64), sedangkan target bertipe bilangan bulat (int64).



4\. Exploratory Data Analysis (EDA)

* Visualisasi distribusi data: Berdasarkan perhitungan grafik Bar Chart, jumlah sampel air yang tidak layak minum (0) lebih banyak daripada air yang layak minum (1).
* Deteksi data tidak seimbang: Terdapat indikasi imbalanced class ringan pada kolom target karena ketimpangan jumlah kelas 0 dan kelas 1.
* Analisis korelasi antar fitur: Berdasarkan visualisasi Heatmap, angka korelasi antar fitur kimia air sangat lemah (mendekati 0), yang berarti tidak ada satu variabel yang secara absolut mendominasi variabel lain.
* Insight awal dari pola data: Diperlukan algoritma pemodelan yang mampu mengolah data non-linear karena batas kelayakan air bergantung pada kombinasi berbagai matriks, bukan hanya satu matriks tunggal.



5\. Data Preparation

* Pembersihan data: Ditemukan null value (data kosong) pada kolom ph, Sulfate, dan Trihalomethanes. Hal ini diatasi dengan teknik imputasi menggunakan nilai rata-rata.
* Encoding data kategorik: Tidak dilakukan proses encoding karena dataset tidak memiliki fitur berupa teks atau kategori.
* Normalisasi / standardisasi data numerik: Dilakukan proses standardisasi menggunakan library `StandardScaler` agar rentang angka antar kolom menjadi seragam dan tidak menyebabkan bias pada model.
* Split data (train-test): Dataset dipisah menggunakan `train\_test\_split` dengan rasio 80% data latih dan 20% data uji.



6\. Modeling

* Pemilihan algoritma: Algoritma yang digunakan adalah Decision Tree dan K-Nearest Neighbors (KNN).
* Alasan pemilihan 2 algoritma: Decision Tree mampu menghasilkan aturan keputusan (if-then) yang mudah dibaca oleh manusia. Sementara KNN digunakan sebagai pembanding karena algoritma ini handal dalam memetakan data berdasarkan kedekatan jarak karakteristik air.
* Implementasi model: Pemrograman dilakukan dengan Python menggunakan library Scikit-Learn.
* Visualisasi model: Visualisasi akar dan daun pada Decision Tree telah di-generate dan dapat dilihat langsung pada file ekstensi `.ipynb`.
* Perbandingan model: Kedua model dilatih menggunakan data latih yang sama lalu diuji kemampuan prediksinya menggunakan matriks klasifikasi.



7\. Evaluation

* Confusion matrix: Kedua model menghasilkan peta sebaran True Positive dan True Negative yang menunjukkan keberhasilan tebakan, sekaligus mendeteksi adanya error berupa False Positive (air tidak aman ditebak aman).
* Metrik evaluasi: Algoritma Decision Tree menghasilkan akurasi di kisaran 63%, sedangkan algoritma KNN menghasilkan akurasi di kisaran 65%. 
* Penjelasan kinerja model: Model KNN dipilih sebagai model yang lebih baik pada proyek ini. Alasannya adalah tingkat Accuracy dan F1-Score pada KNN sedikit lebih unggul dan seimbang dalam membedakan kedua kelas target dibandingkan Decision Tree.



8\. Kesimpulan dan Rekomendasi

* Ringkasan hasil modeling: Eksperimen klasifikasi kualitas air minum berhasil dilakukan menggunakan Machine Learning, di mana KNN memberikan performa yang sedikit lebih optimal.
* Apakah tujuan proyek tercapai?: Ya, sistem otomatisasi untuk memprediksi kelayakan air telah berhasil dibuat.
* Kelebihan dan keterbatasan model: Kelebihannya adalah waktu komputasi yang sangat cepat. Keterbatasannya adalah akurasi model yang belum menyentuh angka di atas 80% akibat lemahnya korelasi antar atribut kimia air bawaan dataset.
* Rekomendasi perbaikan: Untuk penelitian di masa depan, disarankan memakai algoritma tingkat lanjut seperti Random Forest dan menggunakan metode SMOTE untuk menyeimbangkan jumlah data target di awal tahap persiapan.



9\. Referensi

* Ali, V., \& Khan, M. A. (2021). Water Quality Classification Using Machine Learning Algorithms. Journal of Environmental and Public Health, 2021, 1-12.
* Hasan, M. K., \& Shahriar, A. (2022). Comparative Analysis of Machine Learning Approaches for Water Potability Prediction. International Journal of Computer Applications, 184(12), 34-40.
* Pradeep, N., \& Kumar, S. (2023). Application of Decision Tree and K-Nearest Neighbor in Predicting Drinking Water Quality. Environmental Monitoring and Assessment, 195(3), 415-427.
* Setiawan, A., \& Wibowo, A. (2022). Implementasi Algoritma Klasifikasi untuk Analisis Kelayakan Air Konsumsi Menggunakan Python. Jurnal Teknologi Informasi dan Ilmu Komputer, 9(4), 789-796.
* Scikit-learn Documentation. (2024). Supervised Learning: Decision Trees and Nearest Neighbors. Diambil dari https://scikit-learn.org/stable/



10\. Lampiran 

Dataset mentah: `water\_potability.csv`

File pemodelan beserta output grafik lengkap: `uas\_model.ipynb`

