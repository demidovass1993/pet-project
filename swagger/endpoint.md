# Эндпоинты

1. **GET /api/v1/Activities**  
   1. HTTP-метод;  
      GET  
   2. Полный URL запроса:  
      <https://fakerestapi.azurewebsites.net/api/v1/Activities>  
   3. Заголовки запроса:
      "accept: text/json; v=1.0"
   4. Тело запроса (при наличии):
   5. Статус-код ответа:  
      200  
   6. Тело ответа (при наличии):  
[  
  {  
    "id": 1,  
    "title": "Activity 1",  
    "dueDate": "2023-08-16T11:45:43.2292832+00:00",  
    "completed": false  
  },  
  {  
    "id": 2,  
    "title": "Activity 2",  
    "dueDate": "2023-08-16T12:45:43.2292857+00:00",  
    "completed": true  
  },  
  .....  
  ]  

2. **POST ​/api​/v1​/Activities**  
   1. HTTP-метод;  
      POST  
   2. Полный URL запроса:  
      <https://fakerestapi.azurewebsites.net/api/v1/Activities>  
   3. Заголовки запроса:
      "accept: text/plain; v=1.0"  
      "Content-Type: application/json; v=1.0"  
   4. Тело запроса (при наличии):  
{  
  "id": 100,  
  "title": "string",  
  "dueDate": "2023-08-17T15:59:59.505Z",  
  "completed": true  
}  
   5. Статус-код ответа:  
      200  
   6. Тело ответа (при наличии):  
{  
  "id": 100,  
  "title": "string",  
  "dueDate": "2023-08-17T15:59:59.505Z",  
  "completed": true  
}  

3. **POST ​/api​/v1​/Activities**  
   1. HTTP-метод;  
      POST  
   2. Полный URL запроса:  
      <https://fakerestapi.azurewebsites.net/api/v1/Activities>  
   3. Заголовки запроса:
      "accept: text/plain; v=1.0"  
      "Content-Type: application/json; v=1.0"  
   4. Тело запроса (при наличии):  
{  
  "id": qwerty,  
  "title": "string",  
  "dueDate": "2023-08-17T15:59:59.505Z",  
  "completed": true  
}  
   5. Статус-код ответа:  
      400  
   6. Тело ответа (при наличии):  
{  
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",  
  "title": "One or more validation errors occurred.",  
  "status": 400,  
  "traceId": "00-7fc4a3829b85674c98a80c5708eecdc7-b75f3154beb25d43-00",  
  "errors": {  
    "$.id": [  
      "'q' is an invalid start of a value. Path: $.id | LineNumber: 1 | BytePositionInLine: 8."  
    ]  
  }  
}  

4. **GET ​/api​/v1​/Activities​/{id}**  
   1. HTTP-метод;  
      GET  
   2. Полный URL запроса:  
      <https://fakerestapi.azurewebsites.net/api/v1/Activities/12>  
   3. Заголовки запроса:
      "accept: text/plain; v=1.0"  
   4. Тело запроса (при наличии):  
   5. Статус-код ответа:  
      200  
   6. Тело ответа (при наличии):  
{  
  "id": 12,  
  "title": "string",  
  "dueDate": "2023-08-17T16:25:30.205Z",  
  "completed": true  
}  

5. **GET ​/api​/v1​/Activities​/{id}**  
   1. HTTP-метод;  
      GET  
   2. Полный URL запроса:  
      <https://fakerestapi.azurewebsites.net/api/v1/Activities/300>  
   3. Заголовки запроса:
      "accept: text/plain; v=1.0"  
   4. Тело запроса (при наличии):  
   5. Статус-код ответа:  
      404  
   6. Тело ответа (при наличии):  
{  
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.4",  
  "title": "Not Found",  
  "status": 404,  
  "traceId": "00-494a6d047d771646b3e023aab1d3aa86-168784f9f7cd3142-00"  
}  

