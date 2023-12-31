# План автоматизации

## Задача:
Автоматизировать позитивные и негативные сценарии покупки тура.

## Артефакты:
SUT aqa-shop.jar

## Предусловия:
Процедура запуска автотестов описана в файле README.md

Перед каждым тестом открываем страницу http://localhost:8080 в браузере.

## Тестовые сценарии:
Позитивные сценарии:
1. Успешная обработка данных в сервисе платежей (Payment Gate) при вводе валидных данных
   Шаги:

В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4441
В поле "Месяц" ввести валидное значение-текущий месяц
В поле "Год" ввести валидное значение-следующий год
В поле "Владелец" ввести валидное значение латинскими буквами-имя и фамилию
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: появляется всплывающее окно с сообщением "Успешно! Операция одобрена банком."

В БД есть запись APPROVED

2. Успешная обработка данных в кредитном сервисе (Credit Gate) при вводе валидных данных
   Шаги:

Нажать кнопку "Купить в кредит"
В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4441
В поле "Месяц" ввести валидное значение-текущий месяц
В поле "Год" ввести валидное значение-следующий год
В поле "Владелец" ввести валидное значение латинскими буквами-имя и фамилию
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: появляется всплывающее окно с сообщением "Успешно! Операция одобрена банком."

В БД есть запись APPROVED

3. Заполнение заявки на оплату в сервисе платежей (Payment Gate) латинскими буквами в поле "Владелец"
   Шаги:

В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4441
В поле "Месяц" ввести валидное значение-текущий месяц
В поле "Год" ввести валидное значение-следующий год
В поле "Владелец" ввести валидное значение латинскими буквами-имя и фамилию
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: появляется всплывающее окно с сообщением "Успешно! Операция одобрена банком."

В БД есть запись APPROVED

4. Заполнение заявки на оплату в кредитном сервисе (Credit Gate) латинскими буквами в поле "Владелец"
   Шаги:

Нажать кнопку "Купить в кредит"
В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4441
В поле "Месяц" ввести валидное значение-текущий месяц
В поле "Год" ввести валидное значение-следующий год
В поле "Владелец" ввести валидное значение латинскими буквами-имя и фамилию
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: появляется всплывающее окно с сообщением "Успешно! Операция одобрена банком."

В БД есть запись APPROVED

5. Обработка данных в сервисе платежей (Payment Gate) отклонена при вводе валидных данных.
   Шаги:

В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4442
В поле "Месяц" ввести валидное значение-текущий месяц
В поле "Год" ввести валидное значение-следующий год
В поле "Владелец" ввести валидное значение латинскими буквами-имя и фамилию
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: появляется всплывающее окно с сообщением "Ошибка! Банк отказал в проведении операции."

В БД есть запись DECLINED

6. Обработка данных в кредитном сервисе (Credit Gate) отклонена при вводе валидных данных.
   Шаги:

Нажать кнопку "Купить в кредит"
В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4442
В поле "Месяц" ввести валидное значение-текущий месяц
В поле "Год" ввести валидное значение-следующий год
В поле "Владелец" ввести валидное значение латинскими буквами-имя и фамилию
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: появляется всплывающее окно с сообщением "Ошибка! Банк отказал в проведении операции."

В БД есть запись DECLINED

## Негативные сценарии:
## Работа с полем "Номер карты"
1. Заполнение заявки на оплату в сервисе платежей (Payment Gate) несуществующим номером карты
   Шаги:

В поле "Номер карты" ввести несуществующий номер карты-4444 4444 4444 4443
В поле "Месяц" ввести валидное значение-текущий месяц
В поле "Год" ввести валидное значение-следующий год
В поле "Владелец" ввести валидное значение латинскими буквами-имя и фамилию
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: появляется всплывающее окно с сообщением "Ошибка! Банк отказал в проведении операции."

В БД нет новой записи

2. Заполнение заявки на оплату в кредитном сервисе(Credit Gate) несуществующим номером карты
   Шаги:

Нажать кнопку "Купить в кредит"
В поле "Номер карты" ввести несуществующий номер карты-4444 4444 4444 4443
В поле "Месяц" ввести валидное значение-текущий месяц
В поле "Год" ввести валидное значение-следующий год
В поле "Владелец" ввести валидное значение латинскими буквами-имя и фамилию
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: появляется всплывающее окно с сообщением "Ошибка! Банк отказал в проведении операции."

