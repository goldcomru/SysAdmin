# Домашнее задание к занятию «SQL. Часть 2» Попов А.В.

### Задание 1

Одним запросом получите информацию о магазине, в котором обслуживается более 300 покупателей, и выведите в результат следующую информацию: 
- фамилия и имя сотрудника из этого магазина;
- город нахождения магазина;
- количество пользователей, закреплённых в этом магазине.

**Ответ:**

SELECT CONCAT(s1.first_name, ' ', s1.last_name) as Менеджер, c.city as Город, COUNT(c2.customer_id) as 'Количество покупателей'
FROM staff s1
JOIN store s2 ON s2.store_id = s1.store_id
JOIN address a ON a.address_id = s2.address_id
JOIN city c ON c.city_id = a.city_id
JOIN customer c2 ON c2.store_id = s2.store_id
GROUP BY s1.staff_id
HAVING COUNT(c2.customer_id) > 300

![Image alt](https://github.com/goldcomru/SysAdmin/blob/main/sql2.1.png)

### Задание 2

Получите количество фильмов, продолжительность которых больше средней продолжительности всех фильмов.

**Ответ:**

SELECT COUNT(film_id) as 'Количество фильмов'
FROM film
WHERE length > (SELECT AVG(length) from film)


![Image alt](https://github.com/goldcomru/SysAdmin/blob/main/sql2.2.png)

### Задание 3

Получите информацию, за какой месяц была получена наибольшая сумма платежей, и добавьте информацию по количеству аренд за этот месяц.

**Ответ:**

SELECT MONTH(payment_date) as Месяц, SUM(amount) as 'Сумма платежей', COUNT(payment_id) as 'Количество аренд'
FROM payment
GROUP BY MONTH(payment_date)
order by SUM(amount)
desc limit 1;

![Image alt](https://github.com/goldcomru/SysAdmin/blob/main/sql2.3.png)
