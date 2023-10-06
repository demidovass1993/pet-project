# Запросы

Это был групповой проект. Моя задача была фиксировать запросы, ответы и тесты к блоку методов Authors <https://fakerestapi.azurewebsites.net/index.html>

Глобальные переменные:  

url https://fakerestapi.azurewebsites.net

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

- Тесты  

```
pm.test("Запрос успешно отправлен на сервер", function () {
    pm.expect(pm.response.code).to.be.oneOf([200]);
});

pm.test("Статус-код 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Тело ответа представляет собой массив Json", function () {
    pm.expect(pm.response.json()).to.be.an('array');
});

pm.test("Каждое поле JSON объекта соответствует заданному типу данных", function () {
    pm.response.json().forEach(function (author) {
        pm.expect(author.id).to.exist.and.to.be.a('number');
        pm.expect(author.idBook).to.exist.and.to.be.a('number');
        pm.expect(author.firstName).to.exist.and.to.be.a('string');
        pm.expect(author.lastName).to.exist.and.to.be.a('string');
    });
});

pm.test("Проверка заголовков ответа", function () {
    pm.expect(pm.response.headers.has('api-supported-versions: 1.0'))
    pm.expect(pm.response.headers.has('content-type: application/json; charset=utf-8; v=1.0 '))
    pm.expect(pm.response.headers.has('server: Kestrel '))
    pm.expect(pm.response.headers.has('transfer-encoding: chunked '))
});

pm.test("Заголовок запроса содержит правильный метод", function () {
    pm.expect(pm.request.method).to.equal("GET");
});

pm.test("Тело ответа идемпотентно", function () {
    var responseBody = pm.response.json();
    pm.expect(responseBody).to.deep.equal(responseBody);
});
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

- Тесты

```
pm.test("Запрос успешно отправлен на сервер", function () {
    pm.expect(pm.response.code).to.be.oneOf([200]);
});

pm.test("Статус-код 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Тело ответа представляет собой JSON", function () {
    pm.response.to.be.json;
});

pm.test("Каждое поле JSON объекта соответствует схеме", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData).to.have.property('id');
    pm.expect(jsonData).to.have.property('idBook');
    pm.expect(jsonData).to.have.property('firstName');
    pm.expect(jsonData).to.have.property('lastName');
});

pm.test("Ответ содержит данные из запроса", () => {
    const responseJson = pm.response.json();
    pm.expect(responseJson.id).to.eql(parseInt(pm.variables.get("id")));
    pm.expect(responseJson.idBook).to.eql(parseInt(pm.variables.get("idbook")));
    pm.expect(responseJson.firstName).to.eql("Alexandr");
    pm.expect(responseJson.lastName).to.eql('Pushkin');
});

pm.test("Проверка заголовков ответа", function () {
    pm.expect(pm.response.headers.has('api-supported-versions: 1.0'))
    pm.expect(pm.response.headers.has('Content-Type: application/json; charset=utf-8; v=1.0 '))
    pm.expect(pm.response.headers.has('Server: Kestrel '))
    pm.expect(pm.response.headers.has('Transfer-Encoding: chunked '))
});

pm.test("Заголовок запроса содержит правильный метод", function () {
    pm.expect(pm.request.method).to.equal("POST");
});
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

- Тесты

```
pm.test("Запрос успешно отправлен на сервер", function () {
    pm.expect(pm.response.code).to.be.oneOf([200]);
});

pm.test("Статус-код 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Тело ответа представляет собой Json", function () {
    pm.expect(pm.response.json()).to.be.an('array');
});

pm.test("Каждое поле JSON объекта соответствует заданному типу данных", function () {
    pm.response.json().forEach(function (author) {
        pm.expect(author.id).to.exist.and.to.be.a('number');
        pm.expect(author.idBook).to.exist.and.to.be.a('number');
        pm.expect(author.firstName).to.exist.and.to.be.a('string');
        pm.expect(author.lastName).to.exist.and.to.be.a('string');
    });
});

pm.test("Проверка заголовков ответа", function () {
    pm.expect(pm.response.headers.has('api-supported-versions: 1.0'))
    pm.expect(pm.response.headers.has('Content-Type: application/json; charset=utf-8; v=1.0 '))
    pm.expect(pm.response.headers.has('Server: Kestrel '))
    pm.expect(pm.response.headers.has('Transfer-Encoding: chunked '))
});

pm.test("Заголовок запроса содержит правильный метод", function () {
    pm.expect(pm.request.method).to.equal("GET");
});
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

- Тесты

```
pm.test("Запрос успешно отправлен на сервер", function () {
    pm.expect(pm.response.code).to.be.oneOf([200]);
});

