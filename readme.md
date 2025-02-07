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

## Просмотр логов Docker
```bash
# Посмотреть логи конкретного контейнера
docker logs <container_name_or_id>

# Посмотреть логи контейнера в реальном времени (с обновлением)
docker logs -f <container_name_or_id>

# Посмотреть логи конкретного контейнера с ограничением по времени
docker logs --since "2025-02-07T10:00:00" <container_name_or_id>

# Посмотреть логи всех контейнеров
docker-compose logs

# Посмотреть логи всех контейнеров с реальным временем
docker-compose logs -f

# Просмотр логов с фильтрацией по уровню
docker logs --level <level> <container_name_or_id>
```

> **Примечание**: Эти команды помогут вам мониторить и анализировать логи контейнеров Docker для диагностики и отладки.
