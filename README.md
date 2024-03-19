[![Main Kittygram workflow](https://github.com/Dmitriy-boytsev/kittygram_final/actions/workflows/main.yml/badge.svg)](https://github.com/Dmitriy-boytsev/kittygram_final/actions/workflows/main.yml/badge.svg)

# Kittygram - блог для размещение фотографий котиков. 
 
## Описание проекта: 
 
Проект Kittygram даёт возможность пользователям поделиться  фотографиями своих  котиков. Зарегистрированные пользователи могут создавать, просматривать, редактировать и удалять свои записи. "Prod версия" проверена, протестирована и готова для внедрения в производственную среду или в реальное использование пользователями.

## Стек проекта:

- Docker
- Postgres
- Python 3.x 
- Node.js 9.x.x 
- Git 
- Nginx 
- Gunicorn 
- Django (backend) 
- React (frontend)

##  Cсылка на развёрнутое приложение в сети: 
- #### https://django-training.online/ 

## Как развернуть: 
 
 - Клонироуйте репозиторий:
 
    
bash
    git clone git@github.com:Dmitriy-boytsev/kittygram_final.git
 - Создайте файл .env

    
bash
    touch .env
- Заполните файл переменными окружения

    
bash
    POSTGRES_DB=<БазаДанных>
    POSTGRES_USER=<имя пользователя>
    POSTGRES_PASSWORD=<пароль>
    DB_NAME=<имя БазыДанных>
    DB_HOST=db
    DB_PORT=5432
    SECRET_KEY=<ключ Django>
    DEBUG=<DEBUG True/False>
    ALLOWED_HOSTS=<kittygram.ru localhost>

- Запустите Dockercompose

    
bash
    sudo docker compose -f docker-compose.yml up -d

- Сделайте миграции и соберите статику

   
bash
    sudo docker compose -f docker-compose.yml exec backend python manage.py migrate
    sudo docker compose -f docker-compose.yml exec backend python manage.py collectstatic
    sudo docker compose -f docker-compose.yml exec backend cp -r /app/collected_static/. /backend_static/static/ 
    




 ## Автор 
 
- Дмитрий Бойцев - [GitHub](https://github.com/Dmitriy-boytsev)