В БД нет новой записи

3. Заполнение заявки на оплату в сервисе платежей (Payment Gate) невалидным номером карты (недостающее количество символов)
   Шаги:

В поле "Номер карты" ввести несуществующий номер карты-4444 4444 4444 444
В поле "Месяц" ввести валидное значение-текущий месяц
В поле "Год" ввести валидное значение-следующий год
В поле "Владелец" ввести валидное значение латинскими буквами-имя и фамилию
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: поле "Номер карты" подсвечено как ошибочное. Надпись под полем "Неверный формат"

В БД нет новой записи

4. Заполнение заявки на оплату в кредитном сервисе (Credit Gate) невалидным номером карты (недостающее количество символов)
   Шаги:

Нажать кнопку "Купить в кредит"
В поле "Номер карты" ввести несуществующий номер карты-4444 4444 4444 444
В поле "Месяц" ввести валидное значение-текущий месяц
В поле "Год" ввести валидное значение-следующий год
В поле "Владелец" ввести валидное значение латинскими буквами-имя и фамилию
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: поле "Номер карты" подсвечено как ошибочное. Надпись под полем "Неверный формат"

В БД нет новой записи

5. Заполнение заявки на оплату в сервисе платежей (Payment Gate) с незаполненным полем "Номер карты"
   Шаги:

В поле "Номер карты" ничего не вводить. Оставить поле пустым
В поле "Месяц" ввести валидное значение-текущий месяц
В поле "Год" ввести валидное значение-следующий год
В поле "Владелец" ввести валидное значение латинскими буквами-имя и фамилию
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: поле "Номер карты" подсвечено как ошибочное. Надпись под полем "Поле обязательно для заполнения"

В БД нет новой записи

6. Заполнение заявки на оплату в кредитном сервисе (Credit Gate) с незаполненным полем "Номер карты"
   Шаги:

Нажать кнопку "Купить в кредит"
В поле "Номер карты" ничего не вводить. Оставить поле пустым
В поле "Месяц" ввести валидное значение-текущий месяц
В поле "Год" ввести валидное значение-следующий год
В поле "Владелец" ввести валидное значение латинскими буквами-имя и фамилию
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: поле "Номер карты" подсвечено как ошибочное. Надпись под полем "Поле обязательно для заполнения"

В БД нет новой записи

## Работа с полем "Месяц"
1. Заполнение заявки на оплату в сервисе платежей (Payment Gate) невалидными данными в поле "Месяц"
   Шаги:

В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4441
В поле "Месяц" ввести невалидное значение-00
В поле "Год" ввести валидное значение-следующий год
В поле "Владелец" ввести валидное значение латинскими буквами-имя и фамилию
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: поле "Месяц" подсвечено как ошибочное. Надпись под полем "Неверно указан срок действия карты"

В БД нет новой записи

2. Заполнение заявки на оплату в кредитном сервисе (Credit Gate) невалидными данными в поле "Месяц"
   Шаги:

Нажать кнопку "Купить в кредит"
В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4441
В поле "Месяц" ввести невалидное значение-00
В поле "Год" ввести валидное значение-следующий год
В поле "Владелец" ввести валидное значение латинскими буквами-имя и фамилию
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: поле "Месяц" подсвечено как ошибочное. Надпись под полем "Неверно указан срок действия карты"

В БД нет новой записи

3. Заполнение заявки на оплату в сервисе платежей (Payment Gate) несуществующими данными в поле "Месяц"
   Шаги:

В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4441
В поле "Месяц" ввести невалидное значение-13
В поле "Год" ввести валидное значение-следующий год
В поле "Владелец" ввести валидное значение латинскими буквами-имя и фамилию
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: поле "Месяц" подсвечено как ошибочное. Надпись под полем "Неверно указан срок действия карты"

В БД нет новой записи

4. Заполнение заявки на оплату в кредитном сервисе (Credit Gate) несуществующими данными в поле "Месяц"
   Шаги:

Нажать кнопку "Купить в кредит"
В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4441
В поле "Месяц" ввести невалидное значение-13
В поле "Год" ввести валидное значение-следующий год
В поле "Владелец" ввести валидное значение латинскими буквами-имя и фамилию
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: поле "Месяц" подсвечено как ошибочное. Надпись под полем "Неверно указан срок действия карты"

