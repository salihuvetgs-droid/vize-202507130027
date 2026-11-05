Veri Seti Açıklaması — Hafta 4

Proje Bilgileri

Proje: Robot Kol Projelerinde Görüntü İşleyen Kamera ile Model Performans Karşılaştırması

Kura No: 31

Veri Kaynağı

- Veri seti: Car Object Detection
- Platform: Kaggle
- Kaynak: https://www.kaggle.com/datasets/sshikamaru/car-object-detection
- Dosya: train_solution_bounding_boxes (1).csv
- İndirme tarihi: 05.11.2026
- Lisans: Kaggle veri seti sayfasından doğrulanacak.

Veri Setinin İçeriği

Veri seti, araç görüntülerindeki nesnelerin sınırlayıcı kutu koordinatlarını içermektedir.

PostgreSQL'e toplam 559 satır aktarılmıştır.

CSV dosyasında beş sütun bulunmaktadır:

Sütun| Açıklama
image| Görüntü dosyasının adı
xmin| Nesne kutusunun sol koordinatı
ymin| Nesne kutusunun üst koordinatı
xmax| Nesne kutusunun sağ koordinatı
ymax| Nesne kutusunun alt koordinatı

Dört koordinat sütunu sayısal veridir.

PostgreSQL İşlemleri

"robotik_kamera" isimli veritabanı oluşturulmuştur.

Veriler "kamera_verileri" isimli tabloya aktarılmıştır.

PostgreSQL'in sistem sütunuyla çakışmaması için CSV dosyasındaki "xmin" alanı tabloda "bbox_xmin" olarak adlandırılmıştır. Diğer koordinat alanlarında da "bbox_" öneki kullanılmıştır.

"SELECT COUNT(*)" sorgusuyla 559 kaydın yüklendiği doğrulanmıştır.

Veri İnceleme

SQL sorgularıyla koordinat ortalamaları, minimum ve maksimum değerler, nesne kutusu boyutları ve görüntü başına nesne sayıları incelenmiştir.

Veri Temizleme ve Sınırlılıklar

Ham CSV dosyası "data/raw" klasöründe değiştirilmeden saklanmıştır.

Henüz ayrı bir temizlenmiş veri seti oluşturulmamıştır.

Mevcut CSV dosyasında model adı, güven skoru, ışık koşulu ve görüntü tarihi bulunmamaktadır. Bu nedenle mevcut verilerle iki modelin doğruluk karşılaştırması veya ışık koşullarına göre performans analizi yapılamamaktadır.

Bu eksiklikler proje senaryosuyla mevcut veri kaynağı arasındaki sınırlılıklar olarak kaydedilmiştir.