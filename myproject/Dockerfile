# Используем официальный образ Python
FROM python:3.11-slim

# Устанавливаем зависимости для PostgreSQL
RUN apt-get update \
    && apt-get install -y libpq-dev gcc

# Устанавливаем рабочую директорию
WORKDIR /app

# Копируем файлы
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

# Запускаем сервер
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
