
## Problem - DDL ve DML Komutları
Bu senaryo içerisinde sizlere tahsis edilen makinelerde SQL Server 2019 imajını kurmanız ve burada DDL ve DML komutları ile bazı basit işlemleri uyguladığınız bir senaryo hazırlamanız istenmektedir.
---

### Bilgi 

SQL DML (Data Manipulation Language) Veri İşleme Dili:
Veritabanında bilgi üzerinde çalışmayı sağlar. Bilgiyi çağırma, bilgiye yeni bir şeyler ekleme, bilgiden bir şeyler silme, bilgiyi güncelleştirme işlemlerini yapar.

Temel dört komutu vardır:

·SELECT : Veritabanındaki istenilen alanı çağırmayı ve gereken bilgiyi görebilmeyi sağlar.

· UPDATE : Veritabanındaki kayıtlar üzerinde bilgi güncellemeyi sağlar.

· INSERT : Veritabanına alan eklemeyi sağlar.

· DELETE : Veritabanından alan silmeyi sağlar.

SQL DDL (Data Definition Language) Veri Tanımlama Dili:
Verilerin tutulduğu nesneler olan tabloların yaratılmasını, silinmesini ve bazı temel özelliklerinin düzenlenmesini sağlar.

En yaygın kullanılan komutları şunlardır:

.CREATE TABLE : Veritabanı üzerinde bir tablo yaratmak için kullanılır.

.ALTER TABLE : Var olan nesnede değişiklik yapmak, yeni bir sütun eklemek, sütunun tipini veya uzunluğunu değiştirmek gibi yapısal değişiklikler için kullanılır.

.DROP TABLE : Tabloyu verilerle birlikte kalıcı olarak siler.

.TRUNCATE TABLE : Tablodaki veri içeriklerini siler fakat tablo yapısı kalır.

.CREATE INDEX : Index oluşturmak için, tablonun sütun adı üzerinde indeks oluşturur.

.CREATE VIEW : Görüntü oluşturmak için kullanılır.

.DROP VIEW : Görüntüyü siler.

Bu senaryoda, Alpine imajında çalışan bir MSSQL veritabanı oluşturacak ve ardından bir tablo oluşturup tablo içerisine kayıtlar atıp daha sonra bu kayıtları sorgu ile çekeceğiz.

### Talimatlar

1. Servislerimizin çalıştığını `docker version` ile kontrol edelim.
2. Docker Pull komutu ile Docker Hub'tan SQL Server 2019 imajı parça parça indirelim.
3. İndirdiğimiz imajımızı sudo docker run komutu ile ayağa kaldıralım.
4. Docker containerımın `sudo docker ps -a` komutu ile ayağa kalktığını görebiliriz.
5. Docker imajının çalıştığından emin olduktan sonra sudo docker exec komutunu çalıştırıp SQL Server 2019 veritabanına erişelim. 
6. `/opt/mssql-tools/bin/sqlcmd -S localhost -U SA -P "FurkanAytekin@6"` komutunu çalıştırarak bağlantı gerçekleşir ve burada sql komutlarını çalıştırabilirsiniz. 
7. SQL Server 2019 veritabanına bağlandıktan sonra aşağıdaki komutları çalıştırarak en basit SQL sorgularından birisi, hangi SQL Server sürümü ile çalıştığımızı anlamak için kullandığımız @@version system parametresini görüntülemek olacaktır.
"GO" komutu ile o ana dek yazılan SQL sorgusu çalıştırılır.
8. `SELECT @@version` `go` komutu ile basit bir sorgu kullanalım.
9. "TurkTelekom" adında bir database oluşturun ve bu database i kullanın.
10. İçerisinde "id" ve "calisan_adi" isimli columnları olan, "calisanlar" adında bir tablo oluşturun,
11. Oluşturmuş olduğun calisanlar tablosuna id si 23 olan ve çalışan adı "Furkan Aytekin" olan bir çalışan insert edin.
12. Oluşturmuş olduğun kaydı çekip, görüntüleyin.
13. Çıktıyı sql.txt dosyasına kaydedin. İpucu: vi,vim 
14. İşlemleri tamamladıktan sonra "Kontrol Et" butonuna basınız ve senaryoyu tamamlayınız.

### Başarılı Çıktı
 Koşul:  
``` echo
id     calisan_adi                                       
------ --------------------------------------------------
    23 Furkan Aytekin 
```      
