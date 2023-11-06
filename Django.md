## Django

#### Create Virtual Environment
- Create - `python -m venv venv`
- Activate - `source venv/bin/activate`
- Deactivate - `deactivate`

#### Setting up Django Project
- Installation - `pip install Django` , `python -m pip install django`
- Start a Django project - `django-admin startproject wat .` (create **wat** project directory within **.** current directory)
- Run the app server - `python manage.py runserver`

#### Creating App
- Start new app in current directory - `python manage.py startapp appname .`

#### Database Migration
Whenever we change the **models.py** file, we should run the following commands:
This is just to establish the connection between database and django application
- `python manage.py makemigrations`
- `python manage.py migrate`

#### Create Database objects in python shell
- `python manage.py shell`

> **Some basic commands for `Product` object**
> Query all products - `Product.objects.all()` 
> Create products - `Product.objects.create(--add fields--)`

#### Setup Superuser
- `python manage.py createsuperuser`
- set the credentials and use them


