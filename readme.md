# Личный шаблон для старта проекта с Docker

Этот репозиторий — мой личный шаблон для быстрого старта нового проекта с использованием Docker. В нем настроены все необходимые компоненты для запуска веб-приложения:

- **Docker** для контейнеризации приложения.
- **Nginx** для обработки HTTP(S) запросов и проксирования к приложению.
- **SQLite** для хранения данных (легковесная база данных для небольших проектов или прототипов).
- Настроены директории для **медиа-файлов** и **статических файлов**.
- Установлены шаблонные настройки для **названия проекта** и **первой аппки** (например, можно легко изменить на любое ваше имя приложения и проекта).

Этот шаблон позволяет быстро развернуть рабочее окружение для разработки, которое включает все ключевые компоненты: веб-сервер, базу данных и соответствующие настройки для работы с медиа и статикой.



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




```markdown
## Отключение отслеживания изменений прав доступа к файлам в Git

```bash
# Отключить отслеживание изменений прав доступа к файлам
git config core.fileMode false
```

> **Примечание**: Эта настройка позволяет Git игнорировать изменения прав доступа (`chmod`) в файлах. Полезно, если файловая система изменяет права автоматически, но вы не хотите, чтобы эти изменения учитывались в системе контроля версий.
```  




Вот исправленный Markdown с правильным оформлением:  

```markdown
## Изменение прав доступа к файлам с помощью chmod

### Установка прав доступа (числовой метод)
```bash
# Установить полный доступ для владельца, чтение и выполнение для группы и остальных
chmod 755 файл_или_папка

# Установить полный доступ для владельца, чтение для группы и остальных
chmod 744 файл_или_папка

# Установить полный доступ только для владельца
chmod 700 файл_или_папка
``` ```

### Установка прав доступа (символьный метод)
```bash
# Добавить права на выполнение для всех пользователей
chmod +x файл_или_папка

# Убрать права на запись для всех, кроме владельца
chmod go-w файл_или_папка

# Дать только владельцу право на чтение и запись
chmod u+rw,go-rwx файл_или_папка
```

### Разбор числовых значений прав:
| Число | Права владельца (u) | Права группы (g) | Права остальных (o) |
|-------|----------------------|------------------|---------------------|
| 7     | Чтение, запись, выполнение (rwx) | Чтение, запись, выполнение (rwx) | Чтение, запись, выполнение (rwx) |
| 6     | Чтение, запись (rw-) | Чтение, запись (rw-) | Чтение, запись (rw-) |
| 5     | Чтение, выполнение (r-x) | Чтение, выполнение (r-x) | Чтение, выполнение (r-x) |
| 4     | Только чтение (r--) | Только чтение (r--) | Только чтение (r--) |

> **Примечание:**  
> - `u` (user) — владелец файла  
> - `g` (group) — группа, которой принадлежит файл  
> - `o` (others) — все остальные  
> - `a` (all) — все пользователи (включая владельца, группу и остальных)  
> - `+` добавляет права, `-` убирает, `=` задает точное значение  


