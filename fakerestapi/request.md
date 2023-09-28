# Запросы

Глобальные переменные:  

url https://fakerestapi.azurewebsites.net

## Activities

1. **GET /api/v1/Activities**

- URL  
https://fakerestapi.azurewebsites.net/api/v1/Activities

- Ожидаемый результат  
  Получение списка активностей 

- Заголовки запроса  

Content-Type: application/json
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Cache-Control: no-cache
Postman-Token: 8a516102-0d73-4b4c-9c25-2230dac5323d
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

- Заголовки ответа

Content-Type: application/json; charset=utf-8; v=1.0
Date: Sun, 27 Aug 2023 06:45:26 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0 

- Тело ответа  

```
[
    {
        "id": 1,
        "title": "Activity 1",
        "dueDate": "2023-08-27T07:45:26.6445822+00:00",
        "completed": false
    },
    {
        "id": 2,
        "title": "Activity 2",
        "dueDate": "2023-08-27T08:45:26.6445847+00:00",
        "completed": true
    },
    {
        "id": 3,
        "title": "Activity 3",
        "dueDate": "2023-08-27T09:45:26.6445852+00:00",
        "completed": false
    },
    {
        "id": 4,
        "title": "Activity 4",
        "dueDate": "2023-08-27T10:45:26.6445854+00:00",
        "completed": true
    },
    {
        "id": 5,
        "title": "Activity 5",
        "dueDate": "2023-08-27T11:45:26.6445857+00:00",
        "completed": false
    } 
```

2. **POST /api/v1/Activities**

- URL  
  https://fakerestapi.azurewebsites.net/api/v1/Activities

- Ожидаемый результат  
  Добавление нового активности

- Заголовки запроса  

Content-Type: application/json
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Cache-Control: no-cache
Postman-Token: b5bd8901-6584-4e53-b98d-d6b2d7c3056a
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive 

- Тело запроса  

```
{
  "id": 907,
  "title": "string",
  "dueDate": "2023-08-24T17:21:49.906Z",
  "completed": true
}
```

- Заголовки ответа

Content-Type: application/json; charset=utf-8; v=1.0
Date: Sun, 27 Aug 2023 06:51:53 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0

- Тело ответа  

```
{
    "id": 907,
    "title": "string",
    "dueDate": "2023-08-24T17:21:49.906Z",
    "completed": true
}
```

3. **GET /api/v1/Activities/{id}**

- URL  
 https://fakerestapi.azurewebsites.net/api/v1/Activities/1

- Ожидаемый результат  
  Получение активности по id

- Заголовки запроса  

Content-Type: application/json
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Cache-Control: no-cache
Postman-Token: 786afc69-7cc9-44e7-8b43-0f03d390eddf
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive


- Заголовки ответа

Content-Type: application/json; charset=utf-8; v=1.0
Date: Sun, 27 Aug 2023 06:56:28 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0 

- Тело ответа  

```
{
    "id": 1,
    "title": "Activity 1",
    "dueDate": "2023-08-27T07:56:28.7064596+00:00",
    "completed": false
}
```

4. **PUT /api/v1/Activities/{id}**

- URL  
https://fakerestapi.azurewebsites.net/api/v1/Activities/1 

- Ожидаемый результат  
  Получение списка авторов по id книги  

- Заголовки запроса  

Content-Type: application/json
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Cache-Control: no-cache
Postman-Token: 9e2a20c7-eb1f-462c-8a27-195d5819b65b
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive 

- Заголовки ответа

Content-Type: application/json; charset=utf-8; v=1.0
Date: Sun, 27 Aug 2023 07:03:40 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0

- Тело ответа  

```
{
    "id": 1,
    "title": "Activity 1",
    "dueDate": "2023-08-27T07:56:28.7064596+00:00",
    "completed": false
}  
```

5. **DELETE /api/v1/Activities/{id}**

- URL  
https://fakerestapi.azurewebsites.net/api/v1/Activities/1 

- Ожидаемый результат  
  Удаление активности по id 

- Заголовки запроса  

Accept: */*
Cache-Control: no-cache
Postman-Token: 012ec073-1363-416e-8d1f-a082aa189b96 

- Заголовки ответа

Accept: */*
Cache-Control: no-cache
Postman-Token: 012ec073-1363-416e-8d1f-a082aa189b96 


6. **POST /api/v1/Activities; Попытка создать ресурс c телом JSON и c content-type = XML"**

- URL  
https://fakerestapi.azurewebsites.net/api/v1/Activities  

- Ожидаемый результат  
  Ошибка 415 при попытке добавления новой активности 

- Заголовки запроса  

Content-Type: application/xlm
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Cache-Control: no-cache
Postman-Token: 2519e915-f148-4746-8ffd-f7e73c696960
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8
Date: Sun, 27 Aug 2023 07:26:36 GMT
Server: Kestrel
Transfer-Encoding: chunked

- Тело запроса

```
{
  "id": 982,
  "title": "string",
  "dueDate": "2023-08-24T17:21:49.906Z",
  "completed": true
}
```

- Тело ответа  

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.13",
    "title": "Unsupported Media Type",
    "status": 415,
    "traceId": "00-622d379f4c8fe34cad4b78059659a04c-7dae0180c576a942-00"
}
```

7. **POST /api/v1/Activities; Попытка создать ресурс c телом JSON и c content-type = Javascript**

- URL  
https://fakerestapi.azurewebsites.net/api/v1/Activities 

- Ожидаемый результат  
  Ошибка 415 при попытке добавления новой активности 

- Заголовки запроса  

Content-Type: application/javascript
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Cache-Control: no-cache
Postman-Token: 93fdc1ef-ab30-41ae-a99e-ca67623c3227
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive  

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8
Date: Sun, 27 Aug 2023 07:30:56 GMT
Server: Kestrel
Transfer-Encoding: chunked 

- Тело запроса

```
{
  "id": 982,
  "title": "string",
  "dueDate": "2023-08-24T17:21:49.906Z",
  "completed": true
}
```

- Тело ответа  

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.13",
    "title": "Unsupported Media Type",
    "status": 415,
    "traceId": "00-9c2d63cb7b1c9c40b0ea83335396d6e8-30d2ddfaaadb8745-00"
}
```

8. **POST /api/v1/Activities; Попытка создать ресурс c полем, не допускающим значение ""NULL"", но равен ""NULL"" в теле запроса**

- URL  
 https://fakerestapi.azurewebsites.net/api/v1/Activities

- Ожидаемый результат  
  Ошибка 400 при попытке добавления новой активности, ошибка "The JSON value could not be converted to System.Int32. Path: $.id | LineNumber: 1 | BytePositionInLine: 12."

- Заголовки запроса  

Content-Type: application/json
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Cache-Control: no-cache
Postman-Token: e9aae07b-bc21-4fa0-8f23-f5251bc2af56
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

- Тело запроса  

```
{
  "id": null,
  "title": "string",
  "dueDate": "2023-08-24T17:21:49.906Z",
  "completed": true
}
```

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8
Date: Sun, 27 Aug 2023 07:33:46 GMT
Server: Kestrel
Transfer-Encoding: chunked  

- Тело ответа  

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-ef2725916a9ae14484e0decbc6dab071-8abda5534b000b4a-00",
    "errors": {
        "$.id": [
            "The JSON value could not be converted to System.Int32. Path: $.id | LineNumber: 1 | BytePositionInLine: 12."
        ]
    }
}
```

9. **POST /api/v1/Activities; Попытка создать ресурс c пустым Json-файлом**

- URL  
 https://fakerestapi.azurewebsites.net/api/v1/Activities  

- Ожидаемый результат  
  Запрос успешно отправлен на сервер

- Заголовки запроса  

Content-Type: application/json
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Cache-Control: no-cache
Postman-Token: b4a9ec02-fc0f-4497-bd01-86ec2de00267
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

- Тело запроса  

```
{  


}  
```

- Заголовки ответа

Content-Type: application/json; charset=utf-8; v=1.0
Date: Sun, 27 Aug 2023 07:45:29 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0

- Тело ответа  

```
{
    "id": 0,
    "title": null,
    "dueDate": "0001-01-01T00:00:00",
    "completed": false
}  
```

10. **GET /api/v1/Activities/{id} c невалидным id**

- URL  
 https://fakerestapi.azurewebsites.net/api/v1/Activities/31 

- Ожидаемый результат  
  Ошибка 404

- Заголовки запроса  

Content-Type: application/json
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Cache-Control: no-cache
Postman-Token: d82ee822-5a81-44b4-80a1-2fba1e4bbbe0
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8; v=1.0
Date: Sun, 27 Aug 2023 07:55:50 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0

- Тело ответа  

```
{
  {
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.4",
    "title": "Not Found",
    "status": 404,
    "traceId": "00-3a3e4e3c7f84ab4cac39fd9878979fb8-3791dc4c8a729c4d-00"
}
}  
```

11. **PUT /api/v1/Activities с невалидным id**

- URL  
https://fakerestapi.azurewebsites.net/api/v1/Activities/8230948240284028408248  

- Ожидаемый результат  
  Ошибка 400

- Заголовки запроса  

Content-Type: application/json
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Cache-Control: no-cache
Postman-Token: 6e0feb3e-a35e-4090-9ac4-e94f73dfcef3
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive  

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8
Date: Sun, 27 Aug 2023 08:07:45 GMT
Server: Kestrel
Transfer-Encoding: chunked

- Тело ответа  

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-3ed383b0acf0d046975222ca30471346-b47b89c868a0d14c-00",
    "errors": {
        "id": [
            "The value '8230948240284028408248' is not valid."
        ]
    }
}
```

12. **PUT /api/v1/Activities; Попытка редактировать ресурс c телом JSON и c content-type = XML"**

- URL  
https://fakerestapi.azurewebsites.net/api/v1/Activities  

- Ожидаемый результат  
  Ошибка 415 при попытке добавления новой активности 

- Заголовки запроса  

Content-Type: application/xlm
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Cache-Control: no-cache
Postman-Token: 2519e915-f148-4746-8ffd-f7e73c696960
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8
Date: Thu, 29 Aug 2023 07:26:36 GMT
Server: Kestrel
Transfer-Encoding: chunked

- Тело запроса

```
{
  "id": 982,
  "title": "string",
  "dueDate": "2023-08-24T17:21:49.906Z",
  "completed": true
}
```

- Тело ответа  

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.13",
    "title": "Unsupported Media Type",
    "status": 415,
    "traceId": "00-622d379f4c8fe34cad4b78059659a04c-7dae0180c576a942-00"
}
```

13. **PUT /api/v1/Activities; Попытка создать ресурс c телом JSON и c content-type = Javascript**

- URL  
https://fakerestapi.azurewebsites.net/api/v1/Activities 

- Ожидаемый результат  
  Ошибка 415 при попытке добавления новой активности 

- Заголовки запроса  

Content-Type: application/javascript
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Cache-Control: no-cache
Postman-Token: 93fdc1ef-ab30-41ae-a99e-ca67623c3227
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive  

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8
Date: Thu, 29 Aug 2023 07:30:56 GMT
Server: Kestrel
Transfer-Encoding: chunked 

- Тело запроса

```
{
  "id": 982,
  "title": "string",
  "dueDate": "2023-08-24T17:21:49.906Z",
  "completed": true
}
```

- Тело ответа  

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.13",
    "title": "Unsupported Media Type",
    "status": 415,
    "traceId": "00-9c2d63cb7b1c9c40b0ea83335396d6e8-30d2ddfaaadb8745-00"
}
```

14. **PUT /api/v1/Activities; Попытка создать ресурс c полем, не допускающим значение ""NULL"", но равен ""NULL"" в теле запроса**

- URL  
 https://fakerestapi.azurewebsites.net/api/v1/Activities

- Ожидаемый результат  
  Ошибка 400 при попытке добавления новой активности, ошибка "The JSON value could not be converted to System.Int32. Path: $.id | LineNumber: 1 | BytePositionInLine: 12."

