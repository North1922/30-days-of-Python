<div align="center">
  <h1> 30 Дней Python: День 6 - Кортежи</h1>
  <a class="header-badge" target="_blank" href="https://www.linkedin.com/in/asabeneh/">
  <img src="https://img.shields.io/badge/style--5eba00.svg?label=LinkedIn&logo=linkedin&style=social">
  </a>
  <a class="header-badge" target="_blank" href="https://twitter.com/Asabeneh">
  <img alt="Подписка на Twitter" src="https://img.shields.io/twitter/follow/asabeneh?style=social">
  </a>

<sub>Автор:
<a href="https://www.linkedin.com/in/asabeneh/" target="_blank">Асабенех Йетаех</a><br>
<small> Второе издание: Июль, 2021</small>
</sub>

</div>

[<< День 5](../05_Day_Lists/05_lists.md) | [День 7 >>](../07_Day_Sets/07_sets.md)

![30DaysOfPython](../images/30DaysOfPython_banner3@2x.png)

# День 6:

## Кортежи

Кортеж — это коллекция различных типов данных, которая упорядочена и неизменяема (immutable). Кортежи записываются с круглыми скобками, (). После создания кортежа мы не можем изменить его значения. Мы не можем использовать методы добавления, вставки, удаления в кортеже, потому что он не модифицируемый (mutable). В отличие от списка, кортеж имеет немного методов. Методы, связанные с кортежами:

- tuple(): для создания пустого кортежа
- count(): для подсчета количества определенного элемента в кортеже
- index(): для нахождения индекса определенного элемента в кортеже
- - оператор: для объединения двух или более кортежей и создания нового кортежа

### Создание кортежа

- Пустой кортеж: создание пустого кортежа

  ```py
  # синтаксис
  empty_tuple = ()
  # или используя конструктор tuple
  empty_tuple = tuple()
  ```

- Кортеж с начальными значениями

  ```py
  # синтаксис
  tpl = ('item1', 'item2','item3')
  ```

  ```py
  fruits = ('banana', 'orange', 'mango', 'lemon')
  ```

### Длина кортежа

Мы используем метод _len()_, чтобы получить длину кортежа.

```py
# синтаксис
tpl = ('item1', 'item2', 'item3')
len(tpl)
```

### Доступ к элементам кортежа

- Положительная индексация
  Подобно типу данных списка, мы используем положительную или отрицательную индексацию для доступа к элементам кортежа.
  ![Доступ к элементам кортежа](../images/tuples_index.png)

  ```py
  # Синтаксис
  tpl = ('item1', 'item2', 'item3')
  first_item = tpl[0]
  second_item = tpl[1]
  ```

  ```py
  fruits = ('banana', 'orange', 'mango', 'lemon')
  first_fruit = fruits[0]
  second_fruit = fruits[1]
  last_index =len(fruits) - 1
  last_fruit = fruits[last_index]
  ```

- Отрицательная индексация
  Отрицательная индексация означает начало с конца, -1 относится к последнему элементу, -2 к предпоследнему и отрицательное значение длины списка/кортежа относится к первому элементу.
  ![Отрицательная индексация кортежа](../images/tuple_negative_indexing.png)

  ```

  ```

py

# Синтаксис
 ```py
tpl = ('item1', 'item2', 'item3','item4')
first_item = tpl[-4]
second_item = tpl[-3]
 ```


```py
fruits = ('banana', 'orange', 'mango', 'lemon')
first_fruit = fruits[-4]
second_fruit = fruits[-3]
last_fruit = fruits[-1]
```

### Срезы кортежей

Мы можем вырезать подкортеж, указав диапазон индексов, где начать и где закончить в кортеже, возвращаемое значение будет новым кортежем с указанными элементами.

- Диапазон положительных индексов

  ```py
  # Синтаксис
  tpl = ('item1', 'item2', 'item3','item4')
  all_items = tpl[0:4]         # все элементы
  all_items = tpl[0:]         # все элементы
  middle_two_items = tpl[1:3]  # не включает элемент с индексом 3
  ```

  ```py
  fruits = ('banana', 'orange', 'mango', 'lemon')
  all_fruits = fruits[0:4]    # все элементы
  all_fruits= fruits[0:]      # все элементы
  orange_mango = fruits[1:3]  # не включает элемент с индексом 3
  orange_to_the_rest = fruits[1:]
  ```

