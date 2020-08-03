# pull official base image
FROM python:3.8.3-alpine

# set work directory
WORKDIR /usr/src/app

# set environment vars
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# update system image
RUN apk update \
    && apk add python3 postgresql-libs  \
    && apk add --update --no-cache --virtual .build-deps gcc python3-dev musl-dev alpine-sdk python3-dev musl-dev postgresql-dev libffi-dev

# install dependencies
RUN pip install --upgrade pip setuptools
COPY ./requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# copy project
COPY ./entrypoint.sh .
COPY . .

# run entrypoint.sh
ENTRYPOINT ["/usr/src/app/entrypoint.sh"]