- Заголовки запроса  

Content-Type: application/json
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Cache-Control: no-cache
Postman-Token: e9aae07b-bc21-4fa0-8f23-f5251bc2af56
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

- Тело запроса  

```
{
  "id": null,
  "title": "string",
  "dueDate": "2023-08-24T17:21:49.906Z",
  "completed": true
}
```

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8
Date: Thu, 29 Aug 2023 07:33:46 GMT
Server: Kestrel
Transfer-Encoding: chunked  

- Тело ответа  

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-ef2725916a9ae14484e0decbc6dab071-8abda5534b000b4a-00",
    "errors": {
        "$.id": [
            "The JSON value could not be converted to System.Int32. Path: $.id | LineNumber: 1 | BytePositionInLine: 12."
        ]
    }
}
```

15. **PUT /api/v1/Activities; Попытка создать ресурс c пустым Json-файлом**

- URL  
 https://fakerestapi.azurewebsites.net/api/v1/Activities  

- Ожидаемый результат  
  Запрос успешно отправлен на сервер

- Заголовки запроса  

Content-Type: application/json
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Cache-Control: no-cache
Postman-Token: b4a9ec02-fc0f-4497-bd01-86ec2de00267
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

- Тело запроса  

```
{  


}  
```

- Заголовки ответа

Content-Type: application/json; charset=utf-8; v=1.0
Date: Thu, 29 Aug 2023 07:45:29 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0

- Тело ответа  

```
{
    "id": 0,
    "title": null,
    "dueDate": "0001-01-01T00:00:00",
    "completed": false
}  
```

## Authors

Переменные окружения Authors:

| Переменная      | Значение         |
|:-------:|:-----------:|
| id      | 612         |
| idbook  | 111         |
| id_put  | 2           |
| id_del  | 3           |
| id_fail | 20000000000 |
| id_letter | qwe       |

### Позитивные тесты

1. **GET /api/v1/Authors**

- URL  
  {{url}}/api/v1/Authors

- Ожидаемый результат  
  Получение списка авторов  

- Заголовки запроса  

User-Agent: PostmanRuntime/7.32.3  
Cache-Control: no-cache  
Postman-Token: 129cb0e3-6ef2-434a-a2af-ac521f34b14b  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive  

- Заголовки ответа

Content-Type: application/json; charset=utf-8; v=1.0  
Date: Fri, 25 Aug 2023 19:46:53 GMT  
Server: Kestrel  
Transfer-Encoding: chunked  
api-supported-versions: 1.0  

- Тело ответа  

```
[  
    {  
        "id": 1,  
        "idBook": 1,  
        "firstName": "First Name 1",  
        "lastName": "Last Name 1"  
    },  
    {  
        "id": 2,  
        "idBook": 1,  
        "firstName": "First Name 2",  
        "lastName": "Last Name 2"  
    },  
...  
]  
```

2. **POST /api/v1/Authors**

- URL  
  {{url}}/api/v1/Authors

- Ожидаемый результат  
  Добавление нового автора

- Заголовки запроса  

Content-Type: application/json  
User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: b1900d7f-9e7f-417f-93d0-f42bb332e566  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive  

- Тело запроса  

```
{
  "id": {{id}},
  "idBook": {{idbook}},
  "firstName": "Alexandr",
  "lastName": "Pushkin"
}
```

- Заголовки ответа

Content-Type: application/json; charset=utf-8; v=1.0  
Date: Fri, 25 Aug 2023 19:46:54 GMT  
Server: Kestrel  
Transfer-Encoding: chunked  
api-supported-versions: 1.0  

- Тело ответа  

```
{
    "id": 612,
    "idBook": 111,
    "firstName": "Alexandr",
    "lastName": "Pushkin"
}
```

3. **GET ​/api​/v1​/Authors​/authors​/books​/{idBook}**

- URL  
{{url}}/api/v1/Authors/authors/books/{{idbook}}  

- Ожидаемый результат  
  Получение списка авторов по id книги  

- Заголовки запроса  

User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: f3be7714-c775-4144-9dcf-4a85079514b2  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive  

- Заголовки ответа

Content-Type: application/json; charset=utf-8; v=1.0  
Date: Sat, 26 Aug 2023 09:45:50 GMT  
Server: Kestrel  
Transfer-Encoding: chunked  
api-supported-versions: 1.0  

- Тело ответа  

```
[  
    {  
        "id": 337,  
        "idBook": 111,  
        "firstName": "First Name 337",  
        "lastName": "Last Name 337"  
    },  
    {  
        "id": 338,  
        "idBook": 111,  
        "firstName": "First Name 338",  
        "lastName": "Last Name 338"  
    },  
    {  
        "id": 339,  
        "idBook": 111,  
        "firstName": "First Name 339",  
        "lastName": "Last Name 339"  
    }  
]  
```

4. **GET /api/v1/Authors/{id}**

- URL  
{{url}}/api/v1/Authors/{{id_del}}  

- Ожидаемый результат  
  Получение списка авторов по id  

- Заголовки запроса  

User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: 2873a517-3776-45fb-b324-e9de9ee6224c  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive  

- Заголовки ответа

Content-Type: application/json; charset=utf-8; v=1.0  
Date: Sat, 26 Aug 2023 10:03:27 GMT  
Server: Kestrel  
Transfer-Encoding: chunked  
api-supported-versions: 1.0  

- Тело ответа  

```
{  
    "id": 3,  
    "idBook": 1,  
    "firstName": "First Name 3",  
    "lastName": "Last Name 3"  
}  
```

5. **PUT /api/v1/Authors/{id}**

- URL  
  {{url}}/api/v1/Authors/{{id_put}}

- Ожидаемый результат  
  Изменение данных автора по указанному id

- Заголовки запроса  

Content-Type: application/json  
User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: b8242b4d-08cb-42b6-a811-fb9348e9d779  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive  

- Тело запроса  

```
{  
  "id": {{id_put}},  
  "idBook": {{idbook}},  
  "firstName": "Mikhail",  
  "lastName": "Lermontov"  
}  
```

- Заголовки ответа

Content-Type: application/json; charset=utf-8; v=1.0  
Date: Sat, 26 Aug 2023 10:07:54 GMT  
Server: Kestrel  
Transfer-Encoding: chunked  
api-supported-versions: 1.0  

- Тело ответа  

```
{  
    "id": 2,  
    "idBook": 111,  
    "firstName": "Mikhail",  
    "lastName": "Lermontov"  
}  
```

6. **DELETE /api/v1/Authors/{id}**

- URL  
  {{url}}/api/v1/Authors/{{id_del}}  

- Ожидаемый результат  
  Удаление автора по указанному id

- Заголовки запроса  

Accept: */*  
Cache-Control: no-cache  
Postman-Token: f970fdb6-5479-411c-92f6-6188d0b4fc49  

- Заголовки ответа

Content-Length: 0  
Date: Sat, 26 Aug 2023 10:14:56 GMT  
Server: Kestrel  
api-supported-versions: 1.0  

### Негативные тесты

1. **POST /api/v1/Authors /api/v1/Authors - id некорректное число**

- URL  
  {{url}}/api/v1/Authors

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

Content-Type: application/json  
User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: dec02fd1-8940-4060-8c2b-a96650402d17  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive  

- Тело запроса  

```
{  
  "id": {{id_fail}},  
  "idBook": {{idbook}},  
  "firstName": "Alexandr",  
  "lastName": "Pushkin"  
}  
```

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8  
Date: Tue, 29 Aug 2023 10:24:27 GMT  
Server: Kestrel  
Transfer-Encoding: chunked  

- Тело ответа  

```
{  
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",  
    "title": "One or more validation errors occurred.",  
    "status": 400,  
    "traceId": "00-c20f94de38e4c644a615e0934af30d7c-2be5dff6be999c40-00",  
    "errors": {  
        "$.id": [  
            "The JSON value could not be converted to System.Int32. Path: $.id | LineNumber: 1 | BytePositionInLine: 9."  
        ]  
    }  
}  
```

2. **POST /api/v1/Authors /api/v1/Authors - id буквы**

- URL  
  {{url}}/api/v1/Authors

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

Content-Type: application/json  
User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: 8961480c-04b3-4e66-9ee2-7f1d5831c426  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive  

- Тело запроса  

```
{  
  "id": {{id}},  
  "idBook": {{id_letter}},  
  "firstName": "Alexandr",  
  "lastName": "Pushkin"  
}  
```

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8  
Date: Tue, 29 Aug 2023 09:31:11 GMT  
Server: Kestrel  
Transfer-Encoding: chunked  

- Тело ответа  

```
{  
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",  
    "title": "One or more validation errors occurred.",  
    "status": 400,  
    "traceId": "00-c20f94de38e4c644a615e0934af30d7c-2be5dff6be999c40-00",  
    "errors": {  
        "$.id": [  
            "The JSON value could not be converted to System.Int32. Path: $.id | LineNumber: 1 | BytePositionInLine: 9."  
        ]  
    }  
}  
```

3. **POST /api/v1/Authors /api/v1/Authors - id null**

- URL  
  {{url}}/api/v1/Authors

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

Content-Type: application/json  
User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: 3210b27d-9883-4cf2-810c-37a3aab1cefb  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive  

- Тело запроса  

```
{  
  "id": null,  
  "idBook": {{idbook}},  
  "firstName": "Alexandr",  
  "lastName": "Pushkin"  
}   
```

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8  
Date: Tue, 29 Aug 2023 09:33:55 GMT  
Server: Kestrel  
Transfer-Encoding: chunked  

- Тело ответа  

```
{  
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",  
    "title": "One or more validation errors occurred.",  
    "status": 400,  
    "traceId": "00-3ad866e2a816e2478572f1a0aee52876-c432143505ed6440-00",  
    "errors": {  
        "$.id": [  
            "The JSON value could not be converted to System.Int32. Path: $.id | LineNumber: 1 | BytePositionInLine: 12."  
        ]  
    }  
}  
```

4. **POST /api/v1/Authors /api/v1/Authors - пустой JSON файл**

- URL  
  {{url}}/api/v1/Authors

- Ожидаемый результат  
  Добавится новый автор  

- Заголовки запроса  

Content-Type: application/json  
User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: ebe4fdf9-15b4-4c9d-994c-48c44b5c87d2  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive  

- Тело запроса  

```
{  
}   
```

- Заголовки ответа

Content-Type: application/json; charset=utf-8; v=1.0  
Date: Tue, 29 Aug 2023 09:37:42 GMT  
Server: Kestrel  
Transfer-Encoding: chunked  
api-supported-versions: 1.0  

- Тело ответа  

```
{  
    "id": 0,  
    "idBook": 0,  
    "firstName": null,  
    "lastName": null  
}  
```

5. **POST /api/v1/Authors /api/v1/Authors - Content-Type-XML**

- URL  
  {{url}}/api/v1/Authors

- Ожидаемый результат  
  Сервер не сможет принять запрос  

- Заголовки запроса  

Content-Type: application/xml  
User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: 9b308a65-5e87-4f9c-95a2-2202e634482e  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive  

- Тело запроса  

```
{  
  "id": {{id}},  
  "idBook": {{idbook}},  
  "firstName": "Alexandr",  
  "lastName": "Pushkin"  
}  
```

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8  
Date: Tue, 29 Aug 2023 09:46:54 GMT  
Server: Kestrel  
Transfer-Encoding: chunked  

- Тело ответа  

```
{  
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.13",  
    "title": "Unsupported Media Type",  
    "status": 415,  
    "traceId": "00-be3d57c59057f04d8813dcadd92237d1-85d08da7d6a6dc41-00"  
}  
```

6. **POST /api/v1/Authors /api/v1/Authors - Content-Type-Javascript**

- URL  
  {{url}}/api/v1/Authors

- Ожидаемый результат  
  Сервер не сможет принять запрос  

- Заголовки запроса  

Content-Type: application/javascript  
User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: 76632471-afe6-4c21-9114-650ec1b26164  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive  

- Тело запроса  

```
{  
  "id": {{id}},  
  "idBook": {{idbook}},  
  "firstName": "Alexandr",  
  "lastName": "Pushkin"  
}  
```

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8  
Date: Tue, 29 Aug 2023 09:49:56 GMT  
Server: Kestrel  
Transfer-Encoding: chunked  

- Тело ответа  

```
{  
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.13",  
    "title": "Unsupported Media Type",  
    "status": 415,  
    "traceId": "00-bc221ee0e3789e4596a951d860391d0e-1f0aba824aff994f-00"  
}  
```

7. **POST /api/v1/Authors /api/v1/Authors - Отсутсие тела запроса**

- URL  
  {{url}}/api/v1/Authors

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

Content-Type: application/json  
User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: 489ebe97-88f5-44ec-8761-6b08d41f0059  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive  

- Тело запроса  

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8  
Date: Tue, 29 Aug 2023 16:59:13 GMT  
Server: Kestrel  
Transfer-Encoding: chunked  

- Тело ответа  

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",  
    "title": "One or more validation errors occurred.",  
    "status": 400,  
    "traceId": "00-eec8b8638e87c44f80bbe81444e2c5c3-cf7761a24b0c554c-00",  
    "errors": {  
        "": [  
            "A non-empty request body is required."  
        ]  
    }  
}  
```