6. **PUT ​/api​/v1​/Activities​/{id}**  
   1. HTTP-метод;  
      PUT  
   2. Полный URL запроса:  
      <https://fakerestapi.azurewebsites.net/api/v1/Activities/1>  
   3. Заголовки запроса:
      "accept: text/plain; v=1.0"  
      "Content-Type: application/json; v=1.0"  
   4. Тело запроса (при наличии):  
{  
  "id": 0,  
  "title": "string",  
  "dueDate": "2023-08-17T16:33:47.765Z",  
  "completed": true  
}  
   5. Статус-код ответа:  
      200  
   6. Тело ответа (при наличии):  
{  
  "id": 0,  
  "title": "string",  
  "dueDate": "2023-08-17T16:33:47.765Z",  
  "completed": true  
}  

7. **PUT ​/api​/v1​/Activities​/{id}**  
   1. HTTP-метод;  
      PUT  
   2. Полный URL запроса:  
      <https://fakerestapi.azurewebsites.net/api/v1/Activities/1>  
   3. Заголовки запроса:
      "accept: text/plain; v=1.0"  
      "Content-Type: application/json; v=1.0"  
   4. Тело запроса (при наличии):  
{  
  "id": qwerty,  
  "title": "string",  
  "dueDate": "2023-08-17T16:33:47.765Z",  
  "completed": true  
}  
   5. Статус-код ответа:  
      400  
   6. Тело ответа (при наличии):  
{  
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",  
  "title": "One or more validation errors occurred.",  
  "status": 400,  
  "traceId": "00-f89bce2f6696f24cb926d9a5e3f4fbd3-ee67b681f2563f49-00",  
  "errors": {  
    "$.id": [  
      "'q' is an invalid start of a value. Path: $.id | LineNumber: 1 | BytePositionInLine: 8."  
    ]  
  }  
}  

8. **DELETE ​/api​/v1​/Activities​/{id}**  
   1. HTTP-метод;  
      DELETE  
   2. Полный URL запроса:  
      <https://fakerestapi.azurewebsites.net/api/v1/Activities/1>  
   3. Заголовки запроса:
      "accept: */*"  
   4. Тело запроса (при наличии):  
   5. Статус-код ответа:  
      200  
   6. Тело ответа (при наличии):  

9. **GET ​/api​/v1​/Authors**  
   1. HTTP-метод;  
      GET  
   2. Полный URL запроса:  
      <https://fakerestapi.azurewebsites.net/api/v1/Authors>  
   3. Заголовки запроса:
      "accept: text/plain; v=1.0"  
   4. Тело запроса (при наличии):  
   5. Статус-код ответа:  
      200  
   6. Тело ответа (при наличии):  
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
 .....  
  ]  

10. **POST ​/api​/v1​/Authors**  
    1. HTTP-метод;  
       POST  
    2. Полный URL запроса:  
       <https://fakerestapi.azurewebsites.net/api/v1/Authors>  
    3. Заголовки запроса:
       "accept: text/plain; v=1.0"  
       "Content-Type: application/json; v=1.0"  
    4. Тело запроса (при наличии):  
{  
  "id": 10,  
  "idBook": 0,  
  "firstName": "string",  
  "lastName": "string"  
}
    5. Статус-код ответа:  
       200  
    6. Тело ответа (при наличии):  
{  
  "id": 10,  
  "idBook": 0,  
  "firstName": "string",  
  "lastName": "string"  
}  

