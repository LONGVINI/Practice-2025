# Практика 20225
# Куліковський Денис IПЗ-4.01

## Завдання
1. Розробка тестового білду мобільної гри-симулятора ферми "Fogwood" з елементами економічної стратегії
2. Створення базової архітектури проєкту на Unity
3. Імплементація системи взаємодії користувача з ігровими об'єктами
4. Розробка авторизації користувачів на базі Google Play
5. Підключення веб-сокета для швидкої синхронізації даних між клієнтом і сервером

## Виконані завдання

Під час практики було виконано низку ключових задач, що дозволили створити фундамент для подальшої розробки гри-симулятора ферми "Fogwood":

### Розробка ігрової локації та тестових об'єктів

На рисунку 1 зображено початкову зону з декількома тестовими об'єктами:
- домівка: представляє собою об'єкт типу Building та включає у себе можливість переносу по полю;
- слайми: поодинокі вороги, з якими потрібно буде битися, об'єкти типу Enemy;
- скрині: об'єкти Treasure (скарбів), з яких випадає деякий безкоштовний лут;
- бочка: об'єкт Decoration (декоративний);
- трава: об'єкт Destroyable (з можливістю руйнування), для знищення використовує енергію та видає лут.

<p align="center">
    <img src="Screenshots/1.jpg" alt="Початкова сцена гри">
</p>
<p align="center">
    Початкова сцена гри
</p>

### Реалізація системи взаємодії з ігровими об'єктами

Було розроблено комплексну систему взаємодії з різними типами об'єктів:

1. **Взаємодія з Building об'єктом**:
   - при натисканні 1 раз виконується метод OneClick (реалізація інтерфейсу IOneClick);
   - при затисканні кнопки на більше 1 секунди, якщо поле isMoveable має значення «True», тоді стан гри зміниться на Moveable та з'являться кнопки «Rotate», «Install» і «Cancel».

<p align="center">
    <img src="Screenshots/2.jpg" alt="Переміщення об'єкта типу Building">
</p>
<p align="center">
    Переміщення об'єкта типу Building
</p>

2. **Взаємодія з Enemy об'єктом**:
   - при натисканні на enemy один раз буде показано його характеристики (заплановано, але не реалізовано у тестовому білді).

3. **Взаємодія з Treasure об'єктом**:
   - при натисканні з нього в залежності від шансу вдачі випадає декілька різних об'єктів, а сам об'єкт зникає.

<p align="center">
    <img src="Screenshots/3.jpg" alt="Скриня зникла з ігрового поля">
</p>
<p align="center">
    Скриня зникла з ігрового поля
</p>

<p align="center">
    <img src="Screenshots/4.jpg" alt="Отримання нагороди зі скрині">
</p>
<p align="center">
    Отримання нагороди зі скрині
</p>

4. **Взаємодія з Decoration об'єктом**:
   - при затисканні кнопки на більше 1 секунди вмикається стан Moveable, як у попередньому типі, але додатково з'являється кнопка «Storage» (перенесення на склад).

<p align="center">
    <img src="Screenshots/5.jpg" alt="Переміщення декоративного об'єкту">
</p>
<p align="center">
    Переміщення декоративного об'єкту
</p>

5. **Взаємодія з Destroyable об'єктом**:
   - при натисканні з'являється повідомлення з описом предмета та необхідною кількістю енергії для знищення;
   - при подвійному натисканні на об'єкт заплановано, що він зникає та випадає дроп (не реалізовано у тестовому білді).

<p align="center">
    <img src="Screenshots/6.jpg" alt="Повідомлення з описом Destroyable об'єкта">
</p>
<p align="center">
    Повідомлення з описом Destroyable об'єкта
</p>

### Тестування на мобільних пристроях

Було проведено тестування гри за допомогою інструменту Unity Remote, що дозволило налагодити взаємодію з грою безпосередньо на мобільному пристрої:

<p align="center">
    <img src="Screenshots/7.jpg" alt="Тестування на мобільному пристрої з використанням Unity Remote">
</p>
<p align="center">
    Тестування на мобільному пристрої з використанням Unity Remote
</p>

<p align="center">
    <img src="Screenshots/8.jpg" alt="Вигляд інтерфейсу гри на мобільному пристрої">
</p>
<p align="center">
    Вигляд інтерфейсу гри на мобільному пристрої
</p>

### Розробка авторизації та мережевих компонентів

Було успішно реалізовано авторизацію на базі Google Play для забезпечення надійного входу в гру та збереження прогресу гравців. Також налаштовано веб-сокет комунікацію для оперативної передачі даних між клієнтською частиною гри та сервером, що дозволяє синхронізувати ігровий прогрес у режимі реального часу.

Ці компоненти закладають основу для подальшої розробки багатокористувацьких функцій гри та забезпечують надійне зберігання прогресу гравців.
