# Kittygram — социальная сеть для учета достежений котиков.
## Описание проекта:
- Сайт имеет полный функционал по авторизации, авторизованные пользователи могут вести учет достяжений своих котов также сохранять фото не больше 20 Mb., кличку, год рождения и цвет.
## Стек проекта:
- Python 3.9
- Django 3.2.3
- Django REST framework 3.12.4
- JavaScript
## Cсылку на развернутый проект:
- https://kittygram.h1n.ru/
## Процесс запуска проекта (через docker compose):
### Какую версию развернуть:
- В случае развертывания проекта в производственной среде следует использовать прод-версию, а для разработки, тестирования или демонстрации концепции - обычную версию.
### Запуск проекта:
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
## Автор проекта:
Лагоднов Д.С.
