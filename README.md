# Penetration Testing веб-приложения

## Заказчик

Учебный проект по модулю "Penetration Testing" на онлайн-платформе «Нетология»

## Обзор

Тестирование информационных систем Заказчика было проведено в период с 18 по 25 февраля 2025 года независимым специалистом по информационной безопасности Николаем Резепиным. Основной целью тестирования было выявление уязвимостей в веб-приложении, доступном по адресу `http://127.0.0.1:8080`, и связанной базе данных PostgreSQL, работающей на порту `5432`. Задача заключалась в оценке уровня защищенности систем и предоставлении рекомендаций по устранению обнаруженных рисков в режиме black box, моделирующем действия внешнего злоумышленника.

## Задачи

- Выявить уязвимости в веб-приложении, развернутом на `http://127.0.0.1:8080`.
- Обнаружить уязвимости в базе данных PostgreSQL, доступной через порт `5432`.
- Оценить общий уровень защищенности тестируемых систем.
- Предоставить рекомендации по устранению выявленных уязвимостей и повышению безопасности.

## Результаты

Ниже представлена таблица с перечнем обнаруженных уязвимостей, их уровнями риска, уязвимыми системами и рекомендациями по устранению. Результаты основаны на тестировании с использованием инструментов, таких как `nmap`, `OWASP ZAP`, `Metasploit` и кастомных эксплойтов.

| № | Уязвимость                  | Уровень риска | Уязвимая система             | Рекомендации                                                                 |
|---|-----------------------------|---------------|------------------------------|------------------------------------------------------------------------------|
| 1 | Symbolic Link Attack        | Критический   | Веб-приложение (aiohttp)     | Обновить aiohttp до версии 3.8.0+, отключить `follow_symlinks`, скрыть версию сервера. |
| 2 | PostgreSQL Payload Execution| Критический   | PostgreSQL (порт 5432)       | Обновить PostgreSQL до 15.x+, ограничить права учетной записи, отключить загрузку функций. |
| 3 | XSS                         | Высокий       | Веб-приложение (jQuery)      | Обновить jQuery до 3.6.x+, внедрить экранирование ввода, настроить CSP.     |
| 4 | Cookie No Http Only Flag    | Высокий       | Веб-приложение               | Добавить флаг `HttpOnly` и `Secure`, укоротить срок действия сессий.         |
| 5 | Application Error Disclosure| Низкий        | Веб-приложение               | Отключить вывод ошибок, перенести их в логи, внедрить валидацию данных.     |

### Детали критических уязвимостей
- **Symbolic Link Attack**: Уязвимость `CVE-2024-23334` в aiohttp 3.5.3 позволяет получить доступ к файлам системы (например, `/etc/passwd`, `/etc/shadow`) через некорректную обработку символических ссылок.
- **PostgreSQL Payload Execution**: Уязвимость `CVE-2007-3280` дает возможность выполнить произвольный код, получив обратный шелл с правами пользователя `postgres`.

### Потенциальные риски
Критические уязвимости могут привести к полной компрометации системы, утечке данных и остановке бизнес-процессов. Уязвимости высокого уровня усиливают угрозы в сочетании друг с другом.

## Метрики

- **Количество обнаруженных уязвимостей**: 5
- **Распределение по уровням риска**:
  - Критический: 2
  - Высокий: 2
  - Низкий: 1
- **Время тестирования**: 7 дней (с 18 по 25 февраля 2025 года)
- **Подход**: Black box тестирование с использованием общедоступных инструментов

## Ссылки на материалы
- Полный отчет об аудите: [PenetrationTesting_Report.pdf](./PenetrationTesting_Report.pdf)