8. **POST /api/v1/Authors /api/v1/Authors - Некорректный json**

- URL  
  {{url}}/api/v1/Authors

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе 

- Заголовки запроса  

Content-Type: application/json  
User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: 49ac9fb8-690c-4784-a55f-a4cac7187200  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive  

- Тело запроса  

```
{  
  "id"- {{id}},  
  "idBook": {{idbook}},  
  "firstName": "Alexandr",  
  "lastName": "Pushkin"  
}  
```

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8  
Date: Tue, 29 Aug 2023 19:37:00 GMT  
Server: Kestrel  
Transfer-Encoding: chunked  

- Тело ответа  

```
{  
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",  
    "title": "One or more validation errors occurred.",  
    "status": 400,  
    "traceId": "00-43dc82d9fad8cc4b8a427977849666de-37c44ecaca22a84a-00",  
    "errors": {  
        "$": [  
            "'-' is invalid after a property name. Expected a ':'. Path: $ | LineNumber: 1 | BytePositionInLine: 6."  
        ]  
    }  
}  
```

9. **GET ​/api​/v1​/Authors​/authors​/books​/{idBook} id некорректное число**

- URL  
{{url}}/api/v1/Authors/authors/books/{{id_fail}}  

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: d511eb9b-413a-4e8e-9463-b6ac1b43cebc  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive  

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8  
Date: Tue, 29 Aug 2023 09:51:23 GMT  
Server: Kestrel  
Transfer-Encoding: chunked  

- Тело ответа  

```
{  
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",  
    "title": "One or more validation errors occurred.",  
    "status": 400,  
    "traceId": "00-011c37fc37a1304eb0187e43a1bdea8a-f269cb7d63bd2747-00",  
    "errors": {  
        "idBook": [  
            "The value '{{id_fail}}' is not valid."  
        ]  
    }  
}  
```

10. **GET ​/api​/v1​/Authors​/authors​/books​/{idBook} id буквы**

- URL  
{{url}}/api/v1/Authors/authors/books/{{id_letter}}  

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: bbc4c2d2-d4fd-4eff-b8c1-cb9345a1284d  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive  

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8  
Date: Tue, 29 Aug 2023 09:53:28 GMT  
Server: Kestrel  
Transfer-Encoding: chunked  

- Тело ответа  

```
{  
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",  
    "title": "One or more validation errors occurred.",  
    "status": 400,  
    "traceId": "00-eeacd392f6499643bb9e13974202c5ea-c95c4621f02cb44b-00",  
    "errors": {  
        "idBook": [  
            "The value '{{id_letter}}' is not valid."  
        ]  
    }  
}  
```

11. **GET /api/v1/Authors/{id} id некорректное число**

- URL  
{{url}}/api/v1/Authors/{{id_fail}}  

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: f6999428-9b6e-4171-9982-72dc30611b78  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive  

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8  
Date: Tue, 29 Aug 2023 09:55:25 GMT  
Server: Kestrel  
Transfer-Encoding: chunked  

- Тело ответа  

```
{  
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",  
    "title": "One or more validation errors occurred.",  
    "status": 400,  
    "traceId": "00-f47802ede38c934fab4d29542b578edb-2a3d535622848d44-00",  
    "errors": {  
        "id": [  
            "The value '{{id_fail}}' is not valid."  
        ]  
    }  
}  
```

12. **GET /api/v1/Authors/{id} id буквы**

- URL  
{{url}}/api/v1/Authors/{{id_letter}}  

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: ee57b5a8-a5b9-4db3-8eb0-e99ab44fe3b6  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive  

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8  
Date: Tue, 29 Aug 2023 09:57:10 GMT  
Server: Kestrel  
Transfer-Encoding: chunked  

- Тело ответа  

```
{  
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",  
    "title": "One or more validation errors occurred.",  
    "status": 400,  
    "traceId": "00-50aaf5a1abf69f4693a7bcc6d201ea62-bd4d4c44dc68e84a-00",  
    "errors": {  
        "id": [  
            "The value '{{id_letter}}' is not valid."  
        ]  
    }  
}  
```

13. **PUT /api/v1/Authors/{id}  id некорректное число**

- URL  
 {{url}}/api/v1/Authors/{{id_put}}  

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

Content-Type: application/json  
User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: f4757b58-8d9e-4564-85e6-9328b4771829  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive  

- Тело запроса  

```
{  
  "id": {{id_fail}},  
  "idBook": {{idbook}},  
  "firstName": "Mikhail",  
  "lastName": "Lermontov"  
}  
```

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8  
Date: Tue, 29 Aug 2023 10:04:37 GMT  
Server: Kestrel  
Transfer-Encoding: chunked  

- Тело ответа  

```
{  
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",  
    "title": "One or more validation errors occurred.",  
    "status": 400,  
    "traceId": "00-bfd0943bba7dd94fab083323f435f69a-6f73b75d7e15c042-00",  
    "errors": {  
        "id": [  
            "The value '{{id_put}}' is not valid."  
        ],  
        "$.id": [  
            "The JSON value could not be converted to System.Int32. Path: $.id | LineNumber: 1 | BytePositionInLine: 9."  
        ]  
    }  
}   
```

14. **PUT /api/v1/Authors/{id}  id буквы**

- URL  
 {{url}}/api/v1/Authors/{{id_put}}  

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

Content-Type: application/json  
User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: db7538e4-41ee-437a-97fe-28f6dd925fa0  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive  

- Тело запроса  

```
{  
  "id": {{id_letter}},  
  "idBook": {{idbook}},  
  "firstName": "Mikhail",  
  "lastName": "Lermontov"  
}  
```

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8  
Date: Tue, 29 Aug 2023 10:02:15 GMT  
Server: Kestrel  
Transfer-Encoding: chunked  

- Тело ответа  

```
{  
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",  
    "title": "One or more validation errors occurred.",  
    "status": 400,  
    "traceId": "00-b46e5182db90924fb083e2542e2c9f89-a671f0583e2a6c4c-00",  
    "errors": {  
        "$.id": [  
            "'q' is an invalid start of a value. Path: $.id | LineNumber: 1 | BytePositionInLine: 8."  
        ]  
    }  
}  
```

15. **PUT /api/v1/Authors/{id} - id null**

- URL  
 {{url}}/api/v1/Authors/{{id_put}}  

- Ожидаемый результат  
    Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

Content-Type: application/json
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Cache-Control: no-cache
Postman-Token: ba9aac66-f853-49a9-b82f-0fb098fb9ad0
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

- Тело запроса  

```
{  
  "id": null,  
  "idBook": {{idbook}},  
  "firstName": "Mikhail",  
  "lastName": "Lermontov"  
}  
```

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8  
Date: Tue, 29 Aug 2023 10:06:07 GMT  
Server: Kestrel  
Transfer-Encoding: chunked  

- Тело ответа  

```
{  
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",  
    "title": "One or more validation errors occurred.",  
    "status": 400,  
    "traceId": "00-751c9a097daae44e8772a6c7f4d8597d-74cffafb84275d40-00",  
    "errors": {  
        "id": [  
            "The value '{{id_put}}' is not valid."  
        ],  
        "$.id": [  
            "The JSON value could not be converted to System.Int32. Path: $.id | LineNumber: 1 | BytePositionInLine: 12."  
        ]  
    }  
}  
```

16. **PUT /api/v1/Authors/{id} -  пустой JSON файл**

- URL  
 {{url}}/api/v1/Authors/{{id_put}}  

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

Content-Type: application/json  
User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: 1195aa07-aae2-4775-a60e-83aed7ad0131  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive  

- Тело запроса  

```
{  
}   
```

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8  
Date: Tue, 29 Aug 2023 10:11:43 GMT  
Server: Kestrel  
Transfer-Encoding: chunked  

- Тело ответа  

```
{  
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",  
    "title": "One or more validation errors occurred.",  
    "status": 400,  
    "traceId": "00-f85d03e69ca43c49b4ec5a8f01758892-9a3193326cde354e-00",  
    "errors": {  
        "id": [  
            "The value '{{id_put}}' is not valid."  
        ]  
    }  
}  
```

17. **PUT /api/v1/Authors/{id} -  Content-Type-XML**

- URL  
 {{url}}/api/v1/Authors/{{id_put}}  

- Ожидаемый результат  
  Сервер не смог принять запрос  

- Заголовки запроса  

Content-Type: application/xml  
User-Agent: PostmanRuntime/7.32.3
Accept: */*  
Cache-Control: no-cache  
Postman-Token: 61926f49-7f57-4b92-ab8d-2f1f66a9c634  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive  

- Тело запроса  

```
{  
  "id": {{id_put}},  
  "idBook": {{idbook}},  
  "firstName": "Mikhail",  
  "lastName": "Lermontov"  
}    
```

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8  
Date: Tue, 29 Aug 2023 10:13:09 GMT  
Server: Kestrel  
Transfer-Encoding: chunked  

- Тело ответа  

```
{  
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.13",  
    "title": "Unsupported Media Type",  
    "status": 415,  
    "traceId": "00-d4794974b3c2254cb8ba431c45a05e07-259160e20afe244a-00"  
}  
```

18. **PUT /api/v1/Authors/{id} -  Content-Type-Javascript**

- URL  
 {{url}}/api/v1/Authors/{{id_put}}  

- Ожидаемый результат  
  Сервер не смог принять запрос  

- Заголовки запроса  

Content-Type: application/javascript  
User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: 316d0fd5-a897-42c1-b39b-5b4c4791a398  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive  

- Тело запроса  

```
{  
  "id": {{id_put}},  
  "idBook": {{idbook}},  
  "firstName": "Mikhail",  
  "lastName": "Lermontov"  
}    
```

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8  
Date: Tue, 29 Aug 2023 10:15:01 GMT  
Server: Kestrel  
Transfer-Encoding: chunked  

- Тело ответа  

```
{  
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.13",  
    "title": "Unsupported Media Type",  
    "status": 415,  
    "traceId": "00-da67caf9da39de44a6b44d9919b772db-42bf6a2393e05747-00"  
}  
```

19. **PUT /api/v1/Authors/{id} -  Отсутствие тела запроса**

- URL  
 {{url}}/api/v1/Authors/{{id_put}}  

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

Content-Type: application/json  
User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: e783eb52-b99d-4161-a7ef-7cd6cc517d35  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive  

- Тело запроса  

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8  
Date: Tue, 29 Aug 2023 17:04:36 GMT  
Server: Kestrel  
Transfer-Encoding: chunked  

- Тело ответа  

```
{  
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",  
    "title": "One or more validation errors occurred.",  
    "status": 400,  
    "traceId": "00-36b913a429a8a0438f34ae64c3afea62-14db0f7caeec8549-00",  
    "errors": {  
        "": [  
            "A non-empty request body is required."  
        ]  
    }  
}   
```

20.  **PUT /api/v1/Authors/{id} -  Некорректный json**

- URL  
 {{url}}/api/v1/Authors/{{id_put}}  

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

Content-Type: application/json
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Cache-Control: no-cache
Postman-Token: 2701f181-dbf3-48df-ab1b-69594d72d65c
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive  

- Тело запроса  

```
{  
  "id"- {{id_put}},  
  "idBook": {{idbook}},  
  "firstName": "Mikhail",  
  "lastName": "Lermontov"  
}  
```

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8  
Date: Tue, 29 Aug 2023 19:33:21 GMT  
Server: Kestrel  
Transfer-Encoding: chunked  

- Тело ответа  

```
{  
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",  
    "title": "One or more validation errors occurred.",  
    "status": 400,  
    "traceId": "00-fe1a25de66c7a941bd379313e4ae8613-fdefce4e6319504f-00",  
    "errors": {  
        "$": [  
            "'-' is invalid after a property name. Expected a ':'. Path: $ | LineNumber: 1 | BytePositionInLine: 6."  
        ]  
    }  
}   
```

21.  **DELETE /api/v1/Authors/{id} id некорректное число**

- URL  
{{url}}/api/v1/Authors/{{id_fail}}  

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

Accept: */*  
Cache-Control: no-cache  
Postman-Token: 5d2d42a7-e347-4c49-a89f-c5b02969eba0  

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8  
Date: Tue, 29 Aug 2023 10:16:29 GMT  
Server: Kestrel  
Transfer-Encoding: chunked  

