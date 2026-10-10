# Лабораторная работа №2. Node-RED

**Технологии визуального программирования**

| | |
|---|---|
| **Тема** | Освоение Node-RED как low-code инструмента |
| **Репозиторий** | visual-programming-labs-Kliucnik- |
| **Дисциплина** | Технологии визуального программирования |
| **Студент** | Kliuchnik |
| **Node-RED** | v5.0.8 |
| **Node.js** | v24.21.0 |
| **Способ установки** | npm (без Docker) |

---

## 1. Краткое описание

Освоен **Node-RED** как low-code инструмент визуального программирования. Собраны и задеплоены потоки с базовыми и расширенными нодами: `inject`, `debug`, `function`, `switch`, `change`, `template`, `http request`, `mqtt`, `http in/response`, `file`, `context`, `dashboard (gauge/chart)`, `telegram`.

Каждый поток сохранён отдельным файлом `flow-NN-<имя>.json` в папке `lab2/flows/`, скриншоты — в `lab2/screenshots/`.

---

## 2. Установка и запуск

**Способ установки:** npm (без Docker).

```bash
npm install -g --unsafe-perm node-red
npm install -g node-red-dashboard node-red-contrib-telegrambot
node-red --userDir ./lab2/dataВерсии:

Node-RED: v5.0.8

Node.js: v24.21.0

Редактор доступен по адресу http://localhost:1880, dashboard — http://localhost:1880/ui.

https://./screenshots/00-versions.png

3. Освоенные ноды
Нода	Назначение	Где применена
inject	Запуск потока, генерация сообщений	Все потоки
debug	Вывод сообщений в боковую панель	Все потоки
function	JS-логика обработки сообщения	flow-02, 03, 08, 09, 10, 12
switch	Ветвление по условию	flow-03
change	Изменение свойств сообщения	flow-04
template	Формирование текста/JSON по Mustache	flow-05
http request	Запрос к внешнему API	flow-06
mqtt in / mqtt out	Обмен через MQTT-брокер	flow-07
http in / http response	REST-эндпоинты	flow-08
gauge / chart	Визуализация в dashboard	flow-09
telegram receiver / sender / command	Telegram-бот	flow-10
write file / read file	Работа с файлами	flow-11
flow context	Хранение состояния между сообщениями	flow-12
4. Список потоков
№	Файл	Что демонстрирует
01	flow-01-inject-debug.json	Базовый inject → debug
02	flow-02-function.json	Function node с JS-логикой
03	flow-03-switch.json	Ветвление switch по msg.payload
04	flow-04-change.json	Change node: topic, timestamp, payload
05	flow-05-template.json	Mustache-шаблон
06	flow-06-http-request.json	GET-запрос к публичному API
07	flow-07-mqtt.json	Публикация и подписка через hivemq
08	flow-08-endpoints.json	3 GET-эндпоинта
09	flow-09-dashboard.json	Gauge + chart, обновление раз в 5 сек
10	flow-10-telegram.json	Бот с командой /start и echo
11	flow-11-files.json	Запись и чтение JSON-файла
12	flow-12-context.json	Счётчик в flow context
5. REST API
Все эндпоинты описаны подробно в lab2/docs/api.md.

Метод	URL	Ответ
GET	/api/text	Простой текст
GET	/api/info	JSON с 2 полями
GET	/api/items?id=N	200 / 400 / 404
6. Использованные AI-промпты
«Сгенерируй JS-код для function node в Node-RED: использует let/const, if/else, цикл for, массив и объект, возвращает { payload: ... }»

«Сгенерируй Mustache-шаблон для template node, который из объекта {name, age, city} формирует JSON»

«Напиши function node для GET-эндпоинта /api/items, который валидирует query-параметр id и возвращает статусы 400, 404 или 200»

«Как в Node-RED создать gauge и chart в dashboard, обновляемые каждые 5 секунд случайным значением»

7. Выводы
Node-RED позволяет собирать потоки обработки данных без написания большого количества кода — ноды соединяются визуально, а логика задаётся в настройках или коротких JS-функциях.

Инструмент удобен для быстрого прототипирования:

REST API (http in / http response)

Обмена сообщениями через MQTT

Работы с файлами и внешними API

Хранения состояния в контексте

Визуализации данных через dashboard

Telegram-ботов

Основная сложность — освоить специфику отдельных нод (switch, change) и правильно настраивать типы данных (msg.payload, msg.topic, типы значений).

8. Скриншоты
2.1 Inject → Debug
https://./screenshots/01-inject-debug.png

2.2 Function
https://./screenshots/02-function.png

2.3 Switch
https://./screenshots/03-switch.png

2.4 Change
https://./screenshots/04-change.png

2.5 Template
https://./screenshots/05-template.png

2.6 HTTP Request
https://./screenshots/06-http-request.png

2.7 MQTT
https://./screenshots/07-mqtt.png

2.8 GET-эндпоинты
https://./screenshots/08a-endpoints-text.png
https://./screenshots/08b-endpoints-info.png
https://./screenshots/08c-endpoints-items-success.png
https://./screenshots/08d-endpoints-items-404.png
https://./screenshots/08e-endpoints-items-400.png
https://./screenshots/08f-endpoints-flow.png

2.9 Dashboard
https://./screenshots/09-dashboard-flow.png
https://./screenshots/09-dashboard-ui.png

2.10 Telegram
https://./screenshots/10-telegram-flow.png
https://./screenshots/10-telegram-chat.png

2.11 Файлы
https://./screenshots/11-files.png

2.12 Контекст
https://./screenshots/12-context.png
