# REST API YaMDB
![DjangoREST](https://img.shields.io/badge/DJANGO-REST-ff1709?style=for-the-badge&logo=django&logoColor=white&color=ff1709&labelColor=gray)

### Описание:
База отзывов на книги и музыку, доступ через API. Пользователи могут делиться мнением, оценивать произведения, смотреть отзывы других.
Учебный проект, созданный в рамках учебы в Яндекс.Практикуме.

### Техническое описание проекта:
На странице с документацией localhost/redoc/ можно ознакомиться с примерами запросов и ответов на них.

### Зависимости:
См. requirements.txt

## Примеры API-запросов:
См. localhost/redoc/

#### Получение списка всех произведений

```http
  GET /api/v1/titles/
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `token`   | `string` | **Required**. Ваш токен    |

#### Добавление нового отзыва к произведению

```http
  POST /api/v1/titles/{id}/reviews/
```

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `token`   | `string` | **Required**. Ваш токен           |
| `id`      | `string` | **Required**. Id произведения     |
| `text`    | `string` | **Required**. Текст отзыва        |
| `score`   | `integer` | **Required**. Оценка произведения |


### Регистрация:
Для регистрации пользователь может самостоятельно отправить свой username и email на /auth/signup/. После этого он получает письмо с кодом подтвержения. Далее необходимо получит токен для аутентификации, использовав код и передав его вместе с username по адресу /auth/token/.
Администратор также может создать пользователя в базе (с внесенным confiramtion_code), последующашие шаги пользователя аналогичны инструкции выше.

### Импорт данных из csv файлов

Запустить скрипт командой python manage.py runscript CSVtoDB.

### Лицензия:
[MIT](https://choosealicense.com/licenses/mit/)
