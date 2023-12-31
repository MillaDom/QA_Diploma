## ПЛАН ТЕСТИРОВАНИЯ ##

## Перечень автоматизируемых сценариев ##

**Валидные данные:**

Для полей формы валидными данными следует считать:
1. Номер карты - арабские цифры, от 12 до 19 цифр.
2. Месяц -  арабские цифры от 01 до 12, не ранее текущего месяца в случае, если указан текущий год.
3. Год - арабские цифры 2 цифры (последние цифры года).
4. Владелец - символы латиницы, верхний регистр, дефис и пробел, первый и последний символы – буквы.
5. CVC/CVV - арабские цифры 3 цифры.

    Номера карт и их статусы для тестирования:

    - 4444 4444 4444 4441, status APPROVED

    - 4444 4444 4444 4442, status DECLINED

**UI-тесты**

*Позитивные тесты:*
1. Успешная покупка тура с карты: заполнение формы «Оплата по карте» валидными данными с использованием данных действующей карты (заполняем с пробелами). Ожидаемый результат - сообщение об успешной покупке.
2. Успешная покупка тура в кредит: заполнение формы «Кредит по данным карты» валидными данными с использованием данных действующей карты (заполняем с пробелами). Ожидаемый результат - сообщение об успешном получении кредита.
1. Успешная покупка тура с карты: заполнение формы «Оплата по карте» валидными данными с использованием данных действующей карты (заполняем без пробелов). Ожидаемый результат - сообщение об успешной покупке.
2. Успешная покупка тура в кредит: заполнение формы «Кредит по данным карты» валидными данными с использованием данных действующей карты (заполняем без пробелов). Ожидаемый результат - сообщение об успешном получении кредита.
5. Отказ в покупке тура с недействующей карты: заполнение формы валидными данными с использованием данных недействующей карты (заполняем с пробелами). Ожидаемый результат -  сообщение об отклонении покупки
6. Отказ в покупке тура в кредит с недействующей карты: заполнение формы валидными данными с использованием данных недействующей карты (заполняем с пробелами). Ожидаемый результат -  сообщение об отказе в кредите

*Негативные тесты/Проверка валидации полей формы:*

1. Заполнение поля "Номер карты" 11 рандомными арабскими цифрами, прочие поля валидно. Ожидаемый результат - появление сообщения о некорректной длине поля
2. Заполнение поля "Номер карты" 20 рандомными арабскими цифрами, прочие поля валидно. Ожидаемый результат - появление сообщения о некорректной длине поля
3. Заполнение поля "Номер карты" 16 рандомными арабскими цифрами, прочие поля валидно. Ожидаемый результат - появление сообщения об отклонении покупки
4. Заполнение поля "Номер карты" 19 рандомными арабскими цифрами, прочие поля валидно. Ожидаемый результат - появление сообщения об отклонении покупки
5. Заполнение поля "Номер карты" символами, кроме арабских цифр, прочие поля валидно. Ожидаемый результат - появление сообщения о неверно введенном номере карты
6. Оставление поля "Номер карты" пустым, прочие поля валидно. Ожидаемый результат - появление сообщения о поле, обязательном для заполнения
7. Заполнение поля "Месяц" числом больше 12, прочие поля валидно. Ожидаемый результат - появление сообщения о неверно введенном значении
8. Заполнение поля "Месяц" числом 00, прочие поля валидно. Ожидаемый результат - появление сообщения о неверно введенном значении
9. Заполнение поля "Месяц" числом в формате ноль + арабское число от 1 до 9, прочие поля валидно. Ожидаемый результат - сообщение об успешной покупке
10. Заполнение поля "Месяц" символами, кроме арабских цифр, прочие поля валидно. Ожидаемый результат - появление сообщения о неверно введенном значении
11. Заполнение поля "Месяц" номером месяца, меньше текущего, при поле "Год", заполненном текущим годом, прочие поля валидно. Ожидаемый результат - появление сообщения о неверно введенном значении
12. Оставление поля "Месяц" пустым, прочие поля валидно. Ожидаемый результат - появление сообщения о поле, обязательном для заполнения
13. Заполнение поля "Год" годом меньше текущего, прочие поля валидно. Ожидаемый результат - появление сообщения о неверно введенном значении
14. Заполнение поля "Год" нулями, прочие поля валидно. Ожидаемый результат - сообщение о неверно введенном значении
15. Оставление поля "Год" пустым, прочие поля валидно. Ожидаемый результат - появление сообщения о поле, обязательном для заполнения
16. Заполнение поля "Владелец" валидными данными с пробелом в середине, прочие поля валидно. Ожидаемый результат - сообщение об успешной покупке
17. Заполнение поля "Владелец" валидными данными с дефисом в середине, прочие поля валидно. Ожидаемый результат - сообщение об успешной покупке
18. Заполнение поля "Владелец" валидными данными с пробелом в начале, прочие поля валидно. Ожидаемый результат - появление сообщения о неверно введенном значении
19. Заполнение поля "Владелец" валидными данными с пробелом в конце, прочие поля валидно. Ожидаемый результат - появление сообщения о неверно введенном значении
20. Заполнение поля "Владелец" валидными данными с дефисом в начале, прочие поля валидно. Ожидаемый результат - появление сообщения о неверно введенном значении
21. Заполнение поля "Владелец" валидными данными с дефисом в конце, прочие поля валидно. Ожидаемый результат - появление сообщения о неверно введенном значении
22. Заполнение поля "Владелец" валидными данными в нижнем регистре, прочие поля валидно. Ожидаемый результат - автозамена регистра на верхний, сообщение об успешной покупке
23. Заполнения поля "Владелец" символами кириллицы, прочие поля валидно. Ожидаемый результат - появление сообщения о неверно введенном значении
24. Заполнения поля "Владелец" символами латиницы + арабскими цифрами, прочие поля валидно. Ожидаемый результат - появление сообщения о неверно введенном значении
25. Заполнения поля "Владелец" символами латиницы + спецсимволами, прочие поля валидно. Ожидаемый результат - появление сообщения о неверно введенном значении
26. Оставление поля "Владелец" пустым, прочие поля валидно. Ожидаемый результат - появление сообщения о поле, обязательном для заполнения
27. Заполнение поля "CVC/CVV" 2 арабскими цифрами, прочие поля валидно. Ожидаемый результат - появление сообщения о некорректной длине поля
28. Заполнение поля "CVC/CVV" 3 арабскими цифрами, прочие поля валидно. Ожидаемый результат - сообщение об успешной покупке
29. Заполнение поля "CVC/CVV" символами, кроме арабских цифр, прочие поля валидно. Ожидаемый результат - появление сообщения о неверно введенном значении
30. Оставление поля "CVC/CVV" пустым, прочие поля валидно. Ожидаемый результат - появление сообщения о поле, обязательном для заполнения
31. Оставление всех полей пустыми и нажатие кнопки "Продолжить". Ожидаемый результат - появление сообщения о полях, обязательных для заполнения

