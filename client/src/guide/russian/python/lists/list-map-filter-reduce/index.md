---
title: Map, Reduce, Filter
localeTitle: Карта, Уменьшить, Фильтровать
---

Большинство инженеров работают со списками, чтобы обрабатывать список заказов / пользователей и т. Д. Анализ списков может быть сложным и загроможденным быстро, если используется несколько циклов for-loop и вложенных циклов. Следовательно, эти вышеописанные методы могут оптимизировать использование операций с списками.

## карта

Если ваша задача - применить конкретный метод к каждому элементу списка, карта будет полезна. Скажем, у вас есть список значений степени, и вы хотите преобразовать все эти значения в список значений в единицах Fahrenheit.

#### Пример использования

```py
inputs = [10,32,5,40,25] 
 
 def degreesToFahren(deg): 
    fahrenheit = (9.0/5)*deg +32 
    return fahrenheit 
 
 # The most common way of doing this 
 result=[] 
 for i in inputs: 
    iTofahren = degreesToFahren(i) 
    result.append(iTofahren) 
 print(result)   # [50.0, 89.6, 41.0, 104.0, 77.0] 
```

```py
# Using Map 
 result = list(map(degreesToFahren,inputs)) 
 print(result) # [50.0, 89.6, 41.0, 104.0, 77.0] 
```

Как вы могли заметить, использование карты - это просто операция с одним лайнером. Как правило, если у вас есть данные = `[a1,a2,...,an]` и функция `f()` , тогда `map(f,data):` возвращает итератор по `f(a1),f(a2)...f(an).` use `list()` чтобы преобразовать объект итератора в список python.

## Фильтр

Функция фильтра удаляет данные в списке, который вам нужен / не нужен, следовательно, имя. Скажем, вы хотите отфильтровать список на основе значений, которые вам не нужны, например, значения выше 2.

#### Пример использования

```py
data = [1.2,2.5,5.8,0.4,4.7,9.9] 
 result = list(filter(lambda x:x > 2,data)) 
 print(result) 
```

#### Вывод
```
[2.5, 5.8, 4.7, 9.9] 
```

Это также простой 1 лайнер, похожий на вышеприведенную функцию map (). Обратитесь к руководству по лямбда-функциям, если этот термин незначителен.

## уменьшить

От создателя Python, Guido van Rossum `"Use functools.reduce if you really need it; however, 99% of the time an explicit for loop is more readable"`

Как правило, это применить функцию `f()` к элементам данных в списке и использовать этот результат для следующего значения в списке. Визуально,

Данные = \[a 1 , a 2 , ..., a n \] функция = f (x, y)

снизить (е, данных): Шаг 1: val 1 = f (a 1 , a 2 ) Шаг 2: val 2 = f (val 1 , a 3 ) Шаг 3: val 3 = f (val 2 , a 4 ) , , , Шаг n-1: val n-1 = f (val n-2 , a n )

Например, вы хотите умножить все числа в списке.

#### Пример использования

```py
from functools import reduce 
 
 input = [1,2,3,4,5,6] 
 multiplier = lambda x,y:x*y 
 answer = reduce(multiplier,input) 
 print(answer) 
```

#### Вывод
```
720 
```

Однако вышеизложенное может быть вычислено с использованием простого цикла, и использование этих методов зависит от предпочтений.

#### Дополнительная информация:

Официальную документацию по вышеуказанным методам можно найти по адресу http://book.pythontips.com/en/latest/map\_filter.html.