# Yolov4 ile Maske Tespiti


**Yolov4 darknet** ile yazılmıştır.(https://github.com/AlexeyAB/darknet)

### Bu Projenin Amacı:

Yolo4-tiny kullanarak maskeyi tespit etmek. Basit bir şekilde herkesin bu projeyi kolay bir şekilde yapabilmesi.


:tv: **Yakında youtube videosu çekilecektir.**(https://youtu.be ) :point_left:


## YOLOV4-Tiny Kullanımı

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

Not: Dosyaları istediğiniz yere atabilirsiniz. Terminal de kodu yazarken ona göre yazmalısınız. Problem alırsanız Issues kısmına yazabilirsiniz.

Dosya işlemleri yaptıktan sonra terminalde çalıştıralım.

Resim için;
```
cd darknet
./darknet detector test cfg/mask.data cfg/mask-tiny.cfg backup/mask-tiny_last.weights data/face-mask-datasets/2.jpeg 
```
<img src="https://media-exp1.licdn.com/dms/image/C4D22AQFf6Yioshk65g/feedshare-shrink_800-alternative/0/1606147363048?e=1609372800&v=beta&t=bD5Rk1xDsGI7_po6Vn8UDq818sYsvcIxdp0G-VMOd2M">

Video için;
```
cd darknet
./darknet detector demo cfg/mask.data cfg/mask-tiny.cfg backup/mask-tiny_last.weights  
```
