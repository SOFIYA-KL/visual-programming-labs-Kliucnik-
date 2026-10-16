# Лабораторная работа №3 — Bubble

**Студент:** Ключник София  
**Тема:** База контактов  
**Репозиторий:** visual-programming-labs-Kliucnik-

---

## Часть 1. Промпт и генерация каркаса

### Промпт для AI-агента Bubble (дословно)
Создай приложение на тему «База контактов»

Пусть этот сайт будет требующий регистрацию.

Страницу обязательно создай по структуре header + body + footer.

Обязательно укажи в заготовке следующую строку: «ТВП: Ключник»

Добавь несколько интерактивных элементов (реализующих CRUD):

форму добавления нового контакта (имя, телефон, email, дата рождения, избранное)

список контактов с возможностью редактировать и удалять

поиск по имени

кнопку «Добавить в избранное»

### Скриншот результата генерации

![Результат генерации](../screenshots/01-prompt.png)

Commit: Add prompt and generation result

## Часть 2. Исследование идеи (Build Guides)

### Гайд 1: Design Fundamentals

**Что посмотрела:**
Курс про основы дизайна в Bubble — работа с группами, выравнивание, стили.

**Что показалось полезным:**
- Группировка элементов (Group section)
- Настройка alignment для адаптивности
- Работа со стилями

**Что взяла в своё приложение:**
Идеи для группировки карточек контактов и отступов.

![Design Fundamentals](../screenshots/02-buildguide-1.png)

### Гайд 2: Fixed Repeating Group

**Что посмотрела:**
Гайд по Repeating Group с карточками в новом редакторе Bubble.

**Что показалось полезным:**
- Настройка Repeating Group под адаптивный layout
- Вертикальный скроллинг карточек

**Что взяла в своё приложение:**
Улучшила список контактов — карточки с отступами.

![Repeating Group](../screenshots/02-buildguide-2.png)

## Часть 3.1 Ручная доработка UI

Изменила текст заголовка в Header (reusable element) с «База контактов» на «База контактов — София».

![Изменённый заголовок](../screenshots/03-header-change.png)

### 3.2. Global variable для цвета

В приложении есть глобальные переменные цветов (Variables → Colors):
- **Primary** (#1325AE) — основной цвет кнопок
- Text, Surface, Background и др.

Применила переменную **Primary** к кнопке «Создать свою базу».

![Global variables](../screenshots/03-global-variable.png)

### 3.3. Создать новый стиль

Создала новый стиль кнопки **`my-primary-button`** на основе глобальной переменной **Primary**:
- Background: Primary (#1325AE)
- Border radius: 10
- Text: Primary contrast

Стиль применён к кнопкам в приложении.

![Новый стиль](../screenshots/04-style.png)

## Часть 4. Data и Workflows

### 4.1. Data: сущность «Контакт»

AI-агент создал Data Type **Контакт** со следующими полями:
- Email (text)
- Владелец (User)
- Дата рождения (date)
- Имя (text)
- Категория (Категория контакта)
- Статус (Статус контакта)
- Телефон (text)

![Data Type Контакт](../screenshots/06-data-type.png)

В App Data — 16 записей контактов (AI-генерация).

![Записи](../screenshots/07-data-records.png)

### 4.2. Workflows: CRUD

На странице `contacts` реализованы workflows для полного CRUD:

**Create** — workflow Form open new открывает форму нового контакта, Form save сохраняет запись.

![Create](../screenshots/08-workflow-create.png)

**Update** — workflow Form open edit открывает форму редактирования существующего контакта.

![Update](../screenshots/09-workflow-update.png)

**Delete** — workflow Del confirm удаляет выбранный контакт.

![Delete](../screenshots/10-workflow-delete.png)

Все workflows проверены в Preview.

## Часть 6. Отчёт

### Ссылка на dev-версию приложения

(будет заполнено)

### Выводы

(будет заполнено)
