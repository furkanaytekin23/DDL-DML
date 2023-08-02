
## Problem - Veritabanına Kayıt Ekleme
Bu senaryo içerisinde sizlere tahsis edilen makinelerde Postgresql imajını kurmanız ve burada veritabanına bazı kayıtlar eklemeniz istenmektedir.
---

Bu senaryoda amacımız bir şirkette müdür olduğunuz varsayılıp, çalışanlarınızın tablosunu oluşturmanızdır.

### Talimatlar

1. Servislerimizin çalıştığını `docker version` ile kontrol edelim.
2. Postgresql veritabanını docker imajı ile ayağa kaldırabilmek için `docker run --name mypostgresdb -e POSTGRES_PASSWORD=mysecretpassword -p 5432:5432 -d postgres` komutunu çalıştıralım. 
3. Docker imajının çalıştığından emin olduktan sonra komutunu çalıştırıp postgresql veritabanına erişim sağlayalım.
4. Postgresql veritabanına bağlantı gerçekleştirip, burada psql komutlarını çalıştırabilirsiniz.
5. Postgresql veritabanına bağlandıktan sonra aşağıdaki komutları çalıştırarak tablo oluşturup, içerisine kayıtlar insert edeceğiz.
6. "TurkTelekom" adında yeni bir database oluşturun, sonrasında oluşturmuş olduğunuz database'e bağlanın. 
7. Bağlantı yapıldıktan sonra içerisinde "Calisan_id","Calisan_adi","Yasi" şeklinde sütunları olan "Calisanlar" adında bir tablo oluşturunuz ve bu tabloya da id si 23 ismi "Furkan Aytekin" yaşı 27, id si 24 ismi "Jack Nichialson" yaşı 32, id si 25 ismi "Andrew Bailing" yaşı 33 şeklinde olan kayıtlar insert ediniz. 
9. Oluşturmuş olduğun kaydı çekip, görüntüleyin.
10. Çıktıyı sql.txt dosyasına kaydedin. İpucu: vi,vim 
11. İşlemleri tamamladıktan sonra "Kontrol Et" butonuna basınız ve senaryoyu tamamlayınız.

### Başarılı Çıktı
 Koşul:  
``` echo
calisan_id |  calisan_adi   | yasi 
------------+----------------+------
         23 | Furkan Aytekin |   27
         24 | Jack Nichialson |   32
         25 | Andrew Bailing |   38
(3 rows)
```
## Faydalı Linkler
https://www.geeksforgeeks.org/postgresql-psql-commands/
