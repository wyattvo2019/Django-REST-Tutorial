```
<!-- Vỉtual environment -->
python3 -m venv env
source env/bin/activate 
<!-- Install Django and Django REST framework into the virtual environment -->
pip install django
pip install djangorestframework
<!-- Set up a new project with a single application -->
django-admin startproject tutorial .
cd tutorial
django-admin startapp quickstart
cd ..
<!-- sync your database for the first time -->
python manage.py migrate
<!-- create an initial user -->
python manage.py createsuperuser --email admin@example.com --username admin
admin/admin
<!-- Create serializer file -->
touch tutorial/quickstart/serializers.py
<!-- Update views.py -->
<!-- Update tutorial/urls.py -->
<!-- Update tutorial/settings.py -->
<!-- Test API -->
curl -H 'Accept: application/json; indent=4' -u admin:admin http://127.0.0.1:8000/users/


<!-- SNIPPETS APP -->
python manage.py startapp snippets
python manage.py makemigrations snippets
python manage.py migrate snippets

python manage.py runserver

<!-- Install httpie for test API -->
pip install httpie
http http://127.0.0.1:8000/snip/snippets/
http http://127.0.0.1:8000/snip/snippets/2/

http http://127.0.0.1:8000/snip/snippets/ Accept:application/json  # Request JSON
http http://127.0.0.1:8000/snip/snippets/ Accept:text/html         # Request HTML



rm -f db.sqlite3
rm -r snippets/migrations
python manage.py makemigrations snippets
python manage.py migrate
quyvo/quyvo

http POST http://127.0.0.1:8000/snip/snippets/ code="print(123)"
http -a admin:admin POST http://127.0.0.1:8000/snip/snippets/ code="print(789)"

```