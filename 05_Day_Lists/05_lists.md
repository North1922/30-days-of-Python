<div align="center">
  <h1> 30 Дней Python: День 5 - Списки</h1>
  <a class="header-badge" target="_blank" href="https://www.linkedin.com/in/asabeneh/">
  <img src="https://img.shields.io/badge/style--5eba00.svg?label=LinkedIn&logo=linkedin&style=social">
  </a>
  <a class="header-badge" target="_blank" href="https://twitter.com/Asabeneh">
  <img alt="Подписка на Twitter" src="https://img.shields.io/twitter/follow/asabeneh?style=social">
  </a>

<sub>Автор:
<a href="https://www.linkedin.com/in/asabeneh/" target="_blank">Асабенех Йетаех</a><br>
<small> Второе издание: Июль - 2021</small>
</sub>

</div>

[<< День 4](../04_Day_Strings/04_strings.md) | [День 6 >>](../06_Day_Tuples/06_tuples.md)

![30DaysOfPython](../images/30DaysOfPython_banner3@2x.png)

# День 5

## Списки

В Python есть четыре типа данных для хранения коллекций:

- **Список (List)**: упорядоченная и изменяемая коллекция, разрешает дублирующие элементы.
- **Кортеж (Tuple)**: упорядоченная и неизменяемая коллекция, разрешает дублирующие элементы.
- **Множество (Set)**: неупорядоченная, неиндексируемая и изменяемая коллекция, не разрешает дублирующие элементы.
- **Словарь (Dictionary)**: неупорядоченная, изменяемая и индексируемая коллекция, не разрешает дублирующие элементы.

Список — это коллекция различных типов данных, которая является упорядоченной и изменяемой. Список может быть пустым или может содержать различные типы данных.

### Создание списка

Создать список в Python можно двумя способами:

- Используя встроенную функцию list:

```py
# синтаксис
lst = list()
```

```py
empty_list = list() # это пустой список, элементов нет
print(len(empty_list)) # 0
```

- Используя квадратные скобки:

```py
# синтаксис
lst = []
```

```py
empty_list = [] # это пустой список, элементов нет
print(len(empty_list)) # 0
```

Список с начальными значениями. Используем _len()_, чтобы найти длину списка.

```py
fruits = ['banana', 'orange', 'mango', 'lemon']                     # список фруктов
vegetables = ['Tomato', 'Potato', 'Cabbage','Onion', 'Carrot']      # список овощей
animal_products = ['milk', 'meat', 'butter', 'yoghurt']             # список продуктов животноводства
web_techs = ['HTML', 'CSS', 'JS', 'React','Redux', 'Node', 'MongDB'] # список веб-технологий
countries = ['Finland', 'Estonia', 'Denmark', 'Sweden', 'Norway']

# Печатаем списки и их длину
print('Fruits:', fruits)
print('Number of fruits:', len(fruits))
print('Vegetables:', vegetables)
print('Number of vegetables:', len(vegetables))
print('Animal products:',animal_products)
print('Number of animal products:', len(animal_products))
print('Web technologies:', web_techs)
print('Number of web technologies:', len(web_techs))
print('Countries:', countries)
print('Number of countries:', len(countries))
```

- Списки могут содержать элементы различных типов данных:

```py
lst = ['Asabeneh', 250, True, {'country':'Finland', 'city':'Helsinki'}] # список содержит различ

ные типы данных
```

### Доступ к элементам списка с помощью положительной индексации

Мы обращаемся к каждому элементу списка по его индексу. Индексация списка начинается с 0.

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
first_fruit = fruits[0] # обращаемся к первому элементу по индексу
print(first_fruit)      # banana
second_fruit = fruits[1]
print(second_fruit)     # orange
last_fruit = fruits[3]
print(last_fruit) # lemon
# Последний индекс
last_index = len(fruits) - 1
last_fruit = fruits[last_index]
```

### Доступ к элементам списка с помощью отрицательной индексации

Отрицательная индексация означает начало с конца, -1 относится к последнему элементу, -2 к предпоследнему элементу.

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
first_fruit = fruits[-4]
last_fruit = fruits[-1]
second_last = fruits[-2]
print(first_fruit)      # banana
print(last_fruit)       # lemon
print(second_last)      # mango
```

### Распаковка элементов списка

```py
lst = ['item1', 'item2', 'item3', 'item4', 'item5']
first_item, second_item, third_item, *rest = lst
print(first_item)     # item1
print(second_item)    # item2
print(third_item)     # item3
print(rest)           # ['item4', 'item5']
```

### Срезы из списка

