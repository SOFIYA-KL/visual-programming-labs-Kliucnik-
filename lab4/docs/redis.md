# Redis в n8n

Redis был запущен через Docker командой:
`docker run -d --name redis -p 6379:6379 redis:alpine`

В n8n созданы credentials для подключения:
- **Host:** `host.docker.internal`
- **Port:** `6379`

## Реализованные workflow

1. **Создание и чтение ключа (flow-09-redis.json):**
   - `Manual Trigger` → `Redis (Set)` (ключ `kliucnik`, значение `Привет от Софии!`) → `Redis (Get)` (чтение значения).

2. **Удаление и проверка (flow-10-redis.json):**
   - `Manual Trigger` → `Redis (Delete)` (удаление ключа `kliucnik`) → `Redis (Get)` (проверка, что значение больше не возвращается, подтверждая удаление).

Все действия проверены в n8n, скриншоты приложены в папке `screenshots/`.
