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
### Запуск проекта из образов с Docker hub:
- Создаем папку kittygram и переходим в нее:
    mkdir kittygram
    cd kittygram
- Создаем файл .env c параветрами указанными в .env.example:
    nano .env
- Создаем файл docker-compose.production.yml:
    nano docker-compose.production.yml
- Копируем в docker-compose.production.yml (только созданного) созержимое из одноименного файла с   GitHub(https://github.com/lagodmi/kittygram_final/blob/main/docker-compose.production.yml)
- Запускаем его:
    docker compose -f docker-compose.production.yml up -d
### Запуск проекта из исходников GitHub:
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
## Дополнительная информация:
### Команды управления docker-compose (docker-compose.production.yml):
- Остановить.
    docker compose -f docker-compose.yml stop
- Запустить.
    docker compose -f docker-compose.yml start
- Остановить и удалить контейнеры.
    docker compose -f docker-compose.yml down
- Остановить и удалить контейнеры с всеми данными.
    docker compose -f docker-compose.yml down -v
### Настройка CI/CD:
- Файл workflow находится в директории:
    kittygram/.github/workflows/main.yml
- Настройка необходимых переменных в git(/settings/secrets/actions)

    DOCKER_USERNAME                # имя DockerHub
    DOCKER_PASSWORD                # пароль DockerHub

    HOST                           # IP-адрес сервера
    USER                           # имя пользователя сервера
    SSH_KEY                        # SSH-ключ
    SSH_PASSPHRASE                 # пароль для SSH-ключа

    TELEGRAM_TO                    # ID вашего телеграм-аккаунта
    TELEGRAM_TOKEN                 # токен бота(надо создать)
## Автор проекта:
Лагоднов Д.С.