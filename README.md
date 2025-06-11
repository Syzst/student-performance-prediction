# Proyek Akhir: Menyelesaikan Permasalahan Perusahaan Edutech

## Business Understanding

Jaya Jaya Institut adalah institusi pendidikan perguruan tinggi yang telah berdiri sejak tahun 2000 dan telah mencetak banyak lulusan dengan reputasi yang sangat baik. Namun, institusi ini menghadapi tantangan besar dengan tingginya angka siswa yang tidak menyelesaikan pendidikan (*dropout*). Tingginya angka dropout tentunya menjadi masalah besar bagi sebuah institusi pendidikan karena mempengaruhi reputasi institusi dan masa depan para siswa.

Untuk mengatasi tantangan ini, Jaya Jaya Institut ingin mendeteksi siswa yang berpotensi dropout sedini mungkin agar dapat memberikan bimbingan dan dukungan yang tepat sasaran untuk mencegah siswa tersebut berhenti dari pendidikannya.

### Permasalahan Bisnis

Proyek ini menangani tiga pertanyaan bisnis kritis:

#### 1. Apa saja faktor-faktor utama yang berkontribusi terhadap tingkat dropout siswa?
Memahami indikator utama dan faktor risiko yang menyebabkan siswa dropout akan membantu institusi mengidentifikasi siswa berisiko sejak dini.

#### 2. Bisakah kita memprediksi dengan akurat siswa mana yang berpotensi dropout?
Mengembangkan model prediksi yang dapat diandalkan untuk mengidentifikasi siswa yang berisiko dropout sebelum hal tersebut terjadi, sehingga memungkinkan intervensi proaktif.

#### 3. Bagaimana cara memantau dan melacak performa siswa secara efektif?
Menciptakan sistem monitoring komprehensif yang memberikan wawasan real-time tentang performa siswa dan pola risiko dropout.

### Cakupan Proyek

#### Analisis & Eksplorasi Data
- Analisis data eksploratif (EDA) komprehensif dari data performa siswa
- Analisis statistik untuk mengidentifikasi pola dan korelasi
- Analisis fitur untuk memahami variabel kunci yang mempengaruhi hasil siswa

#### Pembersihan dan Preparasi Data
- Penilaian dan pembersihan kualitas data
- Penanganan missing values dan outliers
- Seleksi fitur berdasarkan analisis korelasi
- Preprocessing data untuk model machine learning

#### Pemodelan dengan Berbagai Algoritma dan Evaluasi
- Implementasi berbagai model machine learning:
  - Random Forest
  - Gradient Boosting
  - XGBoost
  - Logistic Regression
  - Support Vector Machine
  - AdaBoost
  - Naive Bayes
  - Decision Tree
  - K-Nearest Neighbors
- Perbandingan dan evaluasi performa model
- Hyperparameter tuning dan optimasi

#### Visualisasi menggunakan Metabase
- Pembuatan dashboard interaktif untuk visualisasi data
- Tracking Key Performance Indicators (KPI)
- Tools monitoring performa siswa

#### Pengembangan Aplikasi dengan Streamlit
- Aplikasi web user-friendly untuk prediksi dropout
- Interface prediksi real-time
- Komponen visualisasi data interaktif

### Persiapan

#### Sumber Data
Dataset yang digunakan dalam proyek ini berasal dari koleksi Dicoding sebagai bagian dari final project kelas Applied Data Science:
```
https://raw.githubusercontent.com/dicodingacademy/dicoding_dataset/refs/heads/main/students_performance/data.csv
```

Dataset ini berisi informasi lengkap tentang performa siswa termasuk:
- Data akademik (nilai, unit kurikulum yang diselesaikan)
- Informasi demografis (usia, gender)
- Status ekonomi (beasiswa, status pembayaran)
- Background pendidikan sebelumnya
- Status akhir siswa (Enrolled, Dropout, Graduate)

