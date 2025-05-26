<div align="center"> 

# Analisis Klasifikasi Daerah Indonesia Berdasarkan Anggaran Negara dan Indikator Ekonomi Sosial untuk Pemetaan Kesejahteraan Masyarakarat

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

Data dan Variabel yang digunakan dalam penelitian ini sebagai berikut.
<div align="center">

| No. | Variabel           | Deskripsi                                                                 |
|-----|--------------------|---------------------------------------------------------------------------|
| 1.  | **KAB_KOTA**        | Nama Kabupaten atau Kota di seluruh Indonesia.                           |
| 2.  | **IPM** (*Indeks Pembangunan Manusia*) | Indeks komposit yang mengukur kualitas hidup berdasarkan umur panjang, kesehatan, pendidikan, dan standar hidup layak. |
| 3.  | **Anggaran**        | Jumlah alokasi anggaran daerah (APBD/APBN) dalam satuan rupiah.          |
| 4.  | **IPG** (*Indeks Pembangunan Gender*) | Menggambarkan tingkat kesetaraan gender dalam pencapaian pembangunan manusia. |
| 5.  | **PKKP** (*Prevalensi Ketidakcukupan Konsumsi Pangan*) | Persentase penduduk yang mengonsumsi pangan kurang dari kebutuhan minimum. |
| 6.  | **PPM** (*Persentase Penduduk Miskin*) | Persentase penduduk yang hidup di bawah garis kemiskinan nasional.           |
| 7.  | **PPK** (*Pengeluaran Per Kapita*) | Jumlah rata-rata pengeluaran individu dalam rumah tangga per tahun.         |
| 8.  | **PPK_Makanan**     | Komponen pengeluaran per kapita khusus untuk konsumsi makanan.           |
| 9.  | **Air_Layak**       | Persentase rumah tangga yang memiliki akses terhadap air minum layak.     |
| 10. | **IKK** (*Indeks Kemahalan Konstruksi*) | Indeks harga barang dan jasa konstruksi di suatu wilayah.                    |
| 11. | **PDRB** (*Produk Domestik Regional Bruto*) | Nilai tambah seluruh barang dan jasa yang dihasilkan di suatu daerah.        |
| 12. | **IKKe** (*Indeks Kemahalan Konsumsi*) | Indeks harga konsumsi barang dan jasa yang dibutuhkan masyarakat.            |
| 13. | **Bekerja_Informal** | Persentase penduduk usia kerja yang bekerja di sektor informal.           |
| 14. | **Bekerja_Formal**   | Persentase penduduk usia kerja yang bekerja di sektor formal.             |

</div>

