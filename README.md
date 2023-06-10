# Добавить в .env ваши данные

# Шаг 1: Установка virtualenv

Первым шагом необходимо установить virtualenv. Для этого в терминале введите следующую команду:


pip install virtualenv==15.1.0


# Шаг 2: Создание виртуального окружения

После установки virtualenv необходимо создать виртуальное окружение. Для этого введите следующую команду:


virtualenv -p /path/to/python2.7 venv


Замените "/path/to/python2.7" на путь к вашей установленной версии Python 2.7.

# Шаг 3: Активация виртуального окружения

После создания виртуального окружения необходимо его активировать. Для этого введите следующую команду:


source venv/bin/activate


# Шаг 4: Установка зависимостей

После активации виртуального окружения необходимо установить зависимости, указанные в файле req.txt. Для этого введите следующую команду:


pip install -r req.txt


# Шаг 5: Миграция базы данных

Далее необходимо провести миграцию базы данных. Для этого введите следующую команду:


python manage.py migrate


# Шаг 6: Миграция djcelery

Возможно не надо))


python manage.py migrate djcelery


# Шаг 7: Создание суперюзера
python manage.py createsuperuser


# Шаг 8: Запуск Redis

Для работы с Celery необходимо запустить Redis. Для этого введите следующую команду:


redis-server


# Шаг 9: Запуск Celery worker

Для запуска Celery worker введите следующую команду:


celery worker --app=config --loglevel=info


# Шаг 10: Запуск Celery beat

Для запуска Celery beat введите следующую команду:


celery beat --app=config --loglevel=info


# Первым делом нужно в админке добавить подписчиков.
