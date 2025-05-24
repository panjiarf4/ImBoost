<div align="center"> 

# Analisis Klasifikasi Daerah Indonesia Berdasarkan Anggaran Negara dan Indikator Sosial Ekonomi untuk Pemetaan kesejahteraan Masyarakarat

![image](https://github.com/user-attachments/assets/402fbd88-ef97-4a44-a675-9b83ce6f2c4e)


</div>

## 📖 Daftar Isi
<a href="#pendahuluan">Pendahuluan</a><br>
<a href="#tujuan-penelitian">Tujuan Penelitian</a><br>
<a href="#metode-penelitian">Metode Penelitian</a><br>
<a href="#sumber-data">Sumber Data</a><br>
<a href="#langkah-analisis">Langkah Analisis</a><br>
<a href="#visualisasi">Visualisasi</a><br>
<a href="#hasil-dan-interpretasi">Hasil dan Interpretasi</a><br>
<a href="#kesimpulan">Kesimpulan</a><br>
<a href="#referensi">Referensi</a>

## 📝 Pendahuluan

<div align="justify">
Kesejahteraan masyarakat Indonesia merupakan tujuan pembangunan nasional Indonesia sebagaimana tertuang dalam Rencana Pembangunan Jangka Menengah Nasioanal (RPJMN) 2025-2029 sebagai langkah strategis untuk mewujudkan visi Indonesia emas 2045. Pemerintah Indonesia menargetkan pada tahun 2024, Indonesia tidak hanya menjadi negara berpendapatan tinggi, tetapi juga memiliki masyarakat yang sejatera, adil, dan merata dalam pembangunan ekonomi nasional (Bappenas, 2024)

## 👨‍💻 Tujuan Penelitian 
- Membangun model klasifikasi daerah berdasarkan tingkat kesejahteraan menggunakan berbagai metode machine learning.
  
- Mengevaluasi performa model machine learning dalam mengklasifikasikan kesejahteraan daerah untuk menentukan metode yang paling efektif.
  
- Memberikan rekomendasi kebijakan berbasis data untuk membantu pemerintah dalam penyusunan prioritas pembangunan dan distribusi anggaran.
</div>

## ✏️ Metode Penelitian
Metode penelitian yang digunakan adalah sebagai beikut:

**1. XGBoost**: Teknik ensembel boosting pohon keputusan yang dikenal efisien dan memiliki performa tinggi pada tugas klasifikasi.


</div>

## 🗂️ Data dan Sumber Data

<div align="center">

| No. | Variabel | Deskripsi |
|-----|----------|-----------|
| 1.  | **KAB_KOTA** | Nama Kabupaten atau Kota di seluruh Indonesia. |
| 2.  | **IPM** (*Indeks Pembangunan Manusia*) | Mengukur kualitas hidup berdasarkan umur panjang, kesehatan, pendidikan, dan standar hidup layak. |
| 3.  | **Anggaran** | Jumlah alokasi anggaran (kemungkinan dari APBD/APBN) dalam satuan rupiah. |
| 4.  | **IPG** (*Indeks Pembangunan Gender*) | Menggambarkan kesetaraan gender dalam pembangunan manusia. |
| 5.  | **PKKP** (*Prevalensi Ketidakcukupan Konsumsi Pangan*) | Persentase penduduk yang mengonsumsi pangan kurang dari kebutuhan minimal. |
| 6.  | **PPM** (*Persentase Penduduk Miskin*) | Penduduk dengan pendapatan di bawah garis kemiskinan. |
| 7.  | **PPK** (*Pengeluaran Per Kapita*) | Jumlah pengeluaran rata-rata individu. |
| 8.  | **Air Layak** | Persentase rumah tangga yang mengakses air minum layak. |
| 9.  | **IKK** (*Indeks Kemahalan Konstruksi*) | Nilai tambah barang/jasa dari konstruksi di suatu wilayah. |
| 10. | **PDRB** (*Produk Domestik Regional Bruto*) | Nilai tambah barang dan jasa yang dihasilkan di suatu daerah. |

</div>

📌 **Sumber Data:**
- [Satu Data Indonesia](https://satudata.go.id)
- [Badan Pusat Statistik (BPS)](https://www.bps.go.id)


## 🔍 Langkah Analisis

- **Pengumpulan Data:** Kumpulkan data sekunder IPM kabupaten/kota beserta variabel pendukung (alokasi anggaran, PDRB, pengeluaran per kapita, kemiskinan, akses air bersih, dll.) dari sumber resmi seperti BPS.
- **Pra-pemrosesan:** Bersihkan data (atasi nilai hilang dan outlier), lakukan transformasi skala (normalisasi/standarisasi), dan encoding variabel kategorikal.
- **Penentuan Label Target:** Ubah nilai IPM menjadi kelas (rendah, sedang, tinggi, sangat tinggi) berdasarkan klasifikasi BPS.
- **Pembagian Data:** Split data menjadi data latih dan uji (misalnya dengan validasi silang k-fold, contoh: 90% latih, 10% uji).
- **Pelatihan Model (XGBoost):** Bangun model klasifikasi menggunakan XGBoost multiclass. Lakukan tuning hyperparameter menggunakan validasi silang.
- **Evaluasi Model:** Hitung akurasi, precision, recall, dan F1-score berdasarkan data uji.
- **Interpretasi & Rekomendasi:** Gunakan feature importance untuk mengidentifikasi variabel kunci, serta rumuskan rekomendasi kebijakan berbasis data.

## 📊 Hasil dan Pembahasan

Model **XGBoost** menunjukkan performa terbaik dengan akurasi 88% dan macro F1-score sebesar 0.87, serta mampu mengklasifikasikan kelas mayoritas dan minoritas secara seimbang. Model ini sangat andal dalam mendeteksi kategori *Kesejahteraan Sedang* (kelas 1) dengan recall 0.99 dan F1-score tinggi pada semua kelas.

Sebaliknya, **SVM** dan **Naive Bayes** menunjukkan kecenderungan bias terhadap kelas mayoritas. Meskipun recall kelas Sedang cukup tinggi, performa pada kelas *Rendah* dan *Tinggi* jauh lebih rendah, menghasilkan macro F1-score hanya sebesar 0.44.

Model **Regresi Logistik** memiliki akurasi dan F1-score terendah (masing-masing 60% dan 0.34), menunjukkan bahwa model ini tidak cocok untuk data ketidakseimbangan kelas seperti pada klasifikasi kesejahteraan wilayah.

#### Tabel Perbandingan antar Model

<div align="center">

| **Model**            | **Akurasi** | **Macro F1** | **Keterangan**                                    |
|----------------------|-------------|--------------|--------------------------------------------------|
| XGBoost              | 0.88        | 0.87         | Performa terbaik dan seimbang antar kelas.       |
| SVM                  | 0.70        | 0.44         | Bias terhadap kelas mayoritas.                   |
| Naive Bayes          | 0.69        | 0.44         | Rentan terhadap kelas minoritas.                 |
| Regresi Logistik     | 0.60        | 0.34         | Tidak cocok untuk data tidak seimbang.           |

</div>

Berdasarkan hasil perbandingan, dapat disimpulkan bahwa **XGBoost** merupakan algoritma yang paling efektif dalam memodelkan klasifikasi tingkat kesejahteraan wilayah berbasis indikator sosial ekonomi. Keunggulan utamanya terletak pada kemampuannya menangani **kompleksitas antar variabel**, **ketidakseimbangan distribusi data**, serta menghasilkan prediksi **multikelas yang presisi dan stabil**.

## ⭕ Kesimpulan
</div>

## 📚 Referensi
</div>








