# API для платформы Yatube (api_final_yatube)
## О проекте:
Данный проект представляет собой реализацию API для небольшой социальной 
сети Yatube с возможностью писать посты, оставлять комментарии, подписываться 
на любимых авторов и отписываться от тех, которые надоели.
## Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/chizhovsky/api_final_yatube
```

```
cd api_final_yatube
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
## Примеры запросов к API:
### Получение публикаций

```
GET /api/v1/posts/
```

Ответ (Response 200):

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

### Создание публикации

```
POST /api/v1/posts/
```

Пример запроса:

```
{
  "text": "string",
  "image": "string",
  "group": 0
}
```

Ответ (Response 201):

```
{
  "id": 0,
  "author": "string",
  "text": "string",
  "pub_date": "2019-08-24T14:15:22Z",
  "image": "string",
  "group": 0
}
```

Ответ (Response 400):

```
{
  "text": [
    "Обязательное поле."
  ]
}
```

Ответ (Response 401):

```
{
  "detail": "Учетные данные не были предоставлены."
}
```

## Автор: 
### Алексей Чижов (https://t.me/Chizhovsky)
