# Задание D10.9

   Проект каталог автомобилей на Django

   ТехЗадание:
1) Весь проект Django состоит из одного приложения.
2) Необходимо описать модель автомобиля (Car) с полями:
   - производитель (BMW, Audi, Tesla и т.д.) (CharField)
   - модель авто (S, TT, X6 и т.д.) (CharField)
   - год выпуска (IntegerField)
   - коробка передач (SmallIntegerField with choices "механика", "автомат", "робот")
   - цвет
3) Необходимо создать главную страницу со списком автомобилей.
4) На главной странице создать форму «фильтрации» (поиска) автомобилей.
5) GET-запросом отправлять данные о фильтрах.
6) Во view собирать запрос с помощью Q-объектов и отображать авто на главной с учётом фильтров.

Для того, чтобы запустить локальный сервер необходимо:
1) Распакуйте проект в папку и через терминал зайдите в директорию проекта
2) Создате виртуальное окружение:
   - python -m venv django
3) Активируйте виртуальное окружение:
   - django\Scripts\activate.bat
4) Установите все необходимые пакеты:
   - pip install -r requirements.txt
5) Выпонить следующую команду:
   - python manage.py runserver

Для того, чтобы сделать деплой на heroku необходимо (при Debug=False):
1) Перейти в каталог с проектом (например):
   - cd C:\my_site
2) Если используете статические файлы, то обязательно в проекте должны быть созданы две папки: static и staticfiles
3) Выполнить следующий команды:
   - git init
   - git add .
   - git commit -m "initial commit
   - heroku login
   - heroku create
   - heroku rename -a oldname newname (переименовываем приложение, если необходимо)
   - heroku addons:create heroku-postgresql --as DATABASE
   - heroku config:set SECRET_KEY=Ваш_секретный_код
   - git push heroku master
   - heroku run python manage.py makemigrations
   - heroku run python manage.py migrate
   - heroku run python manage.py loaddata data.xml
   - heroku run python manage.py createsuperuser
4) Запускаем приложение:
   - heroku open

Данный проект находится на https://carcatalog-skillfactory.herokuapp.com/
По умолчанию логин и пароль для пользователя-администратора в проекте:
- Логин: pws_admin
- Пароль: sf_password
