# Используем более свежий образ Alpine 3.20
FROM alpine:3.20

# Устанавливаем Nginx
RUN apk update && \
    apk add --no-cache nginx && \
    rm -rf /var/cache/apk/*

# Создаем необходимые директории
RUN mkdir -p /run/nginx && \
    mkdir -p /usr/share/nginx/html

# Удаляем дефолтный конфиг Nginx и копируем собственный
COPY nginx.conf /etc/nginx/nginx.conf

# Копируем статические файлы в директорию для Nginx
COPY index.html /usr/share/nginx/html/index.html
COPY assets/css/style.css /usr/share/nginx/html/assets/css/style.css
COPY assets/js/main.js /usr/share/nginx/html/assets/js/main.js

# Открываем порт 80 для доступа к приложению
EXPOSE 80

# Команда для запуска Nginx в режиме демона
CMD ["nginx", "-g", "daemon off;"]
