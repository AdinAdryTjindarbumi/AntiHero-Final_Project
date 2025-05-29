# 📊 Perbandingan Kinerja Algoritma K-Means dan K-Medoids dengan SMOTE dalam Segmentasi Pelanggan Berbasis Perilaku Transaksi

---

### Deskripsi Singkat Proyek dan Latar Belakang Masalah

Proyek ini bertujuan untuk membandingkan kinerja algoritma clustering K-Means dan K-Medoids dalam segmentasi pelanggan berbasis perilaku transaksi pada data e-commerce menggunakan dataset "E-commerce Behavior Data from Multi-category Store" dari Kaggle. 

Dalam era digital dengan pertumbuhan pesat industri e-commerce, data perilaku pelanggan yang besar dan beragam memunculkan tantangan dalam memahami pola transaksi seperti melihat produk, menambahkan ke keranjang, dan melakukan pembelian. Segmentasi pelanggan penting untuk strategi pemasaran yang terpersonalisasi, namun data transaksi sering tidak seimbang, dengan interaksi tertentu seperti view yang sangat dominan dibandingkan interaksi lain. Untuk mengatasi hal ini, proyek ini menerapkan teknik SMOTE guna menyeimbangkan distribusi data sebelum melakukan clustering. Evaluasi hasil segmentasi menggunakan Silhouette Score dilakukan untuk menentukan algoritma mana yang lebih efektif dalam menghasilkan klaster pelanggan yang optimal berdasarkan perilaku transaksi.

---

### Dataset

Dataset yang digunakan dalam proyek ini adalah "E-commerce Behavior Data from Multi-category Store" yang diperoleh dari platform Kaggle. Dataset ini berisi lebih dari 4 juta interaksi pengguna di platform e-commerce multi kategori selama bulan Oktober 2019. Setiap baris data mewakili satu interaksi pelanggan, seperti melihat produk, menambahkan ke keranjang, atau melakukan pembelian.

Tautan : https://www.kaggle.com/datasets/mkechinov/ecommerce-behavior-data-from-multi-category-store. 

**Deskripsi Fitur Dataset:**
| Fitur            | Deskripsi                                                                 | Tipe Data   |
|------------------|---------------------------------------------------------------------------|-------------|
| `event_time`     | Waktu interaksi dalam format UTC                                          | datetime    |
| `event_type`     | Jenis interaksi: view, cart, remove_from_cart, purchase                   | string      |
| `product_id`     | ID unik untuk produk                                                      | integer     |
| `category_id`    | ID kategori produk                                                        | float       |
| `category_code`  | Kode hierarki kategori, seperti electronics.smartphone                   | string      |
| `brand`          | Nama merek produk                                                         | string      |
| `price`          | Harga produk dalam USD                                                    | float       |
| `user_id`        | ID unik pengguna                                                          | integer     |
| `user_session`   | ID sesi unik pengguna saat berinteraksi                                   | string      |


**Ukuran Dataset**
Dataset ini terdiri dari 4.2448.764 baris dengan 9 kolom.
Dataset ini berukuran 5.67GB. Pastikan anda memiliki ruang penyimpanan yang cukup.

**Informasi Tambahan**
- Dataset ini bersifat real-world sehingga mengandung missing values, outlier, dan distribusi yang tidak seimbang.
- Terdapat ketimpangan jumlah interaksi, di mana jenis view sangat dominan dibandingkan purchase.

---

### Algoritma yang Digunakan (K-Means dan K-Medoids)

Proyek ini menggunakan pendekatan unsupervised learning dengan metode clustering untuk melakukan segmentasi pelanggan berdasarkan perilaku transaksi mereka. Dalam proyek ini menggunakan algoritma K-Means dan K-Medoid

**1. K-Means**

K-Means adalah algoritma clustering yang membagi data ke dalam k kelompok berdasarkan kedekatan data terhadap pusat klaster (centroid). Algoritma ini dipilih karena sederhana, cepat, dan efisien untuk dataset berskala besar, sehingga algoritma ini cocok untuk digunakan dalam eksplorasi segmentasi pelanggan.

**Parameter kunci :**
- n_clusters: jumlah klaster yang ingin dibuat (dicoba dalam rentang 2–10).
- init: metode inisialisasi centroid awal ('k-means++' digunakan untuk hasil yang lebih stabil).
- n_init: jumlah inisialisasi ulang (default: 10).
- max_iter: jumlah iterasi maksimum (default: 300).
- random_state: untuk memastikan hasil yang konsisten.
  
**2. K-Medoid**

K-Medoids adalah varian dari K-Means yang lebih tahan terhadap outlier karena pusat klasternya adalah titik data aktual (medoid), bukan rata-rata. Algoritma ini dipilih karena lebih robust terhadap outlier dan noise dibandingkan K-Means.

**Parameter Kunci:**

- n_clusters: jumlah klaster yang ingin dibentuk.
- init: metode pemilihan medoid awal ('k-medoids++').
- metric: metode pengukuran jarak ('euclidean' digunakan).
- max_iter: batas maksimum iterasi pertukaran medoid.

**3. Penyeimbangan Data: SMOTE**

SMOTE (Synthetic Minority Over-sampling Technique) digunakan untuk mengatasi distribusi data yang tidak seimbang, terutama ketika interaksi seperti view jauh lebih dominan dibandingkan purchase. Metode ini digunakan untuk membantu algoritma clustering agar tidak bias terhadap kelas mayoritas serta eningkatkan representasi segmen pelanggan minoritas (misalnya pembeli aktif).

**Parameter Kunci SMOTE:**

- sampling_strategy: proporsi kelas minoritas yang akan dibuat ('auto' digunakan).
- k_neighbors: jumlah tetangga terdekat (default: 5).
- random_state: untuk reproducibility hasil.

