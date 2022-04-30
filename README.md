[![YaMDb workflow](https://github.com/pozarnik/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)](https://github.com/pozarnik/yamdb_final/actions/workflows/yamdb_workflow.yml)
# YaMDb CI & CD 

***YaMDb - API проект, собирающий отзывы пользователей на различные произведения***

## Возможности проекта YaMDb

- Свободная регистрация пользователей
- Получение токена с помощью кода, высылаемого на почту при регистрации
- Система ролей пользователя (*user, moderator, admin*)
- Добавление различных жанров и категорий произведений
- Добавление произведений, с возможностью выбора категории и нескольких жанров
- Публикация отзывов к произведениям
- Публикация комментариев к отзывам

## Особенности CI & CD

- Автоматический запуск тестов **flake8**, **pytest** при обновлении проекта
- Автоматическое обновление образа в Docker Hub **
- Автоматический деплой проекта на сервер и его запуск в Docker **
- Отправка сообщения в Telegram об успешном запуске проекта на рабочем сервере (у вас должен быть чат с вашим ботом) **

****только при мерже pull request в ветку main либо review**

## Технологии

- Python 3.9
- Django 3.2
- Django REST framework 3.12.4
- PostgreSQL 13.0
- Gunicorn 20.0.4
- nginx 1.21.3
- GitHub Actions

## Установка и запуск проекта

Скопируйте содержимое папки **infra/** на свой сервер

```sh
scp infra/docker-compose.yaml <ваш_логин_на_сервере>@<адрес_вашего_сервера>:~/
scp infra/nginx/default.conf <ваш_логин_на_сервере>@<адрес_вашего_сервера>:~/nginx/
```

Зайдите на свой удаленный сервер и установите Docker

```sh
ssh <ваш_логин_на_сервере>@<адрес_вашего_сервера>
sudo apt install docker.io
```

Добавьте в настройках к репозитарию следующие Actions secrets:

```
HOST                   # адрес вашего удаленного сервера
USERNAME               # ваш логин на удаленном сервере
SSH_KEY                # ваш секретный ключ ssh
PASSPHRASE             # фраза-пароль при создании ssh ключа
DOCKERHUB_USERNAME     # ваш логин на docker.com
DOCKERHUB_TOKEN        # ваш пароль на docker.com
TELEGRAM_TO            # id вашего аккаунта в telegram (узнать можно у бота @userinfobot)
TELEGRAM_TOKEN         # токен для доступа к вашему боту (узнать можно у бота @BotFather)
SECRET_KEY             # ключ для генерации хэша Django
DEBUG                  # значение Debug
DB_ENGINE              # укажите используемую БД
DB_NAME                # имя базы данных
POSTGRES_USER          # логин для подключения к БД
POSTGRES_PASSWORD      # пароль для подключения к БД (установите свой)
DB_HOST                # название сервиса (контейнера) БД
DB_PORT                # порт для подключения к БД 
EMAIL_HOST             # адрес сервера исходящей почты
EMAIL_PORT             # порт сервера исходящей почты
EMAIL_HOST_USER        # логин для авторизации на почтовом сервере
EMAIL_HOST_PASSWORD    # пароль для авторизации на почтовом сервере
```

## Документации проекта YaMDb

При запущенном проекте перейдите по одному из адресов в браузере

```sh
http://<адрес_вашего_сервера>/redoc/
http://<адрес_вашего_сервера>/swagger/
```

## Мои профили

- [GitHub](https://github.com/pozarnik/)
- [LinkedIn](https://linkedin.com/in/pozarnik/)

## License

MIT


