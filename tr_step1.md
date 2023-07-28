
## Problem - DDL ve DML Komutları
Bu senaryo içerisinde sizlere tahsis edilen makinelerde Postgresql imajını kurmanız ve burada DDL ve DML komutları ile bazı basit işlemleri uyguladığınız bir senaryo hazırlamanız istenmektedir.
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

Bu senaryoda, Alpine imajında çalışan bir PostgreSQL veritabanı oluşturacak ve ardından bir tablo oluşturup, tablo içerisine kayıtlar insert edip, daha sonra bu kayıtlardan bazılarını update edip, bazılarını da delete yapıcaz ve son halini sorgu ile çekeceğiz.

### Talimatlar

1. Servislerimizin çalıştığını `docker version` ile kontrol edelim.
2. Postgresql veritabanını docker imajı ile ayağa kaldırabilmek için `docker run --name mypostgresdb -e POSTGRES_PASSWORD=mysecretpassword -p 5432:5432 -d postgres` komutunu çalıştıralım. 
3. Docker imajının çalıştığından emin olduktan sonra `docker exec -it mypostgresdb bash` komutunu çalıştırıp postgresql veritabanına erişelim.
4. `psql -U postgres` komutunu çalıştırarak bağlantı gerçekleşir ve burada psql komutlarını çalıştırabilirsiniz.
5. Postgresql veritabanına bağlandıktan sonra aşağıdaki komutları çalıştırarak tablo oluşturup, içerisine kayıtlar insert edeceğiz.
6. `TurkTelekom` adında yeni bir veritabanı oluşturun sonrasında `\c TurkTelekom` diyerek veritabanınıza bağlanın. 
7. Bağlantı yapıldıktan sonra içerisinde "Calisan_id","Calisan_adi","Yasi" şeklinde sütunları olan "Calisanlar" adında bir tablo oluşturunuz ve bu tabloya da id si 23 ismi "Furkan Aytekin" yaşı 27, id si 24 ismi "Jack Nichialson" yaşı 32, id si 25 ismi "Andrew Bailing" yaşı 33 şeklinde olan kayıtlar insert ediniz. 
8. Daha sonra id si 25 olan çalınanın yaşını 38 olarak update edin ve id si 24 olan çalışanı da delete yapın.
9. Oluşturmuş olduğun kaydı çekip, görüntüleyin.
10. Çıktıyı sql.txt dosyasına kaydedin. İpucu: vi,vim 
11. İşlemleri tamamladıktan sonra "Kontrol Et" butonuna basınız ve senaryoyu tamamlayınız.

### Başarılı Çıktı
 Koşul:  
``` echo
calisan_id |  calisan_adi   | yasi 
------------+----------------+------
         23 | Furkan Aytekin |   27
         25 | Andrew Bailing |   38
(2 rows)
```      