22. **DELETE /api/v1/Authors/{id} id буквы**

- URL  
{{url}}/api/v1/Authors/{{id_letter}}  

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

Accept: */*  
Cache-Control: no-cache  
Postman-Token: 04db2c66-5745-4b6c-8fc3-c12ba2fa6465  

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8  
Date: Tue, 29 Aug 2023 10:19:22 GMT  
Server: Kestrel  
Transfer-Encoding: chunked  


**GET/api/v1/Books**

**URL:** https://fakerestapi.azurewebsites.net/api/v1/Books

**Ожидаемый результат:**

- Запрос успешно отправлен на сервер.
- Заголовок запроса содержит правильный метод.
- Статус-код 200.
- Тело ответа представляет собой массив Json.
- Каждое поле JSON объекта соответствует аргументу метода сервиса.
- Тело ответа идемпотентно.

**Заголовки запроса:** 

User-Agent: PostmanRuntime/7.32.3\
Accept: */ *\
Cache-Control: no-cache\
Postman-Token: 9d5a03e3-31bc-4942-804a-f9e0db1fd8c0\
Host: fakerestapi.azurewebsites.net\
Accept-Encoding: gzip, deflate, br\
Connection: keep-alive

**Заголовки ответа:**

Content-Type: application/json; charset=utf-8; v=1.0\
Date: Sat, 26 Aug 2023 09:20:17 GMT\
Server: Kestrel\
Transfer-Encoding: chunked\
api-supported-versions: 1.0

**Тело ответа:** 

```
[
    {
        "id": 1,
        "title": "Book 1",
        "description": "Lorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\n",
        "pageCount": 100,
        "excerpt": "Lorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\n",
        "publishDate": "2023-08-25T09:20:18.1866371+00:00"
    },
    {
        "id": 2,
```

**POST/api/v1/Books**

**URL:** https://fakerestapi.azurewebsites.net/api/v1/Books

**Ожидаемый результат:**

- Запрос успешно отправлен на сервер.
- Заголовок запроса содержит правильный метод.
- Статус-код 200.
- Тело ответа представляет собой Json.
- Каждое поле JSON объекта соответствует аргументу метода сервиса.
- Тело ответа идемпотентно.

**Заголовки запроса:** 

Content-Type: application/json\
User-Agent: PostmanRuntime/7.32.3\
Accept: */ *\
Cache-Control: no-cache\
Postman-Token: 9ab834e1-555e-4e04-975d-0628da711019\
Host: fakerestapi.azurewebsites.net\
Accept-Encoding: gzip, deflate, br\
Connection: keep-alive

**Тело запроса:** 

```
{
    "id": 1,
    "title": "string",
    "description": "string",
    "pageCount": 0,
    "excerpt": "string",
    "publishDate": "2023-08-25T15:48:36.23Z"
}
```

**Заголовки ответа:**

Content-Type: application/problem+json; charset=utf-8\
Date: Sat, 26 Aug 2023 08:58:02 GMT\
Server: Kestrel\
Transfer-Encoding: chunked

**Тело ответа:** 

```
{
    "id": 1,
    "title": "string",
    "description": "string",
    "pageCount": 0,
    "excerpt": "string",
    "publishDate": "2023-08-25T15:48:36.23Z"
}
```

**GET/api/v1/Books/{{bookid}}**

**URL:** https://fakerestapi.azurewebsites.net/api/v1/Books/{{bookid}}

**Ожидаемый результат:**

- Запрос успешно отправлен на сервер.
- Заголовок запроса содержит правильный метод.
- Статус-код 200.
- Тело ответа представляет собой Json.
- Каждое поле JSON объекта соответствует аргументу метода сервиса.
- Тело ответа идемпотентно.

**Заголовки запроса:** 

User-Agent: PostmanRuntime/7.32.3\
Accept: */ *\
Cache-Control: no-cache\
Postman-Token: 288f9277-d377-4a9b-a079-ee55929dc00c\
Host: fakerestapi.azurewebsites.net\
Accept-Encoding: gzip, deflate, br\
Connection: keep-alive

**Заголовки ответа:**

Content-Type: application/problem+json; charset=utf-8; v=1.0\
Date: Sat, 26 Aug 2023 09:18:12 GMT\
Server: Kestrel\
Transfer-Encoding: chunked\
api-supported-versions: 1.0

**Тело ответа:** 

```
{
    "id": 1,
    "title": "Book 1",
    "description": "Lorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\n",
    "pageCount": 100,
    "excerpt": "Lorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\n",
    "publishDate": "2023-08-25T09:50:28.9892674+00:00"
}
```

**PUT/api/v1/Books/{{bookid}}**

**URL:** https://fakerestapi.azurewebsites.net/api/v1/Books/{{bookid}}

**Ожидаемый результат:**

- Запрос успешно отправлен на сервер.
- Заголовок запроса содержит правильный метод.
- Статус-код 200.
- Тело ответа представляет собой Json.
- Каждое поле JSON объекта соответствует аргументу метода сервиса.
- Тело ответа идемпотентно.

**Заголовки запроса:** 

Content-Type: application/json\
User-Agent: PostmanRuntime/7.32.3\
Accept: */ *\
Cache-Control: no-cache\
Postman-Token: b88963d5-ae10-4d6a-a613-239e506aab8a\
Host: fakerestapi.azurewebsites.net\
Accept-Encoding: gzip, deflate, br\
Connection: keep-alive

**Тело запроса:** 

```
{
  "id": 1,
  "title": "ghg",
  "description": "string",
  "pageCount": 0,
  "excerpt": "string",
  "publishDate": "2023-08-25T16:14:23.592Z"
}
```

**Заголовки ответа:**

Content-Type: application/json; charset=utf-8; v=1.0\
Date: Sat, 26 Aug 2023 09:15:05 GMT\
Server: Kestrel\
Transfer-Encoding: chunked\
api-supported-versions: 1.0

**Тело ответа:** 

```
{
  "id": 1,
  "title": "ghg",
  "description": "string",
  "pageCount": 0,
  "excerpt": "string",
  "publishDate": "2023-08-25T16:14:23.592Z"
}
```

**DELETE/api/v1/Books/{{bookid}}**

**URL:** https://fakerestapi.azurewebsites.net/api/v1/Books/{{bookid}}

**Ожидаемый результат:**

- Запрос успешно отправлен на сервер.
- Заголовок запроса содержит правильный метод.
- Статус-код 200.

**Заголовки запроса:** 

User-Agent: PostmanRuntime/7.32.3\
Accept: */ *\
Cache-Control: no-cache\
Postman-Token: 4069c0d4-792f-42e5-8629-d693885e5ec9\
Host: fakerestapi.azurewebsites.net\
Accept-Encoding: gzip, deflate, br\
Connection: keep-alive

**Заголовки ответа:**

Content-Length: 0\
Date: Sat, 26 Aug 2023 09:15:34 GMT\
Server: Kestrel\
api-supported-versions: 1.0

**POST/api/v1/Books**
(некорректный запрос)

**URL:** https://fakerestapi.azurewebsites.net/api/v1/Books

**Ожидаемый результат:**

- Сервер не смог принять запрос.
- Заголовок запроса содержит правильный метод.
- Статус-код 400.
- Тело ответа представляет собой JSON

**Заголовки запроса:** 

Content-Type: application/json\
User-Agent: PostmanRuntime/7.32.3\
Accept: */ *\
Cache-Control: no-cache\
Postman-Token: 9ab834e1-555e-4e04-975d-0628da711019\
Host: fakerestapi.azurewebsites.net\
Accept-Encoding: gzip, deflate, br\
Connection: keep-alive

**Тело запроса:** 

```
{
  "id": a,
  "title": "string",
  "description": "string",
  "pageCount": 0,
  "excerpt": "string",
  "publishDate": "2023-08-26T08:29:14.258Z"
}
```

**Заголовки ответа:**

Content-Type: application/problem+json; charset=utf-8\
Date: Sat, 26 Aug 2023 08:58:02 GMT\
Server: Kestrel\
Transfer-Encoding: chunked

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-d0fcdcb6f97fe64ab198beb6a82ad0e4-db11f0eaaab80343-00",
    "errors": {
        "$.id": [
            "'a' is an invalid start of a value. Path: $.id | LineNumber: 1 | BytePositionInLine: 8."
        ]
    }
}
```

**POST/api/v1/Books**
(пустой json)

**URL:** https://fakerestapi.azurewebsites.net/api/v1/Books

**Ожидаемый результат:**

- Запрос успешно отправлен на сервер.
- Заголовок запроса содержит правильный метод.
- Статус-код 200.
- Тело ответа представляет собой Json.
- Каждое поле JSON объекта соответствует аргументу метода сервиса.

**Заголовки запроса:** 

Content-Type: application/json\
User-Agent: PostmanRuntime/7.32.3\
Accept: */ *\
Cache-Control: no-cache\
Postman-Token: 9ab834e1-555e-4e04-975d-0628da711019\
Host: fakerestapi.azurewebsites.net\
Accept-Encoding: gzip, deflate, br\
Connection: keep-alive

**Тело запроса:** 

```
{
  
}
```

**Заголовки ответа:**

Content-Type: application/problem+json; charset=utf-8\
Date: Sat, 26 Aug 2023 08:58:02 GMT\
Server: Kestrel\
Transfer-Encoding: chunked

**Тело ответа:** 

```
{
    "id": 0,
    "title": null,
    "description": null,
    "pageCount": 0,
    "excerpt": null,
    "publishDate": "0001-01-01T00:00:00"
}
```
**POST/api/v1/Books**
(число вместо строки)

**URL:** https://fakerestapi.azurewebsites.net/api/v1/Books

**Ожидаемый результат:**

- Сервер не смог принять запрос.
- Заголовок запроса содержит правильный метод.
- Статус-код 400.
- Тело ответа представляет собой JSON

**Заголовки запроса:** 

Content-Type: application/json\
User-Agent: PostmanRuntime/7.32.3\
Accept: */ *\
Cache-Control: no-cache\
Postman-Token: 9ab834e1-555e-4e04-975d-0628da711019\
Host: fakerestapi.azurewebsites.net\
Accept-Encoding: gzip, deflate, br\
Connection: keep-alive

**Тело запроса:** 

```
{
  "id": 0,
  "title": 1,
  "description": "string",
  "pageCount": 0,
  "excerpt": "string",
  "publishDate": "2023-08-30T17:45:40.791Z"
}
```

**Заголовки ответа:**

Content-Type: application/problem+json; charset=utf-8\
Date: Sat, 26 Aug 2023 08:58:02 GMT\
Server: Kestrel\
Transfer-Encoding: chunked

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-82f0012ea60127488d598eaef246f741-b4784187efc10040-00",
    "errors": {
        "$.title": [
            "The JSON value could not be converted to System.String. Path: $.title | LineNumber: 2 | BytePositionInLine: 12."
        ]
    }
}
```

