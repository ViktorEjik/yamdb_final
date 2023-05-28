# INFRAN_SP2
![example workflow](https://github.com/ViktorEjik/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)
## Описание
API сервиса YaMDB с Docker контейнером.
## Технологии
Python 3.7 <br>
Django 3.2 <br>
Docker
## Запуск проекта в dev-режиме
В файле `/api_yamdb/api_yamdb/settings.py` параметр `DEBUG = False` изменить на `DEBUG = True`<br>
Установить виртуальное окружениу командамми
```
python3 -m venv venv
sourse 'venv/bin/activate'
```
Установить зависимости
```
pip install -r requirements.txt
```
Находясь в директории `/api_yamdb` запустить сервер разработчика командой
```
python3 manage.py migrate

python3 manage.py runserver
```
## Запуск docer-compose
Находясь в директории `/infra` выполнить команды
```
sudo docker-compose up -d --build

sudo docker-compose exec web python manage.py migrate

sudo docker-compose exec web python manage.py createsuperuser

sudo docker-compose exec web python manage.py collectstatic --no-input
```
Дальше API доступен по адресу http://localhost
