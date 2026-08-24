# 🧠 Beyin Kanseri Görsel Sınıflandırma (CNN)

Bu proje, Kaggle üzerindeki **Multi-Cancer Dataset** verisini kullanarak beyin tarama görsellerini analiz eden ve sınıflandıran bir **Evrişimli Sinir Ağı (CNN)** derin öğrenme modelidir.

---

## 📌 Proje Özeti

* **Veri Seti:** Multi Cancer / Brain Cancer
* **Girdi Boyutu:** 150x150 Piksel (RGB)
* **Mimari:** 3x Conv2D + MaxPooling2D, Flatten, Dense (512), Softmax Output
* **Model Dosyası:** `image_classifier.h5`

---

## 🛠️ Kullanılan Teknolojiler

* **Python 3.x**
* **TensorFlow / Keras** (Model mimarisi ve eğitimi)
* **NumPy** (Veri manipülasyonu)
* **Matplotlib** (Tahminlerin görselleştirilmesi)

---

## 🏗️ Model Mimarisi

Model, öznitelik çıkarma (feature extraction) ve sınıflandırma olmak üzere iki ana bölümden oluşur:

| Katman | Tip | Özellikler / Boyut |
| --- | --- | --- |
| **Input** | Girdi Katmanı | (150, 150, 3) Görsel |
| **Conv2D_1** | Evrişim Katmanı | 32 Filtre, 3x3 Çekirdek, ReLU |
| **MaxPool_1** | Havuzlama | 2x2 Ortaklama |
| **Conv2D_2** | Evrişim Katmanı | 64 Filtre, 3x3 Çekirdek, ReLU |
| **MaxPool_2** | Havuzlama | 2x2 Ortaklama |
| **Conv2D_3** | Evrişim Katmanı | 128 Filtre, 3x3 Çekirdek, ReLU |
| **MaxPool_3** | Havuzlama | 2x2 Ortaklama |
| **Flatten** | Düzleştirme | Vektör dönüşümü |
| **Dense_1** | Tam Bağlantılı | 512 Nöron, ReLU |
| **Dense_2** | Çıkış Katmanı | Sınıf sayısı kadar nöron, Softmax |

---

## 🚀 Kurulum ve Çalıştırma

### 1. Depoyu Klonlayın ve Bağımlılıkları Yükleyin

```bash
git clone https://github.com/kullanici-adi/proje-adi.git
cd proje-adi
pip install tensorflow numpy matplotlib

```

### 2. Veri Seti Yolunu Belirleyin

`main.py` (veya ilgili notebook) içerisindeki `veriyolu` değişkenini yerel veri dizininize göre güncelleyin:

```python
veriyolu = "/path/to/Brain Cancer"

```

### 3. Eğitimi Başlatın ve Tahmin Yapın

Kodu çalıştırdığınızda model 10 epoch boyunca eğitilecek ve `image_classifier.h5` olarak kaydedilecektir. Test görselleri üzerinde tahmin yürütmek için `gercek_deger` fonksiyonu kullanılır:

```python
# Örnek görsel tahmini ve görselleştirmesi
gercek_deger("test_gorseli.jpg", model, train_generator.class_indices)

```

---
