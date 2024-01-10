### Описание проекта.
Сайт имеет полный функционал по авторизации, авторизованные пользователи могут вести учет достяжений своих котов также сохранять фото не больше 20 Mb., кличку, год рождения и цвет.
### Технологии.
Python 3.9
Django 3.2.3
Django REST framework 3.12.4
JavaScript
### Запуск проекта из образов с Docker hub.
- Создаем папку kittygram и переходим в нее:
    mkdir kittygram
    cd kittygram
- Создаем файл .env c параветрами указанными в .env.example:
    nano .env
- Создаем файл docker-compose.production.yml:
    nano docker-compose.production.yml
- Копируем в локалиный docker-compose.production.yml созержимое из одноименного файла
- Запускаем его:
    docker compose -f docker-compose.production.yml up -d
### Запуск проекта из исходников GitHub.
- Клонируем репозиторий:
    git clone git@github.com:lagodmi/kittygram_final.git
- Создаем файл .env в корне проекта c параветрами указанными в .env.example:
    nano .env
- Выполняем запуск:
    docker compose -f docker-compose.yml up -d
- Заходим в интерактивный терминал backend и выполняем команды:
    docker compose exec -it backend bash
        python manage.py migrate
        python manage.py collectstatic
        cp -r /app/collected_static/. /static/static/
- Проект доступен на:
    http://localhost:9000/

### Команды управления docker-compose (docker-compose.production.yml):
- Остановить.
    docker compose -f docker-compose.yml stop
- Запустить.
    docker compose -f docker-compose.yml start
- Остановить и удалить контейнеры.
    docker compose -f docker-compose.yml down
- Остановить и удалить контейнеры с всеми данными.
    docker compose -f docker-compose.yml down -v
