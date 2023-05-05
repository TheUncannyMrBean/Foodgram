![workflow](https://github.com/theuncannymrbean/foodgram-project-react/actions/workflows/main.yml/badge.svg)
# Foodgram - Ваше продуктовый помощник
Этот дипломный проект представляет собой сервис и API для него. Foodgram - это база кулинарных рецептов, функционал которого позволяет публиковать рецепты, добавлять их в "Избранное", подписываться на авторов и формировать корзину покупок. 

## Подготовка для запуска проекта на боевом сервере
1. Клонируйте репозиторий:
```
https://github.com/mikhailsoldatkin/foodgram-project-react.git
```
2. Установите на сервере Docker, Docker Compose:

```
sudo apt install curl                                   
curl -fsSL https://get.docker.com -o get-docker.sh     
sh get-docker.sh                                       
sudo apt-get install docker-compose-plugin              
```
3. Перейдите в папку infra и скопируйте на сервер файлы docker-compose.yml, nginx.conf:

```
scp docker-compose.yml nginx.conf username@IP:/home/username/   
                                                                
```
4. Создайте переменные окружения в разделе Secrets > Actions для работы с GitHub Actions:
```
SECRET_KEY              # секретный ключ Django проекта
DOCKER_PASSWORD         # пароль от Docker Hub
DOCKER_USERNAME         # логин Docker Hub
HOST                    # публичный IP сервера
USER                    # имя пользователя на сервере
PASSPHRASE              # *если ssh-ключ защищен паролем
SSH_KEY                 # приватный ssh-ключ
TELEGRAM_TO             # ID телеграм-аккаунта для посылки сообщения
TELEGRAM_TOKEN          # токен бота, посылающего сообщение

DB_ENGINE               # django.db.backends.postgresql
DB_NAME                 # postgres
POSTGRES_USER           # postgres
POSTGRES_PASSWORD       # postgres
DB_HOST                 # db
DB_PORT                 # 5432 (порт по умолчанию)
```
4. Создайте и запустите контейнеры Docker:
*(версии команд "docker compose" или "docker-compose" отличаются в зависимости от установленной версии Docker Compose):*
```
sudo docker compose up -d
```

5. Выполните миграции:
```
sudo docker compose exec backend python manage.py migrate
```

6. Создайте суперпользователя:
```
sudo docker compose exec backend python manage.py createsuperuser
```

7. Собрите статику:
```
sudo docker compose exec backend python manage.py collectstatic --noinput
```

8. Команды для остановки контейнеров:
```
sudo docker compose down -v      # с их удалением
sudo docker compose stop         # без удаления
```

## Подготовка для запуска проекта на локальном компьютере
1. Откройте терминал и перейдите в каталог, в который планируете скопировать репозиторий
```
cd 
```
Клонируйте репозиторий:
```
git@github.com:TheUncannyMrBean/foodgram-project-react.git
```
Перейдите в корневую директорию проекта:
```
cd foodgram-project-react

```
2. Создайте и активируйте виртуальное окружение, обновите pip и установите зависимости из файла requirements.txt:.
```
python3 -m venv venv
. venv/bin/activate
python3 -m pip install --upgrade pip
pip install -r requirements.txt
```
3. Выполнить миграции:

```
python3 manage.py migrate
```
4. В папке foodgram/foodgram/ создайте файл .env и наполните его следующими данными:

```
DB_ENGINE - django.db.backends.postgresql
DB_NAME - postgres (по умолчанию)
POSTGRES_USER - postgres (по умолчанию)
POSTGRES_PASSWORD - postgres (по умолчанию)
DB_HOST - db
DB_PORT - 5432
```
## Запуск проекта на локальном компьютере

```
python3 manage.py runserver
```
### Проверьте работоспособность адреса развёрнутого проекта:
http://http://84.201.133.200/recipes

### Контакты
Если у вас есть какие-либо вопросы или предложения по проекту, вы можете связаться со мной по следующим контактным данным:

- Email: diuk2001@yandex.ru
- Telegram: @sashagolikov
