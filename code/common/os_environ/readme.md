### Имитация окружения os.environ

Добавляет в скрытый шаблон ::header os.environ и записывает туда что-то.

Позволяет учащимся тренировать использование переменных окружения os.environ.

Мы можем задать переменную окружения в Python в скрытом шаблоне и затем использовать ее в коде.

Задаем:

``` 
import os
os.environ["IS_DEBUG"] = "True" 
```

Используем:

``` 
if os.environ.get("IS_DEBUG")=="True":
    print("DEBUG MODE IS ON") 
else:
    print("DEBUG MODE IS OFF") 

```

 

​