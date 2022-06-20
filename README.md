# Проект YaMDb

Проект YaMDb собирает отзывы пользователей на произведения.

## Описание

* Проект YaMDb собирает отзывы (Review) пользователей на произведения (Titles). Произведения делятся на категории: «Книги», «Фильмы», «Музыка». Список категорий (Category) может быть расширен администратором (например, можно добавить категорию «Изобразительное искусство» или «Ювелирка»).
* Сами произведения в YaMDb не хранятся, здесь нельзя посмотреть фильм или послушать музыку.
* В каждой категории есть произведения: книги, фильмы или музыка. Например, в категории «Книги» могут быть произведения «Винни-Пух и все-все-все» и «Марсианские хроники», а в категории «Музыка» — песня «Давеча» группы «Насекомые» и вторая сюита Баха.
* Произведению может быть присвоен жанр (Genre) из списка предустановленных (например, «Сказка», «Рок» или «Артхаус»). Новые жанры может создавать только администратор.
* Благодарные или возмущённые пользователи оставляют к произведениям текстовые отзывы (Review) и ставят произведению оценку в диапазоне от одного до десяти (целое число); из пользовательских оценок формируется усреднённая оценка произведения — рейтинг (целое число). На одно произведение пользователь может оставить только один отзыв.

## Использованные технологии

* Python 3.9
* Django 2.2.16
* Docker 20.10
* Nginx 1.18

## Шаблон наполнения env-файла

```
DB_ENGINE=django.db.backends.postgresql # указываем, что работаем с postgresql
DB_NAME=postgres # имя базы данных
POSTGRES_USER=postgres # логин для подключения к базе данных
POSTGRES_PASSWORD=postgres # пароль для подключения к БД (установите свой)
DB_HOST=db # название сервиса (контейнера)
DB_PORT=5432 # порт для подключения к БД
```

## Запуск проекта:

### Клонировать репозиторий:

```python
git@github.com:yorriyurri/infra_sp2.git
```

### Перейти в директорию infra/ и запустить docker-compose:

```python
cd infra/
docker-compose up
```

### Применить миграции:

```python
docker-compose exec web python manage.py migrate
```

### Создать суперпользователя:

```python
docker-compose exec web python manage.py createsuperuser
```

### Cобрать статические файлы::

```python
docker-compose exec web python collecstatic --no-input
```

## Заполнение базы данными:

```python
docker-compose exec web python manage.py loaddata fixtures.json
```

## Примеры

Подробная документация API с примерами размещена по адресу:
http://localhost/redoc

## Автор

Студент 29 когорты Факультета Бэкэнд-разработки, Яндекс.Практикум:

* Ивайкин Юрий
