Проект kittygram - это социальная сеть для владельцев котов (и кошек) и тех, кто только собирается ими стать. Здесь можно похвастатся фотографией своего кота, его достижениеми  а также посмотреть на питомцев других пользрвателей.

Инструкция по установке:
1. Скачать проект с репозиитория
2. Зайти на удаленный сервер, используя ключи
3. Перейти в директорию kittygram/ и запустить docker-compose.production.yml, используя команду:
~~~ sudo docker compose -f docker-compose.production.yml up -d ~~~
4. Выполнить миграции:
~~~ sudo docker compose -f docker-compose.production.yml exec backend python manage.py migrate ~~~
5. Пересобрать статику:
~~~ sudo docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic ~~~
6. Копиоуем статику в папку static_backend/static/:
~~~ sudo docker compose -f docker-compose.production.yml exec backend cp -r /app/collected_static/. /backend_static/static/ ~~~


Информация по использованию:

В случае доработок кода повторить операции пункт 2 и через команды 
- git add .
- git commit -m 'comment'
- git push
отправить в репозиторий и во вкладке "actions" проверить, что все прошло корректно. В случае нарушений исправить ошибки.
