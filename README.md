# Ramalan Customer Churn Menggunakan Random Forest

Repositori ini mengandungi kod pelaksanaan untuk prapemprosesan data, kejuruteraan ciri (*feature engineering*), dan pembinaan model pembelajaran mesin bagi meramalkan sama ada pelanggan akan berhenti melanggan (*churn*) atau kekal berdasarkan pelbagai ciri tingkah laku dan demografi.

## **1. Gambaran Keseluruhan Projek**
* **Dataset:** Menggunakan fail `customer_churn.csv` dengan lebih 440,000 baris data pelanggan yang merangkumi maklumat umur, jantina, tempoh langganan (*tenure*), kekerapan penggunaan, panggilan sokongan, kelewatan pembayaran, jenis langganan, dan jumlah perbelanjaan[cite: 8].
* **Pra-pemprosesan & Pembersihan Data:** 
  * Mengisi nilai kosong (*missing values*) pada ciri berangka menggunakan nilai min dan ciri kategori menggunakan mod[cite: 8].
  * Membahagikan data kepada set latihan (*train*) dan ujian (*test*) pada nisbah 80:20 menggunakan `train_test_split`[cite: 8].
* **Pengekodan Ciri (*Feature Encoding*):**
  * Pengekodan binari untuk ciri `Gender` (Lelaki/Perempuan)[cite: 8].
  * Pengekodan ordinal (`OrdinalEncoder`) untuk ciri peringkat seperti `Subscription Type` dan `Contract Length`[cite: 8].
* **Model Pembelajaran Mesin:** Menggunakan algoritma *Random Forest Classifier* dengan kriteria Gini dan kedalaman maksimum `max_depth=4`[cite: 8].

---

## **2. Struktur Kod & Aliran Kerja**
1. **Pemuatan Pustaka & Data:** Mengimport modul penting seperti `pandas`, `numpy`, `matplotlib`, serta memuatkan fail `customer_churn.csv` menggunakan pembatas `;`[cite: 8].
2. **Penerokaan Data (EDA):** Menyemak bentuk data, maklumat lajur, serta taburan kelas sasaran (`Churn`) menggunakan fungsi seperti `df.info()`, `df.shape`, dan `value_counts()`[cite: 8].
3. **Penyediaan & Pembahagian Data:** Membuang kolum pengecam unik seperti `CustomerID` serta memisahkan data kepada ciri input dan pemboleh ubah sasaran[cite: 8].
4. **Pengendalian Nilai Kosong:** Mengira nilai min dan mod bagi data latihan, kemudian melakukan imputasi pada kedua-dua set latihan dan ujian[cite: 8].
5. **Latihan & Ramalan Model:** Melatih model `RandomForestClassifier` menggunakan ciri yang telah dikodkan dan melakukan ramalan ke atas set ujian[cite: 8].
6. **Evaluasi Model:** Menilai prestasi model menggunakan `classification_report` untuk mendapatkan metrik *precision*, *recall*, dan *f1-score*[cite: 8].

---

## **3. Keperluan Sistem & Pustaka**
Pastikan pustaka Python berikut telah dipasang sebelum menjalankan kod:
```bash
pip install pandas numpy matplotlib scikit-learn