**Тестирование API:**

1. Отправка валидного POST запроса платежа с APPROVED карты на http://localhost:9999/payment. Ожидаемый результат - статус 200, появление записи о запросе в базе.
2. Отправка валидного POST запроса платежа с DECLINED карты на http://localhost:9999/payment. Ожидаемый результат - статус 200, появление записи о запросе в базе.
3. Отправка пустого POST запроса платежа на http://localhost:9999/payment. Ожидаемый результат – статус 400, отсутствие записи о запросе в базе и статуса.
4. Отправка POST запроса платежа с пустым значением number (остальные данные body заполнены валидно) на http://localhost:9999/payment. Ожидаемый результат - статус 400, отсутствие записи о запросе в базе и статуса.
5. Отправка POST запроса платежа с пустым значением month (остальные данные body заполнены валидно) на http://localhost:9999/payment. Ожидаемый результат - статус 400, отсутствие записи о запросе в базе и статуса.
6. Отправка POST запроса платежа с пустым значением year (остальные данные body заполнены валидно) на http://localhost:9999/payment. Ожидаемый результат - статус 400, отсутствие записи о запросе в базе и статуса.
7. Отправка POST запроса платежа с пустым значением holder (остальные данные body заполнены валидно) на http://localhost:9999/payment. Ожидаемый результат - статус 400, отсутствие записи о запросе в базе и статуса.
8. Отправка POST запроса платежа с пустым значением cvc (остальные данные body заполнены валидно) на http://localhost:9999/payment. Ожидаемый результат - статус 400, отсутствие записи о запросе в базе и статуса.

9-16. Отправка аналогичных POST запросов для запроса кредита на http://localhost:9999/credit.


## Перечень используемых инструментов ##

1. **IDE:** IntelliJ IDEA (распространенный инструмент с большим количеством настроек).
2. **Язык программирования:** JAVA (распространенный, относительно простой, следовательно жизнеспособный для дальнейшей модификации тестов).
3. **Система сборки:** Gradle (легче настраиваются зависимости по сравнению с Maven).
4. **Библиотека:** JUnit (гибкость, доступность, постоянные обновления).
5. **Фреймворки:** Selenide, REST Assured (простота в использовании, популярность).
6. **Дополнительно:** Faker (для генерации тестовых данных), Lombok (для сокращения ручного написания кода).
7. **Репортинг:** Allure (более сложные системы репортинга не потребуются).
8. **Система контроля версий:** Git (для хранения проекта) и основанный на нем GitHub (вэб-сервис для совместной работы над проектом).
9. **Docker Compose** - инструмент для запуска и управления мультиконтейнерными приложениями (позволит «виртуально» запустить необходимые для проекта СУБД и симулятор банковских сервисов).

## Перечень и описание возможных рисков при автоматизации ##

1. "Поломка" UI-тестов при любом изменении дизайна сайта, добавлении/удалении/переименовании полей в форме, в том числе селекторов.
2.  Поскольку тестирование производится не с реальным банковским сервисом, а с заглушкой, есть риск возникновения непредвиденных ошибок при запуске реального сайта.
3.  Т.к. речь идет о постоянно меняющимся содержании предложения ("Тур дня"), то необходимо использовать «незахардкоренные» тестовые данные.
4.  Возможны трудности настройки SUT из-за необходимости интеграции с двумя базами данных одновременно (MySQL, PostgreSQL)
5.  Из-за отсутствия документации по сервису непонятно, какое поведение компонентов сервиса является приемлемым, а что считать ошибкой
6.  Необходимость очищения БД от записей после каждого прогона тестов.

## Интервальная оценка с учётом рисков (в часах) ##

1. Предварительная настройка и отладка SUT, баз и т.д. - 8-12
2. Написание автотестов - 24-30
3. Создание баг-репортов и отчета по прогону автотестов - 7-8
4. Подготовка документации по итогам автоматизации 5-6
5. Подключение и отладка CI (необязательная задача) - (5-6)

    **Итого 44-56 часов** (45-62 часов с необязательной задачей)

## План сдачи работ ##

1. Написание автотестов 04.08.23
2. Подготовка баг-репортов и отчета по прогону автотестов 07.08.23
3. Подготовка отчета по результатам автоматизации 09.08.23

