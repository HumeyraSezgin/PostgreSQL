# PostgreSQL
### *Patika.dev SQL Eğitimi Ödevleri*
<hr>

## ÖDEV 1

1. <b>film</b> tablosunda bulunan <b>title</b> ve <b>description</b> sütunlarındaki verileri sıralayınız.
```SQL
SELECT title,description FROM film 
```
2. <b>film</b> tablosunda bulunan tüm sütunlardaki verileri film uzunluğu (length) 60 dan büyük <b>VE</b> 75 ten küçük olma koşullarıyla sıralayınız.
```SQL
SELECT * FROM film WHERE length>60 AND length<75
```
3. <b>film</b> tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99 <b>VE</b> replacement_cost 12.99 <b>VEYA</b> 28.99 olma koşullarıyla sıralayınız.
```SQL
SELECT * FROM film WHERE rental_rate =0.99 AND (replacement_cost = 12.99 OR replacement_cost = 28.99)
```

4. <b>customer</b> tablosunda bulunan first_name sütunundaki değeri 'Mary' olan müşterinin last_name sütunundaki değeri nedir?
```SQL
SELECT last_name FROM customer WHERE first_name = 'Mary'
```
5. <b>film</b> tablosundaki uzunluğu(length) 50 ten büyük OLMAYIP aynı zamanda rental_rate değeri 2.99 veya 4.99 OLMAYAN verileri sıralayınız.
```SQL
SELECT * FROM film WHERE  NOT length>50 AND (rental_rate =2.99 OR rental_rate = 4.99)
```

<hr>

## ÖDEV 2

1. <b>film</b> tablosunda bulunan tüm sütunlardaki verileri replacement cost değeri 12.99 dan büyük eşit ve 16.99 küçük olma koşuluyla sıralayınız ( BETWEEN - AND yapısını kullanınız.)
```SQL
SELECT * FROM film WHERE replacement_cost BETWEEN 12.99 AND 16.99 
```

2. <b>actor</b> tablosunda bulunan first_name ve last_name sütunlardaki verileri first_name 'Penelope' veya 'Nick' veya 'Ed' değerleri olması
koşuluyla sıralayınız. ( IN operatörünü kullanınız.)

```SQL
SELECT first_name, last_name FROM actor WHERE first_name IN ('Penelope','Nick', 'ED')
```

3. <b>film</b> tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99, 2.99, 4.99 <b>VE</b> replacement_cost 12.99, 15.99, 28.99 olma koşullarıyla sıralayınız.
(IN operatörünü kullanınız.)

```SQL
SELECT * FROM film WHERE (rental_rate IN (0.99, 2.99, 4.99)) AND (replacement_cost IN (12.99, 15.99, 28.99))
```

<hr>

## ÖDEV 3

1. <b>country</b> tablosunda bulunan <b>country</b> sütunundaki ülke isimlerinden 'A' karakteri ile başlayıp 'a' karakteri ile sonlananları sıralayınız.

```SQL
 SELECT country FROM country  WHERE country LIKE  'A%a'
```

2. <b>country</b> tablosunda bulunan <b>country</b> sütunundaki ülke isimlerinden en az 6 karakterden oluşan ve sonu 'n' karakteri ile sonlananları sıralayınız.

```SQL
SELECT country FROM country WHERE country LIKE '_____%n'
```

3. <b>film</b> tablosunda bulunan <b>title</b> sütunundaki film isimlerinden en az 4 adet büyük ya da küçük harf farketmesizin 'T' karakteri içeren film isimlerini sıralayınız.

```SQL
SELECT title FROM film WHERE title ILIKE '%t%t%t%t%'
```


4. <b>film</b> tablosunda bulunan tüm sütunlardaki verilerden title 'C' karakteri ile başlayan ve uzunluğu (length) 90 dan büyük olan ve rental_rate 2.99
olan verileri sıralayınız.

```SQL
SELECT * FROM film WHERE title LIKE 'C%' AND length>90 AND rental_rate = 2.99
```
<hr>

## ÖDEV 4

1. <b>film</b> tablosunda bulunan <b>replacement_cost</b> sütununda bulunan birbirinden farklı değerleri sıralayınız.

```SQL
SELECT DISTINCT replacement_cost FROM film 
```

2. <b>film</b> tablosunda bulunan <b>replacement_cost</b> sütununda birbirinden farklı kaç tane veri vardır?

