запустите Docker:
docker-compose up -d --build


Открыть порты на сервере (если используется UFW)
sudo ufw allow 80
sudo ufw allow 443


Удалите старые контейнеры и образы
Полностью удалите старые контейнеры и образы, чтобы не было конфликта с кешем:

docker-compose down --volumes --rmi all
docker system prune -af
docker-compose down --volumes --remove-orphans