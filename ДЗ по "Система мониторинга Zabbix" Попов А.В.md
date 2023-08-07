# Домашнее задание к занятию «Система мониторинга Zabbix» Попов А.В.
---

### Задание 1 

Установите Zabbix Server с веб-интерфейсом.

#### Процесс выполнения
1. Выполняя ДЗ сверяйтесь с процессом отражённым в записи лекции.
2. Установите PostgreSQL. Для установки достаточна та версия что есть в системном репозитороии Debian 11
3. Пользуясь конфигуратором комманд с официального сайта, составьте набор команд для установки последней версии Zabbix с поддержкой PostgreSQL и Apache
4. Выполните все необходимые команды для установки Zabbix Server и Zabbix Web Server

#### Требования к результаты 
1. Прикрепите в файл README.md скриншот авторизации в админке
2. Приложите в файл README.md текст использованных команд в GitHub

**Ответ:**
![Image alt](https://github.com/goldcomru/SysAdmin/blob/main/zabbix1.png)
1.wget https://repo.zabbix.com/zabbix/6.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_6.0-4+ubuntu22.04_all.deb

2.dpkg -i zabbix-release_6.0-4+ubuntu22.04_all.deb

3.apt update

4.apt install zabbix-server-pgsql zabbix-frontend-php php8.1-pgsql zabbix-apache-conf zabbix-sql-scripts

5.sudo -u postgres createuser --pwprompt zabbix

6.sudo -u postgres createdb -O zabbix zabbix

7.zcat /usr/share/zabbix-sql-scripts/postgresql/server.sql.gz | sudo -u zabbix psql zabbix

8.systemctl restart zabbix-server apache2

9.systemctl enable zabbix-server apache2

---

### Задание 2 - 3

Установите Zabbix Agent на два хоста.
Установите Zabbix Agent на Windows (компьютер) и подключите его к серверу Zabbix.


#### Процесс выполнения
1. Выполняя ДЗ сверяйтесь с процессом отражённым в записи лекции.
2. Установите Zabbix Agent на 2 виртмашины, одной из них может быть ваш Zabbix Server
3. Добавьте Zabbix Server в список разрешенных серверов ваших Zabbix Agentов
4. Добавьте Zabbix Agentов в раздел Configuration > Hosts вашего Zabbix Servera
5. Проверьте что в разделе Latest Data начали появляться данные с добавленных агентов

#### Требования к результаты 
1. Приложите в файл README.md скриншот раздела Configuration > Hosts, где видно, что агенты подключены к серверу
2. Приложите в файл README.md скриншот лога zabbix agent, где видно, что он работает с сервером
3. Приложите в файл README.md скриншот раздела Monitoring > Latest data для обоих хостов, где видны поступающие от агентов данные.
4. Приложите в файл README.md текст использованных команд в GitHub

#### Требования к результаты 
1. Приложите в файл README.md скриншот раздела Latest Data, где видно свободное место на диске C:

**Ответ:**
![Image alt](https://github.com/goldcomru/SysAdmin/blob/main/zabbix2.png)
![Image alt](https://github.com/goldcomru/SysAdmin/blob/main/zabbix3.png)
![Image alt](https://github.com/goldcomru/SysAdmin/blob/main/zabbix4.png)
![Image alt](https://github.com/goldcomru/SysAdmin/blob/main/zabbix5.png)
![Image alt](https://github.com/goldcomru/SysAdmin/blob/main/zabbix6.png)


---