```SQL
SELECT COUNT(DISTINCT replacement_cost) FROM film
```

3. <b>film</b> tablosunda bulunan film isimlerinde (title) kaç tanesini T karakteri ile başlar ve aynı zamanda rating 'G' ye eşittir?

```SQL
SELECT COUNT * FROM film WHERE LIKE 'T%' AND rating = 'G'
```

4. <b>country</b> tablosunda bulunan ülke isimlerinden (country) kaç tanesi 5 karakterden oluşmaktadır?

```SQL
SELECT COUNT * FROM country WHERE LIKE '_____'
```

5. <b>city</b> tablosundaki şehir isimlerinin kaçtanesi 'R' veya r karakteri ile biter?

```SQL
SELECT COUNT * FROM  city WHERE city_names ILIKE '%r' 
```


<hr>

## ÖDEV 5

1. <b>film</b> tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en uzun (length) 5 filmi sıralayınız.

```SQL
SELECT * FROM film WHERE title LIKE '%n' ORDER BY length DESC LIMIT 5
```

2. <b>film</b> tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en kısa (length) ikinci 5 filmi sıralayınız.

```SQL
SELECT * FROM film WHERE  title LIKE '%n' ORDER BY length OFFSET 5 LIMIT 5
```

3. <b>customer</b> tablosunda bulunan last_name sütununa göre azalan yapılan sıralamada store_id 1 olmak koşuluyla ilk 4 veriyi sıralayınız.

```SQL
SELECT * FROM customer WHERE store_id = 1 ORDER BY last_name DESC LIMIT 4
```


<hr>

## ÖDEV 6

1. <b>film</b> tablosunda bulunan <b>rental_rate</b> sütunundaki değerlerin ortalaması nedir?

```SQL
SELECT AVG(rental_rate) FROM film
```

2. <b>film</b> tablosunda bulunan filmlerden kaç tanesi 'C' karakteri ile başlar?

```SQL
SELECT COUNT(*) FROM WHERE title LIKE 'C%'
```

3. <b>film</b> tablosunda bulunan filmlerden rental_rate değeri 0.99 a eşit olan en uzun (length) film kaç dakikadır?

```SQL
SELECT MAX(length) FROM film WHERE rental_rate = 0.99
```

4. <b>film</b> tablosunda bulunan filmlerin uzunluğu 150 dakikadan büyük olanlarına ait kaç farklı replacement_cost değeri vardır?

```SQL
SELECT COUNT(DISTINCT replacement_cost) FROM film WHERE length>150
```


<hr>

## ÖDEV 7

1. <b>film</b> tablosunda bulunan filmleri <b>rating</b> değerlerine göre gruplayınız.

```SQL
SELECT * FROM film GROUP BY rating
```


2. <b>film</b> tablosunda bulunan filmleri <b>replacement_cost</b> sütununa göre grupladığımızda film sayısı 50 den fazla olan replacement_cost değerini
ve karşılık gelen film sayısını sıralayınız.

```SQL
SELECT replacement_cost, COUNT(*) FROM film GROUP BY replacement_cost HAVING COUNT(*)>50
```


3. <b>customer</b> tablosunda bulunan store_id değerlerine karşılık gelen müşteri sayılarını nelerdir?


```SQL
SELECT store_id, COUNT(*) FROM customer GROUP BY store_id
```

4. <b>city</b> tablosunda bulunan şehir verilerini <b>country_id</b> sütununa göre gruplandırdıktan sonra en fazla şehir sayısı barındıra country_id bilgisini
ve şehir sayısını paylaşınız.


```SQL
SELECT country_id, COUNT(*) FROM city GROUP BY country_id ORDER BY COUNT(*) DESC LIMIT 1
```


<hr>

## ÖDEV 8

1. <b>test</b> veritabanınızda <b>employee</b> isimli sütun bilgileri id(INTEGER), name VARCHAR(50), birthday DATE, email VARCHAR(100) olan bir tablo oluşturalım.

```SQL
CREATE TABLE employee(
id INTEGER,
name VARCHAR(50),
birthday DATE,
email VARCHAR(100)
);
```

2. Oluşturduğumuz <b>employee</b> tablosuna 'Mockaroo' servisini kullanarak 50 adet veri ekleyelim.

