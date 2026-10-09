\# Лабораторная работа №2. Node-RED



\## Краткое описание



Освоен Node-RED как low-code инструмент визуального программирования. 

Собраны и задеплоены потоки с базовыми и расширенными нодами: 

inject, debug, function, switch, change, template, http request, mqtt, 

http in/response, file, context.



\## Способ установки



Установка через \*\*npm\*\* (без Docker).

npm install -g --unsafe-perm node-red

node-red --userDir .\\lab2\\data





\## Версии



\- \*\*Node-RED:\*\* v5.0.8

\- \*\*Node.js:\*\* v24.21.0



\## Освоенные ноды



| Нода | Где применена |

|------|---------------|

| inject | все потоки |

| debug | все потоки |

| function | flow-02, flow-03, flow-08 |

| switch | flow-03 |

| change | flow-04 |

| template | flow-05 |

| http request | flow-06 |

| mqtt in / mqtt out | flow-07 |

| http in / http response | flow-08 |

| write file / read file | flow-11 |



\## Список flow



\- flow-01-inject-debug

\- flow-02-function

\- flow-03-switch

\- flow-04-change

\- flow-05-template

\- flow-06-http-request

\- flow-07-mqtt

\- flow-08-endpoints

\- flow-11-files

\- flow-12-context



\## AI-промпты



\- «Сгенерируй JS-код для function node в Node-RED: использует let/const, if/else, цикл for, массив, объект, возвращает {payload: ...}»

\- «Сгенерируй Mustache-шаблон для Node-RED template node, который формирует JSON из объекта»

\- «Напиши function node для GET-эндпоинта с валидацией query-параметра id, возвращает 400/404/200»



\## Выводы



Node-RED позволяет собирать потоки обработки данных без написания 

большого количества кода — ноды соединяются визуально, а логика 

задаётся в настройках или в коротких JS-функциях. Удобно для 

быстрого прототипирования API, MQTT-обмена, работы с файлами и 

контекстом. Основная сложность — освоить специфику отдельных нод 

(switch, change) и правильно настраивать типы данных.

