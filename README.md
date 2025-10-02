# Секретный Гость (Ostrovok Hackathon 2025)

Прототип функционала “Секретного гостя” для платформы Островок. Позволяет пользователю подать заявку на участие в программе, выбрать отель для проверки, пройти проверку и передать отчет о пребывании. Также реализована админ-панель, где регулируется весь процесс.

- Видео-скринкаст: 

Яндекс диск 

https://disk.yandex.ru/d/5vuxCZIexIr8jw

Гугл диск 

https://drive.google.com/drive/folders/10LK7sdl9NiQdjgFDwFmQnu9V5iS_IuFq?usp=sharing

## Быстрый старт

git clone https://github.com/ostrovok-hackathon-2025/ostrovok
cd admin-console
cp .env.example .env

docker compose up --build


# открыть http://localhost:8080
Рекомендованные ресурсы

2 CPU cores

4GB RAM

Зависимые сервисы
Postgres 16 (облачная база)

Переменные окружения
Содержимое .env (копировать в свой .env):

Маршруты / доступ
UI
/api/auth/login — вход пользователя

/api/auth/register — регистрация пользователя

/api/hotels — раздел с отелями

/api/hotelInspectionRequests — доступные к инспекции отели

/api/guestRequests — заявки на инспекцию

/api/inspectionReports — отчёты

/api/profiles — профили пользователей

API
/health — 200 OK, JSON { "status": "ok" }

/api/auth/login — вход пользователя

/api/auth/register — регистрация пользователя

/api/auth/token/ — фронтенд-логин (access + refresh)

/api/hotels — управление отелями

/api/hotel-inspections — доступные к инспекции отели

/api/guest-requests — заявки на инспекцию

/api/inspection-reports — отчёты о пребывании

/api/profiles — профили секретных гостей

/api/profile-status — статусы профилей

/api/report-media — файлы к отчетам

/api/roles — роли

/api/users — пользователи

/api/cities — города

/api/inspection-reasons — причины инспекций

Тестовый пользователь:

Логин: admin

Пароль: 123

Docker

Все сервисы в контейнерах: ostrovok-backend, ostrovok-nginx

Проброс портов: 8081:8000 (backend), 8080:3000 (frontend)

Secrets хранятся в .env / .env.example

Healthcheck: /health в backend

Логи в stdout / stderr

Docker Compose

Запуск: docker compose up --build

Файл: docker-compose.yml в корне репозитория

env_file: .env / .env.example

healthcheck настроен для корректного старта

Не требуется ручных доустановок кроме Docker/Compose

Кросс-платформенность
Фиксированные версии образов/зависимостей

Сидирование/миграции не нужны (облачная БД)

Большие артефакты/модели отсутствуют