```SQL
insert into MOCK_DATA (id, first_name, birthday, email) values (1, 'Auguste', '2007-06-10', 'atinn0@yolasite.com');
insert into MOCK_DATA (id, first_name, birthday, email) values (2, 'Nikaniki', '2010-04-03', 'npierse1@miitbeian.gov.cn');
insert into MOCK_DATA (id, first_name, birthday, email) values (3, 'Adan', '2020-05-24', 'agregg2@walmart.com');
insert into MOCK_DATA (id, first_name, birthday, email) values (4, 'Ward', '2013-06-26', 'wwoofinden3@pinterest.com');
insert into MOCK_DATA (id, first_name, birthday, email) values (5, 'Mariele', '2017-10-13', 'mklimontovich4@pcworld.com');
insert into MOCK_DATA (id, first_name, birthday, email) values (6, 'Betteanne', '2002-01-18', 'bmactrustey5@joomla.org');
insert into MOCK_DATA (id, first_name, birthday, email) values (7, 'Philippe', '2006-11-24', 'pmallebone6@miibeian.gov.cn');
insert into MOCK_DATA (id, first_name, birthday, email) values (8, 'Pepi', '2002-11-14', 'pwhitby7@simplemachines.org');
insert into MOCK_DATA (id, first_name, birthday, email) values (9, 'Merrick', '2009-07-03', 'madin8@uol.com.br');
insert into MOCK_DATA (id, first_name, birthday, email) values (10, 'Allayne', '2002-10-13', 'aormes9@sun.com');
insert into MOCK_DATA (id, first_name, birthday, email) values (11, 'Marie-jeanne', '2020-08-01', 'mjefferiesa@multiply.com');
insert into MOCK_DATA (id, first_name, birthday, email) values (12, 'Hunfredo', '2010-09-27', 'hgethingsb@harvard.edu');
insert into MOCK_DATA (id, first_name, birthday, email) values (13, 'Addia', '2020-07-30', 'acharnockc@theglobeandmail.com');
insert into MOCK_DATA (id, first_name, birthday, email) values (14, 'Jean', '2019-12-24', 'jriccardid@privacy.gov.au');
insert into MOCK_DATA (id, first_name, birthday, email) values (15, 'Alaric', '2009-12-01', 'aettere@cnn.com');
insert into MOCK_DATA (id, first_name, birthday, email) values (16, 'Pam', '2017-08-09', 'pcopsf@archive.org');
insert into MOCK_DATA (id, first_name, birthday, email) values (17, 'Aggi', '2012-07-26', 'aximenezg@fc2.com');
insert into MOCK_DATA (id, first_name, birthday, email) values (18, 'Sonia', '2008-03-20', 'scamamillh@patch.com');
insert into MOCK_DATA (id, first_name, birthday, email) values (19, 'Alon', '2010-06-15', 'amusprati@hao123.com');
insert into MOCK_DATA (id, first_name, birthday, email) values (20, 'Roshelle', '2011-01-08', 'rmcgenisj@unblog.fr');
insert into MOCK_DATA (id, first_name, birthday, email) values (21, 'Lucille', '2004-08-24', 'lrayburnk@typepad.com');
insert into MOCK_DATA (id, first_name, birthday, email) values (22, 'Astrix', '2018-03-16', 'aitscowiczl@opera.com');
insert into MOCK_DATA (id, first_name, birthday, email) values (23, 'Louise', '2021-05-05', 'lmathanm@ft.com');
insert into MOCK_DATA (id, first_name, birthday, email) values (24, 'Otha', '2020-03-02', 'ocarwardinen@alibaba.com');
insert into MOCK_DATA (id, first_name, birthday, email) values (25, 'Gonzalo', '2020-08-16', 'gwillwoodo@4shared.com');
insert into MOCK_DATA (id, first_name, birthday, email) values (26, 'Brittaney', '2009-12-30', 'bvallowp@edublogs.org');
insert into MOCK_DATA (id, first_name, birthday, email) values (27, 'Devin', '2017-01-09', 'dmaylourq@harvard.edu');
insert into MOCK_DATA (id, first_name, birthday, email) values (28, 'Cris', '2013-01-01', 'coveryr@senate.gov');
insert into MOCK_DATA (id, first_name, birthday, email) values (29, 'Gawain', '2014-10-05', 'gmacentees@nasa.gov');
insert into MOCK_DATA (id, first_name, birthday, email) values (30, 'Beltran', '2016-11-22', 'bbutnert@github.com');
insert into MOCK_DATA (id, first_name, birthday, email) values (31, 'Kylynn', '2009-03-01', 'kshipu@netscape.com');
insert into MOCK_DATA (id, first_name, birthday, email) values (32, 'Parry', '2019-05-14', 'pdashkovv@webs.com');
insert into MOCK_DATA (id, first_name, birthday, email) values (33, 'Logan', '2012-09-19', 'lantonovw@jigsy.com');
insert into MOCK_DATA (id, first_name, birthday, email) values (34, 'Camel', '2009-10-15', 'cfettesx@last.fm');
insert into MOCK_DATA (id, first_name, birthday, email) values (35, 'Kellby', '2008-06-10', 'kkenwortheyy@go.com');
insert into MOCK_DATA (id, first_name, birthday, email) values (36, 'Russ', '2014-06-02', 'rboalerz@columbia.edu');
insert into MOCK_DATA (id, first_name, birthday, email) values (37, 'Shaine', '2009-10-05', 'shughlin10@addtoany.com');
insert into MOCK_DATA (id, first_name, birthday, email) values (38, 'Peder', '2017-08-20', 'pmackenzie11@yandex.ru');
insert into MOCK_DATA (id, first_name, birthday, email) values (39, 'Susanna', '2003-03-10', 'skeune12@uol.com.br');
insert into MOCK_DATA (id, first_name, birthday, email) values (40, 'Antin', '2012-10-22', 'acumming13@netscape.com');
insert into MOCK_DATA (id, first_name, birthday, email) values (41, 'Staci', '2003-07-09', 'sgoadby14@google.ca');
insert into MOCK_DATA (id, first_name, birthday, email) values (42, 'Rancell', '2003-10-04', 'rcard15@loc.gov');
insert into MOCK_DATA (id, first_name, birthday, email) values (43, 'Berni', '2004-01-15', 'bcronkshaw16@time.com');
insert into MOCK_DATA (id, first_name, birthday, email) values (44, 'Pauline', '2011-10-20', 'ptomashov17@craigslist.org');
insert into MOCK_DATA (id, first_name, birthday, email) values (45, 'Jillane', '2019-02-24', 'jcasement18@ebay.co.uk');
insert into MOCK_DATA (id, first_name, birthday, email) values (46, 'Odetta', '2020-10-31', 'olambshine19@mail.ru');
insert into MOCK_DATA (id, first_name, birthday, email) values (47, 'Vera', '2011-10-09', 'vcecere1a@e-recht24.de');
insert into MOCK_DATA (id, first_name, birthday, email) values (48, 'Carlo', '2010-03-03', 'cmchardy1b@e-recht24.de');
insert into MOCK_DATA (id, first_name, birthday, email) values (49, 'Mela', '2001-10-19', 'mklaiser1c@stumbleupon.com');
insert into MOCK_DATA (id, first_name, birthday, email) values (50, 'Curtice', '2016-09-21', 'cmcmakin1d@ox.ac.uk');
```

3. Sütunların her birine göre diğer sütunları güncelleyecek 5 adet UPDATE işlemi yapalım.

```SQL
UPDATE employee
SET first_name = XXX,
birthday = 2001-10-13,
email = xxx@xx.x.com
WHERE id IN (10,12,13,15,17)
```

4. Sütunların her birine göre ilgili satırı silecek 5 adet DELETE işlemi yapalım.

```SQL
DELETE FROM employee
WHERE id IN(10,12,13,15,17)
```


<br>

## ÖDEV 9

1. <b>city</b> tablosu ile <b>country</b> tablosunda bulunan şehir (city) ve ülke (country) isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.

```SQL
SELECT city.name, country.name FROM city JOIN country ON city.country_id = country.country_id
```

2. <b>customer</b> tablosu ile <b>payment</b> tablosunda bulunan payment_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.

```SQL
SELECT payment_id, first_name, last_name FROM customer JOIN payment ON customer.customer_id = payment.customer_id
```


3. <b>customer</b> tablosu ile <b>rental</b> tablosunda bulunan rental_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.

```SQL
SELECT rental_id, first_name, last_name FROM customer JOIN rental ON customer.customer_id = rental.customer_id
```
