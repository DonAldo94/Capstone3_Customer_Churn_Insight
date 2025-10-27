# Capstone Project Module 3 — E-commerce Customer Churn Prediction

## 📘 Overview

Proyek ini merupakan **Capstone Project Modul 3 (Machine Learning)** dari program **Data Science Purwadhika**.
Tujuannya adalah membangun model prediksi **Customer Churn** pada data e-commerce dengan pendekatan *supervised machine learning*.

Model ini menggabungkan seluruh tahapan yang telah dipelajari selama course:

* Business problem understanding
* Data exploration & preprocessing
* Feature engineering
* Model building & tuning (GridSearchCV)
* Evaluation (ROC, PR Curve)
* Business recommendation

---

## 🧩 Business Problem Understanding

Perusahaan e-commerce ingin mengurangi tingkat **customer churn** (pelanggan berhenti bertransaksi).
Tim Retention & CRM membutuhkan sistem prediksi untuk:

* Mengidentifikasi pelanggan yang berisiko churn
* Menjalankan kampanye retensi secara tepat sasaran (voucher, free shipping, re-engagement email)
* Meningkatkan efektivitas biaya promosi dan *lifetime value* pelanggan

📈 **Target bisnis:** menurunkan churn 3–5pp dalam 1–2 kuartal dengan intervensi pada top 10–20% pelanggan berisiko tinggi.

---

## 🧮 Dataset

File: `data_ecommerce_customer_churn.csv`
Format: CSV

**Variabel utama**:

* Demografi pelanggan (usia, jenis kelamin, wilayah)
* Aktivitas transaksi (frekuensi, nilai rata-rata, jumlah transaksi terakhir)
* Interaksi platform (waktu login terakhir, engagement rate)
* Label target: `Churn` (0 = aktif, 1 = churn)

---

## ⚙️ Workflow

1. **Data Understanding**

   * Eksplorasi bentuk data, tipe variabel, missing values, dan distribusi target.
2. **Data Preprocessing**

   * Imputasi median/modus
   * One-hot encoding untuk fitur kategorikal
   * StandardScaler untuk fitur numerik
   * Train-test split (stratify bila target imbalanced)
3. **Modeling**

   * Baseline: Logistic Regression
   * Advanced: Random Forest Classifier
   * Hyperparameter tuning menggunakan `GridSearchCV`
4. **Evaluation**

   * Metrik: Accuracy, Precision, Recall, F1, ROC-AUC, PR-AUC
   * Visualisasi: ROC Curve, Precision-Recall Curve
5. **Business ROI Simulation**

   * Estimasi *return on investment (ROI)* untuk kampanye targeting pelanggan berisiko.
6. **Model Export**

   * Model terbaik disimpan sebagai `.sav` (Pickle) untuk kebutuhan deployment.

---

## 📊 Metrics & Model Selection

Fokus utama model adalah **Recall** dan **PR-AUC**, karena tujuan bisnis lebih penting untuk *mengidentifikasi pelanggan yang benar-benar berisiko churn* daripada meminimalkan false positives.

---

## 💡 Conclusion & Recommendations

* Model berhasil mengidentifikasi pelanggan berisiko churn dengan metrik performa yang baik.
* Hasil ini dapat diintegrasikan ke sistem CRM untuk scoring mingguan dan targeting otomatis.
* Perlu dilakukan *monitoring* model secara berkala untuk mendeteksi data drift.
* Arah pengembangan:

  * Tambah fitur perilaku (RFM, channel, campaign history)
  * Eksperimen dengan model lain (LightGBM, XGBoost)
  * Implementasi explainability tools (SHAP/Feature Importance)

---

## 🗂️ File Structure

```
📁 Capstone_Module3/
 ├── Capstone_Module3_Customer_Churn.ipynb      ← Jupyter Notebook utama
 ├── data_ecommerce_customer_churn.csv          ← Dataset
 ├── churn_best_model.sav                       ← Model hasil training (Pickle)
 ├── README.md                                  ← Dokumentasi proyek
```

---

## 🧰 Tech Stack

* **Python 3.11+**
* **Pandas, NumPy, Matplotlib, Seaborn**
* **Scikit-learn**: model, preprocessing, GridSearchCV, metrics
* **Pickle**: model serialization

---