**4. Evaluasi: Silhouette Score**

Silhouette Score digunakan untuk mengevaluasi kualitas hasil clustering. Skor ini mengukur seberapa dekat setiap titik ke klasternya sendiri dibandingkan dengan klaster terdekat lainnya.

**Interpretasi Nilai Silhouette Score:**
- Nilai mendekati 1: Klaster sangat baik dan terpisah jelas.
- Nilai mendekati 0: Klaster tumpang tindih.
- Nilai negatif: Data mungkin salah klaster.
  
---

### Panduan Menjalankan Kode

**Berikan instruksi langkah demi langkah bagaimana cara menjalankan kode atau proyek ini.**

**Prasyarat Software dan Library**:

1. Python 3.x (disarankan versi terbaru yang kompatibel dengan library yang digunakan)
2. Library Python yang diperlukan:
    -  pandas (untuk manipulasi data)
    -  numpy (untuk komputasi numerik)
    -  scikit-learn (untuk algoritma K-Means, evaluasi Silhouette Score, dan preprocessing)
    -  imbalanced-learn (untuk SMOTE)
    -  matplotlib dan seaborn (untuk visualisasi)
    -  scipy (untuk perhitungan statistik dan distance metric)
    -  scikit-medoids (atau library lain yang menyediakan K-Medoids, jika digunakan)

**Instalasi Dependensi**

Jika tersedia file requirements.txt, jalankan perintah berikut di terminal atau command prompt:

``
pip install -r requirements.txt
``

Jika tidak ada file requirements.txt, Anda dapat menginstal library secara manual dengan perintah berikut:

``
pip install pandas numpy scikit-learn imbalanced-learn matplotlib seaborn scipy scikit-medoids
``

**Struktur Folder (Opsional)**:
- Jika relevan, jelaskan struktur direktori proyek.
  
**Langkah-langkah Eksekusi**:

1. Clone repositori ini ke komputer Anda atau unduh seluruh file proyek.

2. Persiapkan dataset "E-commerce Behavior Data from Multi-category Store" periode Oktober 2019 dari Kaggle, kemudian simpan file dataset tersebut ke dalam folder data/.

3. Buka file notebook Jupyter atau skrip Python yang berisi proses preprocessing, SMOTE, clustering, dan evaluasi yang biasanya terdapat di folder notebooks/ atau src/.

4. Lakukan preprocessing data, meliputi:
Pembersihan data (penanganan missing values, filtering event_type, validasi tanggal dan harga).
Deteksi dan penanganan outlier.
Feature engineering (menghitung jumlah interaksi per pengguna, analisis RFM, perhitungan metrik perilaku seperti Conversion Rate dan Engagement Score).
Transformasi data (log transformation pada fitur skewed, normalisasi Min-Max untuk K-Medoids, dan standardisasi Z-Score untuk K-Means).

5. Terapkan teknik SMOTE untuk menyeimbangkan distribusi data interaksi pelanggan, khususnya untuk mengatasi dominasi interaksi jenis view, dengan parameter seperti:
    -    sampling_strategy='auto'
    -    k_neighbors=5
    -    random_state=42

6. Jalankan algoritma clustering:
    -    K-Means dengan variasi jumlah cluster dari 2 hingga 10, menggunakan parameter seperti init='k-means++', ninit=10, maxiter=300, dan random_state=42.
    -    K-Medoids menggunakan metode PAM dengan parameter serupa (jumlah cluster bervariasi, metric='euclidean', init='k-medoids++').

7. Lakukan clustering pada dua kondisi data: data asli (tanpa SMOTE) dan data hasil augmentasi SMOTE.

8. Evaluasi hasil clustering menggunakan Silhouette Score untuk setiap nilai k, serta analisis performa seperti waktu komputasi dan penggunaan memori.

9. Visualisasikan hasil clustering menggunakan grafik scatter plot, histogram, box plot, dan visualisasi lain sesuai kebutuhan.

10. Analisis klaster yang terbentuk berdasarkan karakteristik perilaku pengguna dan interpretasi hasil segmentasi.

11. Buat laporan akhir yang mencakup kesimpulan, rekomendasi model terbaik, jumlah cluster optimal, serta panduan implementasi praktis.

**Konfigurasi (Opsional)**

    -    Sesuaikan path dataset di dalam kode agar sesuai dengan lokasi penyimpanan dataset lokal Anda.
    -    Atur parameter SMOTE seperti samplingstrategy, kneighbors, dan random_state untuk reproducibility dan efektivitas oversampling.
    -    Sesuaikan jumlah cluster (nclusters) dan parameter algoritma clustering (misalnya init, maxiter) sesuai kebutuhan eksperimen.
    -    Pastikan kernel Python dan semua dependensi telah terpasang dengan benar jika menggunakan notebook Jupyter.

---

### Hasil Output dan Visualisasi
Berikut ini hasil visualisasi dari implementasi Algoritma K-Means dan K-Medoids pada data original maupun data setelah diterapkan SMOTE

![output](https://github.com/user-attachments/assets/87166f60-90ac-470d-87ba-a2756164ddd9)

![image](https://github.com/user-attachments/assets/99c5f5f4-91f8-44c5-9f71-eb202bcfc72e)


Berdasarkan hasil evaluasi SIlhouette Score menunjukkan algoritma K-Medoids memberikan hasil yang lebih baik dibandingkan dengan K-Means di semua data, baik data original maupun data setelah SMOTE. Penerapan SMOTE berhasil menyeimbangkan distribusi kelas, namun tidak selalu meningkatkan nilai Silhouette Score secara signifikan, sehingga perlu evaluasi lebih lanjut dalam konteks segmentasi pelanggan.


**Contoh Teks Output:**
