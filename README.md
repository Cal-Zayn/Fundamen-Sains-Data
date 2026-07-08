# Fundamen-Sains-Data

# Iris Flower Classification: Dimensionality Reduction (PCA vs t-SNE)

*Anggota Tim:*
* Maulana Shiddiq Afdhaluddin (24523022)
* Muhammad Zayyan Achnaf (24523147)
* Raihan Farabi Muzakki (24523246)

---

## 📋 Deskripsi Kasus
Dataset bunga Iris memiliki *4 dimensi* (panjang sepal, lebar sepal, panjang petal, dan lebar petal). Tingginya dimensi ini membuat data sulit untuk divisualisasikan dan dianalisis secara langsung menggunakan plot standar. 

Proyek ini bertujuan untuk menyelesaikan masalah tersebut dengan menerapkan teknik *Dimensionality Reduction* (Pengurangan Dimensi). Tujuan utamanya adalah mereduksi data dari ruang 4D ke ruang 2D sehingga struktur data dan pengelompokan alami (natural clustering) dari spesies bunga Iris dapat diobservasi dengan jelas. Proyek ini juga membandingkan efektivitas antara pendekatan reduksi linier dan non-linier.

## 📊 Dataset yang Digunakan
Proyek ini menggunakan *Iris Flower Dataset* yang sangat populer dalam dunia machine learning.
* *Jumlah Sampel:* 150 data
* *Jumlah Fitur (4):* Sepal Length, Sepal Width, Petal Length, Petal Width (dalam cm)
* *Target/Kelas (3 Spesies):* Iris-setosa, Iris-versicolor, Iris-virginica

## ⚙️ Ringkasan Metode
Proyek ini menggunakan bahasa pemrograman Python dengan pustaka utama seperti scikit-learn, pandas, dan matplotlib. Langkah-langkah metode yang dilakukan meliputi:

1. *Data Preprocessing (Standardisasi):* Mengingat algoritma reduksi dimensi sangat sensitif terhadap skala data, fitur-fitur pada dataset diskalakan menggunakan StandardScaler sehingga setiap fitur memiliki rata-rata (mean) 0 dan standar deviasi 1.
2. *Principal Component Analysis (PCA):*
   Metode reduksi linier yang difokuskan untuk mempertahankan varians maksimum (struktur global) dari data. Data diproyeksikan ke dalam 2 Komponen Utama (Principal Components).
3. *t-Distributed Stochastic Neighbor Embedding (t-SNE):*
   Metode reduksi non-linier yang difokuskan untuk mempertahankan struktur lokal (neighborhoods). Pengaturan yang digunakan adalah n_components=2 dan perplexity=30.

## 📈 Analisis Hasil
Berdasarkan implementasi reduksi dimensi yang dilakukan, kedua metode menunjukkan hasil yang komprehensif namun dengan pendekatan yang berbeda.

Secara keseluruhan, proses reduksi dimensi dari 4D ke 2D berhasil dilakukan dengan sangat baik. Melalui metode *PCA, kita berhasil mempertahankan **95.8%* informasi asli (varians) dari data awal, yang berarti hilangnya informasi (information loss) sangatlah minim (hanya sekitar 4.2%). PCA juga memberikan keunggulan dalam hal interpretabilitas. Komponen Pertama (PC1) menangkap mayoritas variasi ukuran bunga (didominasi oleh fitur ukuran petal), sedangkan Komponen Kedua (PC2) menangkap variasi bentuk kelopak (didominasi oleh fitur ukuran sepal). Meskipun demikian, saat divisualisasikan, PCA masih menunjukkan sedikit tumpang tindih (overlap) antara kelas Versicolor dan Virginica.

Di sisi lain, metode *t-SNE* menunjukkan performa yang sangat luar biasa dalam pemisahan kelas secara visual. Karena t-SNE merupakan pendekatan non-linier yang mengeksplorasi hubungan ketetanggaan lokal, metode ini mampu memisahkan ketiga spesies bunga Iris dengan batas yang sangat jelas tanpa adanya tumpang tindih yang signifikan. Kelemahannya, sumbu pada visualisasi t-SNE tidak merepresentasikan fitur asli sehingga tidak dapat diinterpretasikan secara langsung.

*Kesimpulan:*
Kedua metode saling melengkapi. *PCA* sangat ideal digunakan untuk tahap awal pemahaman data dan rekayasa fitur (feature engineering) karena sifatnya yang transparan dan cepat. Sementara itu, *t-SNE* adalah pilihan terbaik jika tujuan utamanya adalah untuk menemukan pola klastering dan memvisualisasikannya ke audiens. Penggunaan kedua metode secara bersamaan memberikan insight analisis yang lengkap untuk studi kasus Iris ini.
