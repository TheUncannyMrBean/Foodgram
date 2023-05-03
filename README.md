# Foodgram - Ваше продуктовый помощник
Этот дипломный проект представляет собой сервис и API для него. Foodgram - это база кулинарных рецептов, функционал которого позволяет публиковать рецепты, добавлять их в "Избранное", подписываться на авторов и формировать корзину покупок. 

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
http://127.0.0.1:8000/recipes/

### Контакты
Если у вас есть какие-либо вопросы или предложения по проекту, вы можете связаться со мной по следующим контактным данным:

- Email: diuk2001@yandex.ru
- Telegram: @sashagolikov