В БД нет новой записи

5. Заполнение заявки на оплату в сервисе платежей (Payment Gate) невалидными данными в поле "Месяц" (истекшим сроком действия)
   Шаги:

В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4441
В поле "Месяц" ввести невалидное значение-предыдущий месяц
В поле "Год" ввести валидное значение-текущий год
В поле "Владелец" ввести валидное значение латинскими буквами-имя и фамилию
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: поле "Месяц" подсвечено как ошибочное. Надпись под полем "Неверно указан срок действия карты"

В БД нет новой записи

6. Заполнение заявки на оплату в кредитном сервисе (Credit Gate) невалидными данными в поле "Месяц"(истекшим сроком действия)
   Шаги:

Нажать кнопку "Купить в кредит"
В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4441
В поле "Месяц" ввести невалидное значение-предыдущий месяц
В поле "Год" ввести валидное значение-текущий год
В поле "Владелец" ввести валидное значение латинскими буквами-имя и фамилию
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: поле "Месяц" подсвечено как ошибочное. Надпись под полем "Неверно указан срок действия карты"

В БД нет новой записи

7. Заполнение заявки на оплату в сервисе платежей (Payment Gate) с пустым полем "Месяц"
   Шаги:

В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4441
В поле "Месяц" ничего не вводить. Оставить поле пустым
В поле "Год" ввести валидное значение-следующий год
В поле "Владелец" ввести валидное значение латинскими буквами-имя и фамилию
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: поле "Месяц" подсвечено как ошибочное. Надпись под полем "Поле обязательно для заполнения"

В БД нет новой записи

8. Заполнение заявки на оплату в кредитном сервисе (Credit Gate) с пустым полем "Месяц"
   Шаги:

Нажать кнопку "Купить в кредит"
В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4441
В поле "Месяц" ничего не вводить. Оставить поле пустым
В поле "Год" ввести валидное значение-следующий год
В поле "Владелец" ввести валидное значение латинскими буквами-имя и фамилию
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: поле "Месяц" подсвечено как ошибочное. Надпись под полем "Поле обязательно для заполнения"

В БД нет новой записи

## Работа с полем "Год"
1. Заполнение заявки на оплату в сервисе платежей (Payment Gate) невалидными данными в поле "Год" (истекший срок действия)
   Шаги:

В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4441
В поле "Месяц" ввести валидное значение-текущий месяц
В поле "Год" ввести невалидное значение-прошлый год
В поле "Владелец" ввести валидное значение латинскими буквами-имя и фамилию
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: поле "Год" подсвечено как ошибочное. Надпись под полем "Истек срок действия карты"

В БД нет новой записи

2. Заполнение заявки на оплату в кредитном сервисе (Credit Gate) невалидными данными в поле "Год" (истекший срок действия)
   Шаги:

Нажать кнопку "Купить в кредит"
В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4441
В поле "Месяц" ввести валидное значение-текущий месяц
В поле "Год" ввести невалидное значение-прошлый год
В поле "Владелец" ввести валидное значение латинскими буквами-имя и фамилию
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: поле "Год" подсвечено как ошибочное. Надпись под полем "Истек срок действия карты"

В БД нет новой записи

3. Заполнение заявки на оплату в сервисе платежей (Payment Gate) с пустым полем "Год"
   Шаги:

В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4441
В поле "Месяц" ввести валидное значение-текущий месяц
В поле "Год" ничего не вводить. Оставить поле пустым.
В поле "Владелец" ввести валидное значение латинскими буквами-имя и фамилию
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: поле "Год" подсвечено как ошибочное. Надпись под полем "Поле обязательно для заполнения"

В БД нет новой записи

4. Заполнение заявки на оплату в кредитном сервисе (Credit Gate) с пустым полем "Год"
   Шаги:

Нажать кнопку "Купить в кредит"
В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4441
В поле "Месяц" ввести валидное значение-текущий месяц
В поле "Год" ничего не вводить. Оставить поле пустым.
В поле "Владелец" ввести валидное значение латинскими буквами-имя и фамилию
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: поле "Год" подсвечено как ошибочное. Надпись под полем "Поле обязательно для заполнения"

В БД нет новой записи

## Работа с полем "Владелец"
1. Заполнение заявки на оплату в сервисе платежей (Payment Gate) невалидными данными (только имя)
   Шаги:

