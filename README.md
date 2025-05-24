<div align="center"> 

# Analisis Klasifikasi Daerah Indonesia Berdasarkan Anggaran Negara dan Indikator Sosial Ekonomi untuk Pemetaan kesejahteraan Masyarakarat

![image](https://github.com/user-attachments/assets/402fbd88-ef97-4a44-a675-9b83ce6f2c4e)


</div>

## 📖 Daftar Isi

- [Pendahuluan](#pendahuluan)
- [Tujuan Penelitian](#tujuan-penelitian)
- [Metode Penelitian](#metode-penelitian)
- [Data dan Sumber Data](#data-dan-sumber-data)
- [Langkah Analisis](#langkah-analisis)
- [Visualisasi](#visualisasi)
- [Hasil dan Interpretasi](#hasil-dan-interpretasi)
- [Kesimpulan](#kesimpulan)
- [Referensi](#referensi)


## 📝 Pendahuluan

<div align="justify">
   
Pemerintah Indonesia menargetkan tercapainya masyarakat yang sejahtera, adil, dan merata melalui Rencana Pembangunan Jangka Menengah Nasional (RPJMN) 2025–2029 dalam rangka mewujudkan Visi Indonesia Emas 2045. Namun, capaian kesejahteraan masyarakat yang diukur melalui Indeks Pembangunan Manusia (IPM) masih menunjukkan ketimpangan antardaerah, di mana wilayah seperti Yogyakarta mencatat IPM sangat tinggi, sementara daerah seperti Kabupaten Nduga sangat rendah (BPS, 2024; World Bank, 2020).

Ketimpangan ini tidak selalu berkorelasi dengan besarnya anggaran yang dialokasikan, tetapi lebih terkait dengan efektivitas tata kelola dan pemanfaatan anggaran. Oleh karena itu, penelitian ini bertujuan untuk memetakan tingkat kesejahteraan wilayah kabupaten/kota di Indonesia menggunakan pendekatan machine learning, khususnya algoritma XGBoost, berdasarkan indikator sosial ekonomi seperti IPM, pengeluaran per kapita, akses air layak, PDRB, dan lainnya.

Hasil klasifikasi diharapkan dapat mengidentifikasi daerah yang efektif dalam memanfaatkan anggaran serta memberikan rekomendasi intervensi kebijakan yang lebih tepat sasaran untuk mendukung pembangunan berkelanjutan menuju Indonesia Emas 2045.

## 🎯 Tujuan Penelitian

- Membangun model klasifikasi daerah berdasarkan tingkat kesejahteraan menggunakan berbagai metode machine learning.
- Mengevaluasi performa model machine learning dalam mengklasifikasikan kesejahteraan daerah untuk menentukan metode yang paling efektif.
- Memberikan rekomendasi kebijakan berbasis data untuk membantu pemerintah dalam penyusunan prioritas pembangunan dan distribusi anggaran.

## 📝 Metode Penelitian

Metode penelitian yang digunakan adalah sebagai berikut:

1. **XGBoost**  
   Teknik ensembel boosting berbasis pohon keputusan yang dikenal efisien dan memiliki performa tinggi dalam tugas klasifikasi, terutama untuk data yang tidak seimbang.

2. **Support Vector Machine (SVM)**  
   Algoritma klasifikasi yang bekerja dengan mencari hyperplane terbaik untuk memisahkan kelas data. Cocok untuk data berdimensi tinggi namun sensitif terhadap ketidakseimbangan kelas.

3. **Naive Bayes**  
   Model klasifikasi berbasis probabilistik yang mengasumsikan independensi antar fitur. Meskipun sederhana dan cepat, performanya dapat menurun pada data kompleks atau tidak seimbang.

4. **Regresi Logistik**  
   Model statistik klasik untuk klasifikasi biner atau multikelas yang mengestimasi probabilitas berdasarkan fungsi logistik. Umumnya kurang optimal pada data multikelas yang tidak seimbang.


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

## ⭐ Visualisasi

### 1. Distribusi IPM 2024

![image](https://github.com/user-attachments/assets/8a5d0e38-105c-45f4-bc88-c9a6b7d61b66)

Histogram di atas menunjukkan sebaran nilai Indeks Pembangunan Manusia (IPM) pada tahun 2024. Sebagian besar wilayah berada pada kisaran IPM antara 65–75, dengan distribusi condong ke kanan, mengindikasikan masih adanya daerah dengan IPM rendah.

---

### 2. Korelasi Antar Fitur Numerik

![image](https://github.com/user-attachments/assets/314741cd-e370-46da-9ed4-f433a45ad937)

Visualisasi heatmap memperlihatkan korelasi antar fitur numerik. Terlihat bahwa variabel seperti **PPK (Pengeluaran Per Kapita)** dan **Bekerja_Formal** memiliki korelasi positif tinggi dengan IPM, sedangkan **PPM (Persentase Penduduk Miskin)** dan **Bekerja_Informal** berkorelasi negatif. Pola ini menegaskan pentingnya indikator ekonomi dan pekerjaan terhadap kesejahteraan wilayah.



## 📊 Hasil dan Interpretasi

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

#### Feature Importance - XGBoost

<div align="center">

![image](https://github.com/user-attachments/assets/f4bb3b7b-8df7-40e3-a966-04e43d75bc60)

</div>

Gambar di atas menunjukkan bahwa variabel **PPK (Pengeluaran Per Kapita)**, **Akses Air Layak**, dan **Anggaran** merupakan faktor paling berpengaruh dalam menentukan klasifikasi tingkat kesejahteraan wilayah. Hal ini menegaskan pentingnya indikator ekonomi dan akses kebutuhan dasar dalam analisis pembangunan daerah.


## ✅ Kesimpulan Utama

- Model XGBoost terbukti paling efektif dalam klasifikasi tingkat kesejahteraan wilayah berdasarkan IPM, dengan akurasi 88% dan macro F1-score 0.87.
- Variabel paling berpengaruh adalah Pengeluaran Per Kapita (PPK), pekerja informal, dan Indeks Pembangunan Gender (IPG).
- Alokasi anggaran daerah memiliki pengaruh relatif rendah terhadap klasifikasi IPM.
- Rekomendasi kebijakan sebaiknya berfokus pada intervensi kualitas, pengurangan dominasi pekerja informal, dan penguatan kesetaraan gender.
- Pemanfaatan XGBoost dapat mendukung evaluasi pembangunan yang berbasis data dan adaptif terhadap kondisi lokal.



</div>

## 📚 Referensi

- Bappenas. (2024). *Rencana Pembangunan Jangka Menengah Nasional (RPJMN) 2025–2029*. Jakarta: Kementerian PPN/Bappenas.
- Badan Pusat Statistik (BPS). (2024). *Indeks Pembangunan Manusia Indonesia 2023 & 2024*. [https://bps.go.id](https://bps.go.id)
- World Bank. (2020). *Indonesia Public Expenditure Review: Spending for Better Results*. Washington, DC.

</div>








