### Flask – проверка модели

В этом типе задания мы проверяем наличие в модели поля и его типа


Стартовый шаблон:

```

class User(db.Model):

    id = db.Column(db.Integer, primary_key=True)
    name = db.Column(db.String)
    email = db.Column(db.String)

```

Способ проверки:

```
        
from sqlalchemy import inspect
user_inspection = inspect(User)

assert hasattr(user_inspection.columns,"name"), \
    "Отсутствует поле name"
assert str(type(user_inspection.columns.name.type)) == "<class 'sqlalchemy.sql.sqltypes.String'>", \
    "Поле name – не строка"

```