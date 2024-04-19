<div align="center">
  <h1>30 дней Python: День 8 - Словари</h1>
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

[<< День 7](../07_Day_Sets/07_sets.md) | [День 9 >>](../09_Day_Conditionals/09_conditionals.md)

![30DaysOfPython](../images/30DaysOfPython_banner3@2x.png)

- [📘 День 8](#-день-8)
  - [Словари](#словари)
    - [Создание словаря](#создание-словаря)
    - [Длина словаря](#длина-словаря)
    - [Доступ к элементам словаря](#доступ-к-элементам-словаря)
    - [Добавление элементов в словарь](#добавление-элементов-в-словарь)
    - [Изменение элементов в словаре](#изменение-элементов-в-словаре)
    - [Проверка ключей в словаре](#проверка-ключей-в-словаре)
    - [Удаление пар ключ/значение из словаря](#удаление-пар-ключзначение-из-словаря)
    - [Преобразование словаря в список элементов](#преобразование-словаря-в-список-элементов)
    - [Очистка словаря](#очистка-словаря)
    - [Удаление словаря](#удаление-словаря)
    - [Копирование словаря](#копирование-словаря)
    - [Получение ключей словаря в виде списка](#получение-ключей-словаря-в-виде-списка)
    - [Получение значений словаря в виде списка](#получение-значений-словаря-в-виде-списка)
  - [💻 Упражнения: День 8](#-упражнения-день-8)

# 📘 День 8

## Словари

Словарь — это коллекция неупорядоченных, изменяемых (мутабельных) пар (ключ: значение).

### Создание словаря

Для создания словаря мы используем фигурные скобки, {} или встроенную функцию _dict()_.

```py
# синтаксис
empty_dict = {}
# Словарь с начальными значениями
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
```

**Пример:**

```py
person = {
    'first_name':'Asabeneh',
    'last_name':'Yetayeh',
    'age':250,
    'country':'Finland',
    'is_marred':True,
    'skills':['JavaScript', 'React', 'Node', 'MongoDB', 'Python'],
    'address':{
        'street':'Space street',
        'zipcode':'02210'
    }
}
```

В приведенном выше словаре показано, что значение может быть любым типом данных: строкой, логическим, списком, кортежем, множеством или словарем.

### Длина словаря

Она проверяет количество пар 'ключ: значение' в словаре.

```py
#

 синтаксис
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
print(len(dct)) # 4
```

**Пример:**

```py
person = {
    'first_name':'Asabeneh',
    'last_name':'Yetayeh',
    'age':250,
    'country':'Finland',
    'is_marred':True,
    'skills':['JavaScript', 'React', 'Node', 'MongoDB', 'Python'],
    'address':{
        'street':'Space street',
        'zipcode':'02210'
    }
}
print(len(person)) # 7
```

### Доступ к элементам словаря

Мы можем получить доступ к элементам словаря, обратившись к его ключу.

```py
# синтаксис
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
print(dct['key1']) # value1
print(dct['key4']) # value4
```

**Пример:**

```py
person = {
    'first_name':'Asabeneh',
    'last_name':'Yetayeh',
    'age':250,
    'country':'Finland',
    'is_marred':True,
    'skills':['JavaScript', 'React', 'Node', 'MongoDB', 'Python'],
    'address':{
        'street':'Space street',
        'zipcode':'02210'
    }
}
print(person['first_name']) # Asabeneh
print(person['country'])    # Finland
print(person['skills'])     # ['JavaScript', 'React', 'Node', 'MongoDB', 'Python']
print(person['skills'][0])  # JavaScript
print(person['address']['street']) # Space street
print(person['city'])       # Error
```

Доступ к элементу по имени ключа вызывает ошибку, если ключ не существует. Чтобы избежать этой ошибки, сначала мы должны проверить, существует ли ключ, или мы можем использовать метод _get_. Метод get возвращает None, что является объектом данных типа NoneType, если ключ не существует.

```py
person = {
    'first_name':'Asabeneh',
    'last_name':'Yetayeh',
    'age':250,
    'country':'Finland',
    'is_marred':True,
    'skills':['JavaScript', 'React', 'Node', 'MongoDB', 'Python'],
    'address':{
        'street':'Space street',
        'zipcode':'02210'
    }
}
print(person.get('first_name')) # Asabeneh
print(person.get('country'))    # Finland
print(person.get('skills')) #['HTML','CSS','JavaScript', 'React', 'Node', 'MongoDB', 'Python']
print(person.get('city'))   # None
```

### Добавление элементов в словарь

Мы можем добавить новые пары ключ-значение в словарь.

```py
# синтаксис
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
dct['key5'] = 'value5'
```

**Пример:**

```py
person = {
    'first_name':'Asabeneh',
    'last_name':'Yetayeh',
    'age':250,
    'country':'Finland',
    'is_marred':True,
    'skills':['JavaScript', 'React', 'Node', 'MongoDB', 'Python'],
    'address':{
        'street':'Space street',
        'zipcode':'02210'
        }
}
person['job_title'] = 'Instructor'
person['skills'].append('HTML')
print(person)
```

### Изменение элементов в словаре

Мы можем изменять элементы в словаре.

```py
# синтаксис
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
dct['key1'] = 'value-one'
```

**Пример:**

```py
person = {
    'first_name':'Asabeneh',
    'last_name':'Yetayeh',
    'age':250,
    'country':'Finland',
    'is_marred':True,
    'skills':['JavaScript', 'React', 'Node', 'MongoDB', 'Python'],
    'address':{
        'street':'Space street',
        'zipcode':'022

10'
    }
}
person['first_name'] = 'Eyob'
person['age'] = 252
```

### Проверка ключей в словаре

Мы используем оператор _in_, чтобы проверить, существует ли ключ в словаре.

```py
# синтаксис
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
print('key2' in dct) # True
print('key5' in dct) # False
```

### Удаление пар ключ/значение из словаря

- _pop(key)_: удаляет элемент с указанным именем ключа:
- _popitem()_: удаляет последний элемент
- _del_: удаляет элемент с указанным именем ключа

```py
# синтаксис
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
dct.pop('key1') # удаляет элемент key1
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
dct.popitem() # удаляет последний элемент
del dct['key2'] # удаляет элемент key2
```

**Пример:**

```py
person = {
    'first_name':'Asabeneh',
    'last_name':'Yetayeh',
    'age':250,
    'country':'Finland',
    'is_marred':True,
    'skills':['JavaScript', 'React', 'Node', 'MongoDB', 'Python'],
    'address':{
        'street':'Space street',
        'zipcode':'02210'
    }
}
person.pop('first_name')        # Удаляет элемент с именем first_name
person.popitem()                # Удаляет элемент address
del person['is_married']        # Удаляет элемент is_married
```

### Преобразование словаря в список элементов

Метод _items()_ преобразует словарь в список кортежей.

```py
# синтаксис
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
print(dct.items()) # dict_items([('key1', 'value1'), ('key2', 'value2'), ('key3', 'value3'), ('key4', 'value4')])
```

### Очистка словаря

Если мы не хотим элементы в словаре, мы можем очистить их с помощью метода _clear()_

```py
# синтаксис
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
print(dct.clear()) # None
```

### Удаление словаря

Если мы не используем словарь, мы можем полностью его удалить

```py
# синтаксис
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
del dct
```

### Копирование словаря

Мы можем скопировать словарь, используя метод _copy()_. Используя копирование, мы можем избежать мутации оригинального словаря.

```py
# синтаксис
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
dct_copy = dct.copy() # {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
```

### Получение ключей словаря в виде списка

Метод _keys()_ дает нам все ключи словаря в виде списка.

```py
# синтаксис
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
keys = dct.keys()
print(keys)     # dict_keys(['key1', 'key2', 'key3', 'key4'])
```

### Получение значений словаря в виде списка

Метод _values_ дает нам все значения словаря в виде списка.

```py


# синтаксис
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
values = dct.values()
print(values)     # dict_values(['value1', 'value2', 'value3', 'value4'])
```

🌕 Вы потрясающие. Теперь вы наделены мощью словарей. Вы только что завершили задания восьмого дня и на восемь шагов впереди на пути к величию. Теперь поработайте над упражнениями для вашего мозга и мышц.

## 💻 Упражнения: День 8

1. Создайте пустой словарь с именем dog
2. Добавьте имя, цвет, породу, лапы, возраст в словарь dog
3. Создайте словарь student и добавьте имя, фамилию, пол, возраст, семейное положение, навыки, страну, город и адрес как ключи словаря
4. Получите длину словаря student
5. Получите значение skills и проверьте его тип данных, это должен быть список
6. Измените значения skills, добавив один или два навыка
7. Получите ключи словаря в виде списка
8. Получите значения словаря в виде списка
9. Преобразуйте словарь в список кортежей с помощью метода _items()_
10. Удалите один из элементов в словаре
11. Удалите один из словарей

🎉 ПОЗДРАВЛЯЕМ ! 🎉

[<< День 7](../07_Day_Sets/07_sets.md) | [День 9 >>](../09_Day_Conditionals/09_conditionals.md)
