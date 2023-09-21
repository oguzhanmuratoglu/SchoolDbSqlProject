# SchoolDbSqlProject

Projenin Diyagram Görüntüsü :

# ![image](https://github.com/oguzhanmuratoglu/SchoolDbSqlProject/assets/116174285/26046c79-a629-410b-93b9-1766fede07d2)


Bu tabloda tüm kullanıcıların ortak verileri tutulmaktadır:
-  People tablosu : Öğrenciler, Öğretmenler, Müdür ve Müdür Yardımcılarını kapsamaktadır ve bu tablolar ile bire çok ilişki içindedir.
# ![image](https://github.com/oguzhanmuratoglu/SchoolDbSqlProject/assets/116174285/cbb262bf-0fd5-4617-96f3-b53f21b2cbf8), ![image](https://github.com/oguzhanmuratoglu/SchoolDbSqlProject/assets/116174285/5d96bb4a-b3e9-4e93-b41d-724d1cfcb1db)




Bu tabloda öğrencilerin verileri tutulmaktadır:
- Students tablosu : Classes ve people tabloları ile çoka bir ilişki (çok öğrenci bir sınıf), Attendances ve Notes tabloları ile ise bire çok ilişki(bir öğrenci çok yoklama veya bir öğrencinin birden fazla nota sahip olması gibi) ve Exams tablosu ile çoka çok ilişki içindedir.(bir öğrenci birden fazla sınava gireceği gibi bir sınava da birden fazla öğrenci katılabileceği için)
# ![image](https://github.com/oguzhanmuratoglu/SchoolDbSqlProject/assets/116174285/a54b391f-d052-4325-9c4b-2e7814c9bef6), ![image](https://github.com/oguzhanmuratoglu/SchoolDbSqlProject/assets/116174285/5e065f2d-f817-45e3-ab4a-ea5cd3ae006f)



