# SchoolDbSqlProject

Projenin Diyagram Görüntüsü :

# ![image](https://github.com/oguzhanmuratoglu/SchoolDbSqlProject/assets/116174285/26046c79-a629-410b-93b9-1766fede07d2)


Bu tabloda tüm kullanıcıların ortak verileri tutulmaktadır:
-  People tablosu : Öğrenciler, Öğretmenler, Müdür ve Müdür Yardımcılarını kapsamaktadır ve bu tablolar ile bire çok ilişki içindedir.
# ![image](https://github.com/oguzhanmuratoglu/SchoolDbSqlProject/assets/116174285/cbb262bf-0fd5-4617-96f3-b53f21b2cbf8)


Bu tabloda öğrencilerin verileri tutulmaktadır:
- Students tablosu : Classes ve people tabloları ile çoka bir ilişki (çok öğrenci bir sınıf), Attendances ve Notes tabloları ile ise bire çok ilişki(bir öğrenci çok yoklama veya bir öğrencinin birden fazla nota sahip olması gibi) ve Exams tablosu ile çoka çok ilişki içindedir.(bir öğrenci birden fazla sınava gireceği gibi bir sınava da birden fazla öğrenci katılabileceği için)
# ![image](https://github.com/oguzhanmuratoglu/SchoolDbSqlProject/assets/116174285/a54b391f-d052-4325-9c4b-2e7814c9bef6)


Bu tabloda öğretmenlerin verileri tutulmaktadır:
- Teachers tablosu : Exams  tablosu ile bire çok ilişki içerisindedir (bir sınavı hazırlayan 1 öğretmen olur fakat 1 öğretmen birden çok sınav hazırlayabilir.), Classes Tablosu ile hem bire çok hem de çoka çok ilişki içindedir. Sebebi ise bire çok ilişkiyi sınıf öğretmenini belirlemek için kullandım. Böylelikle her sınıfta ek olarak TeacherId kolonu bulunmuş oldu ve bu seçenekle her sınıf için Sınıf öğretmeni verileri tutulabilmektedir. Çoka çok ilişki kurmamın sebebi ise sınıflar ve sınıflara giren öğretmenler ilişkisidir. (bir sınıfa birden çok öğretmen ders vermek için girebilir, bir öğretmen ise birden çok sınıfta ders verebilir.) People ve Lessons Tabloları ile ise çoka bir ilişki içindedir. (Bu tabloda bir öğretmen en fazla bir ders için eğiitm verebilir, fakat bir dersi birden fazla öğretmen anlatabilmektedir.(Örnke vericek olursak : beden eğitimi öğretmeni sadece beden eğitimi dersi verebilir fakat okulda 2 adet beden eğitimi öğretmeni varsa 2'si de beden eğitimi dersi verebilir.))
# ![image](https://github.com/oguzhanmuratoglu/SchoolDbSqlProject/assets/116174285/2ec88801-07e3-4c39-a304-5d2098a0f077)


Bu tabloda sınıfların verileri tutulmaktadır:
Classes tablosu resimdede görüldüğü gibi aslında birçok diğer tablo ile ilişki içinde olan bir tablodur. Bunun seebebinin ise sınıfın hem öğretmen hem öğrenci hem yoklama hem sınavlar... gibi birçok diğer alanları içerisinde kapsamasından kaynaklıdır. Açıklamak gerekirse :
- Classes Tablosu : Attendances tablosu ile bire bir ilişki içinde (sınıf sayısı kadar yoklama sayısı olmalıdır.), Students tablosu ile bire çok (bir sınıfta birden çok öğrenci bulunabilir fakat bir öğrenci bir sınıfa aittir.), Lessons ve Exams tabloları ile ise çoka çok ilişki içerisindedir. (Bir Sınıfta birden çok ders işlenebilineceği gibi bir ders birden çok sınıfta verilebilinir.), Teacher tabloları için ise gerekli bilgileri yukarıda Teachers alanında vermiş bulunmaktayım.   
# ![image](https://github.com/oguzhanmuratoglu/SchoolDbSqlProject/assets/116174285/a0a39251-034b-4d41-8ea6-dafe19462ea1)


Bu tabloda sınavların ve sınavın türünün verileri tutulmaktadır(klasik, çoktan seçmeli, karışık):
- Exams Tablosu : ExamTypes tablosu ile çoka bir ilişki içindedir.(böylelikle her exam girilirken aynı zamanda ExamstypesId alanının da girilmesi gereklidir böylelikle her sınavın exams typeı string değer ile tutulmak yeirne daha fonksiyonel bir şekilde ele alınmıştır.), Classes ve Students tabloları ile çoka çok ilişki içindedir. (bir sınava birden çok öğrenci girebilir aynı zamanda bir öğrenci birden fazla sınava girebilir), Exams tablosunu aynı zamanda teachers tablosu ile de çoka bir ilişki içine aldım böylelikle sınavı hazırlayan öğretmenin de verilerini tutabilmekteyiz. Bu ilişki Lessons için de geçerlidir. Böylelikle sınav tablosuna veri girilirken aşağıda görselde göründüğü gibi kullanıcı aynı zamanda TeacherId, LessonId ve ExamTypeId girmek zorundadır. Böylelikle sınavın türü, sınavı hazırlayan öğretmen bilgileri, sınavın hangi ders için hazırlandığının verileri kolaylıkla tutulmuş olmaktadır. 
# ![image](https://github.com/oguzhanmuratoglu/SchoolDbSqlProject/assets/116174285/3807bba1-71aa-43c4-8df2-536ae51e4187)


Bu tabloda notların verileri tutulmaktadır:
- Notes tablosu, Students tablosu ve Lessons tabloları ile çoka bir ilişki içindedir. Böylelikle notes tablosuna değer girilirken aynı zamanda studentId de girişi yapılarak not ile öğrenci arasındaki bağlantı, lessonId değeri de girilerek ders ile not arasındaki bağlantı sağlanmış olunur.
# ![image](https://github.com/oguzhanmuratoglu/SchoolDbSqlProject/assets/116174285/e9479832-116e-4dde-a63b-c8427c0fe634)


Bu tabloda derslerin verileri tutulmaktadır:
- Lessons tablosu : Notes, Teachers ve Exams tabloları ile bir çok ilişki içindeyken Classes tablosu ile çoka çok ilişki içindedir. 
# ![image](https://github.com/oguzhanmuratoglu/SchoolDbSqlProject/assets/116174285/5b4c4baa-9e3f-49ee-adfc-168e855bf2a6)


Bu tabloda yoklama verileri tutulmaktadır:
- Attendances tablosu students tablosu ile çoka bir classes tablosu ile çoka çok ilişki içindedir. (bir öğrenci bir yoklamaya tabidir fakat bir yoklama birden çok öğrenciyi kapsar)
# ![image](https://github.com/oguzhanmuratoglu/SchoolDbSqlProject/assets/116174285/78128c93-0b30-4e74-8cdb-e8a16915596b)


Bu tablolarda Müdür ve Müdür Yardımcısı verileri tutulmaktadır:
  # ![image](https://github.com/oguzhanmuratoglu/SchoolDbSqlProject/assets/116174285/4ccfd6ae-0d02-4a61-bc18-cc5bc6a31107) 
 # ![image](https://github.com/oguzhanmuratoglu/SchoolDbSqlProject/assets/116174285/2c799aa0-91ad-4843-b058-0dc1a07e77ae)
 
