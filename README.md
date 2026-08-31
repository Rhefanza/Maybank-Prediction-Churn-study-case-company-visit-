# Bank Customer Churn Prediction

Studi kasus machine learning untuk mengidentifikasi nasabah yang berpotensi churn berdasarkan profil, aktivitas, kepemilikan produk, dan saldo.

## Tujuan

Membangun pipeline klasifikasi yang membantu memprioritaskan nasabah berisiko sehingga intervensi retensi dapat dilakukan lebih tepat sasaran.

## Tahapan Analisis

1. Pembersihan dan eksplorasi data.
2. Feature engineering.
3. Penanganan class imbalance.
4. Pelatihan beberapa model.
5. Evaluasi dengan fokus pada recall dan F1 kelas churn.

## Feature Engineering

- `Total_PH` — total produk yang dimiliki nasabah.
- `Total_Balance` — total saldo seluruh produk.
- `Funding_Share` — proporsi dana terhadap total saldo.
- `Funding_to_Wealth_Ratio` — rasio dana terhadap produk wealth.
- `Is_Single_Product` — indikator kepemilikan satu jenis produk.

## Model yang Dibandingkan

- Logistic Regression
- Naive Bayes
- Random Forest
- XGBoost
- CatBoost

SMOTE atau SMOTENC digunakan sebagai bagian dari eksperimen untuk menangani distribusi kelas yang tidak seimbang.

## Menjalankan Notebook

```bash
git clone https://github.com/Rhefanza/Maybank-Prediction-Churn-study-case-company-visit-.git
cd Maybank-Prediction-Churn-study-case-company-visit-
pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn xgboost catboost jupyter
jupyter notebook "mybank_(company_visit).ipynb"
```

Dataset tidak disertakan. Sesuaikan path dataset di notebook sebelum menjalankan pipeline.

## Evaluasi

Gunakan confusion matrix, precision, recall, F1-score, dan ROC-AUC. Untuk kasus retensi, pemilihan threshold perlu mempertimbangkan biaya intervensi dan risiko nasabah churn yang terlewat.

## Catatan

Repositori ini merupakan studi kasus edukasional, bukan sistem keputusan produksi.