В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4441
В поле "Месяц" ввести валидное значение-текущий месяц
В поле "Год" ввести валидное значение-следующий год.
В поле "Владелец" ввести невалидное значение русскими буквами-имя
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: поле "Владелец" подсвечено как ошибочное. Надпись под полем "Введите полное имя и фамилию"

В БД нет новой записи

2. Заполнение заявки на оплату в кредитном сервисе (Credit Gate) невалидными данными (только имя)
   Шаги:

Нажать кнопку "Купить в кредит"
В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4441
В поле "Месяц" ввести валидное значение-текущий месяц
В поле "Год" ввести валидное значение-следующий год.
В поле "Владелец" ввести невалидное значение русскими буквами-имя
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: поле "Владелец" подсвечено как ошибочное. Надпись под полем "Введите полное имя и фамилию"

В БД нет новой записи

3. Заполнение заявки на оплату в сервисе платежей (Payment Gate) невалидными данными (только имя)
   Шаги:

В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4441
В поле "Месяц" ввести валидное значение-текущий месяц
В поле "Год" ввести валидное значение-следующий год.
В поле "Владелец" ввести невалидное значение латинскими буквами-имя
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: поле "Владелец" подсвечено как ошибочное. Надпись под полем "Введите полное имя и фамилию"

В БД нет новой записи

4. Заполнение заявки на оплату в кредитном сервисе (Credit Gate) невалидными данными (только имя)
   Шаги:

Нажать кнопку "Купить в кредит"
В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4441
В поле "Месяц" ввести валидное значение-текущий месяц
В поле "Год" ввести валидное значение-следующий год.
В поле "Владелец" ввести невалидное значение латинскими буквами-имя
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: поле "Владелец" подсвечено как ошибочное. Надпись под полем "Введите полное имя и фамилию"

В БД нет новой записи

5. Заполнение заявки на оплату в сервисе платежей (Payment Gate) невалидными данными (только фамилия)
   Шаги:

В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4441
В поле "Месяц" ввести валидное значение-текущий месяц
В поле "Год" ввести валидное значение-следующий год.
В поле "Владелец" ввести невалидное значение русскими буквами-фамилию
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: поле "Владелец" подсвечено как ошибочное. Надпись под полем "Введите полное имя и фамилию"

В БД нет новой записи

6. Заполнение заявки на оплату в кредитном сервисе (Credit Gate) невалидными данными (только фамилия)
   Шаги:

Нажать кнопку "Купить в кредит"
В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4441
В поле "Месяц" ввести валидное значение-текущий месяц
В поле "Год" ввести валидное значение-следующий год.
В поле "Владелец" ввести невалидное значение русскими буквами-фамилию
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: поле "Владелец" подсвечено как ошибочное. Надпись под полем "Введите полное имя и фамилию"

В БД нет новой записи

7. Заполнение заявки на оплату в сервисе платежей (Payment Gate) невалидными данными (только фамилия)
   Шаги:

В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4441
В поле "Месяц" ввести валидное значение-текущий месяц
В поле "Год" ввести валидное значение-следующий год.
В поле "Владелец" ввести невалидное значение латинскими буквами-фамилию
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: поле "Владелец" подсвечено как ошибочное. Надпись под полем "Введите полное имя и фамилию"

В БД нет новой записи

8. Заполнение заявки на оплату в кредитном сервисе (Credit Gate) невалидными данными (только фамилия)
   Шаги:

Нажать кнопку "Купить в кредит"
В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4441
В поле "Месяц" ввести валидное значение-текущий месяц
В поле "Год" ввести валидное значение-следующий год.
В поле "Владелец" ввести невалидное значение латинскими буквами-фамилию
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: поле "Владелец" подсвечено как ошибочное. Надпись под полем "Введите полное имя и фамилию"

В БД нет новой записи

9. Заполнение заявки на оплату в сервисе платежей (Payment Gate) невалидными данными (имя и фамилия через дефис)
   Шаги:

В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4441
В поле "Месяц" ввести валидное значение-текущий месяц
В поле "Год" ввести валидное значение-следующий год.
В поле "Владелец" ввести невалидное значение имя и фамилию через дефис-Иван-Иванов
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: поле "Владелец" подсвечено как ошибочное. Надпись под полем "Неверный формат"

В БД нет новой записи

10. Заполнение заявки на оплату в кредитном сервисе (Credit Gate) невалидными данными (имя и фамилия через дефис)
    Шаги:

