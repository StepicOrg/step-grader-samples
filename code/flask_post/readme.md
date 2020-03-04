###Flask – route post checker

Этот шаг проверяет прием формы, отправляя пост запрос.

Чтобы использовать этот тип задания

– cформулируйте инструкцию для пользователя

– оформите тестовые данные: задание отправляет словарь, который был передан со стандартного ввода

– измените путь до роута,  если это необходимо

При необходимости вы сможете отредактировать шаблон, чтобы начать проверять статус-код и заголовки

Стартовый шаблон:

```

@app.route("/send/", methods=["POST"])
def render_send():  
    login = request.form.get("login")
    password = request.form.get("password")
    return f"Имя: {login} Пароль: {password}" 

```

Способ проверки:

```

with app.app_context(): 
    
    data = eval(input())
    address = "/send/"
    
    app.testing = True
    response = app.test_client().post(address,data=data)
    data = response.data.decode()       

    print(data) 

```