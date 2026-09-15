# 🐳 Docker Compose: WordPress + MySQL

Учебный репозиторий с примерами развёртывания приложений в Docker Compose.

![Docker](https://img.shields.io/badge/Docker-Compose-2496ED?logo=docker&logoColor=white)
![WordPress](https://img.shields.io/badge/WordPress-latest-21759B?logo=wordpress&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-8.0-4479A1?logo=mysql&logoColor=white)

---

## 📖 О репозитории

Здесь собраны практические работы по контейнеризации приложений с помощью Docker Compose.

Текущая работа — развёртывание сайта на **WordPress** с базой данных **MySQL 8.0** в изолированной Docker-сети.

## 🗂️ Структура репозитория

```
.
├── wordpress/
│   ├── compose.yaml     # Конфигурация Docker Compose
│   └── README.md        # 📘 Подробная инструкция по работе
├── img/                 # Скриншоты для документации
└── README.md            # 👈 Вы здесь
```

## 📚 Работы

| № | Работа | Описание | Ссылка |
|---|--------|----------|--------|
| 1 | WordPress + MySQL | Развёртывание WordPress в Docker Compose | [📘 Открыть инструкцию](wordpress/README.md) |

## ⚙️ Требования

- Docker Engine 20.10+
- Docker Compose v2 (`docker compose`)
- Свободный порт `8081`

## 🚀 Быстрый старт

Полная инструкция — в **[wordpress/README.md](wordpress/README.md)**.

Краткая версия:

```bash
git clone <URL_репозитория>
cd <имя-репозитория>/wordpress
docker compose up -d
```

После запуска откройте: 👉 **http://localhost:8081**

## 📌 Примечания

- WordPress доступен на порту **8081**
- Данные сохраняются в именованных томах `db_data` и `wordpress_data`
- ⚠️ Пароли в `compose.yaml` указаны для локальной разработки — для продакшена смените их

## 📄 Лицензия

Проект распространяется под лицензией MIT.
