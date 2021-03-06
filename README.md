# Django Media-Hosting Server

## Roadmap



# Getting Started

## Install Dependencies

[Docker Desktop](https://www.docker.com/get-started)

[Python 3.8](https://www.python.org/downloads/) alongside your favorite virtual environment [pipenv](https://pypi.org/project/pipenv/) or [virtualenv](https://pypi.org/project/virtualenv/)

## Run Server

```
$ docker-compose -f docker-compose.prod.yml up -d --build
$ docker-compose -f docker-compose.prod.yml exec web python manage.py migrate --noinput
$ docker-compose -f docker-compose.prod.yml exec web python manage.py collectstatic --no-input --clear
```

- These steps build the docker images and prepare django for use.
- Now you can upload an image to [http://localhost:80](http://localhost:80) and view that image from a server-provided link.

## Bring the server down

```
$ docker-compose down -v
```

# Credit

This repo is largely inspired by [django-on-docker](https://github.com/testdrivenio/django-on-docker)