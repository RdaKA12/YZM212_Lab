# Naive Bayes

## Proje: 
Gaussian Naive Bayes algoritması kullanılarak inme (stroke) tahmini yapılmaktadır. Projede Python ve scikit-learn kütüphanesi kullanılarak iki farklı Jupyter Notebook içerisinde model eğitim, değerlendirme ve sonuç görselleştirme işlemleri gerçekleştirilmiştir.

## Veri Seti:
Bu verisetinde, inme (stroke) tahmini amacıyla toplanmış hasta bilgileri bulunmaktadır. Aşağıda verisetinde yer alan başlıklarıntanımlamaları yer almaktadır.

ID: Her hastayı benzersiz şekilde tanımlayan numara.
Gender (Cinsiyet): Hastanın cinsiyet bilgisi (örneğin, male, female veya diğer kategoriler).
Age (Yaş): Hastanın yaşı.
Hypertension (Hipertansiyon): Hastanın yüksek tansiyon durumu; genellikle 0 (yok) veya 1 (var) olarak kodlanır.
Heart Disease (Kalp Hastalığı): Kalp hastalığı öyküsünün varlığı; 0 veya 1 şeklinde gösterilir.
Ever Married (Evlenmiş mi): Hastanın evlilik durumunu belirten bir sütun (örneğin, evli veya bekar).
Work Type (Çalışma Türü): Hastanın çalışma şekli veya mesleki durumu (özel, devlet, serbest meslek vb.).
Residence Type (Yaşam Alanı): Hastanın yaşadığı yerin türü (kentsel veya kırsal).
Avg Glucose Level (Ortalama Glukoz Seviyesi): Kan şekeri düzeyine ilişkin ortalama değer.
BMI (Vücut Kitle İndeksi): Hastanın beden kitle indeksini gösterir.
Smoking Status (Sigara Kullanım Durumu): Hastanın sigara kullanıp kullanmadığı bilgisi.
Stroke (İnme): Hedef değişken; hastanın inme geçirme durumunu belirler (örneğin, 0 inme geçirmemiş, 1 inme geçirmiş).

## Sonuçlar 

### SKlearn kütüphanesiyle elde edilen sonuçlar:
Scikit-Learn Modeli Eğitim Süresi: 0.004120 sn
Scikit-Learn Modeli Tahmin Süresi: 0.001349 sn
Scikit-Learn Modeli Doğruluk Oranı: 0.5719858156028369
Scikit-Learn Karmaşıklık Matrisi:
 [[ 187 1203]
 [   4 1426]]
 
### Pythın ile yazılan model ile elde edilen sonuçlar:
Custom Model Eğitim Süresi: 0.001268 sn
Custom Model Tahmin Süresi: 0.068243 sn
Custom Model Doğruluk Oranı: 0.5719858156028369
Custom Model Karmaşıklık Matrisi:
 [[ 187 1203]
 [   4 1426]]

 ## Yorum:
 Gaussian Naive Bayes, kolay uygulanabilir ve hızlı sonuçlar veren bir başlangıç modeli olarak tercih edilebilir. Ancak, verinin doğası ve varsayımların sağlanmaması nedeniyle elde edilen %60 civarındaki doğruluk oranı, modelin karmaşık yapıyı yakalamada yetersiz kalabileceğini göstermektedir. Bu durumda, veri ön işleme adımlarını gözden geçirmek, farklı özellik mühendisliği teknikleri uygulamak veya daha gelişmiş modellerle çalışmak performansı artırabilir.

 23291414-Arda Karakaş
 
 
