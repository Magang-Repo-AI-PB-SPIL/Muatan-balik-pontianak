# Prediksi Muatan Balik Menggunakan Model Sequence
## 📌 Deskripsi
Repositori ini berisi model dan hasil eksperimen untuk memprediksi muatan balik pada berbagai jenis barang.
Proyek ini menggunakan tiga arsitektur model populer dengan 3 sequence:

LSTM (Long Short-Term Memory)

GRU (Gated Recurrent Unit)

RNN (Recurrent Neural Network)

Setiap model dilatih untuk setiap jenis barang, lalu dipilih dua model terbaik berdasarkan performa pengujian (R² testing) dengan mempertimbangkan juga R² validation dan R² training.


---

## 🔍 Metodologi
1. **Preprocessing Data**  
   - Data dimuat, dibersihkan, dan dipisahkan berdasarkan kategori barang (`col_0`, `col_1`, ..., `col_14`)  
   - Normalisasi dan pembentukan sequence dilakukan agar cocok untuk model RNN, LSTM, dan GRU  

2. **Training Model**  
   - Setiap barang dilatih menggunakan ketiga model sequence  
   - Parameter yang di-tuning:
     - Optimizer
     - Learning rate
     - Batch size

3. **Evaluasi Model**  
   - Metrik yang digunakan:
     - `R² training`
     - `R² validation`
     - `R² testing`
   - Model diurutkan berdasarkan `R² testing`, lalu `R² validation`, lalu `R² training`  

4. **Seleksi Model Terbaik**  
   - Untuk setiap barang, dipilih **dua model terbaik**  
   - Model terbaik disimpan dalam format `.keras` untuk digunakan pada tahap deployment  

---

## 📊 Format Laporan
Setiap hasil training disimpan sebagai file **Excel (.xlsx)** dengan kolom:
- **model** → Jenis model (`lstm`, `gru`, `rnn`)
- **optimizer**
- **learning rate**
- **batch size**
- **r2 training**
- **r2 validation**
- **r2 testing**


## 🚀 Cara Menjalankan
1. **Kloning repositori**
   ```bash
   git clone https://github.com/username/nama-repo.git
   cd nama-repo
