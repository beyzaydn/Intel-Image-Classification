# Akbank Derin Öğrenme Bootcamp: Görüntü Sınıflandırma Projesi

Bu proje, Akbank Derin Öğrenme Bootcamp'i kapsamında, Evrişimli Sinir Ağları (CNN) kullanılarak bir görüntü sınıflandırma modelinin geliştirilmesini içermektedir.

## Projenin Amacı

Projenin temel amacı, verilen bir görüntü veri setini kullanarak yüksek başarımlı bir sınıflandırma modeli eğitmek ve modelin karar verme süreçlerini yorumlamaktır. Bu süreçte veri ön işleme, veri çoğaltma (data augmentation), model tasarımı, model eğitimi, hiperparametre optimizasyonu ve model değerlendirme gibi derin öğrenme proje adımları pratik olarak uygulanmıştır.

## Veri Seti Hakkında Bilgi

Bu projede **Intel Image Classification** veri seti kullanılmıştır. Veri seti, doğal sahnelere ait 6 farklı sınıftan oluşmaktadır:
* Binalar (Buildings)
* Orman (Forest)
* Buzul (Glacier)
* Dağ (Mountain)
* Deniz (Sea)
* Cadde (Street)

Veri seti, yaklaşık 25.000 eğitim ve 14.000 test görüntüsü içermektedir. Tüm görüntüler model için 150x150 piksel boyutuna getirilmiştir.

## Kullanılan Yöntemler

* **Veri Ön İşleme:** Görüntülerin piksel değerleri [0, 1] aralığına normalize edilmiştir.
* **Veri Çoğaltma (Data Augmentation):** Modelin genelleme yeteneğini artırmak ve ezberlemesini (overfitting) önlemek amacıyla eğitim verisine `ImageDataGenerator` kullanılarak rastgele döndürme, yakınlaştırma ve yatay çevirme gibi dönüşümler uygulanmıştır.
* **Model Mimarisi:** Keras Fonksiyonel API'si kullanılarak 3 adet Evrişim (Conv2D) ve Havuzlama (MaxPooling2D) bloğu içeren bir CNN mimarisi oluşturulmuştur. Modelde ezberlemeyi önlemek amacıyla `Dropout` katmanı da bulunmaktadır.
* **Model Değerlendirme:** Modelin performansı; doğruluk/kayıp (accuracy/loss) grafikleri, sınıflandırma raporu (classification report) ve karışıklıklık matrisi (confusion matrix) ile detaylı olarak analiz edilmiştir.
* **Model Yorumlanabilirliği:** Modelin karar anında bir görüntüde nereye "odaklandığını" anlamak için **Grad-CAM** tekniği ile ısı haritaları (heatmap) oluşturulmuştur.
* **Hiperparametre Optimizasyonu:** Modelin başarısını daha da artırma potansiyelini test etmek için **Keras Tuner** kütüphanesi ile `RandomSearch` stratejisi kullanılarak filtre sayısı, dropout oranı ve öğrenme oranı gibi hiperparametreler için kısa bir arama süreci yürütülmüştür.

## Elde Edilen Sonuçlar

* Sıfırdan tasarlanan ve eğitilen CNN modeli, test verisi üzerinde %85 gibi başarılı bir doğruluk (`accuracy`) oranına ulaşmıştır.
* Eğitim ve doğrulama eğrilerinin birbirine paralel ilerlemesi, veri çoğaltma ve dropout teknikleri sayesinde modelin overfitting yapmadığını göstermiştir.
* Sınıflandırma raporu, modelin özellikle 'forest' (orman) sınıfını çok yüksek bir başarıyla tanıdığını ortaya koymuştur.
* Grad-CAM analizi, modelin bir görüntüyü sınıflandırırken anlamsal olarak doğru bölgelere odaklandığını görsel olarak kanıtlamıştır.
* Yapılan kısa hiperparametre optimizasyonu denemelerinde, manuel olarak tasarlanan başlangıç modelinden daha yüksek bir başarı skoruna ulaşılamamıştır. Bu, başlangıç modelimizin zaten oldukça optimize olduğunu göstermektedir.

## Kaggle Notebook

Projenin tüm kodlarını, açıklamalarını ve çıktılarını içeren Kaggle Notebook'una aşağıdaki linkten ulaşabilirsiniz:

**https://www.kaggle.com/code/beyzaydn/derinogrenmebootcamp**
