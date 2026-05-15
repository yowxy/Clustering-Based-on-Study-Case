# Analisis Clustering Berbasis Studi Kasus Sosial-Ekonomi Jawa Timur

Dokumentasi ini merinci implementasi teknis dan alur kerja proyek analisis pengelompokan (clustering) data sosial-ekonomi Kabupaten/Kota di Provinsi Jawa Timur. Proyek ini bertujuan untuk mengidentifikasi pola tersembunyi dan melakukan segmentasi wilayah berdasarkan indikator kesejahteraan, ketenagakerjaan, dan pembangunan manusia.

## Deskripsi Proyek

Analisis ini menggunakan pendekatan komparatif antara berbagai algoritma pengelompokan untuk menentukan segmentasi wilayah yang paling representatif. Data yang digunakan mencakup berbagai dimensi, mulai dari Tingkat Pengangguran Terbuka (TPT), Indeks Pembangunan Manusia (IPM), hingga variabel spesifik terkait kemiskinan dan distribusi pendapatan (Gini Ratio).

## Teknologi dan Pustaka

Proyek ini dibangun menggunakan ekosistem Python untuk data science dengan spesifikasi sebagai berikut:

- **Bahasa Pemrograman**: Python 3.x
- **Pengolahan Data**: Pandas, NumPy
- **Visualisasi Data**: Matplotlib, Seaborn
- **Machine Learning & Statistik**:
  - Scikit-Learn (K-Means, Agglomerative Clustering, PCA)
  - SciPy (Hierarchical Clustering/Dendrogram, Mahalanobis Distance)
  - Gaussian Mixture Models (GMM)
- **Metrik Evaluasi**: Silhouette Score, Calinski-Harabasz Index, Davies-Bouldin Index

## Dataset

Dataset utama disimpan dalam file `Data_AF.xlsx` yang mencakup 23 fitur multidimensi, di antaranya:
- **Ketenagakerjaan**: TPT, TPAK, Rata-rata Upah Formal.
- **Kesejahteraan**: Persentase Pengeluaran Makanan/Bukan Makanan, Gini Rasio.
- **Kesehatan & Sanitasi**: Angka Kesakitan, Pelanggan Air Bersih, Akses Jamban Layak.
- **Pendidikan**: Rata-rata Lama Sekolah, IPM.
- **Ekonomi**: PDRB Harga Konstan, Produksi Padi.

## Tahapan Implementasi

1. **Preprocessing Data**:
   - Pemuatan dataset dari format Excel.
   - Penanganan nilai kosong (Missing Value Handling) menggunakan imputasi mean.
   - Reduksi dimensi dan seleksi fitur dengan menghapus atribut non-numerik (seperti Nama Kabupaten).
   - Standarisasi fitur menggunakan StandardScaler untuk memastikan skala data seragam.

2. **Analisis Eksploratif (EDA)**:
   - Identifikasi outlier menggunakan metode statistik (Mahalanobis Distance).
   - Visualisasi distribusi data.

3. **Pemodelan (Modeling)**:
   - **K-Means Clustering**: Implementasi metode Elbow dan Silhouette untuk menentukan jumlah cluster (k) optimal.
   - **Hierarchical Clustering**: Pembuatan dendrogram untuk visualisasi struktur hierarki antar wilayah.
   - **Gaussian Mixture Models**: Pemodelan berbasis probabilitas untuk menangani distribusi data yang lebih kompleks.

4. **Evaluasi**:
   - Perbandingan performa antar metode menggunakan validasi internal (Silhouette, CH, DB Index).

## Struktur Repositori

```text
├── index.ipynb          # Notebook utama berisi seluruh alur analisis
├── Data_AF.xlsx         # Dataset mentah untuk input analisis
├── Hasil_Clustering.xlsx # Output hasil pengelompokan per wilayah
└── README.md            # Dokumentasi proyek
```

## Cara Menjalankan Proyek

1. Pastikan telah menginstal Python dan Jupyter Notebook/Lab di lingkungan lokal.
2. Instal pustaka yang dibutuhkan melalui terminal:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn scipy openpyxl
   ```
3. Buka file `index.ipynb` menggunakan Jupyter Notebook.
4. Jalankan seluruh cell secara berurutan untuk melihat hasil analisis dan visualisasi.

## Hasil dan Kesimpulan

Hasil clustering memberikan gambaran detail mengenai pengelompokan wilayah di Jawa Timur ke dalam beberapa tingkatan (seperti wilayah maju, wilayah berkembang, dan wilayah yang membutuhkan intervensi khusus). Detail segmentasi wilayah dapat ditemukan pada file `Hasil_Clustering.xlsx` yang dihasilkan di akhir proses eksekusi notebook.

---
**Senior Software Engineer / Data Scientist Approach**
*Implementasi ini menekankan pada akurasi metrik evaluasi dan penanganan data multidimensi secara robust.*