Нажать кнопку "Купить в кредит"
В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4441
В поле "Месяц" ввести валидное значение-текущий месяц
В поле "Год" ввести валидное значение-следующий год
В поле "Владелец" ввести невалидное значение имя и фамилию через дефис-Иван-Иванов
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: поле "Владелец" подсвечено как ошибочное. Надпись под полем "Неверный формат"

В БД нет новой записи

11. Заполнение заявки на оплату в сервисе платежей (Payment Gate) невалидными данными (имя и фамилия в количестве 200 букв)
    Шаги:

В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4441
В поле "Месяц" ввести валидное значение-текущий месяц
В поле "Год" ввести валидное значение-следующий год
В поле "Владелец" ввести невалидное значение-имя и фамилию в количестве 200 букв
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: поле "Владелец" подсвечено как ошибочное. Надпись под полем "Значение поля не может содержать более 100 символов"

В БД нет новой записи

12. Заполнение заявки на оплату в кредитном сервисе (Credit Gate) невалидными данными (имя и фамилия в количестве 200 букв)
    Шаги:

Нажать кнопку "Купить в кредит"
В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4441
В поле "Месяц" ввести валидное значение-текущий месяц
В поле "Год" ввести валидное значение-следующий год
В поле "Владелец" ввести невалидное значение-имя и фамилию в количестве 200 букв
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: поле "Владелец" подсвечено как ошибочное. Надпись под полем "Значение поля не может содержать более 100 символов"

В БД нет новой записи

13. Заполнение заявки на оплату в сервисе платежей (Payment Gate) невалидными данными (цифры вместо букв)
    Шаги:

В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4441
В поле "Месяц" ввести валидное значение-текущий месяц
В поле "Год" ввести валидное значение-следующий год
В поле "Владелец" ввести невалидное значение-123456789
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: поле "Владелец" подсвечено как ошибочное. Надпись под полем "Значение поля может содержать только буквы и дефис"

В БД нет новой записи

14. Заполнение заявки на оплату в кредитном сервисе (Credit Gate) невалидными данными (цифры вместо букв)
    Шаги:

Нажать кнопку "Купить в кредит"
В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4441
В поле "Месяц" ввести валидное значение-текущий месяц
В поле "Год" ввести валидное значение-следующий год
В поле "Владелец" ввести невалидное значение-123456789
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: поле "Владелец" подсвечено как ошибочное. Надпись под полем "Значение поля может содержать только буквы и дефис"

В БД нет новой записи

15. Заполнение заявки на оплату в сервисе платежей (Payment Gate) невалидными данными (1 символ)
    Шаги:

В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4441
В поле "Месяц" ввести валидное значение-текущий месяц
В поле "Год" ввести валидное значение-следующий год
В поле "Владелец" ввести невалидное значение-1 букву
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: поле "Владелец" подсвечено как ошибочное. Надпись под полем "Значение поля должно содержать больше одной буквы"

В БД нет новой записи

16. Заполнение заявки на оплату в кредитном сервисе (Credit Gate) невалидными данными (1 символ)
    Шаги:

Нажать кнопку "Купить в кредит"
В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4441
В поле "Месяц" ввести валидное значение-текущий месяц
В поле "Год" ввести валидное значение-следующий год
В поле "Владелец" ввести невалидное значение-1 букву
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: поле "Владелец" подсвечено как ошибочное. Надпись под полем "Значение поля должно содержать больше одной буквы"

В БД нет новой записи

17. Заполнение заявки на оплату в сервисе платежей (Payment Gate) с пустым полем "Владелец"
    Шаги:

В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4441
В поле "Месяц" ввести валидное значение-текущий месяц
В поле "Год" ввести валидное значение-следующий год
В поле "Владелец" ничего не вводить. Оставить поле пустым
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: поле "Владелец" подсвечено как ошибочное. Надпись под полем "Поле обязательно для заполнения"

В БД нет новой записи

18. Заполнение заявки на оплату в кредитном сервисе (Credit Gate) с пустым полем "Владелец"
    Шаги:

Нажать кнопку "Купить в кредит"
В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4441
В поле "Месяц" ввести валидное значение-текущий месяц
В поле "Год" ввести валидное значение-следующий год
В поле "Владелец" ничего не вводить. Оставить поле пустым
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: поле "Владелец" подсвечено как ошибочное. Надпись под полем "Поле обязательно для заполнения"

