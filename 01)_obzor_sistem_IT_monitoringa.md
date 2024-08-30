# Домашнее задание к занятию «Обзор систем IT-мониторинга»

#### Это задание для самостоятельной отработки навыков и не предполагает обратной связи от преподавателя. Его выполнение не влияет на завершение модуля. Но мы рекомендуем его выполнить, чтобы закрепить полученные знания.

### Цели задания
1. Научиться запускать мониторинг ИТ-системы через Yandex Monitoring
2. Научиться настраивать уведомления о событиях в процессе мониторинга через e-mail 

### Чеклист готовности к домашнему заданию
- [ ] Просмотрите в личном кабинете занятие "Обзор систем ИТ-мониторинга" 

---
 
### Задание 1

Создайте виртуальную машину в Yandex Compute Cloud и с помощью Yandex Monitoring создайте дашборд, на котором будет видно загрузку процессора.

#### Процесс выполнения
1. В окне браузера откройте облачную платформу Yandex Cloud

   ![изображение](https://github.com/user-attachments/assets/4ced6504-7540-48eb-803a-bb5d63d88a91)
   
3. Перейдите в раздел "Все сервисы" > "Инфраструктура и сеть" > "Compute Cloud"

   ![изображение](https://github.com/user-attachments/assets/4b08aff4-efb1-4d17-9b61-88a2339cb51e)

5. Нажмите на синюю кнопку "Создать ВМ" в правом верхнем углу окна браузера

   ![изображение](https://github.com/user-attachments/assets/eb4afeb9-4a3b-4a22-9ab8-21ce0ae78d36)

6. Задайте имя виртуальной машины. Используйте английские буквы и цифры.

   ![изображение](https://github.com/user-attachments/assets/09304437-a686-4a4d-b0d3-30f0673b6874)

8. Выберите операционную систему Debian 11

   ![изображение](https://github.com/user-attachments/assets/d732c7e5-b524-4846-ab3f-23bc0e95f60a)

10. Установите объём HDD равный 3ГБ

    ![изображение](https://github.com/user-attachments/assets/f436c7dc-6a0c-4c0b-b6d9-c66f61fb6a78)

12. Выберите платформу Intel Ice Lake

    ![изображение](https://github.com/user-attachments/assets/0df2ac5e-b2a1-4638-bc78-26ec39267725)

14. Установите количество vCPU равное 2

    ![изображение](https://github.com/user-attachments/assets/1205484c-d58e-482a-91a4-b6670a28e560)

16. Установите гарантированную долю vCPU равную 20%

    ![изображение](https://github.com/user-attachments/assets/fd1154f3-bac1-493d-b5a0-2d0883cf2a50)

18. Задайте количество RAM равное 1ГБ

    ![изображение](https://github.com/user-attachments/assets/ad8987d7-9b9e-442b-a980-5e8e9db655f2)

20. Поставьте галочку "Прерываемая"

    ![изображение](https://github.com/user-attachments/assets/4eb5885b-7fe9-4b54-92a2-dd1d199cea23)

22. В разделе "Доступ" выберите сервисный аккаунт с ролью monitoring.editor. Если такого аккаунта нет, нажмите на кнопку "Создать новый". Задайте имя аккаунта английскими буквами, напротив надписи "Роли в каталоге" нажмите на знак "плюс". Прокручивая колесо мыши на себя, найдите роль monitoring.editor и нажмите на неё левой кнопкой мыши. Теперь вы сможете найти только что созданную роль в выпадающем списке аккаунтов.

    ![изображение](https://github.com/user-attachments/assets/c8d55df6-f3ca-4488-9698-a1cdfb27804f)

24. Задайте логин учётной записи вашей виртуальной машины

    ![изображение](https://github.com/user-attachments/assets/060735d8-783b-4951-b3ea-e135e0d8ccca)

26. Вставьте публичный SHH-ключ в поле SSH-ключ. Если этого ключа у вас нет, создайте его с помощью утилиты PuTTYgen

    ![изображение](https://github.com/user-attachments/assets/9f9be539-e2ab-4621-b87e-d1fd2183741a)

28. Поставьте галочку "Установить" в пункте "Агент сбора метрик"

    ![изображение](https://github.com/user-attachments/assets/221946c0-8643-4074-8d71-e28d5ea04757)

30. Нажмите на синюю кнопку "Создать ВМ"

    ![изображение](https://github.com/user-attachments/assets/acdba4db-26b7-455c-bdee-d329741923c4)

32. Перейдите в раздел "Все сервисы" > "Инфраструктура и сеть" > "Monitoring"

    ![изображение](https://github.com/user-attachments/assets/11429f6e-2570-42df-8f39-f2151d7c90c1)

34. Нажмите на кнопку "Создать дашборд", расположенную в разделе "Возможности сервиса" > "Дашборды"

    ![изображение](https://github.com/user-attachments/assets/db98aa7b-45e1-429f-a6e9-1eb3102beaaf)

36. В открывшемся окне в разделе "Добавить виджет" нажмите на "График"

    ![изображение](https://github.com/user-attachments/assets/b35d9bbe-417e-45af-a492-956c07a1b132)

38. Пред вами предстанет конструктор запросов, выберите "Запрос А"

    ![изображение](https://github.com/user-attachments/assets/765cd170-e60e-407c-bef0-3e381754050d)

40. В параметре service конструктора запросов выберите Compute Cloud

    ![изображение](https://github.com/user-attachments/assets/c005aaa2-0b7c-43ab-8355-539f0d291642)

42. В появившемся параметре name конструктора запросов выберите cpu_utilization

    ![изображение](https://github.com/user-attachments/assets/a70d9849-7445-4e75-82a0-b56713160236)

44. Поправьте диапазон времени отрисовки графика, нажав на кнопку "Сейчас" в верху экрана, левее кнопок 3m, 1h, 1d, 1w, "Отменить".

    ![изображение](https://github.com/user-attachments/assets/8f1747ba-c08c-4145-99d9-9ea97f78e07c)

46. Нажмите на кнопку "Сохранить" в правом верхнем углу экрана

    ![изображение](https://github.com/user-attachments/assets/b8e5d4dc-230a-4283-8c65-19234d510d8a)

48. Задайте имя дашборда, если появится окно ввода имени дашборда

    ![изображение](https://github.com/user-attachments/assets/3b24708e-06b9-48e9-8c11-13741132ba19)



### Задание 2 

С помощью Yandex Monitoring сделайте 2 алерта на загрузку процессора: WARN и ALARM. Создайте уведомление по e-mail.

 ![изображение](https://github.com/user-attachments/assets/efaeb042-fde5-44b7-90fb-141e6319405a)

 ![изображение](https://github.com/user-attachments/assets/d64c9c4f-505b-4cab-a1a0-ac8355eeda14)

 ![изображение](https://github.com/user-attachments/assets/8b313433-799c-45db-bc1a-74f93d028303)

![изображение](https://github.com/user-attachments/assets/c49e82e9-af6f-4633-ad8a-d9c2b412b0a9)

![изображение](https://github.com/user-attachments/assets/2b70a461-c8a8-4d19-82f5-5baa4e78b450)