**POST/api/v1/Books**
(некорректный json)

**URL:** https://fakerestapi.azurewebsites.net/api/v1/Books

**Ожидаемый результат:**

- Сервер не смог принять запрос.
- Заголовок запроса содержит правильный метод.
- Статус-код 400.
- Тело ответа представляет собой JSON

**Заголовки запроса:** 

Content-Type: application/json\
User-Agent: PostmanRuntime/7.32.3\
Accept: */ *\
Cache-Control: no-cache\
Postman-Token: 9ab834e1-555e-4e04-975d-0628da711019\
Host: fakerestapi.azurewebsites.net\
Accept-Encoding: gzip, deflate, br\
Connection: keep-alive

**Тело запроса:** 

```
{
  id: 0,
  "title": "string",
  "description": "string",
  "pageCount": 0,
  "excerpt": "string",
  "publishDate": "2023-08-30T18:06:17.393Z"
}
```

**Заголовки ответа:**

Content-Type: application/problem+json; charset=utf-8\
Date: Sat, 26 Aug 2023 08:58:02 GMT\
Server: Kestrel\
Transfer-Encoding: chunked

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-a340c1bd6241d44d8828596fc81a4a0f-d5c1030bb1f21f4e-00",
    "errors": {
        "$": [
            "'i' is an invalid start of a property name. Expected a '\"'. Path: $ | LineNumber: 1 | BytePositionInLine: 2."
        ]
    }
}
```

**GET/api/v1/Books/{{bookid}}**
(некорректный запрос)

**URL:** https://fakerestapi.azurewebsites.net/api/v1/Books/{{bookid}}

**Ожидаемый результат:**

- Сервер не смог принять запрос.
- Заголовок запроса содержит правильный метод.
- Статус-код 400.
- Тело ответа представляет собой JSON

**Заголовки запроса:** 

User-Agent: PostmanRuntime/7.32.3\
Accept: */ *\
Cache-Control: no-cache\
Postman-Token: 288f9277-d377-4a9b-a079-ee55929dc00c\
Host: fakerestapi.azurewebsites.net\
Accept-Encoding: gzip, deflate, br\
Connection: keep-alive

**Заголовки ответа:**

Content-Type: application/problem+json; charset=utf-8; v=1.0\
Date: Sat, 26 Aug 2023 09:18:12 GMT\
Server: Kestrel\
Transfer-Encoding: chunked\
api-supported-versions: 1.0

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.4",
    "title": "Not Found",
    "status": 404,
    "traceId": "00-61f0500770ab4e498869d78048eb7dab-bd804dd048a9784b-00"
}
```

**PUT/api/v1/Books/{{bookid}}**
(некорректный запрос)

**URL:** https://fakerestapi.azurewebsites.net/api/v1/Books/{{bookid}}

**Ожидаемый результат:**

- Сервер не смог принять запрос.
- Заголовок запроса содержит правильный метод.
- Статус-код 400.
- Тело ответа представляет собой JSON

**Заголовки запроса:** 

Content-Type: application/json\
User-Agent: PostmanRuntime/7.32.3\
Accept: */ *\
Cache-Control: no-cache\
Postman-Token: b88963d5-ae10-4d6a-a613-239e506aab8a\
Host: fakerestapi.azurewebsites.net\
Accept-Encoding: gzip, deflate, br\
Connection: keep-alive

**Тело запроса:** 

```
{
  "id": 0,
  "title": 
  "description": "string",
  "pageCount": 0,
  "excerpt": "string",
  "publishDate": "2023-08-26T08:49:26.231Z"
}
```

**Заголовки ответа:**

Content-Type: application/json; charset=utf-8; v=1.0\
Date: Sat, 26 Aug 2023 09:15:05 GMT\
Server: Kestrel\
Transfer-Encoding: chunked\
api-supported-versions: 1.0

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-2cb5e4e86de06748a46f544154db65c3-c83dda38bb19f840-00",
    "errors": {
        "$": [
            "':' is invalid after a value. Expected either ',', '}', or ']'. Path: $ | LineNumber: 3 | BytePositionInLine: 15."
        ]
    }
}
```

**PUT/api/v1/Books/{{bookid}}**
(пустой json)

**URL:** https://fakerestapi.azurewebsites.net/api/v1/Books/{{bookid}}

**Ожидаемый результат:**

- Сервер не смог принять запрос.
- Заголовок запроса содержит правильный метод.
- Статус-код 400.
- Тело ответа представляет собой JSON

**Заголовки запроса:** 

Content-Type: application/json\
User-Agent: PostmanRuntime/7.32.3\
Accept: */ *\
Cache-Control: no-cache\
Postman-Token: b88963d5-ae10-4d6a-a613-239e506aab8a\
Host: fakerestapi.azurewebsites.net\
Accept-Encoding: gzip, deflate, br\
Connection: keep-alive

**Тело запроса:** 

```
{
  
}
```

**Заголовки ответа:**

Content-Type: application/json; charset=utf-8; v=1.0\
Date: Sat, 26 Aug 2023 09:15:05 GMT\
Server: Kestrel\
Transfer-Encoding: chunked\
api-supported-versions: 1.0

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-d5efbdc2ce00b842beeb8ba063ce02d8-c64b5fd55008d44d-00",
    "errors": {
        "id": [
            "The value '{{bookid}}' is not valid."
        ]
    }
}
```

**PUT/api/v1/Books/{{bookid}}**
(число вместо строки)

**URL:** https://fakerestapi.azurewebsites.net/api/v1/Books/{{bookid}}

**Ожидаемый результат:**

- Сервер не смог принять запрос.
- Заголовок запроса содержит правильный метод.
- Статус-код 400.
- Тело ответа представляет собой JSON

**Заголовки запроса:** 

Content-Type: application/json\
User-Agent: PostmanRuntime/7.32.3\
Accept: */ *\
Cache-Control: no-cache\
Postman-Token: b88963d5-ae10-4d6a-a613-239e506aab8a\
Host: fakerestapi.azurewebsites.net\
Accept-Encoding: gzip, deflate, br\
Connection: keep-alive

**Тело запроса:** 

```
{
  "id": 0,
  "title": 1,
  "description": "string",
  "pageCount": 0,
  "excerpt": "string",
  "publishDate": "2023-08-30T17:48:13.280Z"
}
```

**Заголовки ответа:**

Content-Type: application/json; charset=utf-8; v=1.0\
Date: Sat, 26 Aug 2023 09:15:05 GMT\
Server: Kestrel\
Transfer-Encoding: chunked\
api-supported-versions: 1.0

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-5630d8bd7c350048b2f86a3b6c70d6b6-dd76c83274d1ac49-00",
    "errors": {
        "id": [
            "The value '{{bookid}}' is not valid."
        ],
        "$.title": [
            "The JSON value could not be converted to System.String. Path: $.title | LineNumber: 2 | BytePositionInLine: 12."
        ]
    }
}
```

**PUT/api/v1/Books/{{bookid}}**
(некорректный json)

**URL:** https://fakerestapi.azurewebsites.net/api/v1/Books/{{bookid}}

**Ожидаемый результат:**

- Сервер не смог принять запрос.
- Заголовок запроса содержит правильный метод.
- Статус-код 400.
- Тело ответа представляет собой JSON

**Заголовки запроса:** 

Content-Type: application/json\
User-Agent: PostmanRuntime/7.32.3\
Accept: */ *\
Cache-Control: no-cache\
Postman-Token: b88963d5-ae10-4d6a-a613-239e506aab8a\
Host: fakerestapi.azurewebsites.net\
Accept-Encoding: gzip, deflate, br\
Connection: keep-alive

**Тело запроса:** 

```
{
  id: 0,
  "title": "string",
  "description": "string",
  "pageCount": 0,
  "excerpt": "string",
  "publishDate": "2023-08-30T18:09:12.344Z"
}
```

**Заголовки ответа:**

Content-Type: application/json; charset=utf-8; v=1.0\
Date: Sat, 26 Aug 2023 09:15:05 GMT\
Server: Kestrel\
Transfer-Encoding: chunked

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-325ec26979f42146b71df171198d4ca1-d5bd2d751839e844-00",
    "errors": {
        "$": [
            "'i' is an invalid start of a property name. Expected a '\"'. Path: $ | LineNumber: 1 | BytePositionInLine: 2."
        ],
        "id": [
            "The value '{{bookid}}' is not valid."
        ]
    }
}
```

## CoverPhotos

Переменные окружения CoverPhotos   
Переменная|Значение
:---|:---
cph_id|10
cph_idbook|15
put_id|20
del_id|25
cph_id_fail|10000000000
cph_id_letter|qwerty

1. **GET /api/v1/CoverPhotos**

- URL  
{{url}}/api/v1/CoverPhotos

- Ожидаемый результат  
  Получение списка обложек книг

- Заголовки запроса  

