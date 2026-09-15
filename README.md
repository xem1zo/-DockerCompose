# 🐳 Docker Compose: WordPress + MySQL

Учебный репозиторий с примерами развёртывания приложений в Docker Compose.

![Docker](https://img.shields.io/badge/Docker-Compose-2496ED?logo=docker&logoColor=white)
![WordPress](https://img.shields.io/badge/WordPress-latest-21759B?logo=wordpress&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-8.0-4479A1?logo=mysql&logoColor=white)

---

## 📖 О репозитории

Здесь собраны практические работы по Docker Compose.

Текущая работа — развёртывание сайта на **WordPress** с базой данных **MySQL 8.0** в изолированной Docker-сети.

## 🗂️ Структура репозитория

```
.
├── README.md            # 👈 Вы здесь (точка входа)
└── grrrmonday/          # 📘 Практическая работа
    ├── compose.yaml
    ├── photo_2026-09-15_12-25-52.jpg
    ├── photo_2026-09-15_12-26-02.jpg
    ├── photo_2026-09-15_12-26-06.jpg
    └── README.md        # Подробная инструкция
```

## 📚 Работы

| № | Работа | Описание | Ссылка |
|---|--------|----------|--------|
| 1 | WordPress + MySQL | Развёртывание WordPress в Docker Compose | [📘 Открыть инструкцию](grrrmonday/README.md) |

## 🚀 Быстрый старт

Полная инструкция — в **[grrrmonday/README.md](grrrmonday/README.md)**.

Кратко:

```bash
git clone https://github.com/xem1zo/-DockerCompose.git
cd -DockerCompose/grrrmonday
docker compose up -d
```

После запуска откройте: 👉 **http://localhost:8081**

## ⚙️ Требования

- Docker Engine 20.10+
- Docker Compose v2 (`docker compose`)
- Свободный порт `8081`

## 📄 Лицензия

MIT
