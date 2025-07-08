# Proyek Machine Learning: Segmentasi Pelanggan & Klasifikasi

![Customer Segmentation](/asset/MachineLearning.png)

## 📜 Latar Belakang

Proyek ini merupakan **Tugas Akhir** untuk menyelesaikan kelas **"Belajar Machine Learning untuk Pemula"** dari program beasiswa **IDCamp 2024** yang diselenggarakan oleh Indosat Ooredoo Hutchison dan Dicoding.

Tujuan utama proyek ini adalah mengaplikasikan dua pendekatan utama dalam machine learning—*unsupervised* dan *supervised learning*—untuk menyelesaikan studi kasus nyata, yaitu segmentasi pelanggan (customer segmentation).

## 🎯 Tujuan Proyek

Analisis ini bertujuan untuk:
1.  **Melakukan Segmentasi Pelanggan:** Mengelompokkan pelanggan ke dalam segmen-segmen yang berbeda berdasarkan data demografis dan perilaku belanja mereka menggunakan algoritma *clustering*.
2.  **Membangun Model Klasifikasi:** Membuat model yang dapat memprediksi segmen seorang pelanggan berdasarkan fitur-fitur yang ada, sehingga dapat membantu dalam pengambilan keputusan bisnis di masa depan.

## 📁 Dataset

Dataset yang digunakan adalah **`marketing_campaign.csv`**, yang berisi 29 fitur dan 2240 baris data pelanggan. Informasi di dalamnya mencakup:
* **Data Demografis:** `Year_Birth`, `Education`, `Marital_Status`, `Income`.
* **Data Perilaku Belanja:** Total pengeluaran untuk berbagai produk (`MntWines`, `MntFruits`, dll).
* **Data Interaksi Kampanye:** Jumlah pembelian, kunjungan web, dan respons terhadap kampanye pemasaran.

## 🛠️ Alur Kerja Proyek (Workflow)

Proyek ini dibagi menjadi dua notebook utama:

### **1. Notebook Clustering (`1_Clustering_Pelanggan.ipynb`)**

1.  **Persiapan Data:** Memuat data, melakukan analisis data eksploratif (EDA) untuk memahami distribusi dan korelasi, serta menangani nilai yang hilang.
2.  **Pra-pemrosesan:**
    * Membuat fitur baru (`Age`).
    * Melakukan *Label Encoding* pada fitur kategorikal (`Education`).
    * Melakukan *Feature Scaling* pada fitur `Income` untuk menormalisasi rentang nilainya.
3.  **Pemodelan Clustering (K-Means):**
    * Menentukan jumlah cluster optimal (K=2) menggunakan **Elbow Method** dan **Silhouette Score**.
    * Melatih model K-Means untuk menghasilkan label cluster.
    * Mengevaluasi model dengan *Silhouette Score* sebesar **0.5862**.
4.  **Analisis & Interpretasi Cluster:** Menganalisis karakteristik setiap cluster dan menemukan dua profil pelanggan utama:
    * **Cluster 0:** Pelanggan berusia lebih muda dengan daya beli lebih rendah.
    * **Cluster 1:** Pelanggan senior dengan daya beli tinggi, merupakan segmen premium/loyal.
5.  **Eksperimen Tambahan (Upgrade):**
    * **RobustScaler vs. MinMaxScaler:** Membandingkan teknik *scaling* dan menemukan bahwa keduanya memberikan hasil yang identik untuk dataset ini.
    * **Hierarchical Clustering:** Mencoba algoritma alternatif dan membandingkan hasilnya, di mana K-Means terbukti sedikit lebih unggul.

### **2. Notebook Klasifikasi (`2_Klasifikasi_Segmen.ipynb`)**

1.  **Persiapan Data:** Menggunakan dataset yang telah diberi label dari hasil *clustering* dan membaginya menjadi data latih & uji.
2.  **Pemodelan & Evaluasi:**
    * Membangun model **Random Forest Classifier**.
    * Membangun model **Logistic Regression**.
    * Mengevaluasi kedua model menggunakan metrik *Accuracy*, *F1-Score*, dan *Confusion Matrix*.
3.  **Hasil:**
    * **Random Forest:** Mencapai performa sempurna dengan **Akurasi 100%**.
    * **Logistic Regression:** Juga mencapai performa sempurna dengan **Akurasi 100%**.

## ✨ Kesimpulan & Hasil Utama

* Dari analisis *clustering*, pelanggan dapat disegmentasikan secara efektif menjadi **dua kelompok utama** dengan profil dan perilaku belanja yang sangat berbeda.
* Model klasifikasi **Random Forest** dan **Logistic Regression** keduanya terbukti sangat akurat dalam memprediksi segmen pelanggan, menunjukkan bahwa fitur-fitur yang ada sangat informatif dan mampu memisahkan kedua cluster dengan jelas.

## 🚀 Cara Menjalankan Proyek

1.  **Clone repository ini:**
    ```bash
    git clone https://github.com/RozhakXD/Proyek-Segmentasi-Pelanggan.git
    cd Proyek-Segmentasi-Pelanggan
    ```
2.  **Pastikan library yang dibutuhkan ter-install:**
    ```bash
    pip install pandas numpy matplotlib seaborn scikit-learn
    ```
3.  **Buka dan jalankan notebook:**
    * Mulai dengan `1_Clustering_Pelanggan.ipynb` untuk menghasilkan file `hasil_clustering.csv`.
    * Lanjutkan dengan `2_Klasifikasi_Segmen.ipynb` untuk melakukan prediksi.


## 📄 License

This project is licensed under the MIT License. You are free to use, modify, and distribute this code for personal or commercial purposes, provided that the original copyright and license notice are included. See the [LICENSE](LICENSE) file for more details.

Dibuat dengan ❤️ oleh **Rozhak**.