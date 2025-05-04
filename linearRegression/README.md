# Linear Regression 

Bu README dosyası, YZM212 Makine Öğrenmesi Dersi IV. Laboratuvar Ödevi kapsamında hazırlanmış olan Linear Regression projesinin California Housing veri kümesi ile uygulanmış versiyonudur.

---

## 1. Proje Amacı

Bu projede amaç, **California Housing** veri kümesinde **ortalama oda sayısı (Rooms)** ile **medyan ev fiyatı (Price)** arasındaki ilişkiyi iki farklı yöntemle incelemek:

1. **Ordinary Least Squares (Kapalı Form)**
2. **scikit-learn `LinearRegression`**

Her iki yöntemin başarıları **Mean Squared Error (MSE)** ile ölçülmüş ve grafikle karşılaştırılmıştır.

---

## 2. Veri Kümesi

**Dosya:** `california_rooms_price.csv`

| Rooms (AveRooms) | Price (MedHouseVal) |
|------------------|---------------------|
| 6.984127         | 4.526               |
| 6.238137         | 3.585               |
| …                | …                   |

- Veri, `sklearn.datasets.fetch_california_housing` fonksiyonundan elde edilmiştir.
- Yaklaşık 20.000 satırlık gerçekçi bir konut veri kümesidir.

---

## 3. Kullanılan Yöntemler

### 3.1. Ordinary Least Squares (Kapalı Form)

- Matematiksel Formül:  
  \[
    \hat{\boldsymbol\theta} = (X^T X)^{-1} X^T y
  \]

- Adımlar:
  1. Bias terimi için 1 sütunu eklenir.
  2. Yukarıdaki formülle \(	heta\) parametreleri hesaplanır.
  3. MSE değeri ve regresyon doğrusu çizilir.

**Notebook:** `CaliforniaRegressionOLS.ipynb`

---

### 3.2. Scikit-learn `LinearRegression`

- `fit(X, y)` ile model eğitilir.
- `predict(X)` ile tahminler yapılır.
- `mean_squared_error(y, y_pred)` ile MSE hesaplanır.

**Notebook:** `CaliforniaRegressionSklearn.ipynb`

---

### 3.3. Karşılaştırma

| Yöntem          | Bias (θ₀) | Ağırlık (θ₁) | MSE (örnek) |
|------------------|------------|---------------|-------------|
| Kapalı Form (OLS)| ~0.23      | ~0.12         | ≈ 0.51      |
| Scikit-learn     | ~0.23      | ~0.12         | ≈ 0.51      |

> Gerçek sonuçlar için notebook'taki hücreleri çalıştırınız.

**Notebook:** `CaliforniaRegressionComparison.ipynb`

---

## 4. Çalıştırma Talimatı

1. Gerekli Python kütüphanelerini yükleyin:
    ```bash
    pip install -r requirements.txt
    ```

2. `jupyter notebook` komutuyla arayüzü başlatın.

3. Sırasıyla şu dosyaları çalıştırın:
    - `CaliforniaRegressionOLS.ipynb`
    - `CaliforniaRegressionSklearn.ipynb`
    - `CaliforniaRegressionComparison.ipynb`

---

## 5. Dosya Yapısı

```
CaliforniaRegression/
├── california_rooms_price.csv
├── CaliforniaRegressionOLS.ipynb
├── CaliforniaRegressionSklearn.ipynb
├── CaliforniaRegressionComparison.ipynb
├── requirements.txt
└── README.md
```

---

## 6. Kaynaklar

- scikit-learn Documentation – [LinearRegression](https://scikit-learn.org/stable/modules/linear_model.html)
- California Housing Dataset – [sklearn.datasets.fetch_california_housing](https://scikit-learn.org/stable/modules/generated/sklearn.datasets.fetch_california_housing.html)

---

_Arda Karakaş – 23291414_
