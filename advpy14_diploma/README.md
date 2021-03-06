# Дипломная работа


## VKinder
Все слышали про известное приложение для знакомств - Tinder. Приложение предоставляет простой интерфейс для выбора понравившегося человека. Сейчас в Google Play более 100 миллионов установок.

Используя данные из VK нужно сделать бота как Tinder. Искать людей, подходящих под условия, на основании информации о пользователе из VK:
- диапазон возраста
- пол
- город
- семейное положение


У тех людей, которые подошли по требованиям пользователю, получать топ-3 популярных фотографии с аватара. Популярность определяется по количеству лайков.

Результаты сохраняются в базу данных, состоящая из трех таблиц:
- User - вся информация по пользователю
  - vk_id
  - Имя
  - Фамилия
  - Возраст
  - Диапазон возраста для поиска
  - Пол
  - Город
- DatingUser - Найденные пары для пользователя:
  - vk id
  - Имя
  - Фамилия
  - Возраст
  - foreign_key User, того кто ищет
- Photos - Фотографии найденных пар:
  - ссылка на фотографию
  - количество лайков
  - foreign_key DatingUser, кому принадлежат фотографии
  
![Примерная схема.](https://user-images.githubusercontent.com/12861849/83272909-75388b00-a1d4-11ea-9bc1-b8122f6784bd.png)  
Примерная схема. Таблицы и столбцы могут быть изменены.  

Бот должен предоставлять текстовый интерфейс для работы с пользователем:
- уточняет предпочтения (если надо) и начинается подбор;
- если кто-то понравился - отмечает и человек заносится в БД;
- если нет - пропускает;
- вывод всех понравившихся пар;
- удалить из списка понравившихся пар человека.  

Базовый код для работы с api бота представлен в файле basic_code.py  



## Входные данные
Страница в вк и его группа.

## Выходные данные
Группа с рабочим ботом.

## Требование к сервису:
1. Код программы удовлетворяет PEP8.
2. Получать токен от пользователя с нужными правами.
3. Программа декомпозирована на функции/классы/модули/пакеты.
4. База данных PostgreSQL
5. Люди не должны повторяться при повторном поиске.
6. Реализовать тесты на базовую функциональность.
7. Не запрещается использовать внешние библиотеки для vk.
8. Если используете библиотеки, не забудьте оформить requirements.txt.



## Дополнительные требования (не обязательны для получения диплома):
1. UI интерфейс для работы с ботом.
2. Добавлять человека в черный список чтобы он больше не попадался при поиске, используя БД.
3. Посмотреть черный список.

 