В БД нет новой записи

19. Заполнение заявки на оплату в сервисе платежей (Payment Gate) невалидными данными (вместо имени пробел)
    Шаги:

В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4441
В поле "Месяц" ввести валидное значение-текущий месяц
В поле "Год" ввести валидное значение-следующий год
В поле "Владелец" ввести невалидное значение-вместо имени несколько пробелов
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: поле "Владелец" подсвечено как ошибочное. Надпись под полем "Значение поля может содержать только буквы и дефис"

В БД нет новой записи

20.Заполнение заявки на оплату в в кредитном сервисе(Credit Gate) невалидными данными (вместо имени пробел)
Шаги:

Нажать кнопку "Купить в кредит"
В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4441
В поле "Месяц" ввести валидное значение-текущий месяц
В поле "Год" ввести валидное значение-следующий год
В поле "Владелец" ввести невалидное значение-вместо имени несколько пробелов
В поле CVC/CVV ввести валидное значение-три цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: поле "Владелец" подсвечено как ошибочное. Надпись под полем "Значение поля может содержать только буквы и дефис"

В БД нет новой записи

## Работа с полем CVC/CVV
1. Заполнение заявки на оплату в сервисе платежей (Payment Gate) невалидными данными (1 символ вместо трех)
   Шаги:

В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4441
В поле "Месяц" ввести валидное значение-текущий месяц
В поле "Год" ввести валидное значение-следующий год
В поле "Владелец" ввести валидное значение латинскими буквами-имя и фамилию
В поле CVC/CVV ввести невалидное значение-1 цифру
Нажать на кнопку "Продолжить"
Ожидаемый результат: поле "CVC/CVV" подсвечено как ошибочное. Надпись под полем "Значение поля должно содержать 3 цифры"

В БД нет новой записи

2. Заполнение заявки на оплату в кредитном сервисе (Credit Gate) невалидными данными (1 символ вместо трех)
   Шаги:

Нажать кнопку "Купить в кредит"
В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4441
В поле "Месяц" ввести валидное значение-текущий месяц
В поле "Год" ввести валидное значение-следующий год
В поле "Владелец" ввести валидное значение латинскими буквами-имя и фамилию
В поле CVC/CVV ввести невалидное значение-1 цифру
Нажать на кнопку "Продолжить"
Ожидаемый результат: поле "CVC/CVV" подсвечено как ошибочное. Надпись под полем "Значение поля должно содержать 3 цифры"

В БД нет новой записи

3. Заполнение заявки на оплату в сервисе платежей (Payment Gate) невалидными данными (2 символа вместо трех)
   Шаги:

В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4441
В поле "Месяц" ввести валидное значение-текущий месяц
В поле "Год" ввести валидное значение-следующий год
В поле "Владелец" ввести валидное значение латинскими буквами-имя и фамилию
В поле CVC/CVV ввести невалидное значение-2 цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: поле "CVC/CVV" подсвечено как ошибочное. Надпись под полем "Значение поля должно содержать 3 цифры"

В БД нет новой записи

4. Заполнение заявки на оплату в кредитном сервисе (Credit Gate) невалидными данными (2 символа вместо трех)
   Шаги:

Нажать кнопку "Купить в кредит"
В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4441
В поле "Месяц" ввести валидное значение-текущий месяц
В поле "Год" ввести валидное значение-следующий год
В поле "Владелец" ввести валидное значение латинскими буквами-имя и фамилию
В поле CVC/CVV ввести невалидное значение-2 цифры
Нажать на кнопку "Продолжить"
Ожидаемый результат: поле "CVC/CVV" подсвечено как ошибочное. Надпись под полем "Значение поля должно содержать 3 цифры"

В БД нет новой записи

5. Заполнение заявки на оплату в сервисе платежей (Payment Gate) с пустым полем CVC/CVV
   Шаги:

В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4441
В поле "Месяц" ввести валидное значение-текущий месяц
В поле "Год" ввести валидное значение-следующий год
В поле "Владелец" ввести валидное значение латинскими буквами-имя и фамилию
В поле CVC/CVV ничего не вводить. Оставить поле пустым
Нажать на кнопку "Продолжить"
Ожидаемый результат: поле "CVC/CVV" подсвечено как ошибочное. Надпись под полем "Поле обязательно для заполнения"