content-type: application/json    
User-Agent: PostmanRuntime/7.32.3    
Accept: */*    
Cache-Control: no-cache    
Postman-Token: 85625215-bdd5-411f-9e78-23700da23de6    
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive  

- Заголовки ответа

Content-Type: application/json; charset=utf-8; v=1.0  
Date: Wed, 30 Aug 2023 09:58:36 GMT  
Server: Kestrel  
Transfer-Encoding: chunked  
api-supported-versions: 1.0    

- Тело ответа  

```
[
    {
       "id": 1,
        "idBook": 1,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 1&w=250&h=350"
    },
    {
        "id": 2,
        "idBook": 2,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 2&w=250&h=350"
    },
    {
        "id": 3,
        "idBook": 3,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 3&w=250&h=350"
    },
    {
        "id": 4,
        "idBook": 4,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 4&w=250&h=350"
    },
```

2. **POST /api/v1/CoverPhotos**

- URL  
  {{url}}/api/v1/CoverPhotos

- Ожидаемый результат  
  Добавление новой обложки

- Заголовки запроса  

content-type: application/json   
User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: 8f55261d-d256-469b-b0bb-c424e15e12f2  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive    

- Тело запроса  

```
{
  "id": {{cph_id}},
  "idBook": {{cph_idbook}},
  "url": "string"
}
```

- Заголовки ответа

Content-Type: application/json; charset=utf-8; v=1.0  
Date: Wed, 30 Aug 2023 10:00:37 GMT  
Server: Kestrel  
Transfer-Encoding: chunked  
api-supported-versions: 1.0  

- Тело ответа  

```
{
    "id": 10,
    "idBook": 15,
    "url": "string"
}
```

3. **GET ​/api/v1/CoverPhotos/books/covers/{idBook}**

- URL  
{{url}}/api/v1/CoverPhotos/books/covers/{{cph_idbook}}

- Ожидаемый результат  
  Получение списка  обложек по id книги  

- Заголовки запроса  

User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: 8e813734-fc17-4bae-92ed-79c07dd97246  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive  

- Заголовки ответа

Content-Type: application/json; charset=utf-8; v=1.0  
Date: Wed, 30 Aug 2023 10:21:54 GMT  
Server: Kestrel  
Transfer-Encoding: chunked  
api-supported-versions: 1.0  

- Тело ответа  

```
[
    {
        "id": 15,
        "idBook": 15,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 15&w=250&h=350"
    }
]
```

4. **GET /api/v1/CoverPhotos/{id}**

- URL  
{{url}}/api/v1/CoverPhotos/{{cph_id}}

- Ожидаемый результат  
  Получение списка обложек  по id  

- Заголовки запроса  

User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: 1e9e1479-c488-4879-a89a-21ea45e5da4a  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive  

- Заголовки ответа

Content-Type: application/json; charset=utf-8; v=1.0  
Date: Wed, 30 Aug 2023 10:26:45 GMT  
Server: Kestrel  
Transfer-Encoding: chunked  
api-supported-versions: 1.0  

- Тело ответа  

```
{
    "id": 10,
    "idBook": 10,
    "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 10&w=250&h=350"
}  
```

5. **PUT /api/v1/Authors/{id}**

- URL  
 {{url}}/api/v1/CoverPhotos/{{put_id}}

- Ожидаемый результат  
  Изменение обложки по указанному id

- Заголовки запроса  

content-type: application/json  
User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: dd69d9ca-ade2-4036-8d8f-f46db9c7e1d5  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive  

- Тело запроса  

```
{
  "id": {{put_id}},  
  "idBook":{{cph_idbook}},  
  "url": "string"  
}
```

- Заголовки ответа

Content-Type: application/json; charset=utf-8; v=1.0  
Date: Wed, 30 Aug 2023 10:32:30 GMT  
Server: Kestrel  
Transfer-Encoding: chunked  
api-supported-versions: 1.0  

- Тело ответа  

```
{
    "id": 20,
    "idBook": 15,
    "url": "string"
}
```

6. **DELETE /api/v1/CoverPhotos/{id}**

- URL  
{{url}}/api/v1/CoverPhotos/{{del_id}}

- Ожидаемый результат  
  Удаление обложки по указанному id

- Заголовки запроса  

User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: 2f7b2c9c-6597-4061-8b5b-184f5587e3d3  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br 
Connection: keep-alive  

- Заголовки ответа

Content-Length: 0  
Date: Wed, 30 Aug 2023 10:33:28 GMT  
Server: Kestrel  
api-supported-versions: 1.0   

### Негативные тесты

1. **POST/api/v1/CoverPhotos - id некорректное число**

- URL  
 {{url}}/api/v1/CoverPhotos

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

Content-Type: text/plain  
User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: d5d21969-0d16-43ad-918b-8dbdb8688ea1  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive   

- Тело запроса  

```
{
  "id": {{cph_id_fail}},
  "idBook": {{cph_idbook}},
  "url": "string"
}
```

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8  
Date: Wed, 30 Aug 2023 10:54:04 GMT  
Server: Kestrel  
Transfer-Encoding: chunked  

- Тело ответа  

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.13",
    "title": "Unsupported Media Type",
    "status": 415,
    "traceId": "00-be5aa8be07e4b34399c97f32b44a0e53-f0349f4aec86c947-00"
} 
```

2. **POST /api/v1/CoverPhotos  id  буквы**

- URL  
  {{url}}/api/v1/CoverPhotos

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

Content-Type: text/plain  
User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: dba0a56f-8058-41f3-a8f9-3d046515ee41  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive  

- Тело запроса  

```
{
  "id": {{cph_id_letter}},
  "idBook": {{cph_idbook}},
  "url": "string"
}
```

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8  
Date: Wed, 30 Aug 2023 11:00:31 GMT  
Server: Kestrel  
Transfer-Encoding: chunked   

- Тело ответа  

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.13",
    "title": "Unsupported Media Type",
    "status": 415,
    "traceId": "00-6ec788282fba2c49b442d880191c9228-eba9058099b9e347-00"
} 
```

3. **POST /api/v1/CoverPhotos  id  null**

- URL  
  {{url}}/api/v1/CoverPhotos

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

Content-Type: text/plain  
User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: 40220a07-a3e5-40ad-9f4a-71428a40b97e  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive    

- Тело запроса  

```
{
  "id": null,
  "idBook": {{cph_idbook}},
  "url": "string"
}  
```

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8  
Date: Wed, 30 Aug 2023 11:01:59 GMT  
Server: Kestrel  
Transfer-Encoding: chunked  
- Тело ответа    

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.13",
    "title": "Unsupported Media Type",
    "status": 415,
    "traceId": "00-24bbc5351df11748bb2e264d3d5b2762-bcacc9edff2cf64a-00"
}
```

4. **POST /api/v1/CoverPhotos  пустой JSON**

- URL  
 {{url}}/api/v1/CoverPhotos

- Ожидаемый результат  
  Добавится новый автор  

- Заголовки запроса  

Content-Type: text/plain  
User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: 267cc407-cae1-4c55-a1c7-f38c87d7c902  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive  

- Тело запроса  

```
{  
}   
```

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8  
Date: Wed, 30 Aug 2023 11:05:41 GMT  
Server: Kestrel  
Transfer-Encoding: chunked  

- Тело ответа  

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.13",
    "title": "Unsupported Media Type",
    "status": 415,
    "traceId": "00-9dbad55dbfb93a4b9f97bfd1f83c59d0-747e444a68d99b4e-00"
} 
```

5. **POST /api/v1/CoverPhotos- Content-Type-XML**

- URL  
{{url}}/api/v1/CoverPhotos

- Ожидаемый результат  
  Сервер не сможет принять запрос  

- Заголовки запроса  

Content-Type: application/xml  
User-Agent: PostmanRuntime/7.32.3   
Accept: */*  
Cache-Control: no-cache  
Postman-Token: e5d391c4-bb19-4443-9b0f-5741007a19e7  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive    

- Тело запроса  

```
{
  "id": {{cph_id}},
  "idBook": {{cph_idbook}},
  "url": "string"
}
```

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8  
Date: Wed, 30 Aug 2023 11:13:14 GMT  
Server: Kestrel  
Transfer-Encoding: chunked   

- Тело ответа  

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.13",
    "title": "Unsupported Media Type",
    "status": 415,
    "traceId": "00-aee292247ff18f4b91d5b069b926522f-89eef725ed85e445-00"
}  
```

6. **POST /api/v1/CoverPhotos  Content-Type  javascript**

- URL  
 {{url}}/api/v1/CoverPhotos

- Ожидаемый результат  
  Сервер не сможет принять запрос  

- Заголовки запроса  

Content-Type: application/xml  
User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: e5d391c4-bb19-4443-9b0f-5741007a19e7  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive   

- Тело запроса  

```
{
  "id": {{cph_id}},
  "idBook": {{cph_idbook}},
  "url": "string"
}  
```

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8    
Date: Tue, 29 Aug 2023 09:49:56 GMT    
Server: Kestrel    
Transfer-Encoding: chunked   

- Тело ответа  

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.13",
    "title": "Unsupported Media Type",
    "status": 415,
    "traceId": "00-6e0cb5cd2d25cf4fad91a4f40cddbba5-ae378f7e6444bc4f-00"
} 
```

7. **POST /api/v1/CoverPhotos пустое тело запроса**

- URL  
{{url}}/api/v1/CoverPhotos

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

Content-Type: application/json
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Cache-Control: no-cache
Postman-Token: 25329e08-07b0-4709-a2db-e3c7f070d232
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive  

- Тело запроса  

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8
Date: Wed, 30 Aug 2023 11:27:52 GMT
Server: Kestrel
Transfer-Encoding: chunked

- Тело ответа  

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.13",
    "title": "Unsupported Media Type",
    "status": 415,
    "traceId": "00-fff36310e681d040bbf4472b6750f0cd-63dc6a4d0a5b2241-00"
} 
```

8. **POST /api/v1/CoverPhotos  - Некорректный json**

- URL  
  {{url}}/api/v1/CoverPhotos

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе 

- Заголовки запроса  

Content-Type: application/json    
User-Agent: PostmanRuntime/7.32.3    
Accept: */*    
Cache-Control: no-cache    
Postman-Token: fb0fa894-9ffd-4148-8b9d-077941a7bf3b  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive

- Тело запроса  

```
{
  "id":/ {{cph_id}},
  "idBook":/{{cph_idbook}},
  "url":/ "string"
}    
```

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8  
Date: Wed, 30 Aug 2023 11:34:35 GMT  
Server: Kestrel  
Transfer-Encoding: chunked  

- Тело ответа  

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-edde2ca36da3d144876c493fca5a082c-e25fb0ce75c71a4b-00",
    "errors": {
        "$.id": [
            "'/' is invalid after a value. Expected either ',', '}', or ']'. Path: $.id | LineNumber: 1 | BytePositionInLine: 7."
        ]
    }
} 
```

9. **GET /api/v1/CoverPhotos/books/covers/{{cph_idbook}} id некорректное число**

- URL  
{{url}}/api/v1/CoverPhotos/books/covers/{{cph_id_fail}}

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе  

- Заголовки запроса  
 
User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: 3903f309-6c42-4b71-abf6-be83e1b77b24  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive   
  
- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8  
Date: Wed, 30 Aug 2023 11:46:16 GMT  
Server: Kestrel  
Transfer-Encoding: chunked   

- Тело ответа  

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-46f32c47b644f34493b33aff15aea3e8-6a749b7dd73f4444-00",
    "errors": {
        "idBook": [
            "The value '10000000000' is not valid."
        ]
    }
} 
```

10. **GET /api/v1/CoverPhotos/books/covers/{idBook} буквенное id**

- URL  
{{url}}/api/v1/CoverPhotos/books/covers/{{cph_id_letter}} 

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: f3eb914c-8d58-41c9-8bfe-e0aea21d8eeb  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive  

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8  
Date: Wed, 30 Aug 2023 11:51:15 GMT  
Server: Kestrel  
Transfer-Encoding: chunked   

- Тело ответа  

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-2f2b5292feffb54e825aadd6b1d95ca3-6140ab0bf857c948-00",
    "errors": {
        "idBook": [
            "The value 'qwerty' is not valid."
        ]
    }
} 
```

11. **GET api/v1/CoverPhotos/{id} некорректное id**

- URL  
{{url}}/api/v1/CoverPhotos/{{cph_id_fail}}  

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: 6e427286-76f2-4be8-b7f1-060fd8447e9e  
Host: fakerestapi.azurewebsites.net 
Accept-Encoding: gzip, deflate, br     
Connection: keep-alive    

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8  
Date: Wed, 30 Aug 2023 11:54:32 GMT  
Server: Kestrel  
Transfer-Encoding: chunked   

- Тело ответа  

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-f0abeebf3a044647954d94f181f37c64-cc54cd97e010814c-00",
    "errors": {
        "id": [
            "The value '10000000000' is not valid."
        ]
    }
} 
```

12. **GET api/v1/CoverPhotos/{id} буквенное id**

- URL  
{{url}}/api/v1/CoverPhotos/{{cph_id_letter}} 

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: 7bf84787-47c8-42ee-9eb9-7119db7fefd4  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive   

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8  
Date: Wed, 30 Aug 2023 11:56:21 GMT  
Server: Kestrel  
Transfer-Encoding: chunked   

- Тело ответа  

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-483319011df40540bb206215f9f0ee27-4f9ddd98236d624d-00",
    "errors": {
        "id": [
            "The value 'qwerty' is not valid."
        ]
    }
}  
```

13. **api/v1/CoverPhotos/{id} Некорректное число ID**

- URL  
{{url}}/api/v1/CoverPhotos/{{put_id}}

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

content-type: application/json  
User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: e6067fb5-000a-4b6f-82de-9556f29af5a3  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive    

- Тело запроса  

```
{
  "id": {{cph_id_fail}},
  "idBook":{{cph_idbook}},
  "url": "string"
}  
```

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8  
Date: Wed, 30 Aug 2023 12:00:14 GMT  
Server: Kestrel  
Transfer-Encoding: chunked    

