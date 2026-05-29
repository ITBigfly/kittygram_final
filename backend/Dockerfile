# Выбираем базовый образ питона
FROM python:3.9

# Устанавливаем рабочую директорию внутри контейнера
WORKDIR /app

# Копируем файл с зависимостями
COPY requirements.txt .

# Устанавливаем библиотеки
RUN pip install -r requirements.txt --no-cache-dir
RUN pip install gunicorn
# Копируем весь оставшийся код бэкенда
COPY . .

# Команда, которая запустит Gunicorn при старте контейнера
CMD ["gunicorn", "--bind", "0.0.0.0:8000", "kittygram_backend.wsgi"]