pm.test("Статус-код 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Тело ответа представляет собой JSON", function () {
    pm.response.to.be.json;
});

pm.test("Каждое поле JSON объекта соответствует схеме", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData).to.have.property('id');
    pm.expect(jsonData).to.have.property('idBook');
    pm.expect(jsonData).to.have.property('firstName');
    pm.expect(jsonData).to.have.property('lastName');
});

pm.test("Проверка заголовков ответа", function () {
    pm.expect(pm.response.headers.has('api-supported-versions: 1.0'))
    pm.expect(pm.response.headers.has('Content-Type: application/json; charset=utf-8; v=1.0 '))
    pm.expect(pm.response.headers.has('Server: Kestrel '))
    pm.expect(pm.response.headers.has('Transfer-Encoding: chunked '))
});

pm.test("Заголовок запроса содержит правильный метод", function () {
    pm.expect(pm.request.method).to.equal("GET");
});
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

- Тесты

```
pm.test("Запрос успешно отправлен на сервер", function () {
    pm.expect(pm.response.code).to.be.oneOf([200]);
});

pm.test("Статус-код 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Тело ответа представляет собой JSON", function () {
    pm.response.to.be.json;
});

pm.test("Каждое поле JSON объекта соответствует схеме", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData).to.have.property('id');
    pm.expect(jsonData).to.have.property('idBook');
    pm.expect(jsonData).to.have.property('firstName');
    pm.expect(jsonData).to.have.property('lastName');
});

pm.test("Ответ содержит данные из запроса", () => {
    const responseJson = pm.response.json();
    pm.expect(responseJson.id).to.eql(parseInt(pm.variables.get("id_put")));
    pm.expect(responseJson.idBook).to.eql(parseInt(pm.variables.get("idbook")));
    pm.expect(responseJson.firstName).to.eql("Mikhail");
    pm.expect(responseJson.lastName).to.eql('Lermontov');
});

pm.test("Проверка заголовков ответа", function () {
    pm.expect(pm.response.headers.has('api-supported-versions: 1.0'))
    pm.expect(pm.response.headers.has('Content-Type: application/json; charset=utf-8; v=1.0 '))
    pm.expect(pm.response.headers.has('Server: Kestrel '))
    pm.expect(pm.response.headers.has('Transfer-Encoding: chunked '))
});

pm.test("Заголовок запроса содержит правильный метод", function () {
    pm.expect(pm.request.method).to.equal("PUT");
});
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

- Тесты 

```
pm.test("Запрос успешно отправлен на сервер", function () {
    pm.expect(pm.response.code).to.be.oneOf([200]);
});

pm.test("Статус-код 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Проверка заголовков ответа", function () {
    pm.expect(pm.response.headers.has('api-supported-versions: 1.0'))
    pm.expect(pm.response.headers.has('Content-Type: application/json; charset=utf-8; v=1.0 '))
    pm.expect(pm.response.headers.has('Server: Kestrel '))
    pm.expect(pm.response.headers.has('Transfer-Encoding: chunked '))
});

pm.test("Заголовок запроса содержит правильный метод", function () {
    pm.expect(pm.request.method).to.equal("DELETE");
});
```


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

- Тесты

```
pm.test("Сервер не смог принять запрос", function () {
    pm.expect(pm.response.code).to.be.oneOf([400]);
});

pm.test("Статус-код 400", function () {
    pm.response.to.have.status(400);
});

pm.test("Тело ответа представляет собой JSON", function () {
    pm.response.to.be.json;
});

