FROM python:3.10.13-alpine3.19

LABEL maintainer="<bipinm56567@gmail.com> bipin mishra"

ENV PYTHONUNBUFFERED 1

COPY ./app /app

WORKDIR /app

COPY ../pyproject.toml ../poetry.lock ./

RUN pip install poetry && \
    poetry config virtualenvs.create false && \
    poetry install --no-interaction --no-ansi && \
    adduser \
         --disabled-password  \
         --no-create-home django-user

# switching to user django-user
USER django-user

# Expose port
EXPOSE 8000
