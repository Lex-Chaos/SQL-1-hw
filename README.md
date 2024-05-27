# Домашняя работа к занятию «SQL. Часть 1» - Боровик А. А.

### Задание 1

Ответ:
```
SELECT DISTINCT district
FROM sakila.address
WHERE district LIKE 'K%a' AND district NOT LIKE '% %';
```

![Задание 1](https://github.com/Lex-Chaos/SQL-1-hw/blob/main/img/Task1.png)

---

### Задание 2

Ответ:
```
SELECT *
FROM sakila.payment
WHERE amount > 10.00 AND date(payment_date) BETWEEN '2005-06-15' AND '2005-06-18';
```

![Задание 2](https://github.com/Lex-Chaos/SQL-1-hw/blob/main/img/Task2.png)

---

### Задание 3

Ответ:

```
SELECT *
FROM sakila.rental
ORDER BY rental_date DESC
LIMIT 5;
```

![Задание 3](https://github.com/Lex-Chaos/SQL-1-hw/blob/main/img/Task3.png)

---

### Задание 4

Ответ:

```
SELECT REPLACE(LOWER(first_name), 'll', 'pp')
FROM sakila.customer
WHERE first_name LIKE '%ll%';
```

![Задание 4](https://github.com/Lex-Chaos/SQL-1-hw/blob/main/img/Task4.png)

---

### Задание 5*

Ответ:

```
SELECT
LEFT(email, POSITION('@' IN email) - 1) Имя,
RIGHT(email, CHAR_LENGTH(email) - POSITION('@' IN email)) Домен
FROM sakila.customer c;
```

![Задание 5](https://github.com/Lex-Chaos/SQL-1-hw/blob/main/img/Task5.png)

---

### Задание 6*

Ответ:

```
SELECT
CONCAT(UPPER(LEFT(email, 1)),
LOWER(SUBSTR(LEFT(email, POSITION('@' IN email) - 1), 2, POSITION('@' IN email)))) Имя,
RIGHT(email, CHAR_LENGTH(email) - POSITION('@' IN email)) Домен
FROM sakila.customer c;
```

![Задание 6](https://github.com/Lex-Chaos/SQL-1-hw/blob/main/img/Task6.png)