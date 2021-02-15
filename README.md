# salary

https://realpython.com/asynchronous-tasks-with-django-and-celery/

- pyenv install 3.6.4 []
- pyenv local 3.6.4 []
- virtualenv -p ~/.pyenv/versions/3.6.4/bin/python3.6 venv [] 

1. source venv/bin/activate [x]
2. export PIP_USER=no []
3. pip install -r requirements_1old.txt []
4. python manage.py migrate []
5. python manage.py runserver 8000 --settings=picha.settings [x]

### Celery uses redis as broker to pass messages between Django Project and Celery workers.
- In another terminal, 'brew install redis' []
- redis-server [x]

### back to virtualenv venv

- start a separate virtualenv for the celery worker and celery beat separately
8. celery -A picha worker -l info [x] ``` Start celery worker to receive tasks, and run programs decorated by task ```
9. celery -A picha beat -l info [x] ``` Start celery task scheduler to send tasks per schedule ```

- localhost:8000/feedback