- Тело ответа  

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-2ba8ab27f714824fab5d75ef58441477-c0030f08b9addc41-00",
    "errors": {
        "$.id": [
            "The JSON value could not be converted to System.Int32. Path: $.id | LineNumber: 1 | BytePositionInLine: 19."
        ]
    }
}  
```

14. **PUT api/v1/CoverPhotos/{id} буквенный  ID**

- URL  
 {{url}}/api/v1/CoverPhotos/{{cph_id_letter}} 

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

content-type: application/json  
User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: 376e6af8-5855-4591-ab00-08e4b321c3dd  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive   

- Тело запроса  

```
{
  "id": {{cph_id_letter}},
  "idBook":{{cph_idbook}},
  "url": "string"
} 
```

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8  
Date: Wed, 30 Aug 2023 12:02:37 GMT  
Server: Kestrel  
Transfer-Encoding: chunked   

- Тело ответа  

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-e473fdaf0d53d848803ee1e2e44bfb66-cd021f52d1c1894d-00",
    "errors": {
        "id": [
            "The value 'qwerty' is not valid."
        ],
        "$.id": [
            "'q' is an invalid start of a value. Path: $.id | LineNumber: 1 | BytePositionInLine: 8."
        ]
    }
}  
```

15. **PUT /api/v1/CoverPhotos/{id}   ID null**

- URL  
 {{url}}/api/v1/CoverPhotos/{{cph_id_letter}} 

- Ожидаемый результат  
    Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

content-type: application/json   
User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache
Postman-Token: 04857352-0b9e-41dc-840b-616c94aa4d64  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive  

- Тело запроса  

```
{
  "id": null,
  "idBook":{{cph_idbook}},
  "url": "string"
}  
```

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8  
Date: Wed, 30 Aug 2023 12:03:56 GMT  
Server: Kestrel  
Transfer-Encoding: chunked   

- Тело ответа  

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-455c1032a23b0640924b230a5ae4327e-708400b0116f4549-00",
    "errors": {
        "id": [
            "The value 'qwerty' is not valid."
        ],
        "$.id": [
            "The JSON value could not be converted to System.Int32. Path: $.id | LineNumber: 1 | BytePositionInLine: 12."
        ]
    }
}  
```

16. **PUT /api/v1/CoverPhotos/{id}   пустой JSON**

- URL  
 {{url}}/api/v1/CoverPhotos/{{put_id}} 

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

content-type: application/json  
User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: b74f6733-1ac3-4fd5-b9e8-7fabdbed5c55  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive   

- Тело запроса  

```
{
..
}   
```

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8  
Date: Wed, 30 Aug 2023 12:07:17 GMT  
Server: Kestrel  
Transfer-Encoding: chunked  

- Тело ответа  

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-fa3d2bce32992944b1383133e26c7a3a-842f1acce564ab4f-00",
    "errors": {
        "$": [
            "'.' is an invalid start of a property name. Expected a '\"'. Path: $ | LineNumber: 1 | BytePositionInLine: 0."
        ]
    }
}
```

17. **PUT /api/v1/CoverPhotos/{id} Content-Type-XMLL**

- URL  
 {{url}}/api/v1/CoverPhotos/{{put_id}} 

- Ожидаемый результат  
  Сервер не смог принять запрос  

- Заголовки запроса  

content-type: application/xml  
User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: 28b738e1-492b-45c6-9fc8-178cb6c8eaa7  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive   

- Тело запроса  

```
{
  "id": {{put_id}}
  "idBook":{{cph_idbook}},
  "url": "string"
}    
```

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8    
Date: Wed, 30 Aug 2023 12:10:03 GMT    
Server: Kestrel    
Transfer-Encoding: chunked  

- Тело ответа  

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.13",
    "title": "Unsupported Media Type",
    "status": 415,
    "traceId": "00-2701b3389ddb734d889de3eb5fa899c7-e55bc5389e3c8f4e-00"
} 
```

18. **PUT /api/v1/CoverPhotos/{id} Content-Type-javascript**

- URL  
 {{url}}/api/v1/CoverPhotos/{{put_id}}  

- Ожидаемый результат  
  Сервер не смог принять запрос  

- Заголовки запроса  

content-type: application/javascript 
User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: df6c2728-c279-490b-bb5c-4466c9a1846f  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive    

- Тело запроса  

```
{
  "id": {{put_id}}
  "idBook":{{cph_idbook}},
  "url": "string"
}  
```

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8  
Date: Wed, 30 Aug 2023 12:11:42 GMT  
Server: Kestrel  
Transfer-Encoding: chunked  

- Тело ответа  

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.13",
    "title": "Unsupported Media Type",
    "status": 415,
    "traceId": "00-5fdcf3992e14a848852ac775d85eb44b-bcb95bff24578e45-00"
}  
```

19. **PUT /api/v1/CoverPhotos/{id}   пустое тело запроса**

- URL  
{{url}}/api/v1/CoverPhotos/{{put_id}}  

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

content-type: application/json 
User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: 7be95db0-e4cc-40e2-86d6-a53acbbc71f4  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive   

- Тело запроса  

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8  
Date: Wed, 30 Aug 2023 12:14:13 GMT  
Server: Kestrel  
Transfer-Encoding: chunked  

- Тело ответа  

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-554303be6164794c87c5c97a90a96e38-d64ee2d91772c74b-00",
    "errors": {
        "": [
            "A non-empty request body is required."
        ]
    }
}
```

20.  **PUT /api/v1/CoverPhotos/{id}   Некорректный json**

- URL  
{{url}}/api/v1/CoverPhotos/{{put_id}} 

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

content-type: application/json  
User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: cdefe535-0786-42f9-aaa3-a5b4a6ff9dbe  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive   

- Тело запроса  

```
{
  "id":/ {{put_id}}
  "idBook":/{{cph_idbook}},
  "url":/ "string"
}
```

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8  
Date: Wed, 30 Aug 2023 12:16:15 GMT  
Server: Kestrel  
Transfer-Encoding: chunked   

- Тело ответа  

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-5be85cf4843ba34194ba042d6c9a409a-b972a73618a4644a-00",
    "errors": {
        "$.id": [
            "'/' is invalid after a value. Expected either ',', '}', or ']'. Path: $.id | LineNumber: 1 | BytePositionInLine: 7."
        ]
    }
}  
```

21.  **DELETE /api/v1/CoverPhotos/{id} некорректное число ID**

- URL  
{{url}}/api/v1/CoverPhotos/{{cph_id_fail}} 

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: ef1b7978-03a6-4afb-9f8c-c490788bd205  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive  

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8  
Date: Wed, 30 Aug 2023 12:20:23 GMT  
Server: Kestrel  
Transfer-Encoding: chunked  

- Тело ответа
```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-cffed33fd3fc1f44a354bac68d0f7dd0-a0898de78806eb4e-00",
    "errors": {
        "id": [
            "The value '10000000000' is not valid."
        ]
    }
}
```
22. **DELETE /api/v1/CoverPhotos/{id} буквенное ID**

- URL  
{{url}}/api/v1/CoverPhotos/{{cph_id_letter}} 

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: 34bf9e68-aab0-4dc0-9919-d7988e284d15  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br  
Connection: keep-alive   

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8  
Date: Wed, 30 Aug 2023 12:22:18 GMT  
Server: Kestrel  
Transfer-Encoding: chunked   
- Тело ответа
```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-bca7f3bfe0ba444d9009b0dc43e106bc-9b1c6cc0bfbb0040-00",
    "errors": {
        "id": [
            "The value 'qwerty' is not valid."
        ]
    }
}
```
## Users

Переменные окружения Users   
Переменная|Значение
:---|:---
id|7
id_put|2
id_fail|10000000000
id_letter|asd

1. **GET /api/v1/Users**

- URL  
{{url}}/api/v1/Users

- Ожидаемый результат  
  Получение списка пользователей

- Заголовки запроса  

User-Agent: PostmanRuntime/7.32.3
Accept: */*
Cache-Control: no-cache
Postman-Token: cc8dbe11-653e-421f-8533-80aa4eac5595
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive 

- Заголовки ответа

Content-Type: application/json; charset=utf-8; v=1.0
Date: Wed, 30 Aug 2023 15:37:57 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0

- Тело ответа  

```[
    {
        "id": 1,
        "userName": "User 1",
        "password": "Password1"
    },
    {
        "id": 2,
        "userName": "User 2",
        "password": "Password2"
    },
    {
        "id": 3,
        "userName": "User 3",
        "password": "Password3"
    },
    {
        "id": 4,
        "userName": "User 4",
        "password": "Password4"
    },
    {
        "id": 5,
        "userName": "User 5",
        "password": "Password5"
    }
```

2. **POST /api/v1/Users**

- URL  
 {{url}}/api/v1/Users

- Ожидаемый результат  
  Добавление нового пользователя

- Заголовки запроса  

content-type: application/json
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Cache-Control: no-cache
Postman-Token: 98f66a23-9de1-490a-8817-a8b9efeb9b12
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive 

- Тело запроса  

```
{
  "id": {{id}},
  "userName": "Nik",
  "password": "qwe123"
}
```

- Заголовки ответа

Content-Type: application/json; charset=utf-8; v=1.0
Date: Wed, 30 Aug 2023 15:45:49 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0

- Тело ответа  

```
{
    "id": 7,
    "userName": "Nik",
    "password": "qwe123"
}
```

3. **GET /api/v1/Users/{id}**

- URL  
{{url}}/api/v1/Users/{{id}}

- Ожидаемый результат  
  Получение списка  пользователей по id  

- Заголовки запроса  

User-Agent: PostmanRuntime/7.32.3
Accept: */*
Cache-Control: no-cache
Postman-Token: 4a52868d-62e3-447c-8f6c-682618adab3b
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive 

- Заголовки ответа

Content-Type: application/json; charset=utf-8; v=1.0
Date: Wed, 30 Aug 2023 15:48:17 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0

- Тело ответа  

```
[
    {
    "id": 7,
    "userName": "User 7",
    "password": "Password7"
}
]
```

4. **PUT /api/v1/Users/{id}**

- URL  
{{url}}/api/v1/Users/{{id_put}}

- Ожидаемый результат  
  Изменение  пользователей  по id  

- Заголовки запроса  

content-type: application/json
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Cache-Control: no-cache
Postman-Token: 4e299128-6590-4e35-87a5-d7bbbc1053e9
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
- Тело ответа  

```
{
  "id": {{id_put}},
  "userName": "Kate",
  "password": "123"
}
```
- Заголовки ответа

Content-Type: application/json; charset=utf-8; v=1.0
Date: Wed, 30 Aug 2023 15:54:00 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0  

- Тело ответа  

```
{
    "id": 2,
    "userName": "Kate",
    "password": "123"
} 
```

5.  **DELETE /api/v1/Users/{id}**

- URL  
{{url}}/api/v1/Users/{{id}}

- Ожидаемый результат  
  Удаление пользователей по указанному id

- Заголовки запроса  

User-Agent: PostmanRuntime/7.32.3  
Accept: */*  
Cache-Control: no-cache  
Postman-Token: 2f7b2c9c-6597-4061-8b5b-184f5587e3d3  
Host: fakerestapi.azurewebsites.net  
Accept-Encoding: gzip, deflate, br 
Connection: keep-alive  

- Заголовки ответа

Content-Length: 0
Date: Wed, 30 Aug 2023 15:57:40 GMT
Server: Kestrel
api-supported-versions: 1.0  

### Негативные тесты

1. **/api/v1/Users - id некорректное число**

- URL  
 {{url}}/api/v1/Users

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