11. **POST ​/api​/v1​/Authors**  
    1. HTTP-метод;  
       POST  
    2. Полный URL запроса:  
       <https://fakerestapi.azurewebsites.net/api/v1/Authors>  
    3. Заголовки запроса:
       "accept: text/plain; v=1.0"  
       "Content-Type: application/json; v=1.0"  
    4. Тело запроса (при наличии):  
{  
  "id": 100000000000,  
  "idBook": 0,  
  "firstName": "string",  
  "lastName": "string"  
}  
    5. Статус-код ответа:  
       400  
    6. Тело ответа (при наличии):  
{  
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",  
  "title": "One or more validation errors occurred.",  
  "status": 400,  
  "traceId": "00-1033dfc55dc6e0428a507e9c8933c9da-9ca722794d8b584d-00",  
  "errors": {  
    "$.id": [  
      "The JSON value could not be converted to System.Int32. Path: $.id | LineNumber: 0 | BytePositionInLine: 18."  
    ]  
  }  
}  

12. **GET ​/api​/v1​/Authors​/authors​/books​/{idBook}**  
    1. HTTP-метод;  
       GET  
    2. Полный URL запроса:  
       <https://fakerestapi.azurewebsites.net/api/v1/Authors/authors/books/12>  
    3. Заголовки запроса:
       "accept: text/plain; v=1.0"  
    4. Тело запроса (при наличии):  
    5. Статус-код ответа:  
       200  
    6. Тело ответа (при наличии):  
[  
  {  
    "id": 32,  
    "idBook": 12,  
    "firstName": "First Name 32",  
    "lastName": "Last Name 32"  
  },  
  {  
    "id": 33,  
    "idBook": 12,  
    "firstName": "First Name 33",  
    "lastName": "Last Name 33"  
  },  
  {  
    "id": 34,  
    "idBook": 12,  
    "firstName": "First Name 34",  
    "lastName": "Last Name 34"  
  }  
]  

13. **GET ​/api​/v1​/Authors​/authors​/books​/{idBook}**  
    1. HTTP-метод;  
       GET  
    2. Полный URL запроса:  
       <https://fakerestapi.azurewebsites.net/api/v1/Authors/authors/books/120000000000>  
    3. Заголовки запроса:
       "accept: text/plain; v=1.0"  
    4. Тело запроса (при наличии):  
    5. Статус-код ответа:  
       400  
    6. Тело ответа (при наличии):  
{  
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",  
  "title": "One or more validation errors occurred.",  
  "status": 400,  
  "traceId": "00-e90640d9047fdd46a14a4b26582cd697-34ea173c5609fc41-00",  
  "errors": {  
    "idBook": [  
      "The value '120000000000' is not valid."  
    ]  
  }  
}  

14. **GET ​/api​/v1​/Authors​/{id}**  
    1. HTTP-метод;  
       GET  
    2. Полный URL запроса:  
       <https://fakerestapi.azurewebsites.net/api/v1/Authors/15>  
    3. Заголовки запроса:
       "accept: text/plain; v=1.0"  
    4. Тело запроса (при наличии):  
    5. Статус-код ответа:  
       200  
    6. Тело ответа (при наличии):  
{  
  "id": 15,  
  "idBook": 6,  
  "firstName": "First Name 15",  
  "lastName": "Last Name 15"  
}  

15. **GET ​/api​/v1​/Authors​/{id}**  
    1. HTTP-метод;  
       GET  
    2. Полный URL запроса:  
       <https://fakerestapi.azurewebsites.net/api/v1/Authors/150000>  
    3. Заголовки запроса:
       "accept: text/plain; v=1.0"  
    4. Тело запроса (при наличии):  
    5. Статус-код ответа:  
       404  
    6. Тело ответа (при наличии):  
{  
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.4",  
  "title": "Not Found",  
  "status": 404,  
  "traceId": "00-f60d8f64e3353a45bf0db3ba5fdd1db8-7f20f99a15a8284c-00"  
}  

16. **PUT ​/api​/v1​/Authors​/{id}**  
    1. HTTP-метод;  
       PUT  
    2. Полный URL запроса:  
       <https://fakerestapi.azurewebsites.net/api/v1/Authors/1>  
    3. Заголовки запроса:
       "accept: text/plain; v=1.0"  
       "Content-Type: application/json; v=1.0"  
    4. Тело запроса (при наличии):  
{  
  "id": 0,  
  "idBook": 0,  
  "firstName": "string",  
  "lastName": "string"  
}  
    5. Статус-код ответа:  
       200  
    6. Тело ответа (при наличии):  
{  
  "id": 0,  
  "idBook": 0,  
  "firstName": "string",  
  "lastName": "string"  
}  

