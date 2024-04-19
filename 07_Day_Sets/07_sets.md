<div align="center">
  <h1> 30 Дней Python: День 7 - Множества</h1>
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

[<< День 6](../06_Day_Tuples/06_tuples.md) | [День 8 >>](../08_Day_Dictionaries/08_dictionaries.md)

![30DaysOfPython](../images/30DaysOfPython_banner3@2x.png)

# 📘 День 7

## Множества

Множество — это коллекция элементов. Вспомним урок математики в начальной или средней школе. Математическое определение множества также применимо и в Python. Множество — это коллекция неупорядоченных и непронумерованных уникальных элементов. В Python множество используется для хранения уникальных элементов, и можно найти _объединение_, _пересечение_, _разность_, _симметрическую разность_, _подмножество_, _надмножество_ и _непересекающиеся множества_ среди множеств.

### Создание множества

Мы используем встроенную функцию _set()_.

- Создание пустого множества

```py
# синтаксис
st = set()
```

- Создание множества с начальными элементами

```py
# синтаксис
st = {'item1', 'item2', 'item3', 'item4'}
```

**Пример:**

```py
# синтаксис
fruits = {'banana', 'orange', 'mango', 'lemon'}
```

### Получение длины множества

Мы используем метод **len()** для определения длины множества.

```py
# синтаксис
st = {'item1', 'item2', 'item3', 'item4'}
len(st)
```

**Пример:**

```py
fruits = {'banana', 'orange', 'mango', 'lemon'}
len(fruits)
```

### Доступ к элементам множества

Мы используем циклы для доступа к элементам. Мы увидим это в разделе о циклах.

### Проверка наличия элемента

Чтобы проверить, существует ли элемент в списке, мы используем оператор принадлежности _in_.

```py
# синтаксис
st = {'item1', 'item2', 'item3', 'item4'}
print("Содержит ли множество st элемент item3? ", 'item3' in st) # Содержит ли множество st элемент item3? True
```

**Пример:**

```py
fruits = {'banana', 'orange', 'mango', 'lemon'}
print('mango' in fruits ) # True
```

### Добавление элементов в множество

После создания множества мы не можем изменять его элементы, но можем добавлять новые.

- Добавление одного элемента с помощью _add()_

```py
# синтаксис
st = {'item1', 'item2', 'item3', 'item4'}
st.add('item5')
```

**Пример:**

```py
fruits = {'banana

', 'orange', 'mango', 'lemon'}
fruits.add('lime')
```

- Добавление нескольких элементов с помощью _update()_
  Метод _update()_ позволяет добавить несколько элементов в множество. _update()_ принимает аргумент в виде списка.

```py
# синтаксис
st = {'item1', 'item2', 'item3', 'item4'}
st.update(['item5','item6','item7'])
```

**Пример:**

```py
fruits = {'banana', 'orange', 'mango', 'lemon'}
vegetables = ('tomato', 'potato', 'cabbage','onion', 'carrot')
fruits.update(vegetables)
```

### Удаление элементов из множества

Мы можем удалить элемент из множества, используя метод _remove()_. Если элемент не найден, метод _remove()_ вызовет ошибки, поэтому хорошо проверить, существует ли элемент в данном множестве. Однако метод _discard()_ ошибок не вызывает.

```py
# синтаксис
st = {'item1', 'item2', 'item3', 'item4'}
st.remove('item2')
```

Метод pop() удаляет случайный элемент из списка и возвращает удаленный элемент.

**Пример:**

```py
fruits = {'banana', 'orange', 'mango', 'lemon'}
fruits.pop()  # удаляет случайный элемент из множества
```

Если нам интересен удаленный элемент.

```py
fruits = {'banana', 'orange', 'mango', 'lemon'}
removed_item = fruits.pop()
```

### Очистка элементов в множестве

Если мы хотим очистить или опустошить множество, мы используем метод _clear_.

```py
# синтаксис
st = {'item1', 'item2', 'item3', 'item4'}
st.clear()
```

**Пример:**

```py
fruits = {'banana', 'orange', 'mango', 'lemon'}
fruits.clear()
print(fruits) # set()
```

