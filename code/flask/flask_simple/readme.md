### Простая проверка Flask

Этот шаг проверяет корректность данных, которые отдает роут без параметров.

Для проверки используется 

``` 
with app.app_context():
    
    app.testing = True
    response = app.test_client().get('/')

    data = response.data.decode()
    status_code = response.status_code

    print(data)

```

Чтобы использовать этот шаг

– cформулируйте инструкцию для пользователя

– отредактируйте тестовые данные

– впишите адрес, который должен быть протестирован, в футере