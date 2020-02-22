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
1) Распакуйте проект в папку C:\my_site
2) Откройте командную строку и зайдите в директорию проекта:
   - cd C:\my_site
3) Создате виртуальное окружение:
   - python -m venv django
4) Активируйте виртуальное окружение:
   - django\Scripts\activate.bat
5) Установите все необходимые пакеты:
   - pip install -r requirements.txt
6) Выполнить следующую команду:
   - python manage.py runserver

Для того, чтобы сделать деплой на heroku необходимо:
1) Перейти в каталог с проектом:
   - cd C:\my_site
2) Выпонить следующий команды:
   - git init
   - git add .
   - git commit -m "initial commit"
   - heroku login
   - heroku create
   - heroku addons:create heroku-postgresql --as DATABASE
   - heroku config:set SECRET_KEY=Ваш_секретный_код
   - heroku config:set DISABLE_COLLECTSTATIC=1
   - git push heroku master
   - heroku run python manage.py migrate
   - heroku run python manage.py createsuperuser
3) Если необходимо переименовываем приложение:
   - heroku rename -a oldname newname
4) Запускаем приложение:
   - heroku open

   По умолчанию логин и пароль для пользователя-администратора в проекте:
   Логин: pws_admin
   Пароль: sf_password