- Положительная индексация: мы можем указать диапазон положительных индексов, указав начало, конец и шаг, возвращаемое значение будет новым списком. (значения по умолчанию для start = 0, end = len(lst) - 1 (последний элемент), step = 1)

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
all_fruits = fruits[0:4] # возвращает все фрукты
# это также даст тот же результат, что и выше
all_fruits = fruits[0:] # если мы не установим, где остановиться, он возьмет все остальные
orange_and_mango = fruits[1:3] # не включает первый индекс
orange_mango_lemon = fruits[1:]
orange_and_lemon = fruits[::2] # здесь мы использовали 3-й аргумент, шаг. Он возьмет каждый 2-й элемент - ['banana', 'mango']
```

- Отрицательная индексация: мы можем указать диапазон отрицательных индексов, указав начало, конец и шаг, возвращаемое значение будет новым списком.

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
all_fruits = fruits[-4:] # возвращает все фрукты
orange_and_mango = fruits[-3:-1] # не включает последний индекс,['orange', 'mango']
orange_mango_lemon = fruits[-3:] # это даст начиная с -3 до конца,['orange', 'mango', 'lemon']
reverse_fruits = fruits[::-1] # отрицательный шаг возьмет список в обратном порядке,['lemon', 'mango', 'orange', 'banana']
```

### Модификация списков

Список — это изменяемая или модифицируемая упорядоченная коллекция элементов. Давайте модифицируем список фруктов.

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
fruits[0] = 'avocado'
print(fruits)       #  ['avocado', 'orange', 'mango', 'lemon']
fruits[1] = 'apple'
print(fruits)       #  ['avocado', 'apple', 'mango', 'lemon

']
last_index = len(fruits) - 1
fruits[last_index] = 'lime'
print(fruits)        #  ['avocado', 'apple', 'mango', 'lime']
```

### Проверка элементов в списке

Проверка элемента, если он является членом списка с использованием оператора _in_. Смотрите пример ниже.

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
does_exist = 'banana' in fruits
print(does_exist)  # True
does_exist = 'lime' in fruits
print(does_exist)  # False
```

### Добавление элементов в список

Чтобы добавить элемент в конец существующего списка, мы используем метод _append()_.

```py
# синтаксис
lst = list()
lst.append(item)
```

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
fruits.append('apple')
print(fruits)           # ['banana', 'orange', 'mango', 'lemon', 'apple']
fruits.append('lime')   # ['banana', 'orange', 'mango', 'lemon', 'apple', 'lime']
print(fruits)
```

### Вставка элементов в список

Мы можем использовать метод _insert()_ для вставки одного элемента на определенный индекс в список. Обратите внимание, что другие элементы сдвигаются вправо. Метод _insert()_ принимает два аргумента: индекс и вставляемый элемент.

```py
# синтаксис
lst = ['item1', 'item2']
lst.insert(index, item)
```

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
fruits.insert(2, 'apple') # вставить яблоко между апельсином и манго
print(fruits)           # ['banana', 'orange', 'apple', 'mango', 'lemon']
fruits.insert(3, 'lime')   # ['banana', 'orange', 'apple', 'lime', 'mango', 'lemon']
print(fruits)
```

### Удаление элементов из списка

Метод remove удаляет указанный элемент из списка

```py
# синтаксис
lst = ['item1', 'item2']
lst.remove(item)
```

```py
fruits = ['banana', 'orange', 'mango', 'lemon', 'banana']
fruits.remove('banana')
print(fruits)  # ['orange', 'mango', 'lemon', 'banana'] - этот метод удаляет первое вхождение элемента в список
fruits.remove('lemon')
print(fruits)  # ['orange', 'mango', 'banana']
```

### Удаление элементов с помощью Pop

Метод _pop()_ удаляет указанный индекс (или последний элемент, если индекс не указан):

```py
# синтаксис
lst = ['item1', 'item2']
lst.pop()       # последний элемент
lst.pop(index)
```

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
fruits.pop()
print(fruits)       # ['banana', 'orange', 'mango']

fruits.pop(0)
print(fruits)       # ['orange', 'mango']
```

### Удаление элементов с помощью Del

Ключевое слово _del_ удаляет указанный индекс, и его также можно использовать для удаления элементов в диапазоне индексов. Он также может удалить весь список

```py
# синтаксис
lst = ['item1', 'item2']
del lst[index] # только один элемент
del lst        # полностью удалить список
```

```py
fruits = ['banana', 'orange', 'mango', 'lemon', 'kiwi', 'lime']
del fruits[0]
print(fruits)       # ['orange', 'mango', 'lemon', 'kiwi', 'lime']
del fruits[1]
print(fruits)       # ['orange', 'lemon', 'kiwi', 'lime']
del fruits[1:3]     # это удаляет элементы между заданными индексами, поэтому он не удаля

