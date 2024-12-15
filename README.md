# Analisis Data Pemesanan Hotel

<p align="center">
  <img src="https://avatars.githubusercontent.com/u/31736571?s=200&v=4" alt="Logo Dataset">
</p>

## Pendahuluan
Proyek ini mengeksplorasi dan menganalisis dataset Hotel Bookings, yang berisi informasi mendetail tentang reservasi, demografi pelanggan, dan perilaku pemesanan untuk dua jenis hotel: Resort Hotel dan City Hotel.

### Pernyataan Masalah
Memahami pola dalam pemesanan hotel sangat penting untuk mengoptimalkan operasi, memaksimalkan pendapatan, dan meningkatkan kepuasan pelanggan. Analisis ini bertujuan untuk mengungkap:
- Tren utama dalam pemesanan dan pembatalan.
- Wawasan tentang perilaku pelanggan (misalnya, lead time, frekuensi pemesanan).
- Hubungan antara karakteristik pemesanan dan pendapatan.

### Pendekatan
Dengan menggunakan Python dan berbagai pustaka analisis data, proyek ini:
- Memproses dan membersihkan dataset untuk memastikan akurasi.
- Melakukan analisis data eksplorasi (EDA) untuk menemukan tren dan pola.
- Merangkum temuan untuk membantu para pemangku kepentingan dalam pengambilan keputusan.

Analisis ini bermanfaat bagi manajer hotel dengan memberikan wawasan yang dapat ditindaklanjuti untuk strategi penetapan harga, pengelolaan inventaris, dan pemasaran yang ditargetkan.

---

## Paket yang Diperlukan
Proyek ini menggunakan pustaka Python berikut:

- `gdown`
- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`
- `scikit-learn`

Pastikan Anda telah menginstal pustaka-pustaka ini dengan menjalankan:
```bash
pip install -r requirements.txt
```

---

## Persiapan Data

### Sumber Dataset
- **Sumber**: [Repositori GitHub rfordatascience/tidytuesday](https://github.com/rfordatascience/tidytuesday)
- **Unduhan Langsung**: [Hotel Booking Dataset](https://www.dropbox.com/sh/qwdaldzkp8yrqwj/AADTj_WQcuKA0bsEeCKU__98a?dl=1)

### Gambaran Dataset
Dataset ini berisi:
- **Tujuan Awal**: Dataset terbuka untuk mengeksplorasi perilaku pemesanan hotel.
- **Variabel Utama**:
  - `hotel`: Jenis hotel (Resort/City)
  - `arrival_date`: Tanggal kedatangan
  - `is_canceled`: Indikasi apakah reservasi dibatalkan
  - `lead_time`: Hari antara pemesanan dan kedatangan
  - `adr`: Tarif harian rata-rata (pendapatan per hari)

### Langkah Pembersihan
- Penanganan nilai yang hilang.
- Standarisasi format tanggal.
- Penghapusan entri duplikat.

Ringkasan variabel data yang telah dibersihkan tersedia dalam file `.ipynb`.

---

## Analisis Data Eksplorasi (EDA)

### Temuan Utama
1. **Tren Pemesanan**:
   - Puncak pemesanan pada Mei 2017 dan Oktober 2016.
   - Tren mingguan menunjukkan lonjakan reservasi di pertengahan tahun.

2. **Pembatalan**:
   - Tingkat pembatalan tinggi selama minggu-minggu puncak.
   - Waktu tunggu (lead time) berkorelasi positif dengan pembatalan (0.29).

3. **Analisis Pendapatan**:
   - Pendapatan rata-rata per pemesanan: $101.83.
   - Pendapatan harian tertinggi tercatat selama musim panas dan untuk masa inap 6 hari.

4. **Perilaku Pelanggan**:
   - Tamu non-repetitif memiliki tingkat pembatalan lebih tinggi (37.8%).
   - Sebagian besar pemesanan tanpa deposit.

Plot dan tabel yang memvisualisasikan wawasan ini disertakan dalam file `.ipynb`.

---

## Sistem Prediksi Pembatalan
Sebagai bagian tambahan dari proyek ini, kami juga membuat sebuah sistem prediksi pembatalan sederhana. Sistem ini terinspirasi dari pola pembatalan yang ditemukan selama analisis.

### Alur Program
1. **Persiapan Data**
   - Program menggunakan variabel `lead_time`, `total_of_special_requests`, `total_stays`, `previous_cancellations`, dan `deposit_type` sebagai fitur.
   - `is_canceled` digunakan sebagai target prediksi.
   - Data dibagi menjadi data latih dan data uji menggunakan `train_test_split`.

2. **Pelatihan Model**
   - Model Machine Learning yang digunakan adalah `RandomForestClassifier`.
   - Model dilatih menggunakan data latih (`X_train`, `y_train`).

3. **Fungsi Prediksi**
   - Fungsi `predict_cancellation` meminta input pengguna untuk fitur-fitur seperti:
     - Lead time
     - Total permintaan khusus
     - Lama tinggal
     - Jumlah pembatalan sebelumnya
     - Tipe deposit
   - Berdasarkan input tersebut, program memberikan prediksi apakah reservasi kemungkinan dibatalkan atau tidak beserta probabilitasnya.

---

## Rangkuman

### Ringkasan Utama
- **Wawasan**:
  - Tren pemesanan dan pendapatan sesuai dengan permintaan musiman.
  - Waktu tunggu dan deposit non-refundable memiliki pengaruh signifikan terhadap pembatalan.
- **Rekomendasi**:
  - Fokus pada pemasaran untuk tamu repetitif.
  - Tawarkan opsi pemesanan yang fleksibel untuk mengurangi pembatalan.

### Keterbatasan
- Ruang lingkup dataset terbatas pada dua jenis hotel.
- Faktor eksternal (misalnya, ekonomi, cuaca) tidak dipertimbangkan.

Pekerjaan di masa depan dapat mencakup integrasi dataset eksternal dan penerapan model prediksi yang lebih canggih.

---

## Anggota Tim

![Logo Universitas](https://github.com/Gito0303/Hotel-Booking-Data-Analysis/blob/main/UMM_LOGO.png)

**Ketua Tim** : Fathul Agit Darmawan (202110370311169), Teknik Informatika, Universitas Muhammadiyah Malang  
**Anggota** :  
- M. Bima Mauludin (202110370311193), Teknik Informatika, Universitas Muhammadiyah Malang  
- Galvan Adam Maliki (202110370311188), Teknik Informatika, Universitas Muhammadiyah Malang  

---

## Sumber Daya Tambahan

- Lihat [notebook](hotel_booking_analysis.ipynb) untuk analisis lengkap dan implementasi kode.
- Untuk dependensi paket, lihat [requirements.txt](requirements.txt).
