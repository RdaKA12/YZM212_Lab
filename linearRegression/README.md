# Linear Regression – Study Hours vs Exam Scores

Bu README dosyası, YZM212 Makine Öğrenmesi Dersi IV. Laboratuvar Ödevi kapsamında hazırlanan **Linear Regression** projesini içerir. Aşağıda adım adım uygulanan yöntemler, kod yapısı ve elde edilen sonuçlar özetlenmiştir.

---

## 1. Proje Amacı

Basit bir veri kümesi üzerinde **Linear Regression** modellerini  
1. **Kapalı form Ordinary Least Squares (OLS)**  
2. **scikit-learn `LinearRegression`**  
yaklaşımlarıyla eğitmek ve performanslarını **Mean Squared Error (MSE)** ile karşılaştırmak.

---

## 2. Veri Kümesi

**Dosya:** `study_hours_scores.csv`

| Hours | Scores |
| ----- | ------ |
| 2.5   | 21     |
| 5.1   | 47     |
| …     | …      |
| 7.8   | 86     |

- **Özellik (X):** Günlük çalışma saati  
- **Hedef (y):** Sınavdan alınan not  

Toplam **25** örnek içerir.

---

## 3. Kullanılan Yöntemler

### 3.1. Ordinary Least Squares (Kapalı Form)

- **Formül:**  
  \[
    \hat{\boldsymbol\theta} = (X^T X)^{-1} X^T y
  \]

- **Adımlar:**  
  1. Gözlem matrisine (X) sabit terim (bias) için 1’ler sütunu ekleme  
  2. Yukarıdaki denklemi uygulayıp \(\theta\) parametrelerini elde etme  
  3. Tahminler, MSE ve regresyon doğrusunun görselleştirilmesi  

**Notebook:** `LinearRegressionWLSE.ipynb`

---

### 3.2. Scikit-learn `LinearRegression`

- scikit-learn altyapısında **SVD** tabanlı sayısal çözüm  
- `fit(X, y)` ile parametreleri öğrenme,  
- `predict(X)` ile tahmin  
- MSE karşılaştırması ve görselleştirme  

**Notebook:** `LinearRegressionWSLearn.ipynb`

---

## 4. Karşılaştırma ve Sonuçlar

| Metod            | Bias (θ₀) | Ağırlık (θ₁) | MSE   |
|------------------|-----------|--------------|--------|
| Kapalı Form OLS  | 3.85      | 9.78         | 20.17  |
| Scikit-learn     | 3.85      | 9.78         | 20.17  |

- Her iki yöntemde de **aynı** parametreler ve MSE elde edilmiştir.  
- Görsel karşılaştırma için `LinearRegressionComparison.ipynb` içindeki tek grafik üzerinden de doğrulama yapılabilir.

---

## 5. Çalıştırma Talimatı

1. Gerekli kütüphaneleri yükleyin:
    ```bash
    pip install -r requirements.txt
    ```
2. Jupyter Notebook ortamında projenin kök klasörünü açın.  
3. Aşağıdaki dosyaları sırasıyla çalıştırın:
    - `LinearRegressionWLSE.ipynb`  
    - `LinearRegressionWSLearn.ipynb`  
    - (Opsiyonel) `LinearRegressionComparison.ipynb`  

---

## 6. Dosya Yapısı

```
LinearRegression/
├── study_hours_scores.csv
├── LinearRegressionWLSE.ipynb
├── LinearRegressionWSLearn.ipynb
├── LinearRegressionComparison.ipynb
├── requirements.txt
└── README.md
```

---

## 7. Kaynaklar

- scikit-learn Documentation – [LinearRegression](https://scikit-learn.org/stable/modules/linear_model.html#ordinary-least-squares)  
- Géron, *Hands-On Machine Learning with Scikit-Learn, Keras & TensorFlow*

---

_Arda Karakaş – 23291414_
