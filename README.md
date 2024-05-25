# Домашняя работа к занятию «Работа с данными DDL-DLM» - Боровик А. А.

### Задание 1

Ответ:

Создал учётную запись sys_temp:

```
CREATE USER 'sys_temp'@'localhost' IDENTIFIED BY '1111';
```

Таблица пользователей баз данных:

```
SELECT Users, Host FROM mysql.user
```

![Таблица пользователей](https://github.com/Lex-Chaos/DDL-DLM-hw/blob/main/img/Task1-1_table_of_users.png)


Дал пользователь sys_temp все привилегии:

```
GRANT ALL PRIVILEGES ON *.* TO 'sys_temp'@'localhost' WITH GRANT OPTION;
```

Дальше работал в IDE/

Запрос на получение списка прав для пользователей sys_temp:

```
SHOW GRANTS FOR 'sys_temp'@'localhost';
```

Привилегии пользователя sys_temp:

![Привилегии](https://github.com/Lex-Chaos/DDL-DLM-hw/blob/main/img/Task1-2_privileges.png)

![Ещё привилегии](https://github.com/Lex-Chaos/DDL-DLM-hw/blob/main/img/Task1-3_other_privileges.png)

Восстановил из дампа базу sakila.

Таблицы базы sakila:

![Таблицы базы](https://github.com/Lex-Chaos/DDL-DLM-hw/blob/main/img/Task1-4_tables.png)

---

### Задание 2

Ответ:

[Список таблиц и ключей](https://github.com/Lex-Chaos/DDL-DLM-hw/blob/main/files/list_of_tables.xlsx)

---

### Задание 3*

Ответ:

Сначала оказалось нужно выдать привилегии пользователю sys_temp для базы sakila:

```
GRANT ALL PRIVILEGES ON sakila.* TO 'sys_temp'@'localhost' WITH GRANT OPTION;
```

Потом можно убрать часть привилегий:

```
REVOKE INSERT, DELETE, UPDATE ON sakila.* FROM 'sys_temp'@'localhost';
```

![Привилегии после удаления](https://github.com/Lex-Chaos/DDL-DLM-hw/blob/main/img/Task3-1_privileges_sys_temp.png)