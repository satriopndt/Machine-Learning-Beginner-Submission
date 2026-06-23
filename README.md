# ✂️🪨📄 Rock-Paper-Scissors Image Classification

Submission proyek **Machine Learning untuk Pemula** — membangun model *Convolutional Neural Network* (CNN) untuk mengklasifikasikan gambar tangan ke dalam 3 kelas: **Batu (Rock)**, **Gunting (Scissors)**, dan **Kertas (Paper)**.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/satriopndt/Machine-Learning-Beginner-Submission/blob/main/Machine_Learning_Beginner.ipynb)

---

## 📁 Dataset

Menggunakan dataset **Rock-Paper-Scissors** dari [Dicoding Assets](https://github.com/dicodingacademy/assets/releases/download/release/rockpaperscissors.zip), berisi ribuan gambar tangan dengan 3 kelas (rock, paper, scissors).

---

## 🧠 Arsitektur Model

Model dibangun menggunakan `tf.keras.Sequential` dengan struktur:

```
Conv2D(8, 3x3) → MaxPooling2D
Conv2D(16, 3x3) → MaxPooling2D
Conv2D(32, 3x3) → MaxPooling2D
Flatten
Dense(150, relu)
Dense(60, relu)
Dense(3, softmax)
```

**Konfigurasi training:**
- Optimizer: `Adadelta` (learning rate `1e-3`)
- Loss function: `categorical_crossentropy`
- Callback: `EarlyStopping` (memantau `val_accuracy`, patience 16)
- Image augmentation via `ImageDataGenerator` (rotation, shift, shear, horizontal flip)
- Ukuran gambar input: `180x120`, split data training/validation: `60/40`

---

## 🔍 Tahapan

1. **Persiapan Data** — Download & ekstrak dataset, mount Google Drive.
2. **Image Augmentation** — Menggunakan `ImageDataGenerator` untuk memperbanyak variasi data training dan mengurangi overfitting.
3. **Pembuatan Model CNN** — Susunan layer convolution & pooling bertingkat untuk ekstraksi fitur gambar.
4. **Training Model** — Dilatih dengan `model.fit()` menggunakan data generator.
5. **Prediksi Gambar Baru** — Upload gambar tangan baru lewat Colab untuk diuji langsung ke model yang sudah dilatih.

---

## 🛠️ Tech Stack

- **Python**
- **TensorFlow / Keras** — pembangunan & training model CNN
- `ImageDataGenerator` — augmentasi gambar
- **Google Colab** — environment & GPU runtime
- `matplotlib` — visualisasi hasil prediksi

---

## 🚀 Cara Menjalankan

1. Buka notebook langsung di Google Colab lewat badge di atas, **atau** clone repo:
   ```bash
   git clone https://github.com/satriopndt/Machine-Learning-Beginner-Submission.git
   ```
2. Jalankan seluruh cell secara berurutan (disarankan menggunakan runtime GPU di Colab: **Runtime → Change runtime type → GPU**).
3. Pada cell terakhir, upload gambar tangan (batu/gunting/kertas) untuk melihat hasil prediksi model.

---

## 🧩 Catatan

- Beberapa cell di notebook ini merupakan hasil eksperimen ulang (re-run definisi model & compile) saat proses tuning — bisa disederhanakan jika ingin notebook lebih ringkas.

---

## 👤 Author

**Satrio** — [@satriopndt](https://github.com/satriopndt)