- Диапазон отрицательных индексов

  ```py
  # Синтаксис
  tpl = ('item1', 'item2', 'item3','item4')
  all_items = tpl[-4:]         # все элементы
  middle_two_items = tpl[-3:-1]  # не включает элемент с индексом 3 (-1)
  ```

  ```py
  fruits = ('banana', 'orange', 'mango', 'lemon')
  all_fruits = fruits[-4:]    # все элементы
  orange_mango = fruits[-3:-1]  # не включает элемент с индексом 3
  orange_to_the_rest = fruits[-3:]
  ```

### Преобразование кортежей в списки

Мы можем изменить кортежи на списки и списки на кортежи. Кортеж неизменяем, если мы хотим изменить кортеж, мы должны превратить его в список.

```py
# Синтаксис
tpl = ('item1', 'item2', 'item3','item4')
lst = list(tpl)
```

```py
fruits = ('banana', 'orange', 'mango', 'lemon')
fruits = list(fruits)
fruits[0] = 'apple'
print(fruits)     # ['apple', 'orange', 'mango', 'lemon']
fruits = tuple(fruits)
print(fruits)     # ('apple', 'orange', 'mango', 'lemon')
```

### Проверка наличия элемента в кортеже

Мы можем проверить, существует ли элемент в кортеже, используя _in_, он возвращает логическое значение.

```py
# Синтаксис
tpl = ('item1', 'item2', 'item3','item4')
'item2' in tpl # True
```

```py
fruits = ('banana', 'orange', 'mango', 'lemon')
print('orange' in fruits) # True
print('apple' in fruits) # False
fruits[0] = 'apple' # TypeError: 'tuple' object does not support item assignment
```

### Объединение кортежей

Мы можем объединить два или более кортежа, используя оператор +

```py
# синтаксис
tpl1 = ('item1', 'item2', 'item3')
tpl2 = ('item4', 'item5','item6')
tpl3 = tpl1 + tpl2
```

```py
fruits = ('banana', 'orange', 'mango', 'lemon')
vegetables = ('Tomato', 'Potato', 'Cabbage','Onion', 'Carrot')
fruits_and_vegetables = fruits + vegetables
```

### Удаление кортежей

Удалить отдельный элемент в кортеже нельзя, но можно удалить сам кортеж, используя _del_.

```py
# синтаксис
tpl1 = ('item1', 'item2', 'item3')
del tpl1

```

```py
fruits = ('banana', 'orange', 'mango', 'lemon')
del fruits
```

🌕 Вы такие смелые, вы дошли до сюда. Вы только что завершили задания шестого дня и на шести шагах впереди на пути к величию. Теперь поработайте над упражнениями для вашего мозга и для вашей мышцы.

## 💻 Упражнения: День 6

### Упражнения: Уровень 1

1. Создайте пустой кортеж
2. Создайте кортеж, содержащий имена ваших сестер и братьев (воображаемые братья и сестры тоже подходят)
3. Объедините кортежи братьев и сестер и присвойте его переменной siblings
4. Сколько у вас братьев и сестер?
5. Измените кортеж siblings, добавив имена вашего отца и матери и присвойте его переменной family_members

### Упражнения: Уровень 2

1. Распакуйте братьев, сестер и родителей из family_members
2. Создайте кортежи fruits, vegetables и animal products. Объедините три кортежа и присвойте его переменной food_stuff_tp.
3. Преобразуйте food_stuff_tp кортеж в список food_stuff_lt.
4. Вырежьте средний элемент или элементы из кортежа food_stuff_tp или списка food_stuff_lt.
5. Вырежьте первые три элемента и последние три элемента из списка food_staff_lt.
6. Полностью удалите кортеж food_staff_tp.
7. Проверьте, существует ли элемент в кортеже:

- Проверьте, является ли 'Estonia' скандинавской страной
- Проверьте, является ли 'Iceland' скандинавской страной

  ```py
  nordic_countries = ('Denmark', 'Finland','Iceland', 'Norway', 'Sweden')
  ```

[<< День 5](../05_Day_Lists/05_lists.md) | [День 7 >>](../07_Day_Sets/07_sets.md)
