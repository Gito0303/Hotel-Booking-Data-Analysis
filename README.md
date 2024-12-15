# Analisis Data Pemesanan Hotel

<p align="center">
  <img src="https://avatars.githubusercontent.com/u/31736571?s=200&v=4" alt="Logo Dataset">
</p>

## 🏨 **Pendahuluan**
Proyek ini mengeksplorasi dan menganalisis **dataset Hotel Bookings**, yang berisi informasi mendetail tentang:
- **Reservasi**
- **Demografi pelanggan**
- **Perilaku pemesanan**

Dataset mencakup dua jenis hotel:  
🏖️ **Resort Hotel**  
🏙️ **City Hotel**

---

## ❓ **Pernyataan Masalah**
Memahami pola dalam pemesanan hotel sangat penting untuk:
- 📈 **Mengoptimalkan operasi**  
- 💰 **Memaksimalkan pendapatan**  
- 😊 **Meningkatkan kepuasan pelanggan**

### **Tujuan Analisis**:
1. 🔍 Mengungkap **tren utama** dalam pemesanan dan pembatalan.  
2. 🧠 Memberikan **wawasan perilaku pelanggan** (misalnya, lead time, frekuensi pemesanan).  
3. 🔗 Menganalisis **hubungan antara karakteristik pemesanan dan pendapatan**.

---

## 🛠️ **Pendekatan**
### **Langkah-langkah Proyek**:
1. 🧹 **Data Cleaning**:  
   - Memproses dan membersihkan dataset untuk memastikan akurasi.  

2. 📊 **Analisis Data Eksplorasi (EDA)**:  
   - Menemukan tren dan pola dalam data.  

3. 📝 **Merangkum Temuan**:  
   - Memberikan wawasan yang dapat membantu pemangku kepentingan dalam pengambilan keputusan.

---

## 🎯 **Manfaat**
Analisis ini memberikan **wawasan strategis** bagi manajer hotel untuk:  
- 💸 **Strategi penetapan harga**  
- 📦 **Pengelolaan inventaris**  
- 🎯 **Pemasaran yang lebih efektif**

---


# 🛠️ **Paket yang Diperlukan**

Proyek ini menggunakan pustaka Python berikut:  
- 📥 **`gdown`**: Untuk mengunduh dataset langsung dari Google Drive.  
- 📊 **`pandas`**: Untuk manipulasi dan analisis data.  
- 🔢 **`numpy`**: Untuk operasi numerik.  
- 📉 **`matplotlib`**: Untuk visualisasi data dasar.  
- 🎨 **`seaborn`**: Untuk visualisasi data yang lebih estetis.  
- 🤖 **`scikit-learn`**: Untuk analisis dan pemodelan machine learning.

