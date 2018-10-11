# Differences from the original repo

- PostgreSQL replaced MySQL
- got rid of `yarn`
- django and database configuration moved to `.env` file
- services renamed from `django` and `nuxt` to `backend` and `frontend` respectively

# .env file example

```dotenv
# General settings
DJANGO_SECRET_KEY=secret_key

# PostgreSQL
POSTGRES_USER=postgresuser
POSTGRES_PASSWORD=mysecretpass
```

# Nuxt Auth with Django Rest Framework
Sample application for @nuxtjs/auth with Django Rest Framework(DRF).<br>
Do not use for production environments.

# Overview
```
db -> port: 5432
frontend -> port:3000
backend -> port: 8000
nginx -> port:80 
  /admin,api,static -> proxy to backend
  / -> proxy to frontend
```

# API endpoint
- login(create token): /api/auth/token/create/ (with username, password)
- logout: /api/auth/token/destroy/
- get user property: /api/auth/me/

*generated by [djoser](https://github.com/sunscrapers/djoser)

# How to use
```
git clone git@github.com:sourenaraya/nuxt-django.git
cd nuxt-django/
docker-compose up -d

docker-compose run backend pipenv run ./sample/manage.py migrate

docker-compose run backend pipenv run ./sample/manage.py createsuperuser
```