📌 **Sumber Data:**
- [Satu Data Indonesia](https://satudata.go.id)
- [Badan Pusat Statistik (BPS)](https://www.bps.go.id)

![Blank diagram](https://github.com/user-attachments/assets/cbaf8017-124a-4e75-8315-1592993dad4e)

Proses ini dimulai dari pengumpulan data sosial-ekonomi dari BPS dan Satu Data Indonesia, lalu dilanjutkan dengan pembersihan dan eksplorasi data. Selanjutnya, dilakukan pemodelan menggunakan algoritma XGBoost untuk mengklasifikasikan wilayah berdasarkan tingkat IPM: rendah, sedang, dan tinggi, serta mengevaluasi pengaruh variabel lain seperti pengeluaran per kapita, kemiskinan, dan anggaran.

Hasilnya menunjukkan bahwa kesejahteraan lebih dipengaruhi oleh kualitas hidup masyarakat seperti daya beli dan kesetaraan gender bukan sekadar besar anggaran. Dari sini, analisis ini memberi manfaat konkret.

Bagi masyarakat, hasil ini membantu mengarahkan program seperti bantuan sosial dan sanitasi ke daerah yang benar-benar membutuhkan. Sementara bagi lembaga pemerintah seperti Bappenas, Kemensos, dan pemerintah daerah, analisis ini menjadi dasar perencanaan kebijakan yang lebih tepat sasaran dan berbasis data.

## 🔍 Langkah Analisis

#### 1. Pengumpulan Data
- Data sekunder dikumpulkan dari sumber resmi:
  - **BPS (Badan Pusat Statistik)**
  - **Portal Satu Data Indonesia**
- Variabel yang digunakan meliputi:
  - IPM, alokasi anggaran, PDRB per kapita, pengeluaran per kapita (PPK), tingkat kemiskinan (PPM), akses air bersih, IPG, IKK, dll.

#### 2. Pra-Pemrosesan Data
- Tangani *missing values* dan *outlier*
- Lakukan normalisasi atau transformasi log untuk fitur numerik
- Encode variabel kategorikal
- Dataset siap digunakan untuk pelatihan model

#### 3. Penentuan Label Target
- IPM dikategorikan sesuai standar BPS:
  - Rendah: `< 60`
  - Sedang: `60 – <70`
  - Tinggi: `70 – <80`
  - Sangat tinggi: `≥ 80`

#### 4. Pembagian Data
- Data dibagi menggunakan validasi silang:
  - **10-fold cross-validation**
  - Rasio: 90% data latih, 10% data uji

#### 5. Pelatihan Model

##### a. XGBoost
- Objective: `multi:softprob` (multiclass)
- Tuning:
  - `n_estimators`, `max_depth`, `learning_rate`, `reg_alpha`, `reg_lambda`
- Teknik: Grid Search + Cross-Validation

##### b. SVM
- Kernel: RBF
- Tuning parameter: `C`, `gamma`
- Skema klasifikasi: One-vs-Rest (OvR)

##### c. Naive Bayes
- Model: Gaussian Naive Bayes
- Asumsi: Distribusi normal antar fitur numerik

##### d. Regresi Logistik
- Pendekatan: Multiclass (Softmax)
- Regularisasi: `L2` (ridge)
- Optimasi loss: `categorical_crossentropy`

#### 6. Evaluasi Model
- Metrik evaluasi:
  - **Akurasi**
  - **Precision**, **Recall**, **F1-score per kelas**
  - **Confusion matrix**
- Evaluasi dilakukan pada data latih dan validasi untuk mendeteksi overfitting

#### 7. Interpretasi & Rekomendasi Kebijakan
- Analisis **feature importance** dari model terbaik (XGBoost)
- Identifikasi variabel paling berpengaruh terhadap klasifikasi IPM
- Hasil digunakan sebagai dasar penyusunan:
  - **Intervensi daerah**
  - **Distribusi bantuan sosial**
  - **Kebijakan pembangunan berbasis data**


## 🌟 Eksplorasi Dataset

### 1. Distribusi IPM 2024

<p align="center">
  <img src="https://github.com/user-attachments/assets/8a5d0e38-105c-45f4-bc88-c9a6b7d61b66" alt="Distribusi IPM" width="600"/>
</p>

Histogram di atas menunjukkan sebaran nilai Indeks Pembangunan Manusia (IPM) pada tahun 2024. Sebagian besar wilayah berada dalam kisaran IPM antara 65–75, dengan distribusi condong ke kanan, mengindikasikan masih adanya daerah dengan IPM rendah.

----

### 2. Korelasi Antar Fitur Numerik

<p align="center">
  <img src="https://github.com/user-attachments/assets/314741cd-e370-46da-9ed4-f433a45ad937" alt="Heatmap Korelasi" width="600"/>
</p>

Visualisasi heatmap memperlihatkan korelasi antar fitur numerik. Terlihat bahwa variabel seperti **PPK** dan **Bekerja_Formal** memiliki korelasi positif tinggi dengan IPM, sedangkan **PPM** (*Persentase Penduduk Miskin*) dan **Bekerja_Informal** berkorelasi negatif. Pola ini menegaskan pentingnya indikator ekonomi dan pekerjaan formal dalam meningkatkan kesejahteraan wilayah.




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

#### Feature Importance - XGBoost

<div align="center">

![image](https://github.com/user-attachments/assets/f4bb3b7b-8df7-40e3-a966-04e43d75bc60)

</div>

Gambar di atas menunjukkan bahwa variabel **PPK (Pengeluaran Per Kapita)**, **Akses Air Layak**, dan **Anggaran** merupakan faktor paling berpengaruh dalam menentukan klasifikasi tingkat kesejahteraan wilayah. Hal ini menegaskan pentingnya indikator ekonomi dan akses kebutuhan dasar dalam analisis pembangunan daerah.

#### Pemetaan Kesejahteraan Masyarakat

<p align="center">
  <img src="https://github.com/user-attachments/assets/cce4e6b2-4d45-4ba2-aa69-e13d6fbdf88a" alt="Peta Kesejahteraan Masyarakat" width="750"/>
</p>

Peta di atas menunjukkan hasil klasifikasi kesejahteraan masyarakat di seluruh kabupaten/kota Indonesia berdasarkan model XGBoost. Warna hijau muda merepresentasikan daerah dengan tingkat kesejahteraan **rendah**, hijau sedang untuk **sedang**, dan abu-abu untuk **tinggi**.

Sebagian besar wilayah di Indonesia tergolong dalam kategori kesejahteraan **rendah**, terutama di kawasan Indonesia Tengah dan Timur. Sementara itu, beberapa kabupaten/kota di Papua dan Maluku menunjukkan kemajuan signifikan dengan masuk dalam kategori **sedang**, meskipun masih terdapat tantangan besar dalam pemerataan pembangunan.

Pemetaan ini berguna untuk mengidentifikasi daerah yang memerlukan prioritas intervensi kebijakan berbasis data, serta sebagai alat bantu visual bagi pengambilan keputusan pemerintah dalam merumuskan strategi pembangunan yang lebih terarah.



## ✅ Kesimpulan Utama

- Model XGBoost terbukti paling efektif dalam klasifikasi tingkat kesejahteraan wilayah berdasarkan IPM, dengan akurasi 88% dan macro F1-score 0.87.
- Variabel paling berpengaruh adalah Pengeluaran Per Kapita (PPK), pekerja informal, dan Indeks Pembangunan Gender (IPG).
- Alokasi anggaran daerah memiliki pengaruh relatif rendah terhadap klasifikasi IPM.
-  Pemerintah sebaiknya fokus pada kualitas intervensi, peningkatan daya beli, pengurangan pekerja informal, dan penguatan kesetaraan gender.
- Pemanfaatan XGBoost dapat membantu mendeteksi wilayah prioritas dan menyusun kebijakan berbasis data yang adaptif dan tepat sasaran.



</div>

## 📚 Referensi

- Bappenas. (2024). *Rencana Pembangunan Jangka Menengah Nasional (RPJMN) 2025–2029*. Jakarta: Kementerian PPN/Bappenas.
- Badan Pusat Statistik (BPS). (2024). *Indeks Pembangunan Manusia Indonesia 2023 & 2024*. [https://bps.go.id](https://bps.go.id)
- World Bank. (2020). *Indonesia Public Expenditure Review: Spending for Better Results*. Washington, DC.
- Avendaño-Valencia, L. D., & Fassois, S. D. (2015). Natural vibration response based damage detection for an operating wind turbine via Random Coefficient Linear Parameter Varying AR modelling. Journal of Physics: Conference Series, 628(1), 273–297. https://doi.org/10.1088/1742-6596/628/1/012073
- Chen, T., & Guestrin, C. (2016). XGBoost: A scalable tree boosting system. Proceedings of the ACM SIGKDD International Conference on Knowledge Discovery and Data Mining, 13-17-Augu, 785–794. https://doi.org/10.1145/2939672.2939785
- Hu, T., & Song, T. (2019). Research on XGboost academic forecasting and analysis modelling. Journal of Physics: Conference Series, 1324(1). https://doi.org/10.1088/1742-6596/1324/1/012091
- Sun, Y., Wong, A. K. C., & Kamel, M. S. (2009). Classification of imbalanced data: A review. International Journal of Pattern Recognition and Artificial Intelligence, 23(4), 687–719. https://doi.org/10.1142/S0218001409007326
- Zhou, Z. H., & Feng, J. (2019). Deep forest. National Science Review, 6(1), 74–86. https://doi.org/10.1093/nsr/nwy108 

</div>

## 👨‍👨‍👦‍👦 The ImBoost Team

- 🙎‍♂️ Panji Lokajaya Arifa
- 🙍🏻‍♀️ Desy Endriani
- 🙍🏻‍♀️ Jefita Resti Sari
- 🙍🏻‍♀️ Unique D. Resiloy







