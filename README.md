# Proyek Prediksi Harga Berlian (Diamond Price Prediction)

## 📝 Deskripsi Proyek
Proyek ini bertujuan untuk membangun model machine learning yang dapat memprediksi harga berlian secara akurat berdasarkan atribut-atribut fisiknya. Dengan menganalisis dataset klasik ini, kita akan belajar seluruh alur kerja ilmu data, mulai dari eksplorasi dan pembersihan data hingga pelatihan model dan evaluasi performa. Model ini dapat menjadi alat bantu bagi calon pembeli atau penjual untuk memperkirakan nilai wajar sebuah berlian.

## 💾 Dataset
Dataset yang digunakan adalah dataset 'diamonds' yang populer, diambil langsung dari Kaggle. Dataset ini berisi informasi dari sekitar 54,000 berlian dan mencakup fitur-fitur berikut:
- **price:** dalam dolar Amerika Serikat ($) adalah fitur target.
- **carat:** merepresentasikan bobot (weight) dari diamonds (0.2-5.01), digunakan sebagai ukuran dari batu permata dan perhiasan.
- **cut:** merepresentasikan kualitas pemotongan diamonds (Fair, Good, Very Good, Premium, and Ideal).
- **color:** merepresentasikan warna, dari J (paling buruk) ke D (yang terbaik).
- **clarity:**: merepresentasikan seberapa jernih diamonds (I1 (paling buruk), SI2, SI1, VS2, VS1, VVS2, VVS1, IF (terbaik))
- **x:** merepresentasikan panjang diamonds dalam mm (0-10.74).
- **y:** merepresentasikan lebar diamonds dalam mm (0-58.9).
- **z:** merepresentasikan kedalaman diamonds dalam mm (0-31.8).
- **depth:** merepresentasikan z/mean(x, y) = 2 * z/(x + y) (43-79).
- **table:** merepresentasikan lebar bagian atas berlian relatif terhadap titik terlebar 43-95).

## ⚙️ Alur Kerja Proyek
Proyek ini mengikuti alur kerja machine learning, diantara:
1.  **Data Preparation:** Melakukan persiapan pada data yang masih mentah agar siap digunakan untuk proses analisis selanjutnya.
2.  **Cleaning Data:** Membersihkan data dari nilai yang tidak sesuai atau tidak logis (dimensi x, y, z bernilai 0) dan menghapus kolom yang tidak relevan.
3.  **Eksplorasi Data (EDA):** Melakukan analisis mendalam untuk memahami distribusi data, dan menemukan wawasan awal melalui visualisasi seperti bar plot dan scatter plot.
4.  **Preprocessing Data:** Mengubah fitur kategorikal (`cut`, `color`, `clarity`) menjadi format numerik menggunakan teknik One-Hot Encoding agar dapat diproses oleh model.
5.  **Pembagian Data:** Membagi dataset menjadi data latih (80%) dan data tes (20%) menggunakan `train_test_split` dari Scikit-learn untuk memastikan evaluasi model yang objektif.
6.  **Pemodelan:** Membangun dan melatih model **Regresi Linear (`LinearRegression`)** untuk mempelajari pola hubungan antara fitur-fitur berlian dan harganya.
7.  **Evaluasi Model:** Mengevaluasi performa model pada data tes menggunakan metrik standar regresi seperti R-squared (R²), Mean Absolute Error (MAE), dan Root Mean Squared Error (RMSE).
8.  **Visualisasi Data:** Menunjukkan hasil prediksi model menggunakan scatter plot. 

## 💡 Wawasan Kunci dari EDA
- **`Carat` adalah Faktor Dominan:** Carat memiliki korelasi positif terkuat dengan harga. Hubungannya cenderung eksponensial.
- **Paradoks Kualitas vs. Ukuran:** Ditemukan adanya paradoks menarik di mana kategori dengan `cut` dan `clarity` yang lebih rendah justru memiliki *rata-rata harga* yang lebih tinggi. Analisis lebih lanjut membuktikan bahwa ini disebabkan karena kategori tersebut cenderung berisi berlian dengan **ukuran (`carat`) yang lebih besar**, yang efeknya lebih dominan terhadap harga daripada kualitas.

## 📊 Performa Model
Model Regresi Linear yang dibangun berhasil menunjukkan performa yang sangat baik dengan hasil sebagai berikut pada data tes:
- **R-squared (R²):** **0.9195127194882515**
- **Mean Absolute Error (MAE):** **290368.1265477284**
- **Mean Squared Error (MSE):** **726.299856207592**

## 🛠️ Teknologi yang Digunakan
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn (`sklearn`)
- Google Colab 
