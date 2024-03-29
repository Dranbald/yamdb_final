![yamdb_workflow](https://github.com/Dranbald/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)

# Api для проекта YaMDb

## О проекте

Проект YaMDb собирает отзывы *(Review)* пользователей на произведения *(Titles)*. 

Произведения делятся на категории: 

- «Книги»

- «Фильмы»

- «Музыка»

Список категорий *(Category)* может быть расширен администратором (например, можно добавить категорию «Изобразительное искусство» или «Ювелирка»).
Сами произведения в YaMDb не хранятся, здесь нельзя посмотреть фильм или послушать музыку.


В каждой категории есть произведения: книги, фильмы или музыка. Например, в категории «Книги» могут быть произведения «Винни-Пух и все-все-все» и «Марсианские хроники», а в категории «Музыка» — песня «Давеча» группы «Насекомые» и вторая сюита Баха.
Произведению может быть присвоен жанр *(Genre)* из списка предустановленных (например, «Сказка», «Рок» или «Артхаус»). 

Новые жанры может создавать только администратор.


Благодарные или возмущённые пользователи оставляют к произведениям текстовые отзывы *(Review)* и ставят произведению оценку в диапазоне от одного до десяти (целое число); из пользовательских оценок формируется усреднённая оценка произведения — рейтинг (целое число). На одно произведение пользователь может оставить только один отзыв.


## Список библиотек

Python, Django, git, PostgreSQL, SimpleJWT


## Шаблон наполнения env-файла

```bash
DB_ENGINE=django.db.backends.postgresql
DB_NAME=postgres
POSTGRES_USER=postgres
POSTGRES_PASSWORD=postgres
DB_HOST=db
DB_PORT=5432
```


## Запуск приложения в контейнерах
#### 1. Клонировать репозиторий:

> <sub> https://github.com/Dranbald/yamdb_final </sub>  

> <sub> cd yamdb_final/infra </sub>

#### 2. Запуск docker-compose:

> <sub> docker-compose up -d </sub> 

#### 3. Выполнить миграции:

> <sub> docker-compose exec web python manage.py migrate </sub> 

#### 4. Создать суперпользователя:

> <sub> docker-compose exec web python manage.py createsuperuser </sub> 

#### 5. Подключить статику:

> <sub> docker-compose exec web python manage.py collectstatic --no-input </sub> 

## Заполнение базы данными:

> <sub> docker-compose exec web python manage.py loaddata fixtures.json </sub> 


---
## Автор

Захаров Данил - студент Яндекс Практикум.