17. **PUT ​/api​/v1​/Authors​/{id}**  
    1. HTTP-метод;  
       PUT  
    2. Полный URL запроса:  
       <https://fakerestapi.azurewebsites.net/api/v1/Authors/1>  
    3. Заголовки запроса:
       "accept: text/plain; v=1.0"  
       "Content-Type: application/json; v=1.0"  
    4. Тело запроса (при наличии):  
{  
  "id": qwerty,  
  "idBook": 0,  
  "firstName": "string",  
  "lastName": "string"  
}  
    5. Статус-код ответа:  
       400  
    6. Тело ответа (при наличии):  
{  
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",  
  "title": "One or more validation errors occurred.",  
  "status": 400,  
  "traceId": "00-512336c2a351a747b357aa0efc5ce097-794a9cdabf72444a-00",  
  "errors": {  
    "$.id": [  
      "'q' is an invalid start of a value. Path: $.id | LineNumber: 1 | BytePositionInLine: 8."  
    ]  
  }  
}  

18. **DELETE /api/v1/Authors/{id}**  
    1. HTTP-метод;  
       DELETE  
    2. Полный URL запроса:  
      <https://fakerestapi.azurewebsites.net/api/v1/Authors/12>  
    3. Заголовки запроса:  
      "accept: */*"  
    4. Тело запроса (при наличии):  
    5. Статус-код ответа:  
       200  
    6. Тело ответа (при наличии):  

19. **GET /api/v1/Books**  
    1. HTTP-метод;  
       GET  
    2. Полный URL запроса:  
      <https://fakerestapi.azurewebsites.net/api/v1/Books>  
    3. Заголовки запроса:  
      "accept: text/plain; v=1.0"  
    4. Тело запроса (при наличии):  
    5. Статус-код ответа:  
       200  
    6. Тело ответа (при наличии):  
[  
  {  
    "id": 1,  
    "title": "Book 1",  
    "description": "Lorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\n",  
    "pageCount": 100,  
    "excerpt": "Lorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem   lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\n",  
    "publishDate": "2023-08-16T18:40:41.3734723+00:00"  
  },  
  {  
    "id": 2,  
    "title": "Book 2",  
    "description": "Lorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\n",  
    "pageCount": 200,  
    "excerpt": "Lorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem   lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\n",  
    "publishDate": "2023-08-15T18:40:41.373489+00:00"  
  },  
   .....  
  ]  

20. **POST /api/v1/Books**  
    1. HTTP-метод;  
       POST  
    2. Полный URL запроса:  
       <https://fakerestapi.azurewebsites.net/api/v1/Books>  
    3. Заголовки запроса:  
       "accept: */*"  
       "Content-Type: application/json; v=1.0"  
    4. Тело запроса (при наличии):  
{  
  "id": 10,  
  "title": "string",  
  "description": "string",  
  "pageCount": 0,  
  "excerpt": "string",  
  "publishDate": "2023-08-17T18:43:30.993Z"  
}  
    5. Статус-код ответа:  
       200  
    6. Тело ответа (при наличии):  
{  
  "id": 10,  
  "title": "string",  
  "description": "string",  
  "pageCount": 0,  
  "excerpt": "string",  
  "publishDate": "2023-08-17T18:43:30.993Z"  
}  

