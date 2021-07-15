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

## Ödev 2

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