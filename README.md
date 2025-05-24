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

## 🔗 Data Dan Sumber Data 
**1. KAB_KOTA**: Nama Kabupaten atau Kota yang ada diseluruh Indonesia.

**2. IPM (Indeks Pembangunan Manusia)**: Mengukur kualitas hidup manusia berbasis berbasis tiga dimensi: umur panjang dan sehat, pengetahuan, dan standar hidup layak.

**3. Anggaran**: Jumlah alokasi anggaran (kemungkinan APBD/APBN) dalam satuan rupiah.

**4. IPG (Indeks Pembangunan Gender)**: Menggambarkan kesetaraan gender dalam IPM.

**5. PKKP (Prevalensi Ketidakcukupan Konsumsi Pangan)**: Persentase penduduk dengan konsumsi pangan kurang dari kebutuhan minimal.

**6. PPM (Persentase Penduduk Miskin)**: Persentas penduduk dengan pendapatan di bawa garis kemiskinan.

**7. PPK (Pengeluaran Per Kapita)**: Jumlah pengeluaran rata-rata individu.

**8. Air Layak**: Persentase rumah tangga yang mengakses air minum layak.

**9. IKK (Indeks Kemahalan Kontruksi)**: Nilai tambah barang dan jasa yang dihasilkan di wilayah tersebut.

**10. PDRB (Produk Domestik Regional Bruto)**: Nilai tambah barang dan jasa yang dihasilkan di wilayah tersbut.

**Sumber**: Satu Data Indonesia, dan BPS (Badan Pusat Statistik).
</div>

## 📋 Langkah Analisis
1. Pengumpulan Data: Data sekunder IPM kabupaten/kota dan variabel pendukung (alokasi anggaran, PDRB, pengeluaran per kapita, tingkat kemiskinan, akses air bersih, IPG, IKK, dll.) dikumpulkan dari sumber resmi (BPS, Portal Satu Data Indonesia).
2. Pra-pemrosesan Data: Lakukan pembersihan data (mengatasi nilai hilang dan outlier), transformasi skala (misalnya normalisasi atau log-transformasi), dan encoding variabel kategorikal agar dataset siap untuk pemodelan.
3. Penentuan Label Target: Ubah nilai IPM setiap daerah menjadi kelas kategorikal sesuai ketentuan BPS.
   - IPM Rendah: <60
   - IPM Sedang: 60–<70
   - IPM Tinggi: 70–<80
   - IPM Sangat tinggi: ≥80)
5. Pembagian Data: Bagi dataset menjadi set pelatihan dan pengujian, misalnya menggunakan validasi silang k-fold (10 lipatan, rasio 90% data latih : 10% data uji) untuk menjaga kemampuan generalisasi model.
6. Pelatihan Model XGBoost: Bangun model klasifikasi XGBoost dengan objective multiclass (softmax), kemudian latih model tersebut pada data pelatihan. Lakukan tuning hyperparameter (jumlah pohon, kedalaman, laju pembelajaran, dan regularisasi L1/L2) berdasarkan hasil validasi silang untuk mendapatkan performa optimal.
7. Evaluasi Model: Ukur kinerja model menggunakan matriks kebingungan untuk menghitung akurasi, presisi, recall, dan/atau F1-score per kelas IPM. Bandingkan hasil model pada data latih dan validasi untuk memastikan tidak terjadi overfitting.
8. Interpretasi dan Rekomendasi Kebijakan: Analisis fitur penting (feature importance) dari model untuk menentukan variabel yang paling berpengaruh terhadap klasifikasi IPM. Gunakan hasil klasifikasi dan variabel kunci ini untuk merumuskan rekomendasi intervensi dan kebijakan pembangunan berbasis data 
</div>

## ✅ Hasil dan Interpretasi
</div>

## ⭕ Kesimpulan
</div>

## 📚 Referensi
</div>