pm.test("Проверка заголовков ответа", function () {
    pm.expect(pm.response.headers.has('api-supported-versions: 1.0'))
    pm.expect(pm.response.headers.has('Content-Type: application/json; charset=utf-8; v=1.0 '))
    pm.expect(pm.response.headers.has('Server: Kestrel '))
    pm.expect(pm.response.headers.has('Transfer-Encoding: chunked '))
});

pm.test("Заголовок запроса содержит правильный метод", function () {
    pm.expect(pm.request.method).to.equal("POST");
});
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

- Тесты

```
pm.test("Сервер не смог принять запрос", function () {
    pm.expect(pm.response.code).to.be.oneOf([400]);
});

pm.test("Статус-код 400", function () {
    pm.response.to.have.status(400);
});

pm.test("Тело ответа представляет собой JSON", function () {
    pm.response.to.be.json;
});

pm.test("Проверка заголовков ответа", function () {
    pm.expect(pm.response.headers.has('api-supported-versions: 1.0'))
    pm.expect(pm.response.headers.has('Content-Type: application/json; charset=utf-8; v=1.0 '))
    pm.expect(pm.response.headers.has('Server: Kestrel '))
    pm.expect(pm.response.headers.has('Transfer-Encoding: chunked '))
});

pm.test("Заголовок запроса содержит правильный метод", function () {
    pm.expect(pm.request.method).to.equal("POST");
});
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

- Тесты

```
pm.test("Сервер не смог принять запрос", function () {
    pm.expect(pm.response.code).to.be.oneOf([400]);
});

pm.test("Статус-код 400", function () {
    pm.response.to.have.status(400);
});

pm.test("Тело ответа представляет собой JSON", function () {
    pm.response.to.be.json;
});

pm.test("Проверка заголовков ответа", function () {
    pm.expect(pm.response.headers.has('api-supported-versions: 1.0'))
    pm.expect(pm.response.headers.has('Content-Type: application/json; charset=utf-8; v=1.0 '))
    pm.expect(pm.response.headers.has('Server: Kestrel '))
    pm.expect(pm.response.headers.has('Transfer-Encoding: chunked '))
});

pm.test("Заголовок запроса содержит правильный метод", function () {
    pm.expect(pm.request.method).to.equal("POST");
});
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

- Тесты

```
pm.test("Запрос успешно отправлен на сервер", function () {
    pm.expect(pm.response.code).to.be.oneOf([200]);
});

pm.test("Статус-код 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Тело ответа представляет собой JSON", function () {
    pm.response.to.be.json;
});

pm.test("Проверка заголовков ответа", function () {
    pm.expect(pm.response.headers.has('api-supported-versions: 1.0'))
    pm.expect(pm.response.headers.has('Content-Type: application/json; charset=utf-8; v=1.0 '))
    pm.expect(pm.response.headers.has('Server: Kestrel '))
    pm.expect(pm.response.headers.has('Transfer-Encoding: chunked '))
});

pm.test("Каждое поле JSON объекта соответствует схеме", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData).to.have.property('id');
    pm.expect(jsonData).to.have.property('idBook');
    pm.expect(jsonData).to.have.property('firstName');
    pm.expect(jsonData).to.have.property('lastName');
});

pm.test("Заголовок запроса содержит правильный метод", function () {
    pm.expect(pm.request.method).to.equal("POST");
});
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

- Тесты

```
pm.test("Сервер не смог принять запрос из-за неподдерживаемого типа данных ", function () {
    pm.expect(pm.response.code).to.be.oneOf([415]);
});

pm.test("Статус-код 415", function () {
    pm.response.to.have.status(415);
});

pm.test("Тело ответа представляет собой JSON", function () {
    pm.response.to.be.json;
});

pm.test("Проверка заголовков ответа", function () {
    pm.expect(pm.response.headers.has('api-supported-versions: 1.0'))
    pm.expect(pm.response.headers.has('Content-Type: application/json; charset=utf-8; v=1.0 '))
    pm.expect(pm.response.headers.has('Server: Kestrel '))
    pm.expect(pm.response.headers.has('Transfer-Encoding: chunked '))
});