21. **POST /api/v1/Books**  
    1. HTTP-метод;  
       POST  
    2. Полный URL запроса:  
       <https://fakerestapi.azurewebsites.net/api/v1/Books>  
    3. Заголовки запроса:  
       "accept: */*"  
       "Content-Type: application/json; v=1.0"  
    4. Тело запроса (при наличии):  
{  
  "id": qwerty,  
  "title": "string",  
  "description": "string",  
  "pageCount": 0,  
  "excerpt": "string",  
  "publishDate": "2023-08-17T18:43:30.993Z"  
}  
    5. Статус-код ответа:  
       400  
    6. Тело ответа (при наличии):  
{  
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",  
  "title": "One or more validation errors occurred.",  
  "status": 400,  
  "traceId": "00-b522458cce4e1a4586972c55433cee94-65d33c4c28508c49-00",  
  "errors": {  
    "$.id": [  
      "'q' is an invalid start of a value. Path: $.id | LineNumber: 1 | BytePositionInLine: 8."  
    ]  
  }  
}  

22. **GET /api/v1/Books/{id}**  
    1. HTTP-метод;  
       GET  
    2. Полный URL запроса:  
       <https://fakerestapi.azurewebsites.net/api/v1/Books/1>  
    3. Заголовки запроса:  
       "accept: text/plain; v=1.0"  
    4. Тело запроса (при наличии):  
    5. Статус-код ответа:  
       200  
    6. Тело ответа (при наличии):  
{  
  "id": 1,  
  "title": "Book 1",  
  "description": "Lorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\n",  
  "pageCount": 100,  
  "excerpt": "Lorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\n",  
  "publishDate": "2023-08-16T19:32:08.6467222+00:00"  
}  

23. **GET /api/v1/Books/{id}**  
    1. HTTP-метод;  
       GET  
    2. Полный URL запроса:  
       <https://fakerestapi.azurewebsites.net/api/v1/Books/45555>  
    3. Заголовки запроса:  
       "accept: text/plain; v=1.0"  
    4. Тело запроса (при наличии):  
    5. Статус-код ответа:  
       404  
    6. Тело ответа (при наличии):  
{  
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.4",  
  "title": "Not Found",  
  "status": 404,  
  "traceId": "00-5157940fabcdab458300b6537ac55ca8-8e00f0e2ff6e2d42-00"  
}  

24. **PUT /api/v1/Books/{id}**  
    1. HTTP-метод;  
       PUT  
    2. Полный URL запроса:  
       <https://fakerestapi.azurewebsites.net/api/v1/Books/123>  
    3. Заголовки запроса:  
       "accept: */*"  
       "Content-Type: application/json; v=1.0"  
    4. Тело запроса (при наличии):  
    {  
  "id": 0,  
  "title": "string",  
  "description": "string",  
  "pageCount": 0,  
  "excerpt": "string",  
  "publishDate": "2023-08-17T19:35:57.205Z"  
}  
    5. Статус-код ответа:  
       200  
    6. Тело ответа (при наличии):  
{  
  "id": 0,  
  "title": "string",  
  "description": "string",  
  "pageCount": 0,  
  "excerpt": "string",  
  "publishDate": "2023-08-17T19:35:57.205Z"  
}  

25. **PUT /api/v1/Books/{id}**  
    1. HTTP-метод;  
       PUT  
    2. Полный URL запроса:  
       <https://fakerestapi.azurewebsites.net/api/v1/Books/123000000000>  
    3. Заголовки запроса:  
       "accept: */*"  
       "Content-Type: application/json; v=1.0"  
    4. Тело запроса (при наличии):  
 {  
  "id": 0,  
  "title": "string",  
  "description": "string",  
  "pageCount": 0,  
  "excerpt": "string",  
  "publishDate": "2023-08-17T19:40:30.773Z"  
}  
    5. Статус-код ответа:  
       400  
    6. Тело ответа (при наличии):  
{  
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",  
  "title": "One or more validation errors occurred.",  
  "status": 400,  
  "traceId": "00-c6de9bd20586584aa656beb675022922-e92b21cef689a449-00",  
  "errors": {  
    "id": [  
      "The value '123000000000' is not valid."  
    ]  
  }  
}  

