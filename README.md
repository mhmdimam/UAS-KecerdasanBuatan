Repositori ini dibuat untuk memenuhi Tugas Akhir Semester mata kuliah Kecerdasan Buatan. 
Proyek ini berfokus pada penerapan Machine Learning untuk memprediksi kelayakan air minum berdasarkan parameter kimia dan fisika.

Oleh: Muhamad Imam Assidiq

Penjelasan Langkah Pengerjaan
Berikut adalah alur penyelesaian proyek yang dilakukan dari awal:

1. Pengumpulan Data (Data Gathering)
Dataset yang digunakan adalah `water_potability.csv` yang diperoleh dari platform Kaggle. Dataset ini berisi metrik kualitas air seperti tingkat pH, kesadahan, hingga jumlah karbon organik.

2. Analisis Data Eksploratif (Exploratory Data Analysis / EDA)
Pada tahap ini, dilakukan pengecekan terhadap pola data, antara lain:
* Melihat distribusi kelas pada kolom target (`Potability`) menggunakan Bar Chart untuk mendeteksi apakah ada ketidakseimbangan data.
* Menganalisis korelasi (hubungan) antar fitur kimia air menggunakan visualisasi Heatmap untuk memastikan tidak ada fitur yang redundan.

3. Persiapan Data (Data Preparation)
Sebelum dimasukkan ke dalam model, data mentah harus dibersihkan dan disiapkan melalui proses:
* Pembersihan Null Value: Mengisi sel data yang kosong (NaN) pada kolom tertentu menggunakan nilai rata-rata (mean) dari kolom tersebut agar data utuh.
* Pemisahan Data: Membagi dataset menjadi fitur input (X) dan target output (y), lalu membaginya menjadi data latih (training set 80%) dan data uji (testing set 20%).
* Standardisasi: Menyamakan skala ukuran rentang angka pada semua fitur menggunakan `StandardScaler` agar model tidak bias terhadap angka yang nominalnya terlalu besar.

4. Pemodelan (Modeling)
Proses pelatihan kecerdasan buatan dilakukan menggunakan dua algoritma klasifikasi yang berbeda untuk dibandingkan:
* Decision Tree: Dipilih karena kemampuannya menghasilkan pohon keputusan yang visual dan mudah diinterpretasikan aturan batas parameternya.
* K-Nearest Neighbors (KNN): Dipilih karena kemampuannya mengklasifikasi data berdasarkan jarak kemiripan karakteristik sampel air terdekat.

5. Evaluasi Model (Evaluation)
Setelah model dilatih, pengujian dilakukan menggunakan data uji (20% data tadi). Kinerja kedua model diukur menggunakan Confusion Matrix serta metrik evaluasi standar seperti Accuracy, Precision, Recall, dan F1-Score. Berdasarkan hasil komparasi, ditentukan satu model dengan performa paling optimal dan stabil untuk kasus kelayakan air ini.