pm.test("Каждое поле JSON объекта соответствует схеме", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData).to.have.property('id');
    pm.expect(jsonData).to.have.property('idBook');
    pm.expect(jsonData).to.have.property('firstName');
    pm.expect(jsonData).to.have.property('lastName');
});

pm.test("Заголовок запроса содержит правильный метод", function () {
    pm.expect(pm.request.method).to.equal("POST");
});
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

- Тесты

```
pm.test("Сервер не смог принять запрос из-за неподдерживаемого типа данных ", function () {
    pm.expect(pm.response.code).to.be.oneOf([415]);
});

pm.test("Статус-код 415", function () {
    pm.response.to.have.status(415);
});

pm.test("Тело ответа представляет собой JSON", function () {
    pm.response.to.be.json;
});

pm.test("Проверка заголовков ответа", function () {
    pm.expect(pm.response.headers.has('api-supported-versions: 1.0'))
    pm.expect(pm.response.headers.has('Content-Type: application/json; charset=utf-8; v=1.0 '))
    pm.expect(pm.response.headers.has('Server: Kestrel '))
    pm.expect(pm.response.headers.has('Transfer-Encoding: chunked '))
});

pm.test("Каждое поле JSON объекта соответствует схеме", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData).to.have.property('id');
    pm.expect(jsonData).to.have.property('idBook');
    pm.expect(jsonData).to.have.property('firstName');
    pm.expect(jsonData).to.have.property('lastName');
});

pm.test("Заголовок запроса содержит правильный метод", function () {
    pm.expect(pm.request.method).to.equal("POST");
});
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

- Тесты

```
pm.test("Сервер не смог принять запрос", function () {
    pm.expect(pm.response.code).to.be.oneOf([400]);
});

pm.test("Статус-код 400", function () {
    pm.response.to.have.status(400);
});

pm.test("Тело ответа представляет собой JSON", function () {
    pm.response.to.be.json;
});

pm.test("Проверка заголовков ответа", function () {
    pm.expect(pm.response.headers.has('api-supported-versions: 1.0'))
    pm.expect(pm.response.headers.has('Content-Type: application/json; charset=utf-8; v=1.0 '))
    pm.expect(pm.response.headers.has('Server: Kestrel '))
    pm.expect(pm.response.headers.has('Transfer-Encoding: chunked '))
});

pm.test("Заголовок запроса содержит правильный метод", function () {
    pm.expect(pm.request.method).to.equal("POST");
});
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

- Тесты 

```
pm.test("Сервер не смог принять запрос", function () {
    pm.expect(pm.response.code).to.be.oneOf([400]);
});

pm.test("Статус-код 400", function () {
    pm.response.to.have.status(400);
});

pm.test("Тело ответа представляет собой JSON", function () {
    pm.response.to.be.json;
});

pm.test("Проверка заголовков ответа", function () {
    pm.expect(pm.response.headers.has('api-supported-versions: 1.0'))
    pm.expect(pm.response.headers.has('Content-Type: application/json; charset=utf-8; v=1.0 '))
    pm.expect(pm.response.headers.has('Server: Kestrel '))
    pm.expect(pm.response.headers.has('Transfer-Encoding: chunked '))
});

pm.test("Заголовок запроса содержит правильный метод", function () {
    pm.expect(pm.request.method).to.equal("POST");
});
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

- Тесты

```
pm.test("Сервер не смог принять запрос", function () {
    pm.expect(pm.response.code).to.be.oneOf([400]);
});

pm.test("Статус-код 400", function () {
    pm.response.to.have.status(400);
});

pm.test("Тело ответа представляет собой JSON", function () {
    pm.response.to.be.json;
});

pm.test("Проверка заголовков ответа", function () {
    pm.expect(pm.response.headers.has('api-supported-versions: 1.0'))
    pm.expect(pm.response.headers.has('Content-Type: application/json; charset=utf-8; v=1.0 '))
    pm.expect(pm.response.headers.has('Server: Kestrel '))
    pm.expect(pm.response.headers.has('Transfer-Encoding: chunked '))
});

