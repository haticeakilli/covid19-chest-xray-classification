# COVID-19 Akciğer Röntgen Görüntülerinin Derin Öğrenme ile Sınıflandırılması
## Proje Hakkında

Bu proje, Kocaeli Üniversitesi Bilgisayar Mühendisliği lisans programı kapsamında hazırlanan bitirme projesidir.

Bu projenin amacı, önceden eğitilmiş derin öğrenme algoritmaları hakkında bilgi sahibi olmak ve daha öncesinde yapılmış çalışmalara bakarak 
hangi yöntemlerin hangi teknolojiler ile tespit doğruluğunu en üst düzeye çıkardığına bakıp dijital göğüs röntgen görüntülerinden 
Covid-19 pozitif vakaların otomatik tespiti için bir yöntem belirlemektir.

## Kullanılan Veri Seti

Projede COVID-19 Radiography Database veri seti kullanılmıştır.

Veri seti aşağıdaki üç sınıftan oluşmaktadır:

- COVID-19
- Normal
- Vİral Pnömoni

Model eğitimi için veri seti aşağıdaki şekilde bölünmüştür:

- Eğitim (Training): %70
- Doğrulama (Validation): %15
- Test (Test): %15

Veri seti boyutunun büyük olması nedeniyle GitHub deposuna eklenmemiştir.

## Veri Ön İşleme

Model eğitiminden önce aşağıdaki ön işleme adımları uygulanmıştır:

- Görüntülerin 224×224 boyutuna yeniden ölçeklendirilmesi
- Piksel değerlerinin normalize edilmesi
- Veri artırma (Data Augmentation)
- Döndürme (Rotation)
- Yakınlaştırma (Zoom)
- Yatay ve dikey kaydırma
- Shear dönüşümü
- Parlaklık değişimi
- Yatay çevirme (Horizontal Flip)

## Kullanılan Modeller
### ResNet101

Bu model için sıfırdan oluşturulan bir sınıflandırma yapısı kullanılmıştır.

Model eğitiminde;

- Batch Normalization
- Dropout
- L2 Regularization
- Early Stopping

teknikleri uygulanmıştır.

### DenseNet201

DenseNet201 modeli Transfer Learning yöntemi kullanılarak geliştirilmiştir.

Modelde;

- ImageNet ön eğitimli ağırlıkları
- Global Average Pooling
- Dropout
- Softmax çıkış katmanı

kullanılmıştır.

Eğitim sürecinde;

- Early Stopping
- ReduceLROnPlateau
- Model Checkpoint

yöntemlerinden yararlanılmıştır.

## Kullanılan Teknolojiler
- Python
- TensorFlow
- Keras
- NumPy
- Pandas
- Matplotlib
- Scikit-learn
- OpenCV
- Google Colab

