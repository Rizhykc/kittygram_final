[![Main Kittygram workflow](https://github.com/Rizhykc/kittygram_final/actions/workflows/main.yml/badge.svg)](https://github.com/Rizhykc/kittygram_final/actions/workflows/main.yml)
# Проект: [Kittygram](https://kittigramhikari.serveblog.net/)
### Kittygram - сервис для любителей котиков.

Что умеет проект:

- Добавлять, просматривать, редактировать и удалять котиков.
- Добавлять новые и присваивать уже существующие достижения.
- Просматривать чужих котов и их достижения.

## Содержание

- [Установка и настройка](#установка-и-настройка)
- [Автоматизация и развертывание](#автоматизация-и-развертывание)
- [Работа с проектом](#работа-с-проектом)

## Технологии
![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white)
![Django](https://img.shields.io/badge/Django-3.2-0C4B33?style=flat-square&logo=django&logoColor=white&labelColor=0C4B33)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?logo=github-actions&logoColor=white)
![Nginx](https://img.shields.io/badge/Nginx-009639?logo=nginx&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-336791?logo=postgresql&logoColor=white)
![Python](https://img.shields.io/badge/Python-3.9.13-%23254F72?style=flat-square&logo=python&logoColor=yellow&labelColor=254f72)
![React](https://img.shields.io/badge/React-61DAFB?logo=react&logoColor=black)

## Установка и настройка

1. **Клонируйте репозиторий:**
   ```bash
   git clone https://github.com/Rizhykc/kittygram_final.git
   cd kittygram_final
   ```

2. **Настройте переменные окружения:**
   Создайте файл `.env` в корневой директории проекта и добавьте настройки для PostgreSQL:
   ```env
   DB_NAME=kittygram_db
   DB_USER=kittygram_user
   DB_PASSWORD=your_password
   DB_HOST=db
   DB_PORT=5432
   ```

3. **Запустите Docker Compose:**
   ```bash
   docker-compose up --build
   ```

   Это запустит все контейнеры (backend, frontend, db, и gateway) и поднимет приложение.

## Автоматизация и развертывание

Проект настроен для автоматического тестирования и развертывания с помощью GitHub Actions:
- Проверка кода на соответствие PEP8.
- Запуск тестов для фронтенда и бэкенда.
- Сборка Docker образов и отправка их на Docker Hub.
- Обновление образов на сервере и перезапуск приложения.
- Сборка статики и выполнение миграций.
- Уведомления о завершении деплоя в Telegram.

## Работа с проектом

1. **Запуск тестов:**
   ```bash
   docker-compose exec backend pytest
   docker-compose exec frontend npm test
   ```

2. **Переход к интерфейсу приложения:**
   После запуска контейнеров, приложение доступно по [http://localhost](http://localhost).

3. **Обновление статики:**
   ```bash
   docker-compose exec backend python manage.py collectstatic
   ```

4. **Миграции:**
   ```bash
   docker-compose exec backend python manage.py migrate
   ```

### Автор проекта: [*Рижук Сергей*](https://github.com/Rizhykc)