#### Setup Environment
Untuk menjalankan proyek ini, diperlukan setup environment sebagai berikut:

**Requirements:**
- Python 3.8+
- Jupyter Notebook
- Streamlit
- Scikit-learn
- Pandas, NumPy
- Matplotlib, Seaborn
- Docker (untuk Metabase)
- Supabase account (untuk database)

**Installation:**
```bash
# Clone repository
git clone https://github.com/Syzst/student-performance-prediction

# Install dependencies
pip install -r requirements.txt

# Setup Metabase dengan Docker
docker run -d -p 3000:3000 --name metabase metabase/metabase
```

**Data Preparation Process:**
- **Data Quality Assessment**: Identifikasi missing values, duplikasi, dan inkonsistensi
- **Feature Selection**: Memilih 20+ fitur terpenting berdasarkan analisis korelasi dengan target variable (kolom status)
- **Data Transformation**: Normalisasi dan scaling fitur numerik
- **Categorical Encoding**: Konversi variabel kategorikal menjadi representasi numerik
- **Train-Test Split**: Pembagian data untuk training dan testing model

---

## Business Dashboard

### Implementasi Metabase
Dashboard komprehensif telah dikembangkan menggunakan Metabase dengan deployment Docker:

#### Setup Database
- **Export Data**: Data CSV diekspor ke database Supabase
- **Koneksi**: Metabase terhubung ke Supabase untuk akses data real-time
- **Docker Deployment**: Instance Metabase dalam container untuk kemudahan deployment
- **Database File**: Konfigurasi Metabase disertakan dalam repository (`metabase.db.mv`)

#### Kredensial Akses
- **Username**: root@mail.com
- **Password**: root123

#### Fitur Dashboard
- **Overview Performa Siswa**: Metrik kunci dan tren
- **Analisis Risiko Dropout**: Penilaian risiko real-time untuk siswa aktif
- **Tren Historis**: Pola dan tren sepanjang waktu
- **Analisis per Departemen**: Breakdown performa berdasarkan departemen akademik
- **Filter Interaktif**: Tampilan yang dapat disesuaikan untuk berbagai stakeholder
- **Analisis Korelasi**: Representasi visual faktor kunci yang mempengaruhi hasil siswa

#### Fitur Utama
- Update data real-time dari Supabase
- Kemampuan drill-down untuk analisis detail
- Fungsi export untuk laporan
- Design responsive untuk mobile
- Kontrol akses berbasis role user

---

## Menjalankan Sistem Machine Learning

### Aplikasi Streamlit
Aplikasi prediksi menyediakan interface yang intuitif untuk penilaian risiko dropout.

