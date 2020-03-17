### Проверка SQLAlchemy вместе с Flask

Несколько простых правил для удобной проверки:

1. Используем скулайт в мемори
2. Объявляем модели в скрытом шаблоне
3. Создаем таблицы в скрытом шаблоне
4. Там же добавляем записи и делаем коммит
    
    
    from flask import Flask
    from flask_sqlalchemy import SQLAlchemy
    
    app = Flask(__name__)
    app.config['SQLALCHEMY_DATABASE_URI'] = "sqlite:///:memory:"
    app.config['SQLALCHEMY_TRACK_MODIFICATIONS'] = True
    
    db = SQLAlchemy(app)
    
    class User(db.Model):
        __tablename__ = 'userz'
        uid = db.Column(db.Integer, primary_key=True, autoincrement=True)
        name = db.Column(db.String(50))
        email = db.Column(db.String(50))
    
    db.create_all()
    
    mock_users = []
    
    mock_users.append(User(name="Alex",email="alex@gmail.com"))
    mock_users.append(User(name="Darina",email="darina@gmail.com"))
    mock_users.append(User(name="Prohor",email="prokhor@gmail.com"))
    db.session.add_all(mock_users)
    db.session.commit() 