ет элемент с индексом 3!
print(fruits)       # ['orange', 'lime']
del fruits
print(fruits)       # Это должно дать: NameError: name 'fruits' is not defined
```

### Очистка элементов списка

Метод _clear()_ очищает список:

```py
# синтаксис
lst = ['item1', 'item2']
lst.clear()
```

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
fruits.clear()
print(fruits)       # []
```

### Копирование списка

Можно скопировать список, переназначив его новой переменной следующим образом: list2 = list1. Теперь list2 является ссылкой на list1, любые изменения, которые мы сделаем в list2, также изменят оригинал, list1. Но есть много случаев, когда мы не хотим изменять оригинал, вместо этого мы хотим иметь другую копию. Один из способов избежать вышеуказанной проблемы - использовать _copy()_.

```py
# синтаксис
lst = ['item1', 'item2']
lst_copy = lst.copy()
```

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
fruits_copy = fruits.copy()
print(fruits_copy)       # ['banana', 'orange', 'mango', 'lemon']
```

### Соединение списков

Существует несколько способов объединить или конкатенировать два или более списков в Python.

- Оператор Plus (+)

```py
# синтаксис
list3 = list1 + list2
```

```py
positive_numbers = [1, 2, 3, 4, 5]
zero = [0]
negative_numbers = [-5,-4,-3,-2,-1]
integers = negative_numbers + zero + positive_numbers
print(integers) # [-5, -4, -3, -2, -1, 0, 1, 2, 3, 4, 5]
fruits = ['banana', 'orange', 'mango', 'lemon']
vegetables = ['Tomato', 'Potato', 'Cabbage', 'Onion', 'Carrot']
fruits_and_vegetables = fruits + vegetables
print(fruits_and_vegetables ) # ['banana', 'orange', 'mango', 'lemon', 'Tomato', 'Potato', 'Cabbage', 'Onion', 'Carrot']
```

- Соединение с помощью метода extend()
  Метод _extend()_ позволяет добавлять список в список. Смотрите пример ниже.

```py
# синтаксис
list1 = ['item1', 'item2']
list2 = ['item3', 'item4', 'item5']
list1.extend(list2)
```

```py
num1 = [0, 1, 2, 3]
num2= [4, 5, 6]
num1.extend(num2)
print('Numbers:', num1) # Numbers: [0, 1, 2, 3, 4, 5, 6]
negative_numbers = [-5,-4,-3,-2,-1]
positive_numbers = [1, 2, 3,4,5]
zero = [0]

negative_numbers.extend(zero)
negative_numbers.extend(positive_numbers)
print('Integers:', negative_numbers) # Integers: [-5, -4, -3, -2, -1, 0, 1, 2, 3, 4, 5]
fruits = ['banana', 'orange', 'mango', 'lemon']
vegetables = ['Tomato', 'Potato', 'Cabbage', 'Onion', 'Carrot']
fruits.extend(vegetables)
print('Fruits and vegetables:', fruits ) # Fruits and vegetables: ['banana', 'orange', 'mango', 'lemon', 'Tomato', 'Potato', 'Cabbage', 'Onion', 'Carrot']
```

### Подсчет элементов в списке

Метод _count()_ возвращает количество раз, когда элемент появляется в списке:

```py
# синтаксис
lst = ['item1', 'item2']
lst.count(item)
```

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
print(fruits.count('orange'))   # 1
ages = [22, 19, 24, 25, 26, 24, 25, 24]
print(ages.count(24))           # 3
```

### Поиск индекса элемента

Метод _index()_ возвращает индекс элемента в списке:

```py
# синтаксис
lst = ['item1', 'item2']
lst.index(item)
```

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
print(fruits.index('orange'))   # 1
ages = [22, 19, 24, 25, 26, 24, 25, 24]
print(ages.index(24))           # 2, первое вхождение
```

### Обращение списка

Метод _reverse()_ обращает порядок списка.

```py
# синтаксис
lst = ['item1', 'item2']
lst.reverse()

```

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
fruits.reverse()
print(fruits) # ['lemon', 'mango', 'orange', 'banana']
ages = [22, 19, 24, 25, 26, 24, 25, 24]
ages.reverse()
print(ages) # [24, 25, 24, 26, 25, 24, 19, 22]
```

### Сортировка элементов списка

Для сортировки списков мы можем использовать метод _sort()_ или встроенную функцию _sorted()_. Метод _sort()_ изменяет порядок элементов списка по возрастанию и модифицирует исходный список. Если аргумент метода _sort()_ reverse равен true, он упорядочит список в порядке убывания.

