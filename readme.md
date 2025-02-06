3. Обновить settings.py в Django
Добавьте или измените настройки статики:

STATIC_URL = '/static/'
STATIC_ROOT = '/app/static/'



4. Запуск проекта
Теперь запустите Docker:

docker-compose up -d --build





5 Открыть порты на сервере (если используется UFW)

sudo ufw allow 80
sudo ufw allow 443




docker-compose up -d --build