# WordPress в Docker Compose

Развёртывание WordPress с базой данных MySQL с помощью Docker Compose.

## 📋 Шаг 1: Проверка текущих контейнеров

Проверьте, какие Docker Compose приложения уже запущены:

```bash
docker compose ls
```

Если есть работающие проекты, которые могут конфликтовать, остановите их:

```bash
docker compose stop
```

## 📁 Шаг 2: Создание структуры проекта

Создайте папку проекта и файл `compose.yaml`:

```bash
mkdir -p wordpress && touch wordpress/compose.yaml && cd wordpress
```

## 📝 Шаг 3: Создание файла compose.yaml

Откройте файл `compose.yaml` в текстовом редакторе и вставьте следующее содержимое:

```yaml
services:
  db:
    image: mysql:8.0
    restart: unless-stopped
    environment:
      MYSQL_ROOT_PASSWORD: somewordpress
      MYSQL_DATABASE: wordpress
      MYSQL_USER: wordpress
      MYSQL_PASSWORD: wordpress
    volumes:
      - db_data:/var/lib/mysql
    networks:
      - wp-network

  wordpress:
    depends_on:
      - db
    image: wordpress:latest
    ports:
      - "8081:80"
    restart: unless-stopped
    environment:
      WORDPRESS_DB_HOST: db:3306
      WORDPRESS_DB_USER: wordpress
      WORDPRESS_DB_PASSWORD: wordpress
      WORDPRESS_DB_NAME: wordpress
    volumes:
      - wordpress_data:/var/www/html
    networks:
      - wp-network

networks:
  wp-network:

volumes:
  db_data:
  wordpress_data:
```

## 🚀 Шаг 4: Запуск проекта

Находясь в папке `wordpress`, выполните:

```bash
docker compose up -d
```

Дождитесь загрузки образов — это может занять несколько минут.

![Запуск docker compose up](photo_2026-09-15_12-26-02.jpg)

## ✅ Шаг 5: Проверка статуса

```bash
docker compose ps -a
```

Оба контейнера должны иметь статус **Up**.

## 🌐 Шаг 6: Открытие WordPress

Перейдите в браузере по адресу: **http://localhost:8081**

Пройдите стандартную установку WordPress:

1. Выберите язык
2. Введите данные сайта
3. Создайте пользователя (логин/пароль)
4. Войдите в админ-панель

![Установка WordPress](photo_2026-09-15_12-25-52.jpg)

![Админ-панель WordPress](photo_2026-09-15_12-26-06.jpg)

## 🛠️ Полезные команды

**Просмотр логов:**

```bash
# Логи WordPress
docker compose logs -f wordpress

# Логи базы данных
docker compose logs -f db
```

**Управление:**

```bash
docker compose stop      # Остановить
docker compose start     # Запустить
docker compose restart   # Перезапустить
```

## 🗑️ Удаление проекта

```bash
# Остановить и удалить контейнеры
docker compose down

# Полное удаление с данными (осторожно!)
docker compose down -v
```

## 📌 Примечания

- WordPress доступен на порту **8081**
- Данные БД и файлы WordPress сохраняются в именованных томах `db_data` и `wordpress_data`
- Для продакшена обязательно смените пароли в секции `environment`