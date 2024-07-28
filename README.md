https://github.com/OWNER/REPOSITORY/actions/workflows/WORKFLOW-FILE/badge.svg
#  Проект Kittygram

## Описание
'''
Kittygram — социальная сеть для обмена фотографиями любимых питомцев. Это полностью рабочий проект, который состоит из бэкенд-приложения на Django и фронтенд-приложения на React. Зарегистрированному пользователю доступна возможность просматривать сайт и регистрировать "карточку" кота со следующими параметрами:
- фото;
- Имя;
- цвет;
- год рождения;
- достижения(формируется, как группа).
'''

## Реализованный стек со следующими параметрами:
'''
- Django==3.2.3
- djangorestframework==3.12.4
- djoser==2.1.0
- webcolors==1.11.1
- psycopg2-binary==2.9.3
- Pillow==9.0.0
- pytest==6.2.4
- pytest-django==4.4.0
- pytest-pythonpath==0.7.3
- PyYAML==6.0
- python-dotenv==0.20.0
- gunicorn==20.1.0
'''

### Как развернуть проект:
1.Склонировать проект с репозитория на GitHub:
2.Создать в Docker образы kittygram_backend, kittygram_frontend, kittygram_gateway и отправить на Docker Hub:
'''
docker build -t username/kittygram_backend . 
cd ../backend
docker build -t username/kittygram_frontend .
cd ../gateway
docker build -t username/kittygram_gateway .
docker push username/kittygram_backend
docker push username/kittygram_frontend
docker push username/kittygram_gateway 
'''
3.Зайти на сервер проекта и очистить диск сервера от лишних данных::
'''
Удалить кеш npm: npm cache clean --force;
Удалить кеш APT: sudo apt clean.
Удалить старые системные логи: sudo journalctl --vacuum-time=1d
Полезно будет выполнить команду sudo docker system prune -af: она уберёт все лишние объекты, которые вы могли создать в докере за время выполнения заданий спринта, — неиспользуемые контейнеры, образы и сети.
Удалить Gunicorn-сервис (если установлен).
'''
4.Настроить сервер Nginx для Kittygram так, что все запросы пойдут в Docker, на порт 9000.
5.В папке Kittygram создать файл .env  с переменными из проекта (пример [.env.example](.env.example)).
6.В настройках проекта на GitHub прописать необходимые для работы main.yml переменные.
7.Добавить, откоммитить и отправить проект на сервер GitHub.
8.После проверки в Action и сообщения в Телеграмм на сервере будет развернут проект Kittygram.
'''
### Как заполнить env
'''
Файл .env создается на сервере проекта и локально.
Внутри .env прописываются переменные, которые будут скрыты при публикации проекта.
В файле settings.py импортировать load_dotenv и прописать переменные в необходимых местах с помощью os.getenv().
'''

### Автор
Evgeny Kudryashov: https://github.com/GagarinRu