- sort(): этот метод изменяет оригинальный список

  ```py
  # синтаксис
  lst = ['item1', 'item2']
  lst.sort()                # по возрастанию
  lst.sort(reverse=True)    # по убыванию
  ```

  **Пример:**

  ```py
  fruits = ['banana', 'orange', 'mango', 'lemon']
  fruits.sort()
  print(fruits)             # отсортировано в алфавитном порядке, ['banana', 'lemon', 'mango', 'orange']
  fruits.sort(reverse=True)
  print(fruits) # ['orange', 'mango', 'lemon', 'banana']
  ages = [22, 19, 24, 25, 26, 24, 25, 24]
  ages.sort()
  print(ages) #  [19, 22, 24, 24, 24, 25, 25, 26]

  ages.sort(reverse=True)
  print(ages) #  [26, 25, 25, 24, 24, 24, 22, 19]
  ```

  sorted(): возвращает упорядоченный список без изменения оригинального списка
  **Пример:**

  ```py
  fruits = ['banana', 'orange', 'mango', 'lemon']
  print(sorted(fruits))   # ['banana', 'lemon', 'mango', 'orange']
  # Обратный порядок
  fruits = ['banana', 'orange', 'mango', 'lemon']
  fruits = sorted(fruits,reverse=True)
  print(fruits)     # ['orange', 'mango', 'lemon', 'banana']
  ```

🌕 Вы усердны и уже достигли немало. Вы только что завершили задания пятого дня и на пяти шагах впереди на пути к величию. Теперь поработайте над упражнениями для вашего мозга и мышц.

## 💻 Упражнения: День 5

### Упражнения: Уровень 1

1. Объявите пустой список
2. Объявите список с более чем 5 элементами
3. Найдите длину вашего списка
4. Получите первый

элемент, средний элемент и последний элемент списка 5. Объявите список с именем mixed*data_types, поместите ваше (имя, возраст, рост, семейное положение, адрес) 6. Объявите список с именем it_companies и присвойте начальные значения Facebook, Google, Microsoft, Apple, IBM, Oracle и Amazon. 7. Выведите список с помощью \_print()* 8. Выведите количество компаний в списке 9. Выведите первую, среднюю и последнюю компанию 10. Выведите список после изменения одной из компаний 11. Добавьте IT-компанию в it_companies 12. Вставьте IT-компанию в середину списка компаний 13. Измените имя одной из it_companies на верхний регистр (кроме IBM!) 14. Соедините it_companies с строкой '#;&nbsp; ' 15. Проверьте, существует ли определенная компания в списке it_companies. 16. Отсортируйте список с помощью метода sort() 17. Переверните список в порядке убывания с помощью метода reverse() 18. Вырежьте первые 3 компании из списка 19. Вырежьте последние 3 компании из списка 20. Вырежьте среднюю IT-компанию или компании из списка 21. Удалите первую IT-компанию из списка 22. Удалите среднюю IT-компанию или компании из списка 23. Удалите последнюю IT-компанию из списка 24. Удалите все IT-компании из списка 25. Уничтожьте список IT-компаний 26. Объедините следующие списки:

    ```py
    front_end = ['HTML', 'CSS', 'JS', 'React', 'Redux']
    back_end = ['Node','Express', 'MongoDB']
    ```

27. После объединения списков в вопросе 26 скопируйте объединенный список и присвойте его переменной full_stack. Затем вставьте Python и SQL после Redux.

### Упражнения: Уровень 2

1. Ниже приведен список из 10 возрастов студентов:

```sh
ages = [19, 22, 19, 24, 20, 25, 26, 24, 25, 24]
```

- Отсортируйте список и найдите минимальный и максимальный возраст
- Добавьте минимальный возраст и максимальный возраст обратно в список
- Найдите средний возраст (один средний элемент или два средних элемента, деленные на два)
- Найдите средний возраст (сумма всех элементов, деленная на их количество)
- Найдите размах возрастов (максимальный минус минимальный)
- Сравните значение (мин - средний) и (макс - средний), используйте метод _abs()_

2. Найдите среднюю страну(ы) в [списке стран](https://github.com/Asabeneh/30-Days-Of-Python/tree/master/data/countries.py)
3. Разделите список стран на два равных списка, если он четный, если нет, то одна страна больше для первой половины.
4. ['China', 'Russia', 'USA', 'Finland', 'Sweden', 'Norway', 'Denmark']. Распакуйте первые три страны и остальные как скандинавские страны.

🎉 ПОЗДРАВЛЯЕМ ! 🎉

[<< День 4](../04_Day_Strings/04_strings.md) | [День 6 >>](../06_Day_Tuples/06_tuples.md)
