### Мягкая проверка html-кода

В html-шаблонах, чтобы не подгонять пробелы, переносы строк и большие буквы каждый раз, мы можем привести и решение и образец к порезанному виду

При таком подходе строки "\<h2\> Результат \</h2\>" и "\<h2>Результат\</h2\>"  будут считаться одинаковыми.

Скопируйте во вкладку "Расширенный редактор"

def generate():
    return []

def tidy_up(code):
    clean_code = code.replace(" ","").replace("\n","").replace("\r","").lower()
    return clean_code

def check(reply, clue):
    return tidy_up(reply) == tidy_up(clue)