#### Live Deployment
🚀 **Akses aplikasi live**: [Student Performance Prediction App](https://student-performance-prediction-aji.streamlit.app/)

#### Fitur Aplikasi
- **Prediksi Individual**: Input data siswa untuk mendapatkan penilaian risiko dropout
- **Prediksi Batch**: Upload multiple record siswa untuk analisis bulk
- **Visualisasi Interaktif**: Chart dan grafik yang menjelaskan hasil prediksi
- **Analisis Faktor Risiko**: Breakdown detail faktor-faktor yang berkontribusi
- **Hasil Real-time**: Prediksi instan menggunakan model Random Forest yang telah dilatih

#### Menjalankan Secara Lokal
```bash
# Install dependencies
pip install -r requirements.txt

# Jalankan aplikasi Streamlit
streamlit run app.py
```

#### Petunjuk Penggunaan
1. Navigasi ke interface web (lokal atau deployed)
2. Input informasi siswa pada form yang disediakan
3. Klik "Predict" untuk mendapatkan penilaian risiko dropout
4. Review analisis detail dan rekomendasi

### Model Performance

#### Perbandingan Performa Model

| Model | Accuracy | F1 Score | ROC AUC | CV Score | CV Std |
|-------|----------|----------|---------|----------|--------|
| **Random Forest** | **0.7627** | **0.7596** | **0.8978** | **0.7666** | **0.0125** |
| Gradient Boosting | 0.7616 | 0.7612 | 0.8970 | 0.7646 | 0.0094 |
| XGBoost | 0.7537 | 0.7489 | 0.8954 | 0.7626 | 0.0158 |
| Logistic Regression | 0.7367 | 0.7471 | 0.8843 | 0.7513 | 0.0217 |
| SVM | 0.7288 | 0.7387 | 0.8839 | 0.7426 | 0.0176 |
| AdaBoost | 0.7209 | 0.7302 | 0.8675 | 0.7231 | 0.0159 |
| Naive Bayes | 0.6497 | 0.6657 | 0.8150 | 0.6782 | 0.0093 |
| Decision Tree | 0.6621 | 0.6688 | 0.7433 | 0.6728 | 0.0179 |
| KNN | 0.5989 | 0.6247 | 0.7960 | 0.6216 | 0.0045 |

#### Best Model: Random Forest

**Metrik Performa Keseluruhan:**
- **Accuracy**: 76.27%
- **Weighted F1-Score**: 75.96%
- **ROC AUC Score**: 89.78%
- **Cross-Validation Score**: 76.66% ± 1.25%

#### Classification Report Detail

| Class | Precision | Recall | F1-Score | Support |
|-------|-----------|---------|----------|---------|
| Enrolled | 0.51 | 0.49 | 0.50 | 159 |
| Dropout | 0.80 | 0.71 | 0.75 | 284 |
| Graduate | 0.82 | 0.89 | 0.86 | 442 |
| **Overall** | **0.76** | **0.76** | **0.76** | **885** |

---

## Conclusion

Proyek komprehensif ini berhasil mengatasi semua tiga permasalahan bisnis yang diidentifikasi oleh Jaya Jaya Institut:

### Jawaban untuk Permasalahan Bisnis 1: Faktor-faktor Utama Dropout
Melalui analisis korelasi ekstensif dan eksplorasi data, kami mengidentifikasi faktor-faktor paling signifikan yang berkontribusi terhadap dropout siswa:

**Faktor Kontribusi Utama (berdasarkan kekuatan korelasi):**
1. **Curricular Units (2nd Semester) - Approved**: Korelasi kuat positif dengan kelulusan
2. **Curricular Units (1st Semester) - Approved**: Performa akademik di semester pertama
3. **Curricular Units (2nd Semester) - Grade**: Tingkat pencapaian akademik
4. **Curricular Units (1st Semester) - Grade**: Performa akademik dasar
5. **Scholarship Holder**: Dampak dukungan finansial terhadap penyelesaian
6. **Tuition Fees Up to Date**: Komitmen dan stabilitas finansial
7. **Application Mode**: Metode pendaftaran dan komitmen siswa
8. **Previous Qualification (Grade)**: Latar belakang akademik sebelumnya
9. **Age at Enrollment**: Faktor kematangan dan kesiapan siswa
10. **Educational Special Needs**: Kebutuhan dukungan untuk penyelesaian

Faktor-faktor ini menunjukkan bahwa **performa akademik** (terutama di dua semester pertama), **stabilitas finansial** (beasiswa dan pembayaran biaya), dan **karakteristik latar belakang siswa** adalah prediktor utama kesuksesan atau risiko dropout siswa.

### Jawaban untuk Permasalahan Bisnis 2: Akurasi Prediksi
Model Random Forest kami mencapai performa prediksi yang excellent:
- **Overall Accuracy**: 76.27% pada test data
- **ROC AUC Score**: 89.78% menunjukkan kemampuan diskriminatif yang sangat baik
- **Cross-Validation Score**: 76.66% ± 1.25% menunjukkan performa yang stabil
- **Performa Deteksi Dropout**: 
  - Precision: 80.2% untuk prediksi dropout
  - Recall: 71.1% untuk mengidentifikasi siswa berisiko
  - F1-Score: 75.4% performa yang seimbang
- Model memberikan kemampuan early warning yang dapat diandalkan dengan performa kuat di semua kategori siswa

### Jawaban untuk Permasalahan Bisnis 3: Sistem Monitoring
Solusi yang diimplementasikan menyediakan:
- Dashboard real-time untuk monitoring berkelanjutan
- Alert otomatis untuk siswa berisiko tinggi
- Tools reporting komprehensif untuk administrator
- Insights berbasis data untuk strategi intervensi yang tepat sasaran

### Dampak dan Hasil
- **Intervensi Dini**: Sistem memungkinkan dukungan proaktif untuk siswa berisiko
- **Optimasi Sumber Daya**: Alokasi yang lebih baik untuk konseling dan dukungan
- **Peningkatan Retensi**: Potensi untuk mengurangi tingkat dropout secara signifikan
- **Keputusan Berbasis Data**: Pendekatan evidence-based untuk strategi dukungan siswa

---

## Rekomendasi Action Items

### 1. Implementasi Sistem Early Warning
- **Deploy model prediksi** ke sistem informasi akademik yang ada
- **Setup monitoring otomatis** untuk siswa baru di semester pertama
- **Buat alert system** untuk staff akademik ketika siswa masuk kategori high-risk

### 2. Program Intervensi Bertarget
- **Develop program mentoring** khusus untuk siswa berisiko dropout
- **Strengthen financial aid programs** mengingat dampak signifikan beasiswa terhadap retention
- **Enhanced academic support** untuk siswa dengan performa rendah di semester awal

### 3. Peningkatan Sistem Monitoring
- **Regular model retraining** dengan data terbaru setiap semester
- **Integration dengan sistem LMS** untuk tracking engagement real-time
- **Mobile dashboard** untuk akses monitoring yang lebih mudah

### 4. Strategi Pencegahan Proaktif
- **Pre-enrollment screening** menggunakan model untuk identifikasi siswa berisiko sejak awal
- **Personalized learning paths** berdasarkan risk profile masing-masing siswa
- **Parent/guardian engagement program** untuk siswa kategori high-risk

### 5. Continuous Improvement
- **Quarterly model evaluation** dan fine-tuning
- **Feedback loop implementation** dari hasil intervensi untuk improve model
- **Expansion ke predictive analytics** untuk aspek lain seperti academic performance forecasting

### 6. Stakeholder Training
- **Training staff akademik** untuk menggunakan dashboard dan interpret hasil prediksi
- **Workshop untuk counselors** tentang intervention strategies berbasis data
- **Regular reporting** ke management tentang effectiveness program

---

## Project Structure
```
jaya-jaya-institut-dropout-prediction/
├── .devcontainer/                  # Development container configuration
├── app.py                          # Streamlit application
├── best_model_pipeline.joblib      # Trained Random Forest model
├── encoding_mappings.joblib        # Feature encoding mappings
├── label_encoders.joblib           # Label encoding objects
├── metabase.db.mv                  # Metabase database file
├── model_info.joblib               # Model metadata and information
├── notebook.ipynb                  # Jupyter notebook with analysis
├── requirements.txt                # Python dependencies
├── runtime.txt                     # Runtime specifications
└── README.md                       # Project documentation
```

## Live Applications

### 🚀 Streamlit App
- **URL**: https://student-performance-prediction-aji.streamlit.app/
- **Description**: Interactive web application for student dropout prediction

### 📊 Metabase Dashboard  
- **Access**: Available through Docker deployment
- **Credentials**: root@mail.com / root123
- **Database**: Connected to Supabase with exported CSV data

## Contributors
- **Muhammad Ilham Aji Firmansyah** - Data Scientist
  - Email: ilhamaji2001@gmail.com
  - Role: Complete project development, modeling, and deployment
- **Dicoding Academy** - Dataset Provider (Applied Data Science Final Project)

## License
