# Домашнее задание к занятию «Система мониторинга Zabbix» - `Арзыбов Владислав`

В практике есть 2 основных и 1 дополнительное (со звездочкой) задания. Первые два нужно выполнять обязательно, третье - по желанию и его решение никак не повлияет на получение вами зачета по этому домашнему заданию, при этом вы сможете глубже и/или шире разобраться в материале. 

Пожалуйста, присылайте на проверку всю задачу сразу. Любые вопросы по решению задач задавайте в чате учебной группы.

### Цели задания
1. Научиться устанавливать Zabbix Server c веб-интерфейсом
2. Научиться устанавливать Zabbix Agent на хосты
3. Научиться устанавливать Zabbix Agent на компьютер и подключать его к серверу Zabbix 

### Чеклист готовности к домашнему заданию
- [ ] Просмотрите в личном кабинете занятие "Система мониторинга Zabbix" 


---

### Задание 1 

Установите Zabbix Server с веб-интерфейсом.

#### Процесс выполнения
1. Выполняя ДЗ, сверяйтесь с процессом отражённым в записи лекции.

   **sudo apt update**
   
3. Установите PostgreSQL. Для установки достаточна та версия, что есть в системном репозитороии Debian 11.

   **sudo apt install postgresql**
   
5. Пользуясь конфигуратором команд с официального сайта, составьте набор команд для установки последней версии Zabbix с поддержкой PostgreSQL и Apache.

   **sudo -s**

   **wget https://repo.zabbix.com/zabbix/7.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_7.0-2+ubuntu22.04_all.deb**

   **dpkg -i zabbix-release_7.0-2+ubuntu22.04_all.deb**

   **apt update**

   **apt install zabbix-server-pgsql zabbix-frontend-php php8.1-pgsql zabbix-apache-conf zabbix-sql-scripts zabbix-agent**

   **sudo -u postgres createuser --pwprompt zabbix**
   
   **sudo -u postgres createdb -O zabbix zabbix**

   **zcat /usr/share/zabbix-sql-scripts/postgresql/server.sql.gz | sudo -u zabbix psql zabbix**

   **sed -i 's/# DBPassword=/DBPassword=12345/g' /etc/zabbix/zabbix_server.conf**

   **systemctl restart zabbix-server zabbix-agent apache2**

   **systemctl enable zabbix-server zabbix-agent apache2**

   ![изображение](https://github.com/user-attachments/assets/9e88f489-bcc4-405c-8711-317849096cfd)
   
7. Выполните все необходимые команды для установки Zabbix Server и Zabbix Web Server.

   ![изображение](https://github.com/user-attachments/assets/d363008f-e270-4cb1-b9f5-27c08a336622)


#### Требования к результаты 
1. Прикрепите в файл README.md скриншот авторизации в админке.
2. Приложите в файл README.md текст использованных команд в GitHub.

---

### Задание 2 

Установите Zabbix Agent на два хоста.

#### Процесс выполнения
1. Выполняя ДЗ, сверяйтесь с процессом отражённым в записи лекции.
2. Установите Zabbix Agent на 2 вирт.машины, одной из них может быть ваш Zabbix Server.

   **sudo -s**

   **wget https://repo.zabbix.com/zabbix/7.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_7.0-2+ubuntu22.04_all.deb**

   **dpkg -i zabbix-release_7.0-2+ubuntu22.04_all.deb**

   **apt update**

   **apt install zabbix-agent**

   **systemctl restart zabbix-agent**

   **systemctl enable zabbix-agent**

   ![изображение](https://github.com/user-attachments/assets/89f00078-117e-434d-a4e4-d739eed2bc37)

   ![изображение](https://github.com/user-attachments/assets/f99029ad-c8aa-4a66-b0c1-cd6ff5aa145d)
    
4. Добавьте Zabbix Server в список разрешенных серверов ваших Zabbix Agentов.

   **sed -i 's/Server=127.0.0.1/Server=192.168.123.1/g' /etc/zabbix/zabbix_agentd.conf**
   
6. Добавьте Zabbix Agentов в раздел Configuration > Hosts вашего Zabbix Servera.
7. Проверьте, что в разделе Latest Data начали появляться данные с добавленных агентов.

#### Требования к результаты 
1. Приложите в файл README.md скриншот раздела Configuration > Hosts, где видно, что агенты подключены к серверу
2. Приложите в файл README.md скриншот лога zabbix agent, где видно, что он работает с сервером
3. Приложите в файл README.md скриншот раздела Monitoring > Latest data для обоих хостов, где видны поступающие от агентов данные.
4. Приложите в файл README.md текст использованных команд в GitHub

---
## Задание 3 со звёздочкой*
Установите Zabbix Agent на Windows (компьютер) и подключите его к серверу Zabbix.

#### Требования к результаты 
1. Приложите в файл README.md скриншот раздела Latest Data, где видно свободное место на диске C:
--- 

## Критерии оценки

1. Выполнено минимум 2 обязательных задания
2. Прикреплены требуемые скриншоты и тексты 
3. Задание оформлено в шаблоне с решением и опубликовано на GitHub

