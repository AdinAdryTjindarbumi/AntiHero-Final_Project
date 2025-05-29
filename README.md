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
1. [Langkah pertama, contoh: Clone repositori ini.]
2. [Langkah kedua, contoh: Buka file nama_notebook.ipynb menggunakan Jupyter Notebook.]
3. [Langkah ketiga, contoh: Jalankan semua sel kode secara berurutan.]
4. [Langkah selanjutnya, jika ada.]

**Konfigurasi (Opsional)**:
- Apakah ada file konfigurasi yang perlu disesuaikan sebelum menjalankan kode?

---

### Contoh Hasil Output dan Visualisasi

**Tampilkan beberapa contoh hasil output yang dihasilkan oleh kode Anda. Ini bisa berupa:**

- **Metrik Evaluasi**: (Contoh: Akurasi, Presisi, Recall, F1-score untuk klasifikasi; MAE, MSE, R-squared untuk regresi; Silhouette Score untuk clustering).
- **Prediksi**: Contoh input dan output prediksi dari model.
- **Visualisasi**: Sertakan gambar atau link ke visualisasi data atau hasil model (Contoh: grafik distribusi data, scatter plot, confusion matrix, learning curve, plot hasil clustering). Anda bisa menyertakan gambar langsung di README atau memberikan path ke file gambar.

**Contoh Teks Output:**
