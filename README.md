### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/xeniakutsevol/infra_sp2
```

```
cd infra_sp2
```

Перейти в репозиторий с Dockerfile и собрать образ:

```
cd api_yamdb/api_yamdb/
```

```
docker build -t api_yamdb .
```

Запустите контейнеры docker-compose:

```
cd ../infra/
```

```
docker-compose up -d --build
```

Выполнить миграции, создайте суперпользователя, соберите статику:

```
docker-compose exec web python manage.py migrate
```

```
docker-compose exec web python manage.py createsuperuser
```

```
docker-compose exec web python manage.py collectstatic --no-input
```

Проверьте работоспособность проекта:

```
http://localhost/admin/
```

Документация к API:

```
http://localhost/redoc/
```

Образ проекта также доступен в DockerHub:

```
xeniakutsevol/api_yamdb:v1.00.0000
```
