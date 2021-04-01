# API сервиса YaMDb
![api_yamdb](https://github.com/alexfofanov/yamdb_final/workflows/api_yamdb_workflow/badge.svg)

Сервис YaMDb предназначен для сбора отзывов (Review) пользователей на произведения (Title). Произведения делятся на категории: «Книги», «Фильмы», «Музыка». Список категорий (Category) может быть расширен.

## Установка и запуск

### Установите docker и docker-compose
Проверьте установлен ли docker и docker-compose
    docker -v
    docker-compose -v

В случае отсутствия установите согласно документации по установке [docker](https://docs.docker.com/engine/install/) и [docker-compose](https://docs.docker.com/compose/install/) на официальном сайте.

### Создайте файл .env с переменными окружения для работы с БД в корне приложения и добавьте в него следующие параметры:
    SECRET_KEY=p&l%385148kslhtyn^##a1)ilz@4zqj=rq&agdol^##zgl9(vs #секретный ключ Django (установите свой)
    DB_ENGINE=django.db.backends.postgresql # указываем, что работаем с postgresql
    DB_NAME=postgres # имя базы данных
    POSTGRES_USER=postgres # логин для подключения к базе данных
    POSTGRES_PASSWORD=postgres # пароль для подключения к БД (установите свой)
    DB_HOST=db # название сервиса (контейнера)
    DB_PORT=5432 # порт для подключения к БД

### Запустите docker-compose
    docker-compose up -d

### Выплните миграцию
    docker-compose exec web python manage.py migrate

### Для загрузки тестовых данных используйте команду
    docker-compose run web python manage.py loaddata fixtures.json

### Создайте суперпользователя Django
    docker-compose run web python manage.py createsuperuser
Сервис доступен по адресу http://localhost:8000

### Для остановки и удаления сервиса используйте команду
    docker-compose down

### Технологии    
+ Python  
+ Django
+ Django REST Framework
+ PostgreSQL
+ Gunicorn
+ Nginx
+ Docker
+ Docker Compose
+ GitHub Actions