26. **DELETE /api/v1/Books/{id}**  
    1. HTTP-метод;  
       DELETE  
    2. Полный URL запроса:  
       <https://fakerestapi.azurewebsites.net/api/v1/Books/123>  
    3. Заголовки запроса:  
       "accept: */*"  
    4. Тело запроса (при наличии):  
    5. Статус-код ответа:  
       200  
    6. Тело ответа (при наличии):  

27. **GET /api/v1/CoverPhotos**  
    1. HTTP-метод;  
       GET  
    2. Полный URL запроса:  
       <https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos>  
    3. Заголовки запроса:  
       "accept: text/plain; v=1.0"  
    4. Тело запроса (при наличии):  
    5. Статус-код ответа:  
       200  
    6. Тело ответа (при наличии):  
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
   .....  
  ]  

28. **POST ​/api​/v1​/CoverPhotos**  
    1. HTTP-метод;  
       POST  
    2. Полный URL запроса:  
       <https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos>  
    3. Заголовки запроса:  
       "accept: text/plain; v=1.0"  
       "Content-Type: application/json; v=1.0"  
    4. Тело запроса (при наличии):  
{  
  "id": 10,  
  "idBook": 0,  
  "url": "string"  
}  
    5. Статус-код ответа:  
       200  
    6. Тело ответа (при наличии):  
{  
  "id": 10,  
  "idBook": 0,  
  "url": "string"  
}  

29. **POST ​/api​/v1​/CoverPhotos**  
    1. HTTP-метод;  
       POST  
    2. Полный URL запроса:  
       <https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos>  
    3. Заголовки запроса:  
       "accept: text/plain; v=1.0"  
       "Content-Type: application/json; v=1.0"  
    4. Тело запроса (при наличии):  
{  
  "id": ===,  
  "idBook": 0,  
  "url": "string"  
}  
    5. Статус-код ответа:  
       400  
    6. Тело ответа (при наличии):  
{  
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",  
  "title": "One or more validation errors occurred.",  
  "status": 400,  
  "traceId": "00-17923228152016488867547e22d87214-05da143327a1644d-00",  
  "errors": {  
    "$.id": [  
      "'=' is an invalid start of a value. Path: $.id | LineNumber: 1 | BytePositionInLine: 8."  
    ]  
  }  
}  

30. **GET /api/v1/CoverPhotos/books/covers/{idBook}**  
    1. HTTP-метод;  
       GET  
    2. Полный URL запроса:  
       <https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos/books/covers/123>  
    3. Заголовки запроса:  
       "accept: text/plain; v=1.0"  
    4. Тело запроса (при наличии):  
    5. Статус-код ответа:  
       200  
    6. Тело ответа (при наличии):  
[  
  {  
    "id": 123,  
    "idBook": 123,  
    "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 123&w=250&h=350"  
  }  
]  

31. **GET /api/v1/CoverPhotos/books/covers/{idBook}**  
    1. HTTP-метод;  
       GET  
    2. Полный URL запроса:  
       <https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos/books/covers/1000000000000>  
    3. Заголовки запроса:  
       "accept: text/plain; v=1.0"  
    4. Тело запроса (при наличии):  
    5. Статус-код ответа:  
       400  
    6. Тело ответа (при наличии):  
{  
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",  
  "title": "One or more validation errors occurred.",  
  "status": 400,  
  "traceId": "00-db6f40c5f75757429b7abe077bd6c081-2a756deaa4004542-00",  
  "errors": {  
    "idBook": [  
      "The value '1000000000000' is not valid."  
    ]  
  }  
}  

32. **GET /api/v1/CoverPhotos/{id}**  
    1. HTTP-метод;  
       GET  
    2. Полный URL запроса:  
       <https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos/123>  
    3. Заголовки запроса:  
       "accept: text/plain; v=1.0"  
    4. Тело запроса (при наличии):  
    5. Статус-код ответа:  
       200  
    6. Тело ответа (при наличии):  
{  
  "id": 123,  
  "idBook": 123,  
  "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 123&w=250&h=350"  
}  

