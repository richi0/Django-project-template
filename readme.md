# Django project template

This template is inspired by William S. Vincent's book "Django for Professionals".

## Features

- Postgres Database
- Nginx
- Bootstrap
- Django-Crispy-Forms
- Custom user model
- allauth with custom templates
  - Login
  - Logout
  - Register
  - Change password
  - Reset password
- Static files settings

## Usage

- Fork or download the repo
- create a django.env file inside the django_data folder

```shell
#Example variables for development
SECRET_KEY=thisismysecretkey
ALLOWED_HOSTS=*
POSTGRES_USER=postgres
POSTGRES_PASSWORD=password
DEBUG=True
```

- create a postgres.env file inside the postgres_data folder

```shell
#Example variables for development
POSTGRES_PASSWORD=password
POSTGRES_USER=postgres
```

- start the docker container

```shell
docker-compose up
```

- make migrations

```shell
docker-compose exec web python manage.py makemigrations
docker-compose exec web python manage.py migrate
```

- collect static files

```shell
docker-compose exec web python manage.py collectstatic
```

- restart the docker container

```shell
docker-compose down
docker-compose up
```

- create superuser

```shell
docker-compose exec web python manage.py createsuperuser
```

## Infos

- Nginx is used to serve the static files
- Postgres is the database
- The django_app has two local apps
  - Pages
    - Contains the base template and is used to server static sites
  - Users
    - Contains the CustomUserModel,
    - Views for Login, Logout, Registration...,
    - Templates for all this views
