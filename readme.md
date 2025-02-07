# Руководство по командам Docker

## Запуск сервисов Docker
```bash
# Собрать и запустить контейнеры в фоновом режиме
docker-compose up -d --build
```

## Настройка брандмауэра (UFW)
```bash
# Разрешить HTTP трафик
sudo ufw allow 80

# Разрешить HTTPS трафик
sudo ufw allow 443
```

## Очистка окружения Docker
```bash
# Остановить контейнеры, удалить тома и образы
docker-compose down --volumes --rmi all

# Удалить все неиспользуемые контейнеры, сети, образы
docker system prune -af

# Остановить контейнеры и удалить сирые тома
docker-compose down --volumes --remove-orphans
```

> **Примечание**: Эти команды навсегда удалят все ресурсы Docker. Убедитесь, что у вас есть резервные копии важных данных перед выполнением.
