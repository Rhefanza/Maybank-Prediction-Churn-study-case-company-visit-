# Maybank-Prediction-Churn-study-case-company-visit-
Berikut adalah draf **README.md** yang profesional dan terstruktur untuk proyek analisis churn nasabah bank tersebut. File ini dirancang untuk menjelaskan alur kerja teknis Anda, mulai dari pengolahan data hingga hasil model machine learning.

---

# Bank Customer Churn Prediction 🚀

Proyek ini bertujuan untuk membangun model prediksi **Customer Churn** (kemungkinan nasabah berhenti berlangganan) menggunakan dataset perbankan yang berisi informasi profil nasabah, kepemilikan produk, dan saldo.

## 📌 Gambaran Proyek

Tujuan utama adalah mengidentifikasi nasabah yang berpotensi melakukan churn (`Potential_Churn_2`) sehingga tim marketing atau operasional dapat memberikan intervensi (seperti penawaran khusus) tepat waktu.

## 🛠️ Alur Kerja (Workflow)

### 1. Data Preprocessing & Feature Engineering

Kami menciptakan fitur-fitur baru untuk menangkap perilaku nasabah lebih dalam:

* **Total_PH**: Jumlah total produk yang dimiliki nasabah (Funding, Loan, Wealth).
* **Total_Balance**: Total saldo gabungan dari semua produk.
* **Funding_Share**: Rasio saldo tabungan (funding) terhadap total saldo.
* **Funding_to_Wealth_Ratio**: Rasio antara saldo tabungan dan investasi.
* **Is_Single_Product**: Fitur biner untuk mendeteksi nasabah yang hanya memiliki satu jenis produk (biasanya risiko churn lebih tinggi).
* **Standard Scaling**: Menyamakan skala untuk fitur numerik (`Balance_Funding`, `Balance_Loan`, `Balance_Wealth`).

### 2. Penanganan Imbalance Data

Dataset ini memiliki ketidakseimbangan kelas yang signifikan (kelas churn jauh lebih sedikit). Teknik yang digunakan:

* **SMOTE (Synthetic Minority Over-sampling Technique)**: Menghasilkan sampel sintetis untuk kelas minoritas agar model tidak bias ke kelas mayoritas.
* **SMOTENC**: Digunakan khusus untuk data yang memiliki campuran fitur numerik dan kategorikal.

### 3. Model Machine Learning

Kami membandingkan beberapa algoritma untuk mendapatkan hasil terbaik:

* **Logistic Regression**: Sebagai baseline model untuk melihat *Odds Ratio*.
* **Naive Bayes**: Model statistik sederhana untuk perbandingan.
* **Random Forest**: Algoritma ensemble untuk menangkap hubungan non-linear.
* **XGBoost**: Dioptimalkan untuk performa tinggi dan kecepatan.
* **CatBoost**: Digunakan untuk menangani fitur kategorikal secara otomatis dengan efisiensi tinggi.

## 📊 Hasil & Insight

### Fitur Paling Berpengaruh (Feature Importance)

Berdasarkan model **Random Forest** dan **Logistic Regression**, faktor utama yang memengaruhi churn adalah:

1. **Marital Status**: Nasabah yang berstatus *Married* dan *Single* menunjukkan koefisien yang berbeda terhadap potensi churn.
2. **Activeness (Inactive)**: Nasabah yang tidak aktif memiliki kecenderungan lebih tinggi untuk churn.
3. **Funding Share & Balance Wealth**: Besaran saldo dan bagaimana nasabah mengalokasikan uangnya antara tabungan dan investasi sangat berpengaruh.
4. **Age**: Usia nasabah merupakan faktor demografis kunci.

### Performa Model

Model dievaluasi menggunakan **Classification Report** (Precision, Recall, F1-Score). Fokus utama adalah meningkatkan *Recall* pada kelas churn agar sesedikit mungkin nasabah yang berpotensi churn terlewat oleh model.

## 🚀 Cara Menjalankan

1. Pastikan library berikut terinstall:
```bash
pip install pandas seaborn matplotlib scikit-learn imbalanced-learn xgboost catboost

```


2. Buka file `mybank_(company_visit).ipynb` di Google Colab atau Jupyter Notebook.
3. Sesuaikan path dataset:
```python
df = pd.read_csv("path_ke_file/maybank_churn_dataset_v2_500k.csv")

```



---

**Next Steps**:

* Melakukan Hyperparameter Tuning pada model XGBoost dan CatBoost.
* Menganalisis lebih lanjut profil nasabah pada *top 10% probability churn*.

---