### Удаление множества

Если мы хотим удалить само множество, мы используем оператор _del_.

```py
# синтаксис
st = {'item1', 'item2', 'item3', 'item4'}
del st
```

**Пример:**

```py
fruits = {'banana', 'orange', 'mango', 'lemon'}
del fruits
```

### Преобразование списка в множество

Мы можем преобразовать список в множество и множество в список. Преобразование списка в множество удаляет дубликаты, и будут сохранены только уникальные элементы.

```py
# синтаксис
lst = ['item1', 'item2', 'item3', 'item4', 'item1']
st = set(lst)  # {'item2', 'item4', 'item1', 'item3'} - порядок случайный, потому что множества в целом неупорядоченные
```

**Пример:**

```py
fruits = ['banana', 'orange', 'mango', 'lemon','orange', 'banana']
fruits = set(fruits) # {'mango', 'lemon', 'banana', 'orange'}
```

### Объединение множеств

Мы можем объединить два множества, используя метод _union()_ или _update()_.

- Объединение
  Этот метод возвращает новое множество

```py
# синтаксис
st1 = {'item1', 'item2', 'item3', 'item4'}
st2 = {'item5', 'item6', 'item7', 'item8'}
st3 = st1.union(st2)
```

**Пример:**

```py
fruits = {'banana', 'orange', 'mango', 'lemon'}
vegetables = {'tomato', 'potato', 'cabbage','onion', 'carrot'}
print(fruits.union(vegetables)) # {'lemon

', 'carrot', 'tomato', 'banana', 'mango', 'orange', 'cabbage', 'potato', 'onion'}
```

- Обновление
  Этот метод вставляет множество в заданное множество

```py
# синтаксис
st1 = {'item1', 'item2', 'item3', 'item4'}
st2 = {'item5', 'item6', 'item7', 'item8'}
st1.update(st2) # содержимое st2 добавляется к st1
```

**Пример:**

```py
fruits = {'banana', 'orange', 'mango', 'lemon'}
vegetables = {'tomato', 'potato', 'cabbage','onion', 'carrot'}
fruits.update(vegetables)
print(fruits) # {'lemon', 'carrot', 'tomato', 'banana', 'mango', 'orange', 'cabbage', 'potato', 'onion'}
```

### Нахождение пересечений множеств

Пересечение возвращает множество элементов, которые присутствуют в обоих множествах. Смотрите пример

```py
# синтаксис
st1 = {'item1', 'item2', 'item3', 'item4'}
st2 = {'item3', 'item2'}
st1.intersection(st2) # {'item3', 'item2'}
```

**Пример:**

```py
whole_numbers = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10}
even_numbers = {0, 2, 4, 6, 8, 10}
whole_numbers.intersection(even_numbers) # {0, 2, 4, 6, 8, 10}

python = {'p', 'y', 't', 'h', 'o','n'}
dragon = {'d', 'r', 'a', 'g', 'o','n'}
python.intersection(dragon)     # {'o', 'n'}
```

### Проверка подмножества и надмножества

Множество может быть подмножеством или надмножеством других множеств:

- Подмножество: _issubset()_
- Надмножество: _issuperset_

```py
# синтаксис
st1 = {'item1', 'item2', 'item3', 'item4'}
st2 = {'item2', 'item3'}
st2.issubset(st1) # True
st1.issuperset(st2) # True
```

**Пример:**

```py
whole_numbers = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10}
even_numbers = {0, 2, 4, 6, 8, 10}
whole_numbers.issubset(even_numbers) # False, потому что это надмножество
whole_numbers.issuperset(even_numbers) # True

python = {'p', 'y', 't', 'h', 'o','n'}
dragon = {'d', 'r', 'a', 'g', 'o','n'}
python.issubset(dragon)     # False
```

### Проверка разности между двумя множествами

Она возвращает разность между двумя множествами.

```py
# синтаксис
st1 = {'item1', 'item2', 'item3', 'item4'}
st2 = {'item2', 'item3'}
st2.difference(st1) # set()
st1.difference(st2) # {'item1', 'item4'} => st1\st2
```

