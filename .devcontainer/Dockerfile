FROM python:3.12-slim-bookworm
RUN apt-get update && apt-get install -y \
    curl \
    git

ENV PYTHONDONTWRITEBYTECODE 1 \
    PYTHONUNBUFFERED 1 

RUN curl -sSL https://install.python-poetry.org | POETRY_VERSION=1.7.1 POETRY_HOME=/opt/poetry python3 - && \
    ln -s /opt/poetry/bin/poetry /usr/local/bin/poetry

COPY pyproject.toml poetry.lock ./
RUN poetry config virtualenvs.create false \
    && poetry install