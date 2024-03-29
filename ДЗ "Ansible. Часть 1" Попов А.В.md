# Домашнее задание к занятию «Ansible. Часть 1» Попов А.В. 

### Задание 1

**Ответьте на вопрос в свободной форме.**

Какие преимущества даёт подход IAC?

**Ответ:**
1. Автоматизация
2. Скорость поднятия инфраструктуры
3. Минимизация рисков через уменьшение шанса человеческой ошибки
4. Воспроизводимость
5. Масштубируемость
---

### Задание 2 

**Выполните действия и приложите скриншоты действий.**

1. Установите Ansible.
2. Настройте управляемые виртуальные машины, не меньше двух.
3. Создайте файл inventory. Предлагается использовать файл, размещённый в папке с проектом, а не файл inventory по умолчанию.
4. Проверьте доступность хостов с помощью модуля ping.

**Ответ:**
![Image alt](https://github.com/goldcomru/SysAdmin/blob/main/Ansible%201.png)
---

### Задание 3 

**Ответьте на вопрос в свободной форме.**

Какая разница между параметрами forks и serial? 

**Ответ:**

forks - определяет максимальное количество одновременных подключений, которые Ansible выполняет для каждой задачи в рамках одного запуска. Т.е. это то количество узлов, на которых должна проводиться работа одновременно.

serial - последовательное определяет максимальное количество узлов. Т.е. если узлов 4, а параметр serial = 2, то Ansible будет работать сначала с первыми 2 узлами, и только потом с другими 2мя.

---

### Задание 4 

В этом задании вы будете работать с Ad-hoc коммандами.

**Выполните действия и приложите скриншоты запуска команд.**

1. Установите на управляемых хостах любой пакет, которого нет.
2. Проверьте статус любого, присутствующего на управляемой машине, сервиса. 
3. Создайте файл с содержимым «I like Linux» по пути /tmp/netology.txt.

**Ответ:**
1.
![Image alt](https://github.com/goldcomru/SysAdmin/blob/main/Ansible%202%20%D0%BD%D0%B5%20%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D0%B5%D1%82.png)

Здесь у меня возникли сложности. Первая машина наотрез отказывается работать из под рута. Вторая спокойно работает. Причем они абсолютно идентичные, права выдал одинаковые. Помогла только добавочная команда, приведённая на следующих скриншотах

2.
![Image alt](https://github.com/goldcomru/SysAdmin/blob/main/Ansible%203.png)
![Image alt](https://github.com/goldcomru/SysAdmin/blob/main/Ansible%204.png)

3.
![Image alt](https://github.com/goldcomru/SysAdmin/blob/main/Ansible%205.png)
