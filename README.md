***

<h1 align="center">Analisis Data Pemesanan Hotel</h1>

---

<p align="center">
  <img src="https://avatars.githubusercontent.com/u/31736571?s=200&v=4" alt="Logo Dataset">
  <h2 align="center">(Logo Sumber Data)</h2>
</p>

## 🏨 **Pendahuluan**
Proyek ini mengeksplorasi dan menganalisis **dataset Hotel Bookings**, yang berisi informasi mendetail tentang :
- **Reservasi**
- **Demografi pelanggan**
- **Perilaku pemesanan**
  
Dataset mencakup dua jenis hotel:  
🏖️ **Resort Hotel**  
🏙️ **City Hotel**

Menurut Sumber, Data ini berasal dari kumpulan data permintaan pemesanan hotel terbuka yang disusun oleh Antonio, Almeida, dan Nunes (2019). Berikut kami sertakan Informasi terkait sumber Dataset.

---

## 🌍 **Sumber Dataset**
- **Sumber**: [Repositori GitHub rfordatascience/tidytuesday](https://github.com/rfordatascience/tidytuesday)
- **Unduhan Langsung**: [Hotel Booking Dataset](https://www.dropbox.com/sh/qwdaldzkp8yrqwj/AADTj_WQcuKA0bsEeCKU__98a?dl=1)

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
   - Memproses dan membersihkan dataset.  

2. 📊 **Analisis Data**:  
   - Menemukan tren dan pola dalam data.  

3. 📝 **Merangkum Temuan**:  
   - Memberikan wawasan yang dapat membantu pemangku kepentingan dalam pengambilan keputusan.

---

## 🎯 **Manfaat**
Analisis ini memberikan **wawasan strategis** bagi manajer hotel untuk:  
- 💸 **Strategi penetapan harga**  
- 📦 **Pengelolaan inventaris**  
- 🎯 **Pemasaran yang lebih efektif**

***

<h1 align="center">Paket yang Diperlukan</h1>

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
```

***

<h1 align="center">Persiapan Data</h1>

---

## 📊 **Gambaran Dataset**
Dataset ini berisi informasi tentang pemesanan hotel dan perilaku pelanggan.

- **Tujuan Awal**:  
  Dataset ini digunakan untuk mengeksplorasi perilaku pemesanan hotel.

---

## **Variabel Utama yang Digunakan didalam Analisis ini**

| **Nama Variabel**                       | **Keterangan Singkat**                                                      |
|-----------------------------------------|------------------------------------------------------------------------------|
| 📅 **`arrival_date_year`**              | Tahun kedatangan pelanggan                                                   |
| 🗓 **`arrival_date_month`**             | Bulan kedatangan pelanggan                                                   |
| 📅 **`arrival_date_week_number`**       | Nomor minggu kedatangan pelanggan dalam tahun                                |
| 📅 **`arrival_date_day_of_month`**     | Hari kedatangan pelanggan dalam bulan                                       |
| ❌ **`is_canceled`**                    | Indikasi apakah reservasi dibatalkan (1: dibatalkan, 0: tidak dibatalkan)   |
| ⏳ **`lead_time`**                      | Jumlah hari antara pemesanan dan kedatangan                                  |
| 🛏 **`reserved_room_type`**             | Jenis kamar yang dipesan                                                     |
| 🛏 **`assigned_room_type`**             | Jenis kamar yang diberikan                                                   |
| 💰 **`deposit_type`**                   | Jenis deposit (No Deposit, Refundable, Non Refund)                          |
| 🛎 **`total_of_special_requests`**      | Jumlah permintaan khusus dari tamu                                          |
| 💸 **`adr`**                            | Average Daily Rate (pendapatan rata-rata per hari per reservasi)             |
| 🌐 **`stays_in_weekend_nights`**        | Lama tinggal pada akhir pekan (dalam malam)                                  |
| 🌐 **`stays_in_week_nights`**           | Lama tinggal pada hari kerja (dalam malam)                                   |
| ❌ **`previous_cancellations`**         | Jumlah pembatalan sebelumnya                                                 |
| ✅ **`previous_bookings_not_canceled`** | Jumlah reservasi sebelumnya yang tidak dibatalkan                           |
| 🔁 **`is_repeated_guest`**              | Menandakan apakah tamu adalah tamu berulang (1: ya, 0: tidak)                |

---

## **Variabel Baru yang dihasilkan selama Proses Analisis**

| **Nama Variabel**          | **Keterangan Singkat**                                                     |
|----------------------------|-----------------------------------------------------------------------------|
| 📅 **`arrival_date`**       | Kombinasi tahun dan bulan kedatangan (`arrival_date_year` dan `arrival_date_month`) |
| 🌸 **`season`**             | Musim kedatangan berdasarkan bulan (`arrival_date_month`)                  |
| ✅ **`success_ratio`**      | Rasio keberhasilan reservasi berdasarkan data sebelumnya                    |
| 🏨 **`total_stays`**        | Total lama tinggal, gabungan dari `stays_in_weekend_nights` dan `stays_in_week_nights` |
| ⚠️ **`risk_score`**         | Skor risiko pembatalan berdasarkan `lead_time`, `deposit_type`, dan `season`|

---

## 🧹 **Langkah Pembersihan Data**
Pembersihan data dilakukan dengan langkah-langkah berikut untuk memastikan kualitas data:
- 🔄 **Penanganan Nilai yang Hilang**: Mengganti nilai yang hilang agar data lebih lengkap dan akurat.
- 🔄 **Mengubah Tipe Data Kolom**: Menyesuaikan tipe data pada kolom yang tidak sesuai, seperti mengubah kolom tanggal menjadi tipe `datetime`.

---

## 📑 **Ringkasan Variabel Data**
Ringkasan tentang variabel data yang telah dibersihkan dapat ditemukan dalam file `.ipynb`.

---

<div align="center">
  🔍 **Pembersihan data yang tepat sangat penting untuk hasil analisis yang akurat!** 🔍
</div>

***

<h1 align="center">Insight Analisis</h1>

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

***

<h1 align="center">Sistem Prediksi Pembatalan Sederhana</h1>

---

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

***

<h1 align="center">Rangkuman</h1>

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
  <img src="https://github.com/Gito0303/Hotel-Booking-Data-Analysis/blob/main/LOGO_UMM_INFORMATIKA.png" alt="Logo Informatika & Universitas Muhammadiyah Malang" high="100" width="200">
</div>
---

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

---

### **Anggota Tim**
2. 👤 **Galvan Adam Maliki**  
   📘 **NIM**: 202110370311188  
   🎓 **Program Studi**: Teknik Informatika  
   🏛️ **Universitas Muhammadiyah Malang** 

***

<h1 align="center">Sumber Daya Tambahan</h1>

---

- 🔎 **Analisis Lengkap dan Implementasi Kode**:  
  Lihat notebook lengkap untuk **analisis mendalam** dan **implementasi kode** yang digunakan dalam proyek ini.  
  [📓 Hotel Booking Analysis](Hotel_Booking_Analysis.ipynb)

- 📦 **Dependensi Paket**:  
  Untuk daftar lengkap paket dan dependensi yang diperlukan, buka file **requirements.txt** untuk memastikan lingkungan Anda terinstal dengan benar.  
  [📄 Requirement](requirements.txt)

---

<div align="center">
  📘 **Akses lebih lanjut untuk memahami detail analisis dan implementasi proyek!** 📘
</div>

---
