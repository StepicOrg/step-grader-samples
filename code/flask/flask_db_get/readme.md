### Flask – задание на работу с существующей БД

Этот тип задачи принимает на вход id или другое значение и ищет записи среди заранее созданной базы

Проверка работает через имитацию гет-запроса и распечатывание ответа, полученного от представления

Стартовый шаблон:

```

::code

# class Course(db.Model):
#    __tablename__ = "courses"
#    id = db.Column(db.Integer, primary_key=True)
#    name = db.Column(db.String, nullable=False)
#    topic = db.Column(db.String, nullable=False)
#    alumnus = db.Column(db.Integer, nullable=False)
#    rating = db.Column(db.Integer, nullable=False)
    
@app.route("/course/<int:course_id>")
def render_course(course_id):  
    course = db.session.query(Course).get(course_id)
    return course.name


```

Способ проверки:

```

with app.app_context(): 
    
    address = "/course/"+input()
    app.testing = True
    response = app.test_client().get(address)
    data = response.data.decode()       
    print(data)       

```