---
Pastikan Anda telah menginstal pustaka-pustaka di atas dengan menjalankan perintah berikut di terminal:  
```bash
pip install -r requirements.txt
---


# 📂 **Persiapan Data**

---

## 🌍 **Sumber Dataset**
- **Sumber**: [Repositori GitHub rfordatascience/tidytuesday](https://github.com/rfordatascience/tidytuesday)
- **Unduhan Langsung**: [Hotel Booking Dataset](https://www.dropbox.com/sh/qwdaldzkp8yrqwj/AADTj_WQcuKA0bsEeCKU__98a?dl=1)

---

## 📊 **Gambaran Dataset**
Dataset ini berisi informasi tentang pemesanan hotel dan berfokus pada perilaku pelanggan:

- **Tujuan Awal**:  
  Dataset ini terbuka untuk mengeksplorasi perilaku pemesanan hotel.

### **Variabel Utama**:
1. 🏨 **`hotel`**: Jenis hotel (Resort/City)
2. 📅 **`arrival_date`**: Tanggal kedatangan pelanggan
3. ❌ **`is_canceled`**: Indikasi apakah reservasi dibatalkan
4. ⏳ **`lead_time`**: Jumlah hari antara pemesanan dan kedatangan
5. 💸 **`adr`**: Tarif harian rata-rata (pendapatan)

---

## 🧹 **Langkah Pembersihan Data**
Untuk memastikan kualitas data, langkah-langkah berikut dilakukan:
- 🔄 **Penanganan Nilai yang Hilang**: Mengganti atau menghapus nilai yang hilang.
- 📅 **Standarisasi Format Tanggal**: Menyelaraskan format tanggal agar konsisten.
- 🚫 **Penghapusan Entri Duplikat**: Menghapus data yang terduplikasi untuk menghindari bias.

---

## 📑 **Ringkasan Variabel Data**
Ringkasan tentang variabel data yang telah dibersihkan dapat ditemukan dalam file `.ipynb`.

---

<div align="center">
  🔍 **Pembersihan data yang tepat sangat penting untuk hasil analisis yang akurat!** 🔍
</div>

---

# 🔍 **Insight Analisis**

---

## 🚨 **Temuan Utama**

### 1. 📅 **Tren Pemesanan**:
   - 📈 **Puncak Pemesanan**:  
     Puncak pemesanan terjadi pada **Mei 2017** dan **Oktober 2016**.
   - 🔄 **Tren Mingguan**:  
     Lonjakan reservasi terlihat di **pertengahan tahun**.

### 2. ❌ **Pembatalan**:
   - 📊 **Tingkat Pembatalan**:  
     Tingkat pembatalan tinggi terutama pada **minggu-minggu puncak**.
   - 🔗 **Korelasi Pembatalan dan Lead Time**:  
     Lead time memiliki korelasi positif dengan pembatalan sebesar **0.29**.

### 3. 💰 **Analisis Pendapatan**:
   - 💵 **Pendapatan Rata-Rata per Pemesanan**:  
     Pendapatan rata-rata per pemesanan adalah **$101.83**.
   - 🌞 **Pendapatan Tertinggi**:  
     Pendapatan tertinggi tercatat pada **musim panas** dan untuk **masa inap 6 hari**.

### 4. 👥 **Perilaku Pelanggan**:
   - 🚫 **Tamu Non-Repetitif**:  
     Tamu yang tidak melakukan pemesanan berulang memiliki tingkat pembatalan lebih tinggi, yaitu **37.8%**.
   - 💳 **Pemesanan Tanpa Deposit**:  
     Sebagian besar pemesanan tidak menggunakan **deposit**.

---

## 📊 **Visualisasi**
Plot dan tabel yang memvisualisasikan wawasan ini dapat ditemukan dalam file `.ipynb`.

---

<div align="center">
  🎨 **Data yang eksploratif memberikan wawasan berharga untuk strategi bisnis!** 🎨
</div>

---

# 🔮 **Sistem Prediksi Pembatalan**

Sebagai bagian tambahan dari proyek ini, kami mengembangkan sebuah sistem prediksi pembatalan sederhana. Sistem ini terinspirasi dari pola pembatalan yang ditemukan selama analisis.

---

## 🔄 **Alur Program**

### 1. **📊 Persiapan Data**
   - Program ini menggunakan fitur-fitur berikut sebagai input:
     - **`lead_time`**: Waktu antara pemesanan dan kedatangan.
     - **`total_of_special_requests`**: Jumlah permintaan khusus yang diajukan oleh tamu.
     - **`total_stays`**: Jumlah total masa inap.
     - **`previous_cancellations`**: Jumlah pembatalan sebelumnya oleh tamu yang sama.
     - **`deposit_type`**: Jenis deposit yang digunakan (misalnya, deposit yang dikembalikan atau tidak).
   - **Target Prediksi**:  
     - **`is_canceled`**: Indikator apakah pemesanan dibatalkan (ya/tidak).
   - **Pembagian Data**:  
     Data dibagi menjadi data latih dan data uji menggunakan `train_test_split`.

---

### 2. **🤖 Pelatihan Model**
   - **Model yang Digunakan**:  
     Model **`RandomForestClassifier`** dipilih untuk tugas prediksi pembatalan.
   - **Proses Pelatihan**:  
     Model dilatih menggunakan data latih (**`X_train`, `y_train`**).

---

### 3. **🔮 Fungsi Prediksi**
   - Fungsi **`predict_cancellation`** meminta input pengguna untuk beberapa fitur utama:
     - **Lead time**  
     - **Total permintaan khusus**  
     - **Lama tinggal**  
     - **Jumlah pembatalan sebelumnya**  
     - **Tipe deposit**
   - Berdasarkan input tersebut, program akan memberikan **prediksi** apakah reservasi akan dibatalkan atau tidak, beserta **probabilitas** pembatalan.

---

## ⚙️ **Cara Kerja Sistem**
Sistem ini memungkinkan manajer hotel untuk memprediksi kemungkinan pembatalan pemesanan dan merencanakan langkah-langkah preventif untuk mengurangi dampaknya.

---

<div align="center">
  🎯 **Sistem prediksi pembatalan dapat membantu pengelolaan reservasi yang lebih baik!** 🎯
</div>

---

# 📚 **Rangkuman**

---

## 🔑 **Ringkasan Utama**
### **Wawasan:**
- 📅 **Tren Pemesanan dan Pendapatan**:  
  Pemesanan dan pendapatan menunjukkan **pola musiman** yang jelas.
- ⏳ **Waktu Tunggu & Deposit Non-Refundable**:  
  Waktu tunggu yang lebih lama dan deposit non-refundable memiliki **pengaruh signifikan** terhadap tingkat pembatalan.

### **Rekomendasi:**
- 🎯 **Fokus pada Pemasaran untuk Tamu Repetitif**:  
  Menargetkan tamu yang sering memesan dapat **meningkatkan pendapatan** dan **mengurangi pembatalan**.
- 💡 **Tawarkan Opsi Pemesanan Fleksibel**:  
  Menyediakan opsi pemesanan yang lebih fleksibel dapat mengurangi tingkat pembatalan, memberikan **kenyamanan** kepada tamu.

---

## ⚠️ **Keterbatasan**
- 🔍 **Ruang Lingkup Dataset**:  
  Dataset hanya mencakup dua jenis hotel, yaitu **Resort Hotel** dan **City Hotel**.
- 🌍 **Faktor Eksternal**:  
  Faktor eksternal seperti kondisi **ekonomi** dan **cuaca** tidak dipertimbangkan dalam analisis ini.

### 🔮 **Pekerjaan di Masa Depan:**
- 💼 Integrasi dengan **dataset eksternal** (misalnya, data cuaca atau ekonomi) untuk analisis yang lebih komprehensif.
- 🤖 Penerapan **model prediksi yang lebih canggih** untuk meningkatkan akurasi prediksi pembatalan.

---

<div align="center">
  🏨 **Dengan pemahaman yang lebih baik, hotel dapat mengoptimalkan strategi pemesanan dan pendapatan!** 🏨
</div>

---

## Anggota Tim

<div align="center">
  <img src="https://github.com/Gito0303/Hotel-Booking-Data-Analysis/blob/main/UMM_LOGO.png" alt="Logo Universitas Muhammadiyah Malang" width="200">
</div>

### **Ketua Tim**
👤 **Fathul Agit Darmawan**  
📘 **NIM**: 202110370311169  
🎓 **Program Studi**: Teknik Informatika  
🏛️ **Universitas Muhammadiyah Malang**

---

### **Anggota Tim**
1. 👤 **M. Bima Mauludin**  
   📘 **NIM**: 202110370311193  
   🎓 **Program Studi**: Teknik Informatika  
   🏛️ **Universitas Muhammadiyah Malang**

2. 👤 **Galvan Adam Maliki**  
   📘 **NIM**: 202110370311188  
   🎓 **Program Studi**: Teknik Informatika  
   🏛️ **Universitas Muhammadiyah Malang** 

---

# 📚 **Sumber Daya Tambahan**

---

- 🔎 **Analisis Lengkap dan Implementasi Kode**:  
  Lihat notebook lengkap untuk **analisis mendalam** dan **implementasi kode** yang digunakan dalam proyek ini.  
  [📓 Hotel Booking Analysis](hotel_booking_analysis.ipynb)

- 📦 **Dependensi Paket**:  
  Untuk daftar lengkap paket dan dependensi yang diperlukan, buka file **requirements.txt** untuk memastikan lingkungan Anda terinstal dengan benar.  
  [📄 requirements.txt](requirements.txt)

---

<div align="center">
  📘 **Akses lebih lanjut untuk memahami detail analisis dan implementasi proyek!** 📘
</div>

---
