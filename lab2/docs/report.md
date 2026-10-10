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

Освоен **Node-RED** как low-code инструмент визуального программирования. 
Собраны и задеплоены потоки с базовыми и расширенными нодами: 
`inject`, `debug`, `function`, `switch`, `change`, `template`, 
`http request`, `mqtt`, `http in/response`, `file`, `context`.

Каждый поток сохранён отдельным файлом `flow-NN-<имя>.json` в папке `lab2/flows/`, 
скриншоты — в `lab2/screenshots/`.

---

## 2. Установка и запуск

**Способ установки:** npm (без Docker).

```bash
npm install -g --unsafe-perm node-red
node-red --userDir ./lab2/data
Версии:

Node-RED: v5.0.8

Node.js: v24.21.0

После запуска редактор доступен по адресу http://localhost:1880.

3. Освоенные ноды
Нода	Назначение	Где применена
inject	Запуск потока, генерация сообщений	Все потоки
debug	Вывод сообщений в боковую панель	Все потоки
function	JS-логика обработки сообщения	flow-02, 03, 08, 12
switch	Ветвление по условию	flow-03
change	Изменение свойств сообщения	flow-04
template	Формирование текста/JSON по Mustache	flow-05
http request	Запрос к внешнему API	flow-06
mqtt in / mqtt out	Обмен через MQTT-брокер	flow-07
http in / http response	REST-эндпоинты	flow-08
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
11	flow-11-files.json	Запись и чтение файла
12	flow-12-context.json	Счётчик в flow context
5. Использованные AI-промпты
«Сгенерируй JS-код для function node в Node-RED: использует let/const, if/else, цикл for, массив и объект, возвращает { payload: ... }»

«Сгенерируй Mustache-шаблон для template node, который из объекта {name, age, city} формирует JSON»

«Напиши function node для GET-эндпоинта /api/items, который валидирует query-параметр id и возвращает статусы 400, 404 или 200»

6. Не выполнено
2.9 Dashboard — требует установки node-red-dashboard, планируется доделать отдельно.

2.10 Telegram-бот — требует создания бота через BotFather, планируется доделать отдельно.

7. Выводы
Node-RED позволяет собирать потоки обработки данных без написания большого количества кода — ноды соединяются визуально, а логика задаётся в настройках или коротких JS-функциях.

Инструмент удобен для быстрого прототипирования:

REST API (http in / http response)

Обмена сообщениями через MQTT

Работы с файлами и внешними API

Хранения состояния в контексте

Основная сложность — освоить специфику отдельных нод (switch, change) и правильно настраивать типы данных (msg.payload, msg.topic, типы значений).

8. Скриншоты
Все скриншоты находятся в папке lab2/screenshots/:

00-versions.png — версии Node-RED и Node.js

01-inject-debug.png — базовый поток

02-function.png — function node

03-switch.png — switch

04-change.png — change

05-template.png — template

06-http-request.png — http request

07-mqtt.png — mqtt

08a-08f-endpoints-*.png — 5 эндпоинтов + схема

11-files.png — файлы

12-context.png — контекст