Bu tabloda öğretmenlerin verileri tutulmaktadır:
- Teachers tablosu : Exams  tablosu ile bire çok ilişki içerisindedir (bir sınavı hazırlayan 1 öğretmen olur fakat 1 öğretmen birden çok sınav hazırlayabilir.), Classes Tablosu ile hem bire çok hem de çoka çok ilişki içindedir. Sebebi ise bire çok ilişkiyi sınıf öğretmenini belirlemek için kullandım. Böylelikle her sınıfta ek olarak TeacherId kolonu bulunmuş oldu ve bu seçenekle her sınıf için Sınıf öğretmeni verileri tutulabilmektedir. Çoka çok ilişki kurmamın sebebi ise sınıflar ve sınıflara giren öğretmenler ilişkisidir. (bir sınıfa birden çok öğretmen ders vermek için girebilir, bir öğretmen ise birden çok sınıfta ders verebilir.) People ve Lessons Tabloları ile ise çoka bir ilişki içindedir. (Bu tabloda bir öğretmen en fazla bir ders için eğiitm verebilir, fakat bir dersi birden fazla öğretmen anlatabilmektedir.(Örnke vericek olursak : beden eğitimi öğretmeni sadece beden eğitimi dersi verebilir fakat okulda 2 adet beden eğitimi öğretmeni varsa 2'si de beden eğitimi dersi verebilir.))
# ![image](https://github.com/oguzhanmuratoglu/SchoolDbSqlProject/assets/116174285/2ec88801-07e3-4c39-a304-5d2098a0f077) , ![image](https://github.com/oguzhanmuratoglu/SchoolDbSqlProject/assets/116174285/1fc0496b-f1d8-4ecd-b415-19e8e1a1ccaa)



Bu tabloda sınıfların verileri tutulmaktadır:
Classes tablosu resimdede görüldüğü gibi aslında birçok diğer tablo ile ilişki içinde olan bir tablodur. Bunun seebebinin ise sınıfın hem öğretmen hem öğrenci hem yoklama hem sınavlar... gibi birçok diğer alanları içerisinde kapsamasından kaynaklıdır. Açıklamak gerekirse :
- Classes Tablosu : Attendances tablosu ile bire bir ilişki içinde (sınıf sayısı kadar yoklama sayısı olmalıdır.), Students tablosu ile bire çok (bir sınıfta birden çok öğrenci bulunabilir fakat bir öğrenci bir sınıfa aittir.), Lessons ve Exams tabloları ile ise çoka çok ilişki içerisindedir. (Bir Sınıfta birden çok ders işlenebilineceği gibi bir ders birden çok sınıfta verilebilinir.), Teacher tabloları için ise gerekli bilgileri yukarıda Teachers alanında vermiş bulunmaktayım.   
# ![image](https://github.com/oguzhanmuratoglu/SchoolDbSqlProject/assets/116174285/a0a39251-034b-4d41-8ea6-dafe19462ea1), ![image](https://github.com/oguzhanmuratoglu/SchoolDbSqlProject/assets/116174285/21c6c22c-6f7c-431a-9f9c-90daf972e499)



Bu tabloda sınavların ve sınavın türünün verileri tutulmaktadır(klasik, çoktan seçmeli, karışık):
- Exams Tablosu : ExamTypes tablosu ile çoka bir ilişki içindedir.(böylelikle her exam girilirken aynı zamanda ExamstypesId alanının da girilmesi gereklidir böylelikle her sınavın exams typeı string değer ile tutulmak yeirne daha fonksiyonel bir şekilde ele alınmıştır.), Classes ve Students tabloları ile çoka çok ilişki içindedir. (bir sınava birden çok öğrenci girebilir aynı zamanda bir öğrenci birden fazla sınava girebilir), Exams tablosunu aynı zamanda teachers tablosu ile de çoka bir ilişki içine aldım böylelikle sınavı hazırlayan öğretmenin de verilerini tutabilmekteyiz. Bu ilişki Lessons için de geçerlidir. Böylelikle sınav tablosuna veri girilirken aşağıda görselde göründüğü gibi kullanıcı aynı zamanda TeacherId, LessonId ve ExamTypeId girmek zorundadır. Böylelikle sınavın türü, sınavı hazırlayan öğretmen bilgileri, sınavın hangi ders için hazırlandığının verileri kolaylıkla tutulmuş olmaktadır. 
# ![image](https://github.com/oguzhanmuratoglu/SchoolDbSqlProject/assets/116174285/3807bba1-71aa-43c4-8df2-536ae51e4187), ![image](https://github.com/oguzhanmuratoglu/SchoolDbSqlProject/assets/116174285/5a81814d-b8fe-480a-9e51-a29e05d54240)



Bu tabloda notların verileri tutulmaktadır:
- Notes tablosu, Students tablosu ve Lessons tabloları ile çoka bir ilişki içindedir. Böylelikle notes tablosuna değer girilirken aynı zamanda studentId de girişi yapılarak not ile öğrenci arasındaki bağlantı, lessonId değeri de girilerek ders ile not arasındaki bağlantı sağlanmış olunur.
# ![image](https://github.com/oguzhanmuratoglu/SchoolDbSqlProject/assets/116174285/e9479832-116e-4dde-a63b-c8427c0fe634), ![image](https://github.com/oguzhanmuratoglu/SchoolDbSqlProject/assets/116174285/2d6ea05b-d841-4a0b-8721-c09c2304d41f)



Bu tabloda derslerin verileri tutulmaktadır:
- Lessons tablosu : Notes, Teachers ve Exams tabloları ile bir çok ilişki içindeyken Classes tablosu ile çoka çok ilişki içindedir. 
# ![image](https://github.com/oguzhanmuratoglu/SchoolDbSqlProject/assets/116174285/5b4c4baa-9e3f-49ee-adfc-168e855bf2a6), ![image](https://github.com/oguzhanmuratoglu/SchoolDbSqlProject/assets/116174285/015906ec-d869-4334-96b4-22a2a229f6c4)



Bu tabloda yoklama verileri tutulmaktadır:
- Attendances tablosu students tablosu ile çoka bir classes tablosu ile çoka çok ilişki içindedir. (bir öğrenci bir yoklamaya tabidir fakat bir yoklama birden çok öğrenciyi kapsar)
# ![image](https://github.com/oguzhanmuratoglu/SchoolDbSqlProject/assets/116174285/78128c93-0b30-4e74-8cdb-e8a16915596b), ![image](https://github.com/oguzhanmuratoglu/SchoolDbSqlProject/assets/116174285/ac80410e-27ab-4afe-b5ae-c5d80736de45)



Bu tablolarda Müdür ve Müdür Yardımcısı verileri tutulmaktadır:
# ![image](https://github.com/oguzhanmuratoglu/SchoolDbSqlProject/assets/116174285/4ccfd6ae-0d02-4a61-bc18-cc5bc6a31107) , ![image](https://github.com/oguzhanmuratoglu/SchoolDbSqlProject/assets/116174285/2c799aa0-91ad-4843-b058-0dc1a07e77ae)


# STORED PROCEDURES
  
- # "CalculateAverageScore" adlı özel bir STORED PROCEDURE örneği:

Bu STORED PROCEDURE, "SchoolDb" adlı veritabanında bulunan öğrenci notlarını kullanarak öğrencinin ortalama puanını hesaplamak için kullanılır. Prosedür, öğrenci kimlik numarasını giriş olarak alır ve bu öğrencinin notlarını kullanarak ortalama bir puan hesaplar.

Prosedürün ana işlevleri şunlardır:

1-Öğrencinin notlarını alır (Score1, Score2 ve Score3).
2-Eğer öğrencinin üçüncü bir notu varsa, bu üç notun ortalamasını hesaplar. Eğer üçüncü not yoksa, sadece iki notun ortalamasını hesaplar.
3-Hesaplanan ortalama puanı "Notes" tablosunda ilgili öğrencinin "Average" alanına kaydeder.

```TSQL
USE [SchoolDb]
GO
/****** Object:  StoredProcedure [dbo].[CalculateAverageScore]    Script Date: 21.09.2023 13:17:17 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
ALTER PROCEDURE [dbo].[CalculateAverageScore]
    @StudentId INT
AS
BEGIN
    DECLARE @Average INT

    SELECT @Average = CASE
        WHEN Score3 IS NOT NULL THEN ROUND((Score1 + Score2 + Score3) / 3.0, 0) 
        ELSE ROUND((Score1 + Score2) / 2.0, 0) 
    END
    FROM Notes
    WHERE StudentId = @StudentId

    UPDATE Notes SET Average = @Average WHERE StudentId = @StudentId
END
```

- # "CalculateClassAverageNote" Stored Procedure:
  
Bu stored procedure, belirli bir sınıftaki öğrencilerin ortalama notlarını hesaplamak için kullanılır. İşlevi aşağıdaki adımlardan oluşur:

1- Sınıf Kimliğini Alır: Saklama prosedürü, hesaplamayı yapmak istediğiniz sınıfın kimliğini giriş olarak alır.

2- Öğrenci Bilgilerini ve Ortalama Notları Getirir: Verilen sınıf kimliğine sahip öğrencilerin adlarını ve bu öğrencilerin notlarının ortalamasını alır.

3- Ortalama Notları Yuvarlar: Ortalama notları tam sayıya yuvarlar, böylece net bir görüntü sağlar.

4- Sonuçları Döndürür: Sınıf içindeki her öğrencinin adı ve ortalama notu sonuç olarak döndürür.

```TSQL 

USE [SchoolDb]
GO
/****** Object:  StoredProcedure [dbo].[CalculateClassAverageNote]    Script Date: 21.09.2023 13:31:30 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
ALTER PROCEDURE [dbo].[CalculateClassAverageNote]
    @ClassId INT
AS
BEGIN
    SELECT
        S.Name AS StudentName,
		ROUND(AVG(N.Average),0) AS AverageGrade
    FROM Students AS S
    INNER JOIN Notes AS N ON S.Id = N.StudentId
    WHERE S.ClassId = @ClassId
    GROUP BY S.Name
END

```

- # "GetClassStudents" Stored Procedure

Bu stored procedure, belirli bir sınıfa ait öğrencileri getirmek için kullanılır. İşlevi aşağıdaki adımlardan oluşur:

1- Sınıf Kimliğini Alır: Saklama prosedürü, istenen sınıfın kimliğini giriş olarak alır.

2- Öğrencileri Getirir: Verilen sınıf kimliğine sahip tüm öğrencileri "Students" tablosundan seçer.

3- Sonuçları Döndürür: Belirtilen sınıfa ait tüm öğrencileri sonuç olarak döndürür.

```TSQL

USE [SchoolDb]
GO
/****** Object:  StoredProcedure [dbo].[GetClassStudents]    Script Date: 21.09.2023 13:34:20 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
ALTER PROCEDURE [dbo].[GetClassStudents]
    @ClassId INT
AS
BEGIN
    SELECT *
    FROM Students
    WHERE ClassId = @ClassId
END

```
