# Django-Celery

## APP1: Django Celery with RabbitMQ basic 'add' task
run:

celery -A proj worker -l info --pool=solo

python manage.py shell

from app1.tasks import add

add.delay(3, 5)

see result:

<AsyncResult: f4884962-19a1-4e84-bea3-7c86b545274d>

[2022-12-22 11:46:55,428: INFO/MainProcess] Task app1.tasks.add[f4884962-19a1-4e84-bea3-7c86b545274d] succeeded in 0.0s: 8


## APP2: Sending Emails

run:

celery -A proj worker -l info --pool=solo

python manage.py runserver

send a review via
http://127.0.0.1:8000/reviews/