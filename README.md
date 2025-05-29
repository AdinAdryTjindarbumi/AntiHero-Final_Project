# 📊 Dokumentasi Utama Proyek

## Perbandingan Kinerja Algoritma K-Means dan K-Medoids dengan SMOTE dalam Segmentasi Pelanggan Berbasis Perilaku Transaksi

---

### Deskripsi Singkat Proyek dan Latar Belakang Masalah

Proyek ini bertujuan untuk membandingkan kinerja algoritma clustering K-Means dan K-Medoids dalam segmentasi pelanggan berbasis perilaku transaksi pada data e-commerce menggunakan dataset "E-commerce Behavior Data from Multi-category Store" dari Kaggle. Dalam era digital dengan pertumbuhan pesat industri e-commerce, data perilaku pelanggan yang besar dan beragam memunculkan tantangan dalam memahami pola transaksi seperti melihat produk, menambahkan ke keranjang, dan melakukan pembelian. Segmentasi pelanggan penting untuk strategi pemasaran yang terpersonalisasi, namun data transaksi sering tidak seimbang, dengan interaksi tertentu seperti view yang sangat dominan dibandingkan interaksi lain. Untuk mengatasi hal ini, proyek ini menerapkan teknik SMOTE guna menyeimbangkan distribusi data sebelum melakukan clustering. Evaluasi hasil segmentasi menggunakan Silhouette Score dilakukan untuk menentukan algoritma mana yang lebih efektif dalam menghasilkan klaster pelanggan yang optimal berdasarkan perilaku transaksi.

---

### Penjelasan Dataset

**Jelaskan dataset yang Anda gunakan dalam proyek ini. Informasi yang bisa dimasukkan antara lain:**

- **Sumber Dataset**: Dari mana dataset ini diperoleh? (Contoh: Kaggle, data perusahaan, hasil survei sendiri, dll.)
- **Deskripsi Fitur/Kolom**: Jelaskan arti dari masing-masing kolom atau fitur yang ada dalam dataset.
- **Ukuran Dataset**: Berapa jumlah baris dan kolom?
- **Tipe Data**: Apa saja tipe data yang ada pada setiap fitur (numerik, kategorikal, teks, dll.)?
- **Informasi Tambahan**: Apakah ada hal khusus yang perlu diketahui mengenai dataset ini (misalnya, data yang hilang, ketidakseimbangan kelas, dll.)?

---

### Algoritma yang Digunakan (K-Means dan K-Medoids)

- **Jenis Algoritma**: Apakah ini masalah klasifikasi, regresi, atau clustering?
- **Nama Algoritma**: Sebutkan nama algoritma yang digunakan (Contoh: Logistic Regression, K-Means, Support Vector Machine, Decision Tree, Neural Network, dll.).
- **Alasan Pemilihan**: Mengapa Anda memilih algoritma tersebut untuk menyelesaikan masalah ini? Apa kelebihan algoritma tersebut dalam konteks proyek Anda?
- **Parameter Penting (Opsional)**: Jika ada, sebutkan parameter-parameter kunci dari algoritma yang Anda tuning atau gunakan dengan nilai spesifik.

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

### Contoh Hasil Output dan Visualisasi

**Tampilkan beberapa contoh hasil output yang dihasilkan oleh kode Anda. Ini bisa berupa:**

- **Metrik Evaluasi**: (Contoh: Akurasi, Presisi, Recall, F1-score untuk klasifikasi; MAE, MSE, R-squared untuk regresi; Silhouette Score untuk clustering).
- **Prediksi**: Contoh input dan output prediksi dari model.
- **Visualisasi**: Sertakan gambar atau link ke visualisasi data atau hasil model (Contoh: grafik distribusi data, scatter plot, confusion matrix, learning curve, plot hasil clustering). Anda bisa menyertakan gambar langsung di README atau memberikan path ke file gambar.

**Contoh Teks Output:**
