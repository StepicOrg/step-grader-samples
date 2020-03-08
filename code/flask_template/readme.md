Все содержимое поля ввода записывается в файл шаблона index.html а затем  файл обрабатывается с помощью render_templates. 

В качестве параметров обрабатывается словарь из input() пропущенный через enum

Для проверки используется 

``` 

with open('index.html', 'w') as fd:
    fd.write(template) 

with app.app_context():
    kwargs = eval(input())
    output = render_template("index.html",**kwargs)
    print(output)

```