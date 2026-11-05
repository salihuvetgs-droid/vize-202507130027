VERİTABANI YÖNETİM SİSTEMLERİ — VİZE PROJE RAPORU

Öğrenci No: 202507130027
Bölüm: Robotik ve Yapay Zekâ
Kura No: 31
Teslim Tarihi: 06.11.2026

1. Projenin Konusu ve Amacı

Projenin konusu, robot kol uygulamalarında kullanılan görüntü işleyen kameraların nesne tespit performansının incelenmesidir.

Projenin temel amacı, iki farklı nesne tespit modelinin doğruluğunu nesne sınıflarına ve ışık koşullarına göre karşılaştırmaktır.

2. Kullanılan Veri Seti

Projenin veri inceleme aşamasında Kaggle platformundaki Car Object Detection veri seti kullanılmıştır.

Veri setindeki "train_solution_bounding_boxes (1).csv" dosyası, görüntülerdeki araçların konumlarını belirleyen koordinat bilgilerini içermektedir.

Veriler PostgreSQL veritabanına aktarılmıştır.

Toplam kayıt sayısı: 559

Veri setinde görüntü adı ve dört sayısal koordinat alanı bulunmaktadır.

3. Veritabanı İşlemleri

PostgreSQL üzerinde "robotik_kamera" veritabanı ve "kamera_verileri" tablosu oluşturulmuştur.

CSV dosyasındaki veriler tabloya aktarılmış ve SQL sorgularıyla kontrol edilmiştir.

Verilerin incelenmesinde "SELECT", "COUNT", "AVG", "MIN", "MAX", "GROUP BY", "ORDER BY" ve "CASE WHEN" gibi SQL ifadeleri kullanılmıştır.

4. SQL Analiz Sonuçları

Yapılan sorgularda aşağıdaki sonuçlara ulaşılmıştır:

- Toplam kayıt: 559
- Ortalama başlangıç X koordinatı: 263,39
- Ortalama başlangıç Y koordinatı: 186,52
- Küçük nesne kutusu: 504
- Orta nesne kutusu: 53
- Büyük nesne kutusu: 2

Bu sonuçlar, veri setindeki nesne kutularının büyük çoğunluğunun belirlenen alan eşiklerine göre küçük kategorisinde olduğunu göstermektedir.

5. Veri Setinin Sınırlılıkları

Kullanılan veri setinde iki farklı modelin tahminleri, güven skorları ve ışık koşulları bulunmamaktadır.

Bu nedenle projenin ana sorusu olan model doğruluğu ve ışık koşullarına göre performans karşılaştırması mevcut verilerle gerçekleştirilememiştir.

Mevcut çalışma, görüntülerdeki nesne konumlarının veritabanına aktarılması ve temel SQL analizlerinin yapılması aşamasını kapsamaktadır.

6. Sonuç

Bu çalışmada gerçek bir veri seti PostgreSQL ortamına aktarılmış, 559 kayıt üzerinde SQL sorguları uygulanmış ve nesne kutularının koordinat ve boyut dağılımları incelenmiştir.

Projenin sonraki aşamasında, iki modelin tahminleri ve ışık koşulu bilgileri içeren uygun verilerle performans karşılaştırmasının yapılması hedeflenmektedir.

Veri kaynağı: https://www.kaggle.com/datasets/sshikamaru/car-object-detection

Yapay zekâ kullanımı: ChatGPT desteği alınmış olup ayrıntılar "AI_BEYAN.md" dosyasında açıklanmıştır.