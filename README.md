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
