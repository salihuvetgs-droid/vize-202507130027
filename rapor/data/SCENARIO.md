# Robot Kol Projelerinde Görüntü İşleyen Kamera ile Yapay Zekâ Model Performanslarının Karşılaştırılması

**Ders:** Veritabanı Yönetim Sistemleri (BLP 105)  
**Bölüm:** Robotik ve Yapay Zekâ  
**Öğrenci No:** 202507130027  
**Kura No:** 31  
**Proje Alanı:** Eğitim  
**Sistem:** Görüntü İşleyen Kamera  
**YZ Bileşeni:** Model Performans Karşılaştırması

## 1. Projenin Hikâyesi ve Problemi

Bir meslek lisesinde öğrenciler, robot kol projelerinde nesneleri tanımak amacıyla kamera sistemleri kullanmaktadır.

Kamera tarafından elde edilen görüntüler, yapay zekâ destekli nesne tanıma modelleriyle analiz edilmektedir.

Ancak farklı yapay zekâ modelleri aynı nesneyi farklı güven skorlarıyla tanıyabilmektedir. Ayrıca ortamın ışık koşulları da nesne tanıma sonuçlarını etkileyebilmektedir.

Bu projede iki farklı nesne tanıma modelinin sonuçları karşılaştırılacaktır.

## 2. Projenin Amacı

Projenin amacı, iki farklı yapay zekâ modelinin nesne tanıma sonuçlarını veritabanı üzerinden incelemektir.

Modellerin nesne sınıflarına göre tespit sayıları, ortalama güven skorları ve farklı ışık koşullarındaki performansları analiz edilecektir.

## 3. Ana Araştırma Sorusu

Hangi yapay zekâ modeli hangi nesne sınıfında daha doğru sonuç vermektedir ve modeller arasındaki fark ortamın ışık koşullarına göre değişmekte midir?

## 4. Hedef Kullanıcılar

Projenin hedef kullanıcıları:

- Robotik ve yapay zekâ eğitimi alan öğrenciler
- Robotik laboratuvarında görev yapan öğretmenler
- Görüntü işleme sistemleri geliştiren araştırmacılar
- Robot kol projelerinde nesne tanıma kullanan geliştiriciler

## 5. Veritabanı Tablo Adayları

Proje kapsamında üç tablo adayı belirlenmiştir.

### Tablo 1: images

Kamera tarafından elde edilen görüntülerin bilgilerini saklar.

Sütunlar:
- id: Görüntü kimlik numarası
- lighting: Ortamın ışık koşulu
- captured_at: Görüntünün çekildiği tarih ve saat

### Tablo 2: detections

Yapay zekâ modellerinin nesne tespit sonuçlarını saklar.

Sütunlar:
- id: Tespit kimlik numarası
- goruntu_id: Görüntü kimlik numarası
- model_name: Kullanılan yapay zekâ modeli
- class: Tespit edilen nesne sınıfı
- confidence: Modelin güven skoru

### Tablo 3: true_objects

Görüntülerde gerçekte bulunan nesnelerin sınıflarını saklar.

Sütunlar:
- id: Kayıt kimlik numarası
- goruntu_id: Görüntü kimlik numarası
- class: Gerçek nesne sınıfı

Bu tablolar dönem projesinin ilerleyen aşamalarında kullanılabilecek tablo adaylarıdır.

## 6. Yapay Zekâ Bileşeni

Projenin yapay zekâ bileşeni model performans karşılaştırmasıdır.

İki farklı nesne tanıma modelinin sonuçları incelenecektir.

Modellerin ürettiği güven skorları ve nesne sınıfları karşılaştırılacaktır.

Gerçek nesne etiketleriyle model tahminleri eşleştirilebildiğinde doğru ve yanlış tespitler de değerlendirilebilecektir.

Işık koşullarının model sonuçlarına etkisi ayrıca analiz edilecektir.

## 7. Veri Kaynağı Adayları

Proje için aşağıdaki veri kaynakları araştırılacaktır.

**1. COCO Dataset**

Web sitesi: https://cocodataset.org/

Nesne tanıma çalışmalarında kullanılan görüntü ve nesne etiketleri için değerlendirilecektir.

**2. Kaggle Datasets**

Web sitesi: https://www.kaggle.com/datasets

Arama kelimeleri:
- object detection
- robot arm vision

Veri seti seçilirken kullanım lisansı ve içerdiği sütunlar kontrol edilecektir.

## 8. Veri Gereksinimleri

Proje kapsamında en az 500 nesne tespit kaydı kullanılacaktır.

İki farklı yapay zekâ modeline ait tespit sonuçları karşılaştırılacaktır.

Veri setinin en az %70'i gerçek kaynaklardan elde edilecektir.

Genel proje kuralları doğrultusunda veri setinde en az dört sayısal sütun ve bir tarih/zaman sütunu bulunması hedeflenmektedir.

Kullanılan veri kaynakları ve veri temizleme işlemleri ayrıca `data/README.md` dosyasında açıklanacaktır.

## 9. Beklenen Veri Sorunları

Veriler incelenirken aşağıdaki sorunlarla karşılaşılabilir:

- Işık koşullarının `good`, `Good`, `bad` gibi farklı biçimlerde yazılması
- Bazı görüntülerin ışık koşulu bilgisinin eksik olması
- Güven skorlarının 0 ile 1 aralığının dışında bulunması
- Bazı tespit kayıtlarında eksik değerlerin olması

Bu sorunlar veri temizleme aşamasında incelenecek ve yapılan işlemler belgelenecektir.

## 10. Beklenen Sonuç

Proje sonunda iki farklı nesne tanıma modelinin tespit sayıları ve ortalama güven skorları karşılaştırılacaktır.

Farklı ışık koşullarında modellerin sonuçlarının nasıl değiştiği incelenecektir.

Güven skorunun tek başına doğruluk anlamına gelmediği dikkate alınacak, gerçek nesne etiketleri mevcutsa doğruluk değerlendirmesi de yapılacaktır.

Elde edilen sonuçlar PostgreSQL üzerinde SQL sorguları kullanılarak analiz edilecektir.