pm.test("Заголовок запроса содержит правильный метод", function () {
    pm.expect(pm.request.method).to.equal("GET");
});
```

10.  **GET ​/api​/v1​/Authors​/authors​/books​/{idBook} id буквы**

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

- Тесты

```
pm.test("Сервер не смог принять запрос", function () {
    pm.expect(pm.response.code).to.be.oneOf([400]);
});

pm.test("Статус-код 400", function () {
    pm.response.to.have.status(400);
});

pm.test("Тело ответа представляет собой JSON", function () {
    pm.response.to.be.json;
});

pm.test("Проверка заголовков ответа", function () {
    pm.expect(pm.response.headers.has('api-supported-versions: 1.0'))
    pm.expect(pm.response.headers.has('Content-Type: application/json; charset=utf-8; v=1.0 '))
    pm.expect(pm.response.headers.has('Server: Kestrel '))
    pm.expect(pm.response.headers.has('Transfer-Encoding: chunked '))
});

pm.test("Заголовок запроса содержит правильный метод", function () {
    pm.expect(pm.request.method).to.equal("GET");
});

```

11.  **GET /api/v1/Authors/{id} id некорректное число**

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

- Тесты

```
pm.test("Сервер не смог принять запрос", function () {
    pm.expect(pm.response.code).to.be.oneOf([400]);
});

pm.test("Статус-код 400", function () {
    pm.response.to.have.status(400);
});

pm.test("Тело ответа представляет собой JSON", function () {
    pm.response.to.be.json;
});


pm.test("Проверка заголовков ответа", function () {
    pm.expect(pm.response.headers.has('api-supported-versions: 1.0'))
    pm.expect(pm.response.headers.has('Content-Type: application/json; charset=utf-8; v=1.0 '))
    pm.expect(pm.response.headers.has('Server: Kestrel '))
    pm.expect(pm.response.headers.has('Transfer-Encoding: chunked '))
});

pm.test("Заголовок запроса содержит правильный метод", function () {
    pm.expect(pm.request.method).to.equal("GET");
});
```

12.  **GET /api/v1/Authors/{id} id буквы**

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

- Тесты

```
pm.test("Сервер не смог принять запрос", function () {
    pm.expect(pm.response.code).to.be.oneOf([400]);
});

pm.test("Статус-код 400", function () {
    pm.response.to.have.status(400);
});

pm.test("Тело ответа представляет собой JSON", function () {
    pm.response.to.be.json;
});


pm.test("Проверка заголовков ответа", function () {
    pm.expect(pm.response.headers.has('api-supported-versions: 1.0'))
    pm.expect(pm.response.headers.has('Content-Type: application/json; charset=utf-8; v=1.0 '))
    pm.expect(pm.response.headers.has('Server: Kestrel '))
    pm.expect(pm.response.headers.has('Transfer-Encoding: chunked '))
});

pm.test("Заголовок запроса содержит правильный метод", function () {
    pm.expect(pm.request.method).to.equal("GET");
});
```

13.  **PUT /api/v1/Authors/{id}  id некорректное число**

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

- Тесты

```
pm.test("Сервер не смог принять запрос", function () {
    pm.expect(pm.response.code).to.be.oneOf([400]);
});

pm.test("Статус-код 400", function () {
    pm.response.to.have.status(400);
});

pm.test("Тело ответа представляет собой JSON", function () {
    pm.response.to.be.json;
});

pm.test("Проверка заголовков ответа", function () {
    pm.expect(pm.response.headers.has('api-supported-versions: 1.0'))
    pm.expect(pm.response.headers.has('Content-Type: application/json; charset=utf-8; v=1.0 '))
    pm.expect(pm.response.headers.has('Server: Kestrel '))
    pm.expect(pm.response.headers.has('Transfer-Encoding: chunked '))
});

pm.test("Заголовок запроса содержит правильный метод", function () {
    pm.expect(pm.request.method).to.equal("PUT");
});
```

14.  **PUT /api/v1/Authors/{id}  id буквы**

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

- Тесты

```
pm.test("Сервер не смог принять запрос", function () {
    pm.expect(pm.response.code).to.be.oneOf([400]);
});

