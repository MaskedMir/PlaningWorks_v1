# Используем Python 3.9 как базовый образ
FROM python:3.9-slim

# Установка зависимостей
WORKDIR /app
COPY ./backend/requirements.txt /app/requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Копируем исходный код
COPY ./backend /app

# Указываем команду запуска
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]
