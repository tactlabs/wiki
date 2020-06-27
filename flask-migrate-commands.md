# MongoDB Commands

**Note:** notes



#### Basic commands
```
python manage.py db heads
python manage.py db current

python manage.py db stamp head
python manage.py db migrate
python manage.py db upgrade

python manage.py db history
python manage.py db head
python manage.py db current
python manage.py db show
python manage.py db merge
python manage.py db heads
```


#### Issues:

1. Target database is not up to date

Sol:
db heads
db current
db stamp heads
db current
  * [soltuion ref](https://stackoverflow.com/questions/17768940/target-database-is-not-up-to-date)

### Ref :

  * [Basics](https://flask-migrate.readthedocs.io/en/latest/)
