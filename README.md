## Yolov4-Tiny ile Maske Tespiti

Videolu Anlatım için: https://www.youtube.com/watch?v=owqs8XVxiLk
**Yolov4 darknet** ile yazılmıştır.(https://github.com/AlexeyAB/darknet)

#### Bu Projenin Amacı:


Yolo4-tiny kullanarak maskeyi tespit etmek. Basit bir şekilde herkesin bu projeyi kolay bir şekilde yapabilmesi.

#### Yolov4-Tiny mAP ve Loss Değeri:
<img src="chart_mask-tiny.png"/>

###### Not: Eğitimi belli bir yerden sonra durdurmak lazım. Yoksa ezber yapıyor. Lakin eğitimi gece yaptığı için kendi otomatik sonlandı. Daha iyi sonuçlar için sizlerin sonlandırmasını tavsiye ederim.

###### Not2: Eğitim veri seti benzer olduğundan doğruluk oranı %80'lerde sabit şekilde ilerlemiş. Veri seti oluştururken gerçek dünyaya yakın resimlerin olması size çok şey katacaktır.

#### YOLOV4-Tiny Kurulumu:

İlk önce https://github.com/AlexeyAB/darknet github sayfasını klonlama işlemi yapıyoruz.
```
git clone https://github.com/AlexeyAB/darknet
```
Gpu kullanımı için, makefile dosyasında GPU=0,CUDNN=0,CUDNN_HALF=0,OPENCV=0 değerleri değiştirmemiz gerekiyor.
```
GPU=1
CUDNN=1
OPENCV=1
```
Yaptığımız bu değişiklikleri aktif bir şekilde çalışması için, terminal ekranında çalışması lazım.

```
cd darknet
make -j8
```
Gpu kurulumu başarılı bir şekilde olduysa yolov4-tiny test edebiliriz. Önce dosya işlemlerini anlatmak istiyorum.

- cfg,name,data dosyaları darknet>cfg klasörün içerisinde atabilirsiniz.
- models klasörün içindeki dosyaları backup klasörün içerisine atabilirsiniz.
- Face Mask Dataset klasörü data klasörün içerisine atabilirsiniz.

###### Not: Dosyaları istediğiniz yere atabilirsiniz. Terminal de kodu yazarken ona göre yazmalısınız. Problem alırsanız Issues kısmına yazabilirsiniz.

Dosya işlemleri yaptıktan sonra terminalde çalıştıralım.

**Resim için;**
```
cd darknet
./darknet detector test cfg/mask.data cfg/mask-tiny.cfg backup/mask-tiny_last.weights data/face-mask-datasets/2.jpeg 
```

**Video için;**
```
cd darknet
./darknet detector demo cfg/mask.data cfg/mask-tiny.cfg backup/mask-tiny_last.weights  
```