В БД нет новой записи

6. Заполнение заявки на оплату в кредитном сервисе (Credit Gate) с пустым полем CVC/CVV
   Шаги:

Нажать кнопку "Купить в кредит"
В поле "Номер карты" ввести валидный номер карты-4444 4444 4444 4441
В поле "Месяц" ввести валидное значение-текущий месяц
В поле "Год" ввести валидное значение-следующий год
В поле "Владелец" ввести валидное значение латинскими буквами-имя и фамилию
В поле CVC/CVV ничего не вводить. Оставить поле пустым
Нажать на кнопку "Продолжить"
Ожидаемый результат: поле "CVC/CVV" подсвечено как ошибочное. Надпись под полем "Поле обязательно для заполнения"

В БД нет новой записи

## Работа с пустой заявкой
1. Заполнение заявки на оплату в сервисе платежей (Payment Gate) с пустыми полями
   Шаги:

Не заполняя ни одно из полей, нажать на кнопку "Продолжить"
Ожидаемый результат: Все поля подсвечиваются, под каждым полем надпись "Поле обязательно для заполнения"

В БД нет новой записи

2. Заполнение заявки на оплату в кредитном сервисе (Credit Gate) с пустыми полями
   Шаги:

Нажать кнопку "Купить в кредит"
Не заполняя ни одно из полей, нажать на кнопку "Продолжить"
Ожидаемый результат: Все поля подсвечиваются, под каждым полем надпись "Поле обязательно для заполнения"

В БД нет новой записи

## Перечень используемых инструментов
- Java 11 - самый популярный язык программирования для написания кроссплатформенных приложений. Также успешно применяется в автоматизации тестирования.
- IntelliJ IDEA Community Edition 2023.1.2-среда разработки, поддерживающая множество плагинов, систем управления и контроля версий
- Gradle-система автоматической сборки и управления зависимостями
- JUnit 5- одна из самых популярных платформ модульного тестирования
- Docker- открытая платформа для разработки, доставки и эксплуатации приложений, с помощью которой можно разворачивать мультиконтейнерные приложения без установки специального отдельного ПО(в данном случае MySQL, PostgreSQL, Node)
- Selenide: 6.18.0 - библиотека для написания лаконичных и стабильных UI тестов с открытым исходным кодом  на основе Selenium WebDriver.
- MySQL 8.0.18 (заявлена поддержка этой СУБД)
- PostgreSQL 12-alpine (заявлена поддержка этой СУБД)
- REST Assured 4.3.0-Java-библиотека для тестирования RESTful API, для того, чтобы посылать запросы и проверять ответы
- Allure 2.16.1 - фреймворк,предназначенныйдля создания визуально нагляднойкартины выполнения тестов.Генерирует более интересные и содержательные отчёты, чем Gradle.
- Java Faker-библиотека, которую можно использовать для создания широкого спектра реально выглядящих данных от адресов до ссылок на популярные культуры.
- Версия 117.0.5938.92 (Официальная сборка), (64 бит) (Официальная сборка), (64 бит)-один из самых популярных и удобных браузеров.
- GitHub-крупнейший веб-сервис для хостинга IT-проектов и их совместной разработки, основанный на системе контроля Git.

## Перечень и описание возможных рисков при автоматизации

1. Отсутствие технической документации, без которой нет точного понимания как должна работать SUT, и какое именно поведение системы будет считаться ошибкой.
1. Реальная система будет отличаться от SUT.
1. Использование захардкоренных номеров карт может привести к ошибкам в работе реальной системы, т.к. существует множество различных банковских карт (и с 16-значными, и с 12-значными, и с 10-значными номерами).
1. Использование двух БД может привести к затруднениям и ошибкам.

## Интервальная оценка с учётом рисков (в часах)

1. Создание проекта и запуск SUT-13 часов.
1. Написание тест-плана - 10 часов.
1. Написание и прогон автотестов - 135 часов.
1. Дополнительное время на устранение замечаний - 24 часа.
1. Подготовка отчетов по итогам тестирования - 15 часов.
1. Подготовка учетных документов по итогам автоматизации - 10 часов.

## План сдачи работ
1. Автотесты - 8 октября.
1. Отчётные документы по итогам тестирования - 12 октября. 
1. Подготовка отчета по итогам автоматизации - 16 октября.
