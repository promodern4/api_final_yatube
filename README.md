# **Проект api_final**
#### Назначение
Проект *api_final* представляет собой учебный проект, предназначенный для реализации полученных навыков в области *API*
#### Описание
Проект *api_final* включает в себя следующие возможности:
> Создание, редактирование, удаление и просмотр постов;
> Создание, редактирование, удаление и просмотр комментариев к постам;
> Просмотр списка и информации о сообществах;
> Создание подписки на других пользователей.

При этом каждый пункт разграничен для аунтетифицированных и неатентифицированных пользователей. А также не автору того или иного объекта разрешено только просматривать его.

### Как запустить проект:
Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/promodern4/api_final_yatube.git
```
```
cd kittygram
```

Cоздать и активировать виртуальное окружение:

```
python3 -m venv env
```

```
source env/bin/activate
```

Установить зависимости из файла requirements.txt:

```
python3 -m pip install --upgrade pip
```

```
pip install -r requirements.txt
```

Выполнить миграции:

```
python3 manage.py migrate
``` 
Запустить проект:
```
python3 manage.py runserver
```
### Примеры запросов
*Получение публикаций*
GET
```
http://127.0.0.1:8000/api/v1/posts/
```
RESPONCE
```
{
    "count": 123,
    "next": "http://api.example.org/accounts/?offset=400&limit=100",
    "previous": "http://api.example.org/accounts/?offset=200&limit=100",
    "results": [
        {
            "id": 0,
            "author": "string",
            "text": "string",
            "pub_date": "2021-10-14T20:41:29.648Z",
            "image": "string",
            "group": 0
        }
    ]
}
```


*Добавление комментария*
POST
```
http://127.0.0.1:8000/api/v1/posts/{post_id}/comments/
```
PAYLOAD
```
{
  "text": "string"
}
```
RESPONCE
```
{
  "id": 0,
  "author": "string",
  "text": "string",
  "created": "2019-08-24T14:15:22Z",
  "post": 0
}
```


*Подписка*
POST
```
http://127.0.0.1:8000/api/v1/follow/
```
PAYLOAD
```
{
  "following": "string"
}
```
RESPONCE
```
{
  "user": "string",
  "following": "string"
}
```