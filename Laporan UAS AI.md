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

* Chatterjee, D., Ghosh, P., Banerjee, A., & Das, S. S. (2024). Optimizing machine learning for water safety: A comparative analysis with dimensionality reduction and classifier performance in potability prediction. PLOS Water, 3(8), e0000259. https://doi.org/10.1371/journal.pwat.0000259
* Musleh, F. A. (2024). A Comprehensive Comparative Study of Machine Learning Algorithms for Water Potability Classification. International Journal of Computing and Digital Systems, 15(1), 1189-1200. http://dx.doi.org/10.12785/ijcds/150184[cite: 2].
* Akhlaq, M., Ellahi, A., Niaz, R., Khan, M., Sammen, S. S., & Scholz, M. (2024). Comparative Analysis of Machine Learning Algorithms for Water Quality Prediction. Tellus A: Dynamic Meteorology and Oceanography, 76(1), 177-192. https://doi.org/10.16993/tellusa.4069[cite: 3].
* Ghosh, H., Tusher, M. A., Rahat, I. S., Khasim, S., & Mohanty, S. N. (2023). Water Quality Assessment Through Predictive Machine Learning. Dalam V. E. Balas, V. B. Semwal, & A. Khandare (Eds.), Intelligent Computing and Networking: Proceedings of IC-ICN 2023 (hlm. 77-88). Springer. https://doi.org/10.1007/978-981-99-3177-4_6[cite: 4]
* Patel, S., Shah, K., Vaghela, S., Aglodiya, M., & Bhattad, R. (2023). Water Potability Prediction Using Machine Learning. Research Square. https://doi.org/10.21203/rs.3.rs-2965961/v1[cite: 5]



10\. Lampiran 

Dataset mentah: `water\_potability.csv`

File pemodelan beserta output grafik lengkap: `uas\_model.ipynb`

