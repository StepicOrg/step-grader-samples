### Проверка результата работы JSON API PATCH

Этот шаг проверяет json который возвращается роутом .

Чтобы использовать этот тип задания

– cформулируйте инструкцию для пользователя

– оформите тестовые данные: на вход подается адрес, на выход – тело ответа в json.

При необходимости вы сможете отредактировать шаблон, чтобы начать проверять статус-код и заголовки

Стартовый шаблон:

```

@app.route("/")
def api_get_index():  
    return jsonify(message="api works")
        
```

Скрипт проверки:

```
raw_input = input().split(" ", 2)
    method = raw_input[0]
    address = raw_input[1]   
    data = eval(raw_input[2])   

    app.testing = True
    
    if method=="PATCH":
        response = app.test_client().patch(address,json=data)
        data = json.loads(response.data)
   
        print(data) 
```


Стандартный ввод:

```
PATCH /trains/2 {"leaving":"11:50"}
```

Стандартный вывод:

```
{'leaving': '11:50', 'number': '801В', 'title': 'Ласточка', 'txt_from': 'Москва', 'txt_to': 'Санкт-Петербург'}
```