**Пример:**

```py
whole_numbers = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10}
even_numbers = {0, 2, 4, 6, 8, 10}
whole_numbers.difference(even_numbers) # {1, 3, 5, 7, 9}

python = {'p', 'y', 't', 'o','n'}
dragon = {'d', 'r', 'a', 'g', 'o','n'}
python.difference(dragon)     # {'p', 'y', '

t'}  - результат неупорядочен (характеристика множеств)
dragon.difference(python)     # {'d', 'r', 'a', 'g'}
```

### Нахождение симметрической разности между двумя множествами

Она возвращает симметрическую разность между двумя множествами. Это означает, что она возвращает множество, содержащее все элементы из обоих множеств, за исключением элементов, присутствующих в обоих множествах, математически: (A\B) ∪ (B\A)

```py
# синтаксис
st1 = {'item1', 'item2', 'item3', 'item4'}
st2 = {'item2', 'item3'}
# это означает (A\B)∪(B\A)
st2.symmetric_difference(st1) # {'item1', 'item4'}
```

**Пример:**

```py
whole_numbers = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10}
some_numbers = {1, 2, 3, 4, 5}
whole_numbers.symmetric_difference(some_numbers) # {0, 6, 7, 8, 9, 10}

python = {'p', 'y', 't', 'h', 'o','n'}
dragon = {'d', 'r', 'a', 'g', 'o','n'}
python.symmetric_difference(dragon)  # {'r', 't', 'p', 'y', 'g', 'a', 'd', 'h'}
```

### Объединение множеств

Если два множества не имеют общих элементов, мы называем их непересекающимися множествами. Мы можем проверить, являются ли два множества пересекающимися или непересекающимися, используя метод _isdisjoint()_.

```py
# синтаксис
st1 = {'item1', 'item2', 'item3', 'item4'}
st2 = {'item2', 'item3'}
st2.isdisjoint(st1) # False
```

**Пример:**

```py
even_numbers = {0, 2, 4 ,6, 8}
even_numbers = {1, 3, 5, 7, 9}
even_numbers.isdisjoint(odd_numbers) # True, потому что нет общих элементов

python = {'p', 'y', 't', 'h', 'o','n'}
dragon = {'d', 'r', 'a', 'g', 'o','n'}
python.isdisjoint(dragon)  # False, есть общие элементы {'o', 'n'}
```

🌕 Вы — восходящая звезда. Вы только что завершили задания седьмого дня и на семи шагах впереди на пути к величию. Теперь поработайте над упражнениями для вашего мозга и для вашей мышцы.

## 💻 Упражнения: День 7

```py
# множества
it_companies = {'Facebook', 'Google', 'Microsoft', 'Apple', 'IBM', 'Oracle', 'Amazon'}
A = {19, 22, 24, 20, 25, 26}
B = {19, 22, 20, 25, 26, 24, 28, 27}
age = [22, 19, 24, 25, 26, 24, 25, 24]
```

### Упражнения: Уровень 1

1. Найдите длину множества it_companies
2. Добавьте 'Twitter' в it_companies
3. Вставьте несколько ИТ-компаний сразу в множество it_companies
4. Удалите одну из компаний из множества it_companies
5. В чем разница м

ежду remove и discard

### Упражнения: Уровень 2

1. Объедините A и B
2. Найдите пересечение A и B
3. Является ли A подмножеством B
4. Являются ли A и B непересекающимися множествами
5. Объедините A с B и B с A
6. Какая симметричная разность между A и B
7. Удалите множества полностью

### Упражнения: Уровень 3

1. Преобразуйте возрасты в множество и сравните длину списка и множества, какой больше?
2. Объясните разницу между следующими типами данных: строка, список, кортеж и множество
3. _Я учитель, и мне нравится вдохновлять и учить людей._ Сколько уникальных слов было использовано в предложении? Используйте методы split и set, чтобы получить уникальные слова.

🎉 ПОЗДРАВЛЯЕМ ! 🎉

[<< День 6](../06_Day_Tuples/06_tuples.md) | [День 8 >>](../08_Day_Dictionaries/08_dictionaries.md)