User-Agent: PostmanRuntime/7.32.3
Accept: */*
Cache-Control: no-cache
Postman-Token: 1b151b77-7c5c-432d-bcdd-dfa4eb804319
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive 

- Тело запроса  

```
{
  "id": {{id_fail}},
  "userName": "Nik",
  "password": "qwe123"
}
```

- Заголовки ответа

Content-Length: 0
Date: Wed, 30 Aug 2023 15:57:40 GMT
Server: Kestrel
api-supported-versions: 1.0

- Тело ответа  

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.13",
    "title": "Unsupported Media Type",
    "status": 415,
    "traceId": "00-be5aa8be07e4b34399c97f32b44a0e53-f0349f4aec86c947-00"
} 
```

2. **POST /api/v1/Users - id буквы**

- URL  
  {{url}}/api/v1/CoverPhotos

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

content-type: application/json
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Cache-Control: no-cache
Postman-Token: 8e8f9eb8-fce3-4e94-9928-69711a6c2af8
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive  

- Тело запроса  

```
{
  "id": {{id_letter}},
  "userName": "Nik",
  "password": "qwe123"
}
```

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8
Date: Wed, 30 Aug 2023 16:31:49 GMT
Server: Kestrel
Transfer-Encoding: chunked  

- Тело ответа  

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-b39f6e426ed5ad4dabe0eaa7071605ee-4526b0a9c538c643-00",
    "errors": {
        "$.id": [
            "'a' is an invalid start of a value. Path: $.id | LineNumber: 1 | BytePositionInLine: 8."
        ]
    }
}
```

3. **POST /api/v1/Users - id null**

- URL  
 {{url}}/api/v1/Users

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

content-type: application/json
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Cache-Control: no-cache
Postman-Token: a127edca-b872-4348-bc1c-2e18b7e0b483
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive  

- Тело запроса  

```
{
  "id": null,
  "userName": "Nik",
  "password": "qwe123"
} 
```

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8
Date: Wed, 30 Aug 2023 16:33:12 GMT
Server: Kestrel
Transfer-Encoding: chunked
- Тело ответа    

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-fd3c6a4b93eaf446a2f29263df2c7e11-0f8555a200a7604a-00",
    "errors": {
        "$.id": [
            "The JSON value could not be converted to System.Int32. Path: $.id | LineNumber: 1 | BytePositionInLine: 12."
        ]
    }
}
```

4. **POST //api/v1/Users - пустой json**

- URL  
 {{url}}/api/v1/Users

- Ожидаемый результат  
  Добавится новый автор  

- Заголовки запроса  

content-type: application/json
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Cache-Control: no-cache
Postman-Token: 5d7e08fb-a3a1-4dfd-ba93-43900626ef81
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive  

- Тело запроса  

```
{  
...
}   
```

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8
Date: Wed, 30 Aug 2023 16:36:13 GMT
Server: Kestrel
Transfer-Encoding: chunked

- Тело ответа  

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-24abe5a804fc8e4388a774389071545f-a22bf8b2a6ff2b48-00",
    "errors": {
        "$": [
            "'.' is an invalid start of a property name. Expected a '\"'. Path: $ | LineNumber: 1 | BytePositionInLine: 3."
        ]
    }
} 
```

5. **POST /api/v1/Users - Content-Type-XML**

- URL  
{{url}}/api/v1/Users

- Ожидаемый результат  
  Сервер не сможет принять запрос  

- Заголовки запроса  

content-type: application/xml
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Cache-Control: no-cache
Postman-Token: 07a54a23-0c65-4ee1-a756-278dcca62e93
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive    

- Тело запроса  

```
{
  "id": {{id}},
  "userName": "Nik",
  "password": "qwe123"
}
```

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8
Date: Wed, 30 Aug 2023 16:39:32 GMT
Server: Kestrel
Transfer-Encoding: chunked

- Тело ответа  

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.13",
    "title": "Unsupported Media Type",
    "status": 415,
    "traceId": "00-21dcca5bff3cae4d8527d0aff5727402-0599d33bef28524a-00"
} 
```

6. **POST /api/v1/Users - отсутствие тела запроса**

- URL  
{{url}}/api/v1/Users

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

content-type: application/json
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Cache-Control: no-cache
Postman-Token: c2b833de-fa6b-4803-9173-1c127fa6551e
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive 

- Тело запроса  

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8
Date: Wed, 30 Aug 2023 16:41:35 GMT
Server: Kestrel
Transfer-Encoding: chunked

- Тело ответа  

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-ce86fe0726330b4daeeedeffe00f26af-21d034f2c28b1f44-00",
    "errors": {
        "": [
            "A non-empty request body is required."
        ]
    }
}
```

7. **POST /api/v1/Users - некорректный json**

- URL  
 {{url}}/api/v1/Users

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе 

- Заголовки запроса  

content-type: application/json
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Cache-Control: no-cache
Postman-Token: 08cb62ad-db52-4ce3-87fa-ced8505e2672
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

- Тело запроса  

```
{
  "id": {{id}},
  "userName"- "Nik",
  "password": "qwe123"
}    
```

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8
Date: Wed, 30 Aug 2023 16:43:48 GMT
Server: Kestrel
Transfer-Encoding: chunked 

- Тело ответа  

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-104cba01f7048742a310d5cf1459d386-f97f113361046c46-00",
    "errors": {
        "$": [
            "'-' is invalid after a property name. Expected a ':'. Path: $ | LineNumber: 2 | BytePositionInLine: 12."
        ]
    }
```
8. **GET /api/v1/Users/{id} - id некорректное число**

- URL  
{{url}}/api/v1/Users/{{id_fail}}  

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

User-Agent: PostmanRuntime/7.32.3
Accept: */*
Cache-Control: no-cache
Postman-Token: 872e25ef-72a0-41ed-85f0-656fdad0a2c6
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive  

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8
Date: Wed, 30 Aug 2023 16:49:11 GMT
Server: Kestrel
Transfer-Encoding: chunked  

- Тело ответа  

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-40d88c4e5d772f49b519ac545bf5b992-5adb5d07fbfdeb47-00",
    "errors": {
        "id": [
            "The value '10000000000' is not valid."
        ]
    }
}
```

9. **GET /api/v1/Users/{id} - id буквы**

- URL  
{{url}}/api/v1/Users/{{id_letter}}

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

User-Agent: PostmanRuntime/7.32.3
Accept: */*
Cache-Control: no-cache
Postman-Token: a7ac35f7-d577-4c43-a6a5-2114048dc2d3
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive  

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8
Date: Wed, 30 Aug 2023 16:52:29 GMT
Server: Kestrel
Transfer-Encoding: chunked  

- Тело ответа  

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-2bc67302bba1204387a842dbe8e7a725-630e958a531f3742-00",
    "errors": {
        "id": [
            "The value 'asd' is not valid."
        ]
    }
}
````
10. **PUT /api/v1/Users/{id} - id некорректное число**

- URL  
{{url}}/api/v1/CoverPhotos/{{put_id}}

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

content-type: application/json
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Cache-Control: no-cache
Postman-Token: a696b606-9ab8-4776-90f6-2109778dbaa5
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive   

- Тело запроса  

```
{
  "id": {{id_fail}},
  "userName": "Kate",
  "password": "123"
}  
```

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8
Date: Wed, 30 Aug 2023 16:55:20 GMT
Server: Kestrel
Transfer-Encoding: chunked   

- Тело ответа  

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-92a179bcd827894f91bb7a5aa44fa843-b2b56406d6af5749-00",
    "errors": {
        "$.id": [
            "The JSON value could not be converted to System.Int32. Path: $.id | LineNumber: 1 | BytePositionInLine: 19."
        ]
    }
} 
```

11. **PUT /api/v1/Users/{id} - id буквы**

- URL  
{{url}}/api/v1/Users/{{id_put}}

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

content-type: application/json
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Cache-Control: no-cache
Postman-Token: a696b606-9ab8-4776-90f6-2109778dbaa5
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive   

- Тело запроса  

```
{
  "id": {{id_letter}},
  "userName": "Kate",
  "password": "123"
}
```

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8
Date: Wed, 30 Aug 2023 16:55:20 GMT
Server: Kestrel
Transfer-Encoding: chunked

- Тело ответа  

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-7371688a23e80046b138f7ff6eecb1e1-b979223dc1772648-00",
    "errors": {
        "$.id": [
            "'a' is an invalid start of a value. Path: $.id | LineNumber: 1 | BytePositionInLine: 8."
        ]
    }
}
```

12. **PUT/api/v1/Users/{id}   ID null**

- URL  
{{url}}/api/v1/Users/{{id_put}}

- Ожидаемый результат  
    Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

content-type: application/json
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Cache-Control: no-cache
Postman-Token: 31d87ff0-3e71-467f-b24d-dde847b78bfd
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive 

- Тело запроса  

```
{
  "id": null,
  "userName": "Kate",
  "password": "123"
}
```

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8
Date: Wed, 30 Aug 2023 16:59:48 GMT
Server: Kestrel
Transfer-Encoding: chunked  

- Тело ответа  

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-cda1a9b56c283f43b02fbde0c91534ec-5dce87c7667f9745-00",
    "errors": {
        "$.id": [
            "The JSON value could not be converted to System.Int32. Path: $.id | LineNumber: 1 | BytePositionInLine: 12."
        ]
    }
}  
```

13. **PUT /api/v1/Users/{id} - пустой json**

- URL  
 {{url}}/api/v1/Users/{{id_put}}

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

content-type: application/json
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Cache-Control: no-cache
Postman-Token: dc0b1844-2bf6-44df-bb8b-a31e52658c43
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive  

- Тело запроса  

```
{

}   
```

- Заголовки ответа

Content-Type: application/json; charset=utf-8; v=1.0
Date: Wed, 30 Aug 2023 17:04:29 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0  

- Тело ответа  

```
{
    "id": 0,
    "userName": null,
    "password": null
}
```

14. **PUT /api/v1/Users/{id} - Content-Type-XML**

- URL  
 {{url}}/api/v1/CoverPhotos/{{put_id}} 

- Ожидаемый результат  
  Сервер не смог принять запрос  

- Заголовки запроса  

content-type: application/xml
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Cache-Control: no-cache
Postman-Token: c95f0c94-25c2-4b21-9236-71ccd42dd02b
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive  

- Тело запроса  

```
{
  "id": {{id}},
  "userName": "Kate",
  "password": "123"
}    
```

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8
Date: Wed, 30 Aug 2023 17:07:33 GMT
Server: Kestrel
Transfer-Encoding: chunked 

- Тело ответа  

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.13",
    "title": "Unsupported Media Type",
    "status": 415,
    "traceId": "00-d3d704798f164a42a9d0bde447211b7d-ac47995f5939e841-00"
}
```

15. **PUT /api/v1/Users/{id} - отсутствие тела запроса**

- URL  
{{url}}/api/v1/Users/{{id_put}} 

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

content-type: application/xml
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Cache-Control: no-cache
Postman-Token: c95f0c94-25c2-4b21-9236-71ccd42dd02b
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

- Тело запроса  

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8
Date: Wed, 30 Aug 2023 17:07:33 GMT
Server: Kestrel
Transfer-Encoding: chunked 

- Тело ответа  

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-7dd50dffdc26b648b63b71ee82f3d9f5-404f692238b0db43-00",
    "errors": {
        "": [
            "A non-empty request body is required."
        ]
    }
}
```

16.  **PUT /api/v1/Users/{id} - некорректный json**

- URL  
{{url}}/api/v1/Users/{{id_put}}

- Ожидаемый результат  
  Сервер сообщает о неккорректном запросе  

- Заголовки запроса  

content-type: application/json
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Cache-Control: no-cache
Postman-Token: fb2ffee8-0168-4a2c-be15-8e0f4eaec236
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive  

- Тело запроса  

```
{
  "id": {{id}},
  "userName"-- "Kate",
  "password": "123"
}
```

- Заголовки ответа

Content-Type: application/problem+json; charset=utf-8
Date: Wed, 30 Aug 2023 17:11:59 GMT
Server: Kestrel
Transfer-Encoding: chunked

- Тело ответа  

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-08e9680058c6b44397f77ba12c93738f-e8248fd7cf93f447-00",
    "errors": {
        "$": [
            "'-' is invalid after a property name. Expected a ':'. Path: $ | LineNumber: 2 | BytePositionInLine: 12."
        ]
    }
}
```


} 
```