pm.test("Статус-код 400", function () {
    pm.response.to.have.status(400);
});

pm.test("Тело ответа представляет собой JSON", function () {
    pm.response.to.be.json;
});

pm.test("Проверка заголовков ответа", function () {
    pm.expect(pm.response.headers.has('api-supported-versions: 1.0'))
    pm.expect(pm.response.headers.has('Content-Type: application/json; charset=utf-8; v=1.0 '))
    pm.expect(pm.response.headers.has('Server: Kestrel '))
    pm.expect(pm.response.headers.has('Transfer-Encoding: chunked '))
});

pm.test("Заголовок запроса содержит правильный метод", function () {
    pm.expect(pm.request.method).to.equal("PUT");
});
```

15.  **PUT /api/v1/Authors/{id} - id null**

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

- Тесты

```
pm.test("Сервер не смог принять запрос", function () {
    pm.expect(pm.response.code).to.be.oneOf([400]);
});

pm.test("Статус-код 400", function () {
    pm.response.to.have.status(400);
});

pm.test("Тело ответа представляет собой JSON", function () {
    pm.response.to.be.json;
});

pm.test("Проверка заголовков ответа", function () {
    pm.expect(pm.response.headers.has('api-supported-versions: 1.0'))
    pm.expect(pm.response.headers.has('Content-Type: application/json; charset=utf-8; v=1.0 '))
    pm.expect(pm.response.headers.has('Server: Kestrel '))
    pm.expect(pm.response.headers.has('Transfer-Encoding: chunked '))
});

pm.test("Заголовок запроса содержит правильный метод", function () {
    pm.expect(pm.request.method).to.equal("PUT");
});
```

16.  **PUT /api/v1/Authors/{id} -  пустой JSON файл**

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

- Тесты

```
pm.test("Сервер не смог принять запрос", function () {
    pm.expect(pm.response.code).to.be.oneOf([400]);
});

pm.test("Статус-код 400", function () {
    pm.response.to.have.status(400);
});

pm.test("Тело ответа представляет собой JSON", function () {
    pm.response.to.be.json;
});

pm.test("Проверка заголовков ответа", function () {
    pm.expect(pm.response.headers.has('api-supported-versions: 1.0'))
    pm.expect(pm.response.headers.has('Content-Type: application/json; charset=utf-8; v=1.0 '))
    pm.expect(pm.response.headers.has('Server: Kestrel '))
    pm.expect(pm.response.headers.has('Transfer-Encoding: chunked '))
});

pm.test("Заголовок запроса содержит правильный метод", function () {
    pm.expect(pm.request.method).to.equal("PUT");
});
```

17.  **PUT /api/v1/Authors/{id} -  Content-Type-XML**

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

- Тесты

```
pm.test("Сервер не смог принять запрос из-за неподдерживаемого типа данных ", function () {
    pm.expect(pm.response.code).to.be.oneOf([415]);
});

pm.test("Статус-код 415", function () {
    pm.response.to.have.status(415);
});

pm.test("Тело ответа представляет собой JSON", function () {
    pm.response.to.be.json;
});

pm.test("Проверка заголовков ответа", function () {
    pm.expect(pm.response.headers.has('api-supported-versions: 1.0'))
    pm.expect(pm.response.headers.has('Content-Type: application/json; charset=utf-8; v=1.0 '))
    pm.expect(pm.response.headers.has('Server: Kestrel '))
    pm.expect(pm.response.headers.has('Transfer-Encoding: chunked '))
});

pm.test("Заголовок запроса содержит правильный метод", function () {
    pm.expect(pm.request.method).to.equal("PUT");
});
```

18.  **PUT /api/v1/Authors/{id} -  Content-Type-Javascript**

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

- Тесты

```
pm.test("Сервер не смог принять запрос из-за неподдерживаемого типа данных ", function () {
    pm.expect(pm.response.code).to.be.oneOf([415]);
});

pm.test("Статус-код 415", function () {
    pm.response.to.have.status(415);
});

pm.test("Тело ответа представляет собой JSON", function () {
    pm.response.to.be.json;
});

