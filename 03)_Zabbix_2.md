# Домашнее задание к занятию «`Система мониторинга Zabbix. Часть 2`» - `Арзыбов Владислав`

В практике есть 4 основных и 5 дополнительных (со звездочкой) заданий. Основные задания нужно выполнять обязательно, со звездочкой - по желанию и его решение никак не повлияет на получение вами зачета по этому домашнему заданию, при этом вы сможете глубже и/или шире разобраться в материале. 

Пожалуйста, присылайте на проверку все задачи сразу. Любые вопросы по решению задавайте в чате учебной группы.

### Цели задания
1. Научитья создавать свои шаблоны в Zabbix, добавлять в Zabbix хосты и связывать шаблон с хостами
2. Научиться составлять кастомный дашборд
3. Научиться создавать UserParameter на Bash
4. Научиться создавать Python-скрип, добавляться в него UserParameter и прикреплять к шаблону
5. Научиться создавать Vagrant-скрипты для Zabbix Agent

### Чеклист готовности к домашнему заданию
- [ ] Просмотрите в личном кабинете занятие "Система мониторинга Zabbix. Часть 2" 

 ---

### Задание 1
Создайте свой шаблон, в котором будут элементы данных, мониторящие загрузку CPU и RAM хоста.

#### Процесс выполнения
1. Выполняя ДЗ сверяйтесь с процессом отражённым в записи лекции.
2. В веб-интерфейсе Zabbix Servera в разделе Templates создайте новый шаблон

   ![изображение](https://github.com/user-attachments/assets/a9eff5dc-a057-440c-b0d8-254d1cc600f7)

4. Создайте Item который будет собирать информацию об загрузке CPU в процентах
5. Создайте Item который будет собирать информацию об загрузке RAM в процентах

   ![изображение](https://github.com/user-attachments/assets/5a18ecd1-ba67-43e5-9a82-7df984a236e2)

#### Требования к результату
- [ ] Прикрепите в файл README.md скриншот страницы шаблона с названием «Задание 1»

  ![изображение](https://github.com/user-attachments/assets/781d9ada-f442-4f85-b2c6-1e4f1d2d4f36)

  ![изображение](https://github.com/user-attachments/assets/a45e9fa3-96e7-4d0c-9592-719add321a15)

    

 ---

### Задание 2
Добавьте в Zabbix два хоста и задайте им имена <фамилия и инициалы-1> и <фамилия и инициалы-2>. Например: ivanovii-1 и ivanovii-2.

#### Процесс выполнения
1. Выполняя ДЗ сверяйтесь с процессом отражённым в записи лекции.
2. Установите Zabbix Agent на 2 виртмашины, одной из них может быть ваш Zabbix Server

   ![363482510-89f00078-117e-434d-a4e4-d739eed2bc37](https://github.com/user-attachments/assets/cfda67d2-123f-45e1-8113-747b022d28cc)

   ![363482605-f99029ad-c8aa-4a66-b0c1-cd6ff5aa145d](https://github.com/user-attachments/assets/2e082ad7-accd-4cf1-ae89-b9ed99360c9e)

4. Добавьте Zabbix Server в список разрешенных серверов ваших Zabbix Agentов

   ![изображение](https://github.com/user-attachments/assets/e581c04f-ac6d-4461-91bf-81dda22f64f8)

   ![изображение](https://github.com/user-attachments/assets/72e312c9-3464-4d06-a344-d598aecf00d4)

6. Добавьте Zabbix Agentов в раздел Configuration > Hosts вашего Zabbix Servera  
8. Прикрепите за каждым хостом шаблон Linux by Zabbix Agent

   ![изображение](https://github.com/user-attachments/assets/b5d35184-2ef1-478a-8467-5f65e68e02c5)

9. Проверьте что в разделе Latest Data начали появляться данные с добавленных агентов

   ![изображение](https://github.com/user-attachments/assets/8f045521-fb4e-4ced-af1a-c43b408f7bdb)

   ![изображение](https://github.com/user-attachments/assets/f3828e5b-fdde-457d-90d6-5d338d817abb)

#### Требования к результату
- [ ] Результат данного задания сдавайте вместе с заданием 3

 ---

### Задание 3
Привяжите созданный шаблон к двум хостам. Также привяжите к обоим хостам шаблон Linux by Zabbix Agent.

#### Процесс выполнения
1. Выполняя ДЗ сверяйтесь с процессом отражённым в записи лекции.
2. Зайдите в настройки каждого хоста и в разделе Templates прикрепите к этому хосту ваш шаблон

   ![изображение](https://github.com/user-attachments/assets/0c721b8e-74b0-45fa-98b2-5ac297b2fa42)

4. Так же к каждому хосту привяжите шаблон Linux by Zabbix Agent
5. Проверьте что в раздел Latest Data начали поступать необходимые данные из вашего шаблона

   ![изображение](https://github.com/user-attachments/assets/231aff14-1abb-4cf9-b34a-e3fbb0cb0bd8)

   ![изображение](https://github.com/user-attachments/assets/66cab757-d5fe-497f-a8b1-22587c755444)

   ![изображение](https://github.com/user-attachments/assets/f7b0ef75-c04d-4017-9a01-8fd97031880a)

   ![изображение](https://github.com/user-attachments/assets/9b569b00-fdb1-464b-b945-75a77c06282c)

#### Требования к результату
- [ ] Прикрепите в файл README.md скриншот страницы хостов, где будут видны привязки шаблонов с названиями «Задание 2-3». Хосты должны иметь зелёный статус подключения

 ---

### Задание 4
Создайте свой кастомный дашборд.

#### Процесс выполнения
1. Выполняя ДЗ сверяйтесь с процессом отражённым в записи лекции.
2. В разделе Dashboards создайте новый дашборд

   ![изображение](https://github.com/user-attachments/assets/a3cff082-c29b-48ae-b978-9916574ad964)
   
4. Разместите на нём несколько графиков на ваше усмотрение.

   ![изображение](https://github.com/user-attachments/assets/b0f03699-15c0-4a68-aa37-402492481b0d)

#### Требования к результату
- [ ] Прикрепите в файл README.md скриншот дашборда с названием «Задание 4»

 ---

### Задание 5* со звёздочкой
Создайте карту и расположите на ней два своих хоста.

#### Процесс выполнения
1. Настройте между хостами линк.

   ![изображение](https://github.com/user-attachments/assets/5fe028e2-d850-4601-8029-662869a36fc2)

3. Привяжите к линку триггер, связанный с agent.ping одного из хостов, и установите индикатором сработавшего триггера красную пунктирную линию.

   ![изображение](https://github.com/user-attachments/assets/49c90af2-6b47-4f3c-8fc4-5dc3f684d367)

   ![изображение](https://github.com/user-attachments/assets/757e6c98-6e21-4c8e-9cf4-bc33338304e0)
   
5. Выключите хост, чей триггер добавлен в линк. Дождитесь срабатывания триггера.

   ![изображение](https://github.com/user-attachments/assets/f75190e7-8a96-4254-8930-57982a5dc217)



#### Требования к результату
- [ ] Прикрепите в файл README.md скриншот карты, где видно, что триггер сработал, с названием «Задание 5» 

 ---

### Задание 6* со звёздочкой
Создайте UserParameter на bash и прикрепите его к созданному вами ранее шаблону. Он должен вызывать скрипт, который:
- при получении 1 будет возвращать ваши ФИО,
- при получении 2 будет возвращать текущую дату.

#### Требования к результату
- [ ] Прикрепите в файл README.md код скрипта, а также скриншот Latest data с результатом работы скрипта на bash, чтобы был виден результат работы скрипта при отправке в него 1 и 2
 
 ---

### Задание 7* со звёздочкой
Доработайте Python-скрипт из лекции, создайте для него UserParameter и прикрепите его к созданному вами ранее шаблону. 
Скрипт должен:
- при получении 1 возвращать ваши ФИО,
- при получении 2 возвращать текущую дату,
- делать всё, что делал скрипт из лекции.

- [ ] Прикрепите в файл README.md код скрипта в Git. Приложите в Git скриншот Latest data с результатом работы скрипта на Python, чтобы были видны результаты работы скрипта при отправке в него 1, 2, -ping, а также -simple_print.*
 
 ---

### Задание 8* со звёздочкой

Настройте автообнаружение и прикрепление к хостам созданного вами ранее шаблона.

#### Требования к результату
- [ ] Прикрепите в файл README.md скриншот правила обнаружения, а также скриншот страницы Discover, где видны оба хоста.*

 ---

### Задание 9* со звёздочкой

Доработайте скрипты Vagrant для 2-х агентов, чтобы они были готовы к автообнаружению сервером, а также имели на борту разработанные вами ранее параметры пользователей.

- [ ] Приложите в GitHub файлы Vagrantfile и zabbix-agent.sh.*

## Критерии оценки

1. Выполнено минимум 4 обязательных задания
2. Прикреплены требуемые скриншоты, код и файлы 
3. Задание оформлено в шаблоне с решением и опубликовано на GitHub

