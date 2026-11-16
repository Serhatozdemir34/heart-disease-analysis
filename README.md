# Kalp Hastalığı Tespiti: Uçtan Uca Makine Öğrenmesi Projesi 🫀📊

Bu proje, kalp hastalığı veri seti üzerinde **Keşifsel Veri Analizi (EDA)**, kapsamlı **Veri Ön İşleme**, **Özellik Mühendisliği (Feature Engineering)** ve **Makine Öğrenmesi (Machine Learning)** modellerinin gelişimini içeren uçtan uca bir sınıflandırma projesidir.

Proje kapsamında veriler analize hazır hale getirilmiş, Random Forest ve Gradient Boosting algoritmaları eğitilmiş ve en başarılı model dışa aktarılarak saklı veri (holdout) üzerinde test edilmiştir.

## 🚀 Kullanılan Teknolojiler ve Kütüphaneler
* **Veri İşleme ve Analiz:** `Pandas`, `NumPy`
* **Veri Görselleştirme:** `Matplotlib`, `Seaborn`
* **Makine Öğrenmesi & Ön İşleme:** `Scikit-Learn` (MinMaxScaler, LabelEncoder, RandomForestClassifier, GradientBoostingClassifier).
* **Model Kaydetme:** `Joblib`

## 📂 Proje Adımları

### 1. Veri Ön İşleme (Data Preprocessing)[cite: 14]
* **Eksik Veri Yönetimi:** `Cholesterol` sütunundaki '0' değerleri eksik veri olarak kabul edilip NaN değerine dönüştürüldü ve sütun ortalaması ile dolduruldu.
* **Aykırı Değer Temizliği:** Sayısal sütunlarda Z-Skoru (Z > 3) hesaplanarak gürültülü ve aykırı veriler (28 satır) temizlendi.
* **Kategorik Veri Dönüşümü:** Kategorik değişkenler `LabelEncoder` kullanılarak sayısal formata dönüştürüldü.
* **Normalizasyon:** Modellerin performansını artırmak için özellikler `MinMaxScaler` ile 0-1 aralığına ölçeklendi.

### 2. Özellik Mühendisliği (Feature Engineering)
* Hastaların yaşlarına göre anlamlı bir öznitelik oluşturmak amacıyla **Age_Category** (0: Genç, 1: Orta, 2: Yaşlı) isimli yeni bir sütun türetildi.

### 3. Makine Öğrenmesi ve Modelleme.
Veri seti, modelin gerçek dünya performansını ölçmek amacıyla %10 Holdout (Saklı Veri) ve %90 Eğitim-Test (%80 Train, %20 Test) olacak şekilde iki aşamalı olarak bölündü.

Kullanılan Modeller:
* **Random Forest Classifier:** 5 katlı Çapraz Doğrulama (Cross Validation) ile eğitildi ve model değerlendirildi.
* **Gradient Boosting Classifier:** Yüksek tahmin gücü için hiperparametreler ayarlanarak (n_estimators=100, learning_rate=0.1) eğitildi. Sınıf bazlı performansları Karmaşıklık Matrisi (Confusion Matrix) ve F1-Score grafikleri ile görselleştirildi.

### 4. Final Sonuçları ve Model Kaydı
* Geliştirilen **Gradient Boosting** modeli `kalp_modeli_gb.pkl` dosyası olarak kaydedildi.
* Model, daha önce hiç görmediği Holdout (Saklı Veri) setine uygulanarak **%91 oranında final doğruluğu (Accuracy)** elde etti.
* Tahmin sonuçları `tahmin_sonuclari.csv` olarak dışa aktarıldı.

## 💻 Nasıl Çalıştırılır?
1. Repoyu bilgisayarınıza klonlayın:
   ```bash
   git clone [https://github.com/Serhatozdemir34/heart-disease-analysis.git](https://github.com/Serhatozdemir34/heart-disease-analysis.git)
