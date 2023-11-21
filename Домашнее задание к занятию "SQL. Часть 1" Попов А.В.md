# Домашнее задание к занятию «SQL. Часть 1»

Задание можно выполнить как в любом IDE, так и в командной строке.

### Задание 1

Получите уникальные названия районов из таблицы с адресами, которые начинаются на “K” и заканчиваются на “a” и не содержат пробелов.

**Ответ:**

SELECT DISTINCT district 
FROM address 
WHERE district LIKE 'K%a' AND district NOT LIKE '% %';

![Image alt](https://github.com/goldcomru/SysAdmin/blob/main/sql1.png)

### Задание 2

Получите из таблицы платежей за прокат фильмов информацию по платежам, которые выполнялись в промежуток с 15 июня 2005 года по 18 июня 2005 года **включительно** и стоимость которых превышает 10.00.

**Ответ:**

SELECT *
FROM payment
WHERE payment_date BETWEEN '2005-06-1' AND '2005-06-19' AND amount > 10;

![Image alt](https://github.com/goldcomru/SysAdmin/blob/main/sql2.png)

### Задание 3

Получите последние пять аренд фильмов.

**Ответ:**

SELECT *
FROM rental
ORDER BY rental_date DESC
LIMIT 5;

![Image alt](https://github.com/goldcomru/SysAdmin/blob/main/sql3.png)

### Задание 4

Одним запросом получите активных покупателей, имена которых Kelly или Willie. 

Сформируйте вывод в результат таким образом:
- все буквы в фамилии и имени из верхнего регистра переведите в нижний регистр,
- замените буквы 'll' в именах на 'pp'.

**Ответ:**

SELECT REPLACE(LOWER (first_name), 'll', 'pp'), LOWER (last_name)
FROM customer
WHERE first_name LIKE 'Kelly' or first_name LIKE 'Willie' and active = 1;

![Image alt](https://github.com/goldcomru/SysAdmin/blob/main/sql4.png)
