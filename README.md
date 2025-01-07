# Домашнее задание по теме "Модели данных Pydantic"

Цель: научиться описывать и использовать Pydantic модель.

Задача "Модель пользователя":

Подготовка:

Используйте CRUD запросы из предыдущей задачи.

Создайте пустой список users = []

Создайте класс(модель) User, наследованный от BaseModel, который будет содержать следующие поля:
1. id - номер пользователя (int)
2. username - имя пользователя (str)
3. age - возраст пользователя (int)

Измените и дополните ранее описанные 4 CRUD запроса:

get запрос по маршруту '/users' теперь возвращает список users.

post запрос по маршруту '/user/{username}/{age}', теперь:

1. Добавляет в список users объект User.
2. id этого объекта будет на 1 больше, чем у последнего в списке users. Если список users пустой, то 1.
3. Все остальные параметры объекта User - переданные в функцию username и age соответственно.
4. В конце возвращает созданного пользователя.

put запрос по маршруту '/user/{user_id}/{username}/{age}' теперь:

1. Обновляет username и age пользователя, если пользователь с таким user_id есть в списке users и возвращает его.
2. В случае отсутствия пользователя выбрасывается исключение HTTPException с описанием "User was not found" и кодом 404.

delete запрос по маршруту '/user/{user_id}', теперь:

1. Удаляет пользователя, если пользователь с таким user_id есть в списке users и возвращает его.
2. В случае отсутствия пользователя выбрасывается исключение HTTPException с описанием "User was not found" и кодом 404.
Выполните каждый из этих запросов по порядку. Ответы должны совпадать:

1. GET '/users'
[]

2. POST '/user/{username}/{age}' # username - UrbanUser, age - 24

![image](https://github.com/user-attachments/assets/f3150d6c-92b3-4e3b-aa1a-a64c350a9c3b)

3. POST '/user/{username}/{age}' # username - UrbanTest, age - 36

![image](https://github.com/user-attachments/assets/44c4f336-31d0-44a8-bda9-02c222a464fb)

4. POST '/user/{username}/{age}' # username - Admin, age - 42

![image](https://github.com/user-attachments/assets/9576366a-8133-4bc4-af38-8d94533c5c1f)

5. PUT '/user/{user_id}/{username}/{age}' # user_id - 1, username - UrbanProfi, age - 28

![image](https://github.com/user-attachments/assets/30b50e52-509d-4f4d-829e-ba57000d7188)

6. DELETE '/user/{user_id}' # user_id - 2

![image](https://github.com/user-attachments/assets/782768c5-c1b2-45ec-833e-7aae538efa1d)

7. GET '/users'

![image](https://github.com/user-attachments/assets/542eee86-0089-4e2f-b676-b8be6b345aea)

8. DELETE '/user/{user_id}' # user_id - 2

![image](https://github.com/user-attachments/assets/e30b17cb-a95e-41d8-b397-16177c19277c)
