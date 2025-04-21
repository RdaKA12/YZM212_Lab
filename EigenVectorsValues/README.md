# EigenVectorsValues Ödev Raporu

Bu README dosyası, YZM212 Makine Öğrenmesi Dersi III. Laboratuvar Ödevini içermektedir.


## 1. Matris Manipülasyonu ile Özdeğer ve Özvektörlerin Makine Öğrenmesindeki İlişkisi

### a) Temel Tanımlar
- **Matris (Matrix):** Sayıları satır ve sütun düzeninde organize eden iki boyutlu yapı. Veri kümelerini (örnek × özellik) temsil eder ve lineer dönüşümler, projeksiyonlar gibi işlemlerin temelini oluşturur.
- **Özdeğer (Eigenvalue, λ):** A kare matris için A·v = λ·v denkleminde vektörü skaler olarak büyüten veya küçülten değerdir. Bir matrisin kuvvetli yönelimlerini nicelendirir.
- **Özvektör (Eigenvector, v):** A·v = λ·v eşitliğini sağlayan, matris dönüşümü altında yalnızca ölçeklenen (yönü değişmeyen) vektördür.

### b) Makine Öğrenmesindeki Kullanım Alanları
1. **Principal Component Analysis (PCA):** Kovaryans matrisinin özdekompozisyonuyla veri içindeki en yüksek varyansa sahip doğrultuları (ana bileşenleri) bularak boyut indirgeme yapar ve gürültüyü azaltır.
2. **Singular Value Decomposition (SVD):** Veri matrisini U·Σ·Vᵀ’ye ayırarak tekil değerler üzerinden varyans dağılımını inceler. Öneri sistemleri, gürültü azaltma ve düşük-rank yaklaşımlarında kullanılır.
3. **Spektral Kümeleme (Spectral Clustering):** Laplasyan matrisinin küçük özdeğerlerine karşılık gelen özvektörlerden oluşturulan gömme uzayında kümeleri belirler. Karmaşık geometrili verilerde etkili sonuç verir.
4. **Kernel PCA:** Lineer olmayan veri yapılarında özdekompozisyonu kernel fonksiyonları aracılığıyla gerçekleştirerek doğrusal olmayan boyut indirgeme sağlar.
5. **Linear Discriminant Analysis (LDA):** Sınıflar arası ayrımı maksimize eden doğrultuları bulmak için sınıf içi ve sınıflar arası kovaryans matrislerinin özdekompozisyonunu kullanır.
6. **Markov Zincirleri & PageRank:** Geçiş matrislerinin özvektörleri, durağan dağılımları ve PageRank skorlarını belirler; grafik tabanlı öğrenme ve sıralama algoritmalarında kullanılır.
7. **Graf Gömme (Graph Embedding):** Grafik Laplasyan matrisinin özdekompozisyonu, düğümlerin düşük boyutlu temsillerini öğrenmede kullanılır (örneğin Laplacian Eigenmaps).


## 2. NumPy’nin `linalg.eig` Fonksiyonunun İncelenmesi

```python
eigenvalues, eigenvectors = numpy.linalg.eig(a)
```

- **Parametre:**
  - `a`: (..., M, M) boyutlu kare matris veya matris yığını.
- **Dönüş:**
  - `eigenvalues`: (..., M) boyutlu dizi — Özdeğerler.
  - `eigenvectors`: (..., M, M) boyutlu dizi — Sağ özvektörler.

### 2.1. İşleyiş Adımları
1. **Python Katmanı:** `numpy.linalg.eig` çağrısı `_umath_linalg.eig` C/Fortran uzantısına köprü kurar.
2. **LAPACK Rutinleri:** DGEEV/ZGEEV algoritmaları çalışır:
   - **Dengeleme (Balancing):** Ölçekleme ile sayısal kararlılığı iyileştirir.
   - **Hessenberg Formuna İndirgeme:** Householder yansımalarıyla gerçekleştirir.
   - **QR İterasyonu & Schur Ayrışımı:** Özdeğerler bulunur.
   - **Özvektörlerin Rekonstrüksiyonu:** Orijinal uzaya geri dönülür.
3. **Normalize Etme:** Özvektörler birim uzunlukta sonuçlanır.

### 2.2. Hata Durumu
- `LinAlgError`: Hesaplama yakınsama gerçekleştiremezse fırlatılır.


## 3. Özdeğer Hesaplamalarının Karşılaştırılması

### 3.1. Problem Tanımı
- **Matris:**
  ```python
  A = [[6, 1, -1],
       [0, 7,  0],
       [3, -1, 2]]
  ```
- **Amaç:**
  1. **Manuel Yöntem:** Lucas BN’in karakteristik polinom köklerini hesaplayan implementasyonunu kullanmak.
  2. **NumPy Yöntemi:** `np.linalg.eig` fonksiyonunu uygulayıp sonuçları karşılaştırmak.

### 3.2. Karşılaştırma Sonuçları
- **Manuel Yöntem (`find_eigenvalues`):** `[5. 3. 7.]` değerleri elde edildi.
- **NumPy Yöntemi:**
  ```python
  import numpy as np
  from numpy.linalg import eig

  A = np.array([[6,1,-1],[0,7,0],[3,-1,2]], dtype=float)
  w, v = eig(A)
  print(w)  # [5. 3. 7.]
  ```
- **Özvektörler:** Her iki yöntemde de normalize edilmiş ve yönsel olarak eşleşen vektörler bulundu.

**Sonuç:** Manuel polinom tabanlı hesaplama ile NumPy’nın LAPACK tabanlı `eig` fonksiyonu, hem özdeğer hem de özvektör sonuçlarında tam uyum göstermiştir.

---

## Kaynaklar

1. Machine Learning Mastery, “Introduction to matrices for machine learning” (Erişim: 21 Nisan 2025) – https://machinelearningmastery.com/introduction-matrices-machine-learning/
2. Machine Learning Mastery, “Introduction to eigendecomposition, eigenvalues and eigenvectors” (Erişim: 21 Nisan 2025) – https://machinelearningmastery.com/introduction-to-eigendecomposition-eigenvalues-and-eigenvectors/
3. NumPy Documentation: `numpy.linalg.eig` (Erişim: 21 Nisan 2025) – https://numpy.org/doc/stable/reference/generated/numpy.linalg.eig.html
4. Lucas BN, “Eigenvalues and Eigenvectors” GitHub Repo (Erişim: 21 Nisan 2025) – https://github.com/LucasBN/Eigenvalues-and-Eigenvectors
5. scikit-learn Documentation, “Kernel PCA” (Erişim: 21 Nisan 2025) – https://scikit-learn.org/stable/modules/kernel_pca.html
6. scikit-learn Documentation, “Linear Discriminant Analysis” (Erişim: 21 Nisan 2025) – https://scikit-learn.org/stable/modules/lda_qda.html
7. Wikipedia, “PageRank” (Erişim: 21 Nisan 2025) – https://en.wikipedia.org/wiki/PageRank
8. Wikipedia, “Laplacian eigenmaps” (Erişim: 21 Nisan 2025) – https://en.wikipedia.org/wiki/Laplacian_eigenmap

### Arda Karakaş - 23291414
