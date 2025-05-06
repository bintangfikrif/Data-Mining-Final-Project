# 🐚 Deteksi Outlier dan Evaluasi Model pada Dataset Abalon

## 📌 Gambaran Proyek
Proyek ini berfokus pada pendeteksian dan penanganan outlier dalam dataset Abalon menggunakan dua metode statistik - **Z-Score** dan **IQR** (Interquartile Range) - serta menganalisis dampaknya terhadap model regresi linear yang digunakan untuk memprediksi usia abalon.

**Tujuan**: Mengevaluasi bagaimana penghapusan outlier memengaruhi performa model dan membandingkan efektivitas kedua metode dalam meningkatkan akurasi prediksi.

---

## 🎯 Tujuan Penelitian
1. Mengidentifikasi outlier pada data usia abalon menggunakan metode IQR dan Z-Score.
2. Menganalisis perubahan performa model sebelum dan setelah penghapusan outlier.
3. Membandingkan efektivitas kedua metode deteksi outlier dalam meningkatkan akurasi prediksi.

---

## 📁 Deskripsi Dataset
- **Sumber**: UCI Machine Learning Repository
- **Target**: Usia (dihitung dari Rings + 1.5)
- **Fitur**: Karakteristik fisik abalon (Panjang, Diameter, Berat, dll.) dan fitur kategorikal *Sex* yang di-encode dengan one-hot encoding.

---

## ⚙️ Metodologi
### 1. Persiapan Data
- Memuat dataset dan melakukan pra-pemrosesan, termasuk transformasi target dan one-hot encoding.

### 2. Eksplorasi Data (EDA)
- Visualisasi distribusi target (Usia) menggunakan histogram dan KDE plot.
- Scatter plot untuk melihat hubungan antara Panjang dan Usia (sebelum & sesudah filtering).

### 3. Fungsi Evaluasi Model
Fungsi reusable untuk melatih dan mengevaluasi model Regresi Linear dengan:
- **RMSE** (Root Mean Squared Error)
- **R² Score**

### 4. Deteksi Outlier
Dua metode yang digunakan:
- **Z-Score**: Menghapus baris dengan Z-Score > 2.5 pada fitur numerik.
- **IQR**: Menghapus baris di luar range `[Q1 - 1.5×IQR, Q3 + 1.5×IQR]`.

### 5. Pelatihan & Evaluasi Model
Model dilatih pada:
- Dataset asli
- Dataset hasil filter Z-Score
- Dataset hasil filter IQR

### 6. Visualisasi & Ringkasan
- Visualisasi performa prediksi dan distribusi sampel.
- Ringkasan hasil dalam tabel perbandingan.

---

## 📈 Ringkasan Hasil
| Dataset          | RMSE  | R² Score | Jumlah Sampel |
|------------------|-------|----------|---------------|
| Asli            |  2.21   |  0.55    |  4177         |
| Filter Z-Score  |  1.87   |  0.49    |  3849         |
| Filter IQR      |  1.62   |  0.53    |  3781         |

---

## 🔍 Insight & Kesimpulan
1. **Filter Z-Score**:
   - Menghapus nilai ekstrem dengan mempertahankan variabilitas data.
   - Peningkatan performa model moderat tanpa kehilangan banyak data.

2. **Filter IQR**:
   - Menghasilkan dataset lebih terstruktur dengan akurasi lebih baik.
   - Berpotensi kehilangan data signifikan.

3. **Pertimbangan**:
   - Trade-off antara peningkatan performa dan pengurangan sampel perlu diperhatikan sesuai kebutuhan.

---

## 📂 File Proyek
- `Outlier_Abalone_Complete_Analysis.ipynb`: Notebook analisis lengkap.
- `README.md`: Dokumentasi proyek.

---

## 👨‍💻 Penulis
📌 [Kelompok 3 - Data Mining]
| Nama                 | NIM       | 
|----------------------|-----------|
| Bintang Fikri Fauzan | 122140008 |  
| Arkan Hariz C. Liem  | 122140038 |  
| Naufal Haris N.      | 122140040 |  
| Rahmat Aldi Nasda    | 122140077 |  
| Cici Tri Fadila.As   | 122140086 |  
| Dito Rifki Irawan    | 122140153 |  
| Ihya Razky Hidayat   | 122140167 | 
---

## ✅ Persyaratan
- Python 3.x
- Library: `numpy`, `pandas`, `matplotlib`, `seaborn`, `scikit-learn`

---

## 📜 Lisensi
Proyek ini dilisensikan di bawah **MIT License** - bebas digunakan, dimodifikasi, dan dibagikan.
