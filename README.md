# Akbank Derin Öğrenme Bootcamp: Görüntü Sınıflandırma Projesi

Bu proje, Akbank Derin Öğrenme Bootcamp'i kapsamında, Evrişimli Sinir Ağları (CNN) kullanılarak bir görüntü sınıflandırma modelinin geliştirilmesini içermektedir.

## Projenin Amacı

Projenin temel amacı, verilen bir görüntü veri setini kullanarak yüksek başarımlı bir sınıflandırma modeli eğitmektir. Bu süreçte veri ön işleme, veri çoğaltma (data augmentation), model tasarımı, model eğitimi, hiperparametre optimizasyonu ve model değerlendirme gibi derin öğrenme proje adımları pratik olarak uygulanmıştır.

## Veri Seti Hakkında Bilgi

Bu projede **Intel Image Classification** veri seti kullanılmıştır. Veri seti, doğal sahnelere ait 6 farklı sınıftan oluşmaktadır:
* Binalar (Buildings)
* Orman (Forest)
* Buzul (Glacier)
* Dağ (Mountain)
* Deniz (Sea)
* Cadde (Street)

Veri seti, yaklaşık 14.000 eğitim, 3.000 doğrulama (validation) ve 7.000 test görüntüsü içermektedir. Görüntüler 150x150 piksel boyutundadır.

## Kullanılan Yöntemler

* **Veri Ön İşleme:** Görüntüler yeniden boyutlandırıldı ve piksel değerleri [0, 1] aralığına normalize edildi.
* **Veri Çoğaltma (Data Augmentation):** Modelin genelleme yeteneğini artırmak ve ezberlemesini (overfitting) önlemek amacıyla eğitim verisine `ImageDataGenerator` (veya `torchvision.transforms`) kullanılarak rastgele döndürme, yakınlaştırma, yatay çevirme gibi dönüşümler uygulandı.
* **Model Mimarisi:** Proje gereksinimlerine uygun olarak Convolutional, MaxPooling, Dropout ve Dense katmanlarından oluşan bir CNN mimarisi oluşturuldu. Aktivasyon fonksiyonu olarak ReLU ve Softmax kullanıldı.
* **Optimizasyon:** Model, Adam optimizer ve `categorical_crossentropy` kayıp fonksiyonu kullanılarak derlendi.

## Elde Edilen Sonuçlar

(Bu bölümü projenin sonunda dolduracağız. Şimdilik boş kalabilir.)
Modelin eğitim ve doğrulama setleri üzerindeki başarım grafikleri, confusion matrix ve sınıflandırma raporu gibi metrikler burada özetlenecektir. Ayrıca Grad-CAM ile yapılan görselleştirmelerden elde edilen bulgulara yer verilecektir.

## Kaggle Notebook

Projenin tüm kodlarını ve teknik detaylarını içeren Kaggle Notebook'una aşağıdaki linkten ulaşabilirsiniz:

**[Kaggle Notebook Linki Buraya Gelecek]**