33. **GET /api/v1/CoverPhotos/{id}**  
    1. HTTP-метод;  
       GET  
    2. Полный URL запроса:  
       <https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos/111111111111>  
    3. Заголовки запроса:  
       "accept: text/plain; v=1.0"  
    4. Тело запроса (при наличии):  
    5. Статус-код ответа:  
       400  
    6. Тело ответа (при наличии):  
{  
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",  
  "title": "One or more validation errors occurred.",  
  "status": 400,  
  "traceId": "00-b23232a294f76f4c9853347144ffc6b9-e52906d886870b43-00",  
  "errors": {  
    "id": [  
      "The value '111111111111' is not valid."  
    ]  
  }  
}  

34. **PUT /api/v1/CoverPhotos/{id}**  
    1. HTTP-метод;  
       PUT  
    2. Полный URL запроса:  
       <https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos/1>  
    3. Заголовки запроса:  
       "accept: text/plain; v=1.0"  
       "Content-Type: application/json; v=1.0"  
    4. Тело запроса (при наличии):  
{  
  "id": 0,  
  "idBook": 0,  
  "url": "string"  
}  
    5.Статус-код ответа:  
      200  
    6.Тело ответа (при наличии):  
{  
  "id": 0,  
  "idBook": 0,  
  "url": "string"  
}  

35. **PUT /api/v1/CoverPhotos/{id}**  
    1. HTTP-метод;  
       PUT  
    2. Полный URL запроса:  
       <https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos/1>  
    3. Заголовки запроса:  
       "accept: text/plain; v=1.0"  
       "Content-Type: application/json; v=1.0"  
    4. Тело запроса (при наличии):  
{  
  "id": ===,  
  "idBook": 0,  
  "url": "string"  
}  
    5. Статус-код ответа:  
       400  
    6. Тело ответа (при наличии):  
{  
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",  
  "title": "One or more validation errors occurred.",  
  "status": 400,  
  "traceId": "00-17528681e4da3847ad9dc83d24d3000a-3f778eb154ed5c44-00",  
  "errors": {  
    "$.id": [  
      "'=' is an invalid start of a value. Path: $.id | LineNumber: 1 | BytePositionInLine: 8."  
    ]  
  }  
}  

36. **DELETE /api/v1/CoverPhotos/{id}**  
    1. HTTP-метод;  
       DELETE  
    2. Полный URL запроса:  
       <https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos/12>  
    3. Заголовки запроса:  
       "accept: */*"  
    4. Тело запроса (при наличии):  
    5. Статус-код ответа:  
       200  
    6. Тело ответа (при наличии):  

37. **GET /api/v1/Users**  
    1. HTTP-метод;  
      GET  
    2. Полный URL запроса:  
      <https://fakerestapi.azurewebsites.net/api/v1/Users>  
    3. Заголовки запроса:
       "accept: text/plain; v=1.0"  
    4. Тело запроса (при наличии):
    5. Статус-код ответа:  
       200  
    6. Тело ответа (при наличии):  
 [  
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
  .....  
  ]  

38. **POST /api/v1/Users**  
    1. HTTP-метод;  
       POST  
    2. Полный URL запроса:  
       <https://fakerestapi.azurewebsites.net/api/v1/Users>  
    3. Заголовки запроса:
       "accept: */*"  
       "Content-Type: application/json; v=1.0"  
    4. Тело запроса (при наличии):  
{  
  "id": 100,  
  "userName": "string",  
  "password": "string"  
}  
    5. Статус-код ответа:  
       200  
    6. Тело ответа (при наличии):  
{  
  "id": 100,  
  "userName": "string",  
  "password": "string"  
}  

