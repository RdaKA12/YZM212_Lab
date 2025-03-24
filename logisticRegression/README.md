# Titanic Hayatta Kalma Tahmini - Logistic Regression Uygulaması

Bu proje, Titanic veri setini kullanarak yolcu hayatta kalma durumunun (Survived) tahminini gerçekleştirmeyi amaçlar. Logistic Regression algoritması, hem scikit-learn kütüphanesi kullanılarak hem de manuel yöntemlerle uygulanmış olup modelin performansı çeşitli metrikler (accuracy, precision, recall...) üzerinden değerlendirilmiştir.

## Proje İçeriği

### Titanic-Dataset.xlsx:
Titanic veri setini içeren Excel dosyası. Dosya, yolculara ait özellikler (Pclass, Sex, Age, SibSp, Parch, Fare, Embarked, vb.) ve hedef değişken olan "Survived" (0: Hayatta kalmadı, 1: Hayatta kaldı) bilgilerini barındırmaktadır.

#### logisticRegression.ipynb:
Logistic Regression algoritmasının uygulanması, veri ön işleme, model eğitimi, test edilmesi ve performans değerlendirmesi adımlarını içeren Jupyter Notebook dosyası.

Notebook içerisinde:

Veri setinin yüklenmesi ve temizlenmesi,

Eksik verilerin tamamlanması, kategorik verilerin kodlanması,

Modelin scikit-learn kullanılarak ve manuel yöntemle eğitilmesi,

Modelin çalışma süresi ölçümleri ile birlikte değerlendirilmesi yer almaktadır.

## Veri Seti ve Önişleme Adımları

Özellikler (Features):
Yolcuların sınıfı (Pclass), cinsiyeti (Sex), yaşı (Age), aile bilgileri (SibSp, Parch), bilet ücreti (Fare) ve binilen liman (Embarked) gibi özellikler.

Hedef Değişken (Target):
Her yolcunun hayatta kalma durumu (Survived: 0 veya 1).

Önişleme adımları:
Eksik değerler uygun yöntemlerle (sürekli değişkenler için ortalama, kategorik için mod) tamamlanmıştır.

Kategorik veriler modelin gereksinimlerine uygun şekilde kodlanmıştır.

Gerekirse özellik ölçeklendirme ve seçimi adımları uygulanmıştır.

Model Eğitimi ve Değerlendirme
Logistic Regression modeli iki aşamada ele alınmıştır:

Model Eğitimi:

Veri seti, eğitim ve test olarak bölünmüştür.

Model, scikit-learn kütüphanesi kullanılarak veya custom model ile oluşturulmuş fit metodu ile eğitilmiştir.

Eğitim sırasında modelin maksimum likelihood estimation (MLE) ve gradient descent temelli cost function üzerinden optimize edilmesi sağlanmıştır.

Model Testi ve Performans Ölçümü:

Eğitilen model predict metodu ile test verileri üzerinde tahminler yapmıştır.

Model performansı karmaşıklık matrisi (confusion matrix), accuracy, precision, recall ve ROC-AUC gibi metriklerle değerlendirilmiştir.

Eğitim ve test işlemlerinin çalışma süreleri time modülüyle ölçüşlmüştür.

## Sonuçlar
Doğruluk (Accuracy): Modelin genel sınıflandırma başarısı raporlanmıştır.

Hassasiyet (Precision) & Duyarlılık (Recall): Özellikle hayatta kalan sınıf için metrikler hesaplanarak modelin performansı analiz edilmiştir.

Çalışma Süresi: scikit-learn uygulaması ile modelin eğitim ve test süreleri karşılaştırılmıştır.

Bu sonuçlar, modelin Titanic veri seti üzerinde uygulanabilirliğini ve farklı yaklaşımlar arasındaki performans farklarını ortaya koymaktadır.

## Gereksinimler
Projede kullanılan temel Python kütüphaneleri:

Python (3.x)

NumPy

Pandas

Matplotlib

Scikit-learn

Gerekli tüm paketler, Requirements.txt dosyasında listelenmiştir.

## Çalıştırma Adımları
Projeyi GitHub deposundan klonlayın veya ilgili dosyaları indirin.

Gerekli Python kütüphanelerini pip install -r Requirements.txt komutu ile yükleyin.

Jupyter Notebook'u açarak logisticRegression.ipynb dosyasını çalıştırın.

Notebook içerisinde yer alan hücreleri sırasıyla çalıştırarak model eğitimi, test ve performans değerlendirme adımlarını izleyin.

## Kişisel Yorum ve Tartışma

Model Performansı:
Logistic Regression, Titanic veri setinde belirgin özelliklere dayalı olarak hayatta kalma tahmininde makul bir doğruluk oranı sağlamaktadır.

Ön İşleme ve Özellik Mühendisliği:
Veri setindeki eksik veriler ve kategorik özellikler uygun şekilde işlendikten sonra model performansında iyileşmeler gözlemlenmiştir.

Uygulama Kolaylığı:
scikit-learn kullanılarak geliştirilen model, eğitim ve test süreçlerinde daha optimize sonuçlar verirken, manuel yöntem algoritmanın detaylarını anlamak açısından bir öğrenme süreci sunmuştur.

##Arda Karakaş - 23291414