pm.test("Проверка заголовков ответа", function () {
    pm.expect(pm.response.headers.has('api-supported-versions: 1.0'))
    pm.expect(pm.response.headers.has('Content-Type: application/json; charset=utf-8; v=1.0 '))
    pm.expect(pm.response.headers.has('Server: Kestrel '))
    pm.expect(pm.response.headers.has('Transfer-Encoding: chunked '))
});

pm.test("Заголовок запроса содержит правильный метод", function () {
    pm.expect(pm.request.method).to.equal("PUT");
});

```

19.  **PUT /api/v1/Authors/{id} -  Отсутствие тела запроса**

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

- Тесты

```
pm.test("Сервер не смог принять запрос", function () {
    pm.expect(pm.response.code).to.be.oneOf([400]);
});

pm.test("Статус-код 400", function () {
    pm.response.to.have.status(400);
});

pm.test("Тело ответа представляет собой JSON", function () {
    pm.response.to.be.json;
});

pm.test("Проверка заголовков ответа", function () {
    pm.expect(pm.response.headers.has('api-supported-versions: 1.0'))
    pm.expect(pm.response.headers.has('Content-Type: application/json; charset=utf-8; v=1.0 '))
    pm.expect(pm.response.headers.has('Server: Kestrel '))
    pm.expect(pm.response.headers.has('Transfer-Encoding: chunked '))
});

pm.test("Заголовок запроса содержит правильный метод", function () {
    pm.expect(pm.request.method).to.equal("PUT");
});
```

20.   **PUT /api/v1/Authors/{id} -  Некорректный json**

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

- Тесты

```
pm.test("Сервер не смог принять запрос", function () {
    pm.expect(pm.response.code).to.be.oneOf([400]);
});

pm.test("Статус-код 400", function () {
    pm.response.to.have.status(400);
});

pm.test("Тело ответа представляет собой JSON", function () {
    pm.response.to.be.json;
});

pm.test("Проверка заголовков ответа", function () {
    pm.expect(pm.response.headers.has('api-supported-versions: 1.0'))
    pm.expect(pm.response.headers.has('Content-Type: application/json; charset=utf-8; v=1.0 '))
    pm.expect(pm.response.headers.has('Server: Kestrel '))
    pm.expect(pm.response.headers.has('Transfer-Encoding: chunked '))
});

pm.test("Заголовок запроса содержит правильный метод", function () {
    pm.expect(pm.request.method).to.equal("PUT");
});
```

21.   **DELETE /api/v1/Authors/{id} id некорректное число**

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

- Тесты

```
pm.test("Сервер не смог принять запрос", function () {
    pm.expect(pm.response.code).to.be.oneOf([400]);
});

pm.test("Статус-код 400", function () {
    pm.response.to.have.status(400);
});

pm.test("Проверка заголовков ответа", function () {
    pm.expect(pm.response.headers.has('api-supported-versions: 1.0'))
    pm.expect(pm.response.headers.has('Content-Type: application/json; charset=utf-8; v=1.0 '))
    pm.expect(pm.response.headers.has('Server: Kestrel '))
    pm.expect(pm.response.headers.has('Transfer-Encoding: chunked '))
});

pm.test("Заголовок запроса содержит правильный метод", function () {
    pm.expect(pm.request.method).to.equal("DELETE");
});
```

22.  **DELETE /api/v1/Authors/{id} id буквы**

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

- Тесты

```
pm.test("Сервер не смог принять запрос", function () {
    pm.expect(pm.response.code).to.be.oneOf([400]);
});

pm.test("Статус-код 400", function () {
    pm.response.to.have.status(400);
});

pm.test("Проверка заголовков ответа", function () {
    pm.expect(pm.response.headers.has('api-supported-versions: 1.0'))
    pm.expect(pm.response.headers.has('Content-Type: application/json; charset=utf-8; v=1.0 '))
    pm.expect(pm.response.headers.has('Server: Kestrel '))
    pm.expect(pm.response.headers.has('Transfer-Encoding: chunked '))
});

pm.test("Заголовок запроса содержит правильный метод", function () {
    pm.expect(pm.request.method).to.equal("DELETE");
});
```