39. **POST /api/v1/Users**  
    1. HTTP-метод;  
       POST  
    2. Полный URL запроса:  
      <https://fakerestapi.azurewebsites.net/api/v1/Users>  
    3. Заголовки запроса:
       "accept: */*"  
       "Content-Type: application/json; v=1.0"  
    4. Тело запроса (при наличии):  
{  
  "id": qwerty,  
  "userName": "string",  
  "password": "string"  
}  
    5. Статус-код ответа:  
       400  
    6. Тело ответа (при наличии):  
{  
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",  
  "title": "One or more validation errors occurred.",  
  "status": 400,  
  "traceId": "00-96c0dba0e0d25a4caffa0e2576aecdb1-afe745cfeb29c644-00",  
  "errors": {  
    "$.id": [  
      "'q' is an invalid start of a value. Path: $.id | LineNumber: 1 | BytePositionInLine: 8."  
    ]  
  }  
}  

40. **GET /api/v1/Users/{id}**  
    1. HTTP-метод;  
       GET  
    2. Полный URL запроса:  
       <https://fakerestapi.azurewebsites.net/api/v1/Users/5>  
    3. Заголовки запроса:
       "accept: */*"  
    4. Тело запроса (при наличии):  
    5. Статус-код ответа:  
       200  
    6. Тело ответа (при наличии):  
{  
  "id": 5,  
  "userName": "User 5",  
  "password": "Password5"  
}  

41. **GET /api/v1/Users/{id}**  
    1. HTTP-метод;  
       GET  
    2. Полный URL запроса:  
      <https://fakerestapi.azurewebsites.net/api/v1/Users/12>  
    3. Заголовки запроса:
       "accept: */*"  
    4. Тело запроса (при наличии):  
    5. Статус-код ответа:  
       404  
    6. Тело ответа (при наличии):  
{  
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.4",  
  "title": "Not Found",  
  "status": 404,  
  "traceId": "00-8cb7eb9ee4e2a541b10bccb2938289e4-803c5b9a8c47d948-00"  
}  

42. **PUT /api/v1/Users/{id}**  
    1. HTTP-метод;  
       PUT  
    2. Полный URL запроса:  
       <https://fakerestapi.azurewebsites.net/api/v1/Users/5>  
    3. Заголовки запроса:
       "accept: */*"  
       "Content-Type: application/json; v=1.0"  
    4. Тело запроса (при наличии):  
{  
  "id": 0,  
  "userName": "string",  
  "password": "string"  
}  
    5. Статус-код ответа:  
       200
    6. Тело ответа (при наличии):  
{  
  "id": 0,  
  "userName": "string",  
  "password": "string"  
}  

43. **PUT /api/v1/Users/{id}**  
    1. HTTP-метод;  
       PUT  
    2. Полный URL запроса:  
       <https://fakerestapi.azurewebsites.net/api/v1/Users/5>  
    3. Заголовки запроса:
       "accept: */*"  
       "Content-Type: application/json; v=1.0"  
    4. Тело запроса (при наличии):  
{  
  "id": ===,  
  "userName": "string",  
  "password": "string"  
}  
    5. Статус-код ответа:  
       400  
    6. Тело ответа (при наличии):  
{  
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",  
  "title": "One or more validation errors occurred.",  
  "status": 400,  
  "traceId": "00-a74d4c51601fd74daeb86dc4e92fcec9-dbe9e3be1f832d43-00",  
  "errors": {  
    "$.id": [  
      "'=' is an invalid start of a value. Path: $.id | LineNumber: 1 | BytePositionInLine: 8."  
    ]  
  }  
}  

44. **DELETE /api/v1/Users/{id}**  
    1. HTTP-метод;  
       DELETE  
    2. Полный URL запроса:  
       <https://fakerestapi.azurewebsites.net/api/v1/Users/5>  
    3. Заголовки запроса:
       "accept: */*"  
    4. Тело запроса (при наличии):  
    5. Статус-код ответа:  
       200  
    6. Тело ответа (при наличии):  
