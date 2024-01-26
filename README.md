# Домашнее задание к занятию «Резервное копирование баз данных» - Николай Копосов

### Задание 1. Резервное копирование

### Кейс
Финансовая компания решила увеличить надёжность работы баз данных и их резервного копирования. 

Необходимо описать, какие варианты резервного копирования подходят в случаях: 

1.1. Необходимо восстанавливать данные в полном объёме за предыдущий день.

1.2. Необходимо восстанавливать данные за час до предполагаемой поломки.

1.3.* Возможен ли кейс, когда при поломке базы происходило моментальное переключение на работающую или починенную базу данных.

*Приведите ответ в свободной форме.*

### Решение 1:
Для финансовой компании, где надежность и безопасность данных являются особенно важными, рекомендуется использовать комбинацию различных методов резервного копирования :

1.1. Полное резервное копирование (Full backup):

Ежедневное полное резервное копирование: Создание полной копии базы данных каждый день в конце рабочего дня. Это обеспечит возможность восстановления данных за предыдущий день в случае поломки.

Хранение на отдельных носителях: Копии базы данных должны храниться на отдельных носителях, таких как жесткие диски или в облачном хранилище. Такой подход обеспечивает защиту данных от физических повреждений или потерь.

Когда то работая в финансовой организации, я копировал данные на магнитные ленты (кассеты), сейчас даже не знаю, делает кто-то так или нет. Процесс долгий, хорошо что серверная была под 2 замками и не было необходимости в сейф убирать кассету

1.2. Необходимо восстанавливать данные за час до предполагаемой поломки:

Репликация: Использование технологии репликации для создания резервных копий базы данных на отдельные серверы. В случае поломки можно переключиться на одну из реплик, которая будет содержать данные, близкие к часу до поломки.

1.3.* Возможен ли кейс, когда при поломке базы происходило моментальное переключение на работающую или починенную базу данных:

Горячее резервирование БД: Создание резервных копий базы данных в реальном времени. Это позволяет моментально переключиться на резервную копию в случае поломки основной базы данных.

---

### Задание 2. PostgreSQL

2.1. С помощью официальной документации приведите пример команды резервирования данных и восстановления БД (pgdump/pgrestore).

2.1.* Возможно ли автоматизировать этот процесс? Если да, то как?

*Приведите ответ в свободной форме.*

### Решение 2:

``` sql
pg_dump -U koposov  -h kophost -p 5432 -d netology_bd -f > backup_file.sql 
```

```sql 
pg_restore -U koposov  -h kophost -p 5432 -d netology_bd -f < backup_file.sql
```
- koposov - имя пользователя базы данных
- kophost - имя хоста базы данных
- 5432 - порт базы данных (обычно 5432)
- netology_bd - имя базы данных, которую необходимо скопировать
- backup_file.sql - путь и имя файла, в который будет сохранен резервный дамп данных (в разных источниках видел еще расширение *.dump, но оно особо ни на что не влияет)
---

### Задание 3. MySQL

3.1. С помощью официальной документации приведите пример команды инкрементного резервного копирования базы данных MySQL. 

3.1.* В каких случаях использование реплики будет давать преимущество по сравнению с обычным резервным копированием?

*Приведите ответ в свободной форме.*

### Решение 3:

---

Задания, помеченные звёздочкой, — дополнительные, то есть не обязательные к выполнению, и никак не повлияют на получение вами зачёта по этому домашнему заданию. Вы можете их выполнить, если хотите глубже шире разобраться в материале.