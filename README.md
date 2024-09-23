# Тема 4. Функции и модули.
Отчет по теме 4 выполнила:
- Теплоухова Ирина Алексеевна
- АИС-22-1


| Задание | Лаб_раб | Сам_раб |
| ------------- | ------------- | ------------- |
| Задание 1 | + | + |
| Задание 2 | + | + |
| Задание 3 | + | + |
| Задание 4 | + | + |
| Задание 5 | + | + |
| Задание 6 | + |  |
| Задание 7 | + |  |
| Задание 8 | + |  |
| Задание 9 | + |  |
| Задание 10 | + |  |

знак "+" - задание выполнено; знак "-" - задание не выполнено;

Работу проверили:
- к.э.н., доцент Панов М.А.

  ## Лабораторная работа №4
### 1) Напишите функцию, которая выполняет любые арифметические действия и выводит результат в консоль. Вызовите функцию используя “точку входа”.
```python
def main(): 
    print (2+2)

if __name__ == '__main__':
    main()
```

### Результат
![Меню](https://github.com/tplxv/hh/blob/%D0%A2%D0%B5%D0%BC%D0%B0_4/1.jpg)

### 2) Напишите функцию, которая выполняет любые арифметические действия, возвращает при помощи return значение в место, откуда вызывали функцию. Выведите результат в консоль. Вызовите функцию используя “точку входа”.
```python
def main(): 
    return 2+2

if __name__ == '__main__':
    print(main())
```

### Результат
![Меню](https://github.com/tplxv/hh/blob/%D0%A2%D0%B5%D0%BC%D0%B0_4/2.jpg)

### 3) Напишите функцию, в которую передаются два аргумента, над ними производится арифметическое действие, результат возвращается туда, откуда эту функцию вызывали. Выведите результат в консоль. Вызовите функцию в любом небольшом цикле.
```python
def main(one, two):
    return one+two

if __name__ == '__main__':
    answer=main(one=1, two=10)
    print(answer)
```

### Результат
![Меню](https://github.com/tplxv/hh/blob/%D0%A2%D0%B5%D0%BC%D0%B0_4/3.jpg)

### 4) Напишите функцию, на вход которой подается какое-то изначальное неизвестное количество аргументов, над которыми будет производится арифметические действия. Для выполнения задания необходимо использовать кортеж “*args”.

```python
def main(x, *args):
    one=x
    two=sum(args)
    three=float(len(args))
    print(f"one={one}\ntwo={two}\nthree={three}")
    return x+sum(args)/float(len(args))

if __name__ == '__main__':
    result = main(10, 0,1,2,-1,0,-1,1,2)
    print(f"\nresult={result}")
```

### Результат
![Меню](https://github.com/tplxv/hh/blob/%D0%A2%D0%B5%D0%BC%D0%B0_4/4.jpg)

### 5) Напишите функцию, которая на вход получает кортеж “**kwargs” и при помощи цикла выводит значения, поступившие в функцию. На скриншоте ниже указаны два варианта вызова функции с “**kwargs” и два варианта работы с данными, поступившими в эту функцию. Комментарии в коде и теоретическая часть помогут вам разобраться в этом нелегком аспекте. Вызовите функцию используя “точку входа”.
```python
def main(**kwargs):
    for i in kwargs.items():
        print(i[0], 1[1])
    print()
    
    for key in kwargs:
        print(f"{key}={kwargs[key]}")
if __name__ == '__main__':
    main(x=[1, 2, 3], y=[3, 3, 0], z=[2, 3, 0], q = [3, 3, 0], w = [3, 3, 0])
    print()
    main(**{'x': [1, 2, 3], 'y': [3, 3, 0]})
```

### Результат
![Меню](https://github.com/tplxv/hh/blob/%D0%A2%D0%B5%D0%BC%D0%B0_4/5.jpg)

### 6) Напишите две функции. Первая – получает в виде параметра “**kwargs”. Вторая считает среднее арифметическое из значений первой функции. Вызовите первую функцию используя “точку входа” и минимум 4 аргумента.
```python
def main (**kwargs): 
    for i, j in kwargs.items():
        print(f"{i}. Mean = {mean (j)}")
        
def mean (data):
    return sum(data)/ float(len(data))
if __name__ =='__main__':
    main (x= [1,2,3], y=[3,3,0])
```

### Результат
![Меню](https://github.com/tplxv/hh/blob/%D0%A2%D0%B5%D0%BC%D0%B0_4/6.jpg)

### 7) Создайте дополнительный файл .py. Напишите в нем любую функцию, которая будет что угодно выводить в консоль, но не вызывайте ее в нем. Откройте файл main.py, импортируйте в него функцию из нового файла и при помощи “точки входа” вызовите эту функцию
```python
def say_hello():
    print('Hello students!')
```
```python
from for_import import say_hello
if __name__ == '.__main__':
    say_hello()
```

### Результат
![Меню](https://github.com/tplxv/hh/blob/%D0%A2%D0%B5%D0%BC%D0%B0_4/7.2.jpg)

### 8) Напишите программу, которая будет выводить корень, синус, косинус полученного от пользователя числа.
```python
import math
def main(): 
    value = int(input('Введите значение: '))
    print(math.sqrt(value))
    print(math. sin(value))
    print(math.cos(value))
if __name__ == '__main__':
    main()
```

### Результат
![Меню](https://github.com/tplxv/hh/blob/%D0%A2%D0%B5%D0%BC%D0%B0_4/8.jpg)

### 9) Напишите программу, которая будет рассчитывать какой день недели будет через n-нное количество дней, которые укажет пользователь.
```python
from datetime import datetime as dt
from datetime import timedelta as td

def main():
    print(
        f"Сегодня {dt.today().date()}. "
        f"День недели - {dt.today().isoweekday()}"
    )
    n= int(input('Введите количество дней:'))
    today = dt.today()
    result = today+td(days=n)
    print(
        f"Через {n} дней будет {result.date()}. "
        f"День недели - {result.isoweekday()}"
    )

if __name__ == '__main__':
    main()
```

### Результат
![Меню](https://github.com/tplxv/hh/blob/%D0%A2%D0%B5%D0%BC%D0%B0_4/9.jpg)

### 10) Напишите программу с использованием глобальных переменных, которая будет считать площадь треугольника или прямоугольника в зависимости от того, что выберет пользователь. Получение всей необходимой информации реализовать через input(), а подсчет площадей выполнить при помощи функций. Результатом программы будет число, равное площади, необходимой фигуры.
```python
global result

def rectangle():
    a = float(input("Ширина: "))
    b = float(input("Высота: "))
    global result
    result =a*b

def triangle():
    a = float(input("Основание: "))
    h = float(input("Высота: "))
    global result
    result = 0.5 *a*h

figure = input("1-прямоугольник, 2-треугольник: ")

if figure == '1':
    rectangle()
elif figure == '2':
    triangle()
print(f"Площадь: {result}")
```

### Результат
![Меню](https://github.com/tplxv/hh/blob/%D0%A2%D0%B5%D0%BC%D0%B0_4/10.jpg)

  ## Самостоятельная работа №4. 
### 1) Дайте подробный комментарий для кода, написанного ниже. Комментарий нужен для каждой строчки кода, нужно описать что она делает. Не забудьте, что функции комментируются по-особенному.
```python
number = 1
for i in range(2):
    number *= 5
    number += 1
print(number)
```

### Результат
![Меню](https://github.com/tplxv/hh/blob/%D1%84%D0%BE%D1%82%D0%BE3/1.1.jpg)
### Вывод
  - Переменная `number` инициализируется со значением 1.
  - Цикл `for` выполняется 2 раза.
  - В каждой итерации значение переменной `number` умножается на 5 и прибавляется 1.
  - Программа выводит на экран значение переменной `number`, равное 31.

### 2) Напишите программу, которая будет заменять игральную кость с 6 гранями. Если значение равно 5 или 6, то в консоль выводится «Вы победили», если значения 3 или 4, то вы рекурсивно должны вызвать эту же функцию, если значение 1 или 2, то в консоль выводится «Вы проиграли». При этом каждый вызов функции необходимо выводить в консоль значение “кубика”. Для выполнения задания необходимо использовать стандартную библиотеку random. Программу нужно написать, используя одну функцию и “точку входа”
```python
p= "Hello World"
r_p= p[::-1]
for letter in r_p: print(letter)
```

### Результат
![Меню](https://github.com/tplxv/hh/blob/%D1%84%D0%BE%D1%82%D0%BE3/2.1.jpg)
### Вывод
- Определяем строку p с текстом «Hello World».
- Используем срез, чтобы получить r_p - фразу в обратном порядке.
- Проходим по каждому символу в r_p и выводим его на экран.

### 3) Напишите программу, которая будет выводить текущее время, с точностью до секунд на протяжении 5 секунд. Программу нужно написать с использованием цикла. Подсказка: необходимо использовать модуль datetime и time, а также вам необходимо как-то “усыплять” программу на 1 секунду.
```python
number = int(input("Введите число от 0 до 10: "))
if number <= 3:
    print("Диапазон: от 0 до 3")
elif number <= 6:
    print("Диапазон: от 3 до 6")
elif 6< number<= 10:
    print("Диапазон: от 6 до 10")
else:
    print("Число не лежит в диапазоне")
```

### Результат
![Меню](https://github.com/tplxv/hh/blob/%D1%84%D0%BE%D1%82%D0%BE3/3.1.jpg)
![Меню](https://github.com/tplxv/hh/blob/%D1%84%D0%BE%D1%82%D0%BE3/3.2.jpg)
![Меню](https://github.com/tplxv/hh/blob/%D1%84%D0%BE%D1%82%D0%BE3/3.3.jpg)
![Меню](https://github.com/tplxv/hh/blob/%D1%84%D0%BE%D1%82%D0%BE3/3.4.jpg)
### Вывод
- Пользователь вводит число.
- Программа определяет диапазон и выводит соответствующее сообщение.

### 4) Напишите программу, которая считает среднее арифметическое от аргументов вызываемое функции, с условием того, что изначальное количество этих аргументов неизвестно. Программу необходимо реализовать используя одну функцию и “точку входа”.

```python
sentence=input("Введите предложение: ")

l= len(sentence)
print(f"Длина предложения: {l}")

l_case = sentence.lower()
print(f"Предложение в нижнем регистре: {l_case}")

v= "aeiou"
count_v= sum(1 for char in sentence.lower() if char in v)
print(f"Количество гласных: {count_v}")

rep = sentence.replace("ugly", "beauty")
print(f"Предложение после замены 'ugly' на 'beauty': {rep}")

st_w_t = sentence.startswith("The")
en_w_e = sentence.endswith("end")
print(f"Начинается с 'The': {st_w_t}, заканчивается на 'end': {en_w_e}")
```

### Результат
![Меню](https://github.com/tplxv/hh/blob/%D1%84%D0%BE%D1%82%D0%BE3/4.1.jpg)
![Меню](https://github.com/tplxv/hh/blob/%D1%84%D0%BE%D1%82%D0%BE3/4.2.jpg)
![Меню](https://github.com/tplxv/hh/blob/%D1%84%D0%BE%D1%82%D0%BE3/4.3.jpg)
### Вывод
- Длина предложения: Программа вычисляет и выводит длину введённого предложения.
- Перевод в нижний регистр: Предложение преобразуется в нижний регистр и выводится на экран.
- Подсчет гласных: Программа подсчитывает количество гласных букв в предложении.
- Замена "ugly" на "beauty": Если в предложении есть слово "ugly", оно заменяется на "beauty", и результат отображается.
- Проверка на начало и конец: Проверяется, начинается ли предложение с "The" и заканчивается ли оно на "end". Результаты проверок выводятся.

### 5) Создайте два Python файла, в одном будет выполняться вычисление площади треугольника при помощи формулы Герона (необходимо реализовать через функцию), а во втором будет происходить взаимодействие с пользователем (получение всей необходимой информации и вывод результатов). Напишите эту программу и выведите в консоль полученную площадь.
```python
counter = 0
values = [0, 2, 4, 6, 8, 10]
string = 'hello'
memory = ' world'

while counter != 10:
    if counter in values:
        print(string + memory)
    else:
        print(string)

    counter += 1
```

### Результат
![Меню](https://github.com/tplxv/hh/blob/%D1%84%D0%BE%D1%82%D0%BE3/5.1.jpg)
### Вывод
- Инициализируем переменные counter, values, string и memory.
- Запускаем цикл while, который выполняется, пока counter не станет равен 10.
- Внутри цикла проверяем, находится ли текущее значение counter в списке values. Если да, то выводим "hello world", если нет — просто "hello".
- После каждой итерации увеличиваем значение counter.

  ## Вывод
- Операторы в Python делятся на семь типов: арифметические, сравнения, присваивания, битовые, логические, принадлежности и тождественности. 
- Битовые операторы, такие как побитовое И (&), ИЛИ (|), Исключающее ИЛИ (^), а также операторы сдвига (<<, >>) и побитовое отрицание (~), манипулируют двоичными представлениями чисел.
- Условные конструкции if, elif и else обеспечивают выполнение различного кода в зависимости от условий, в то время как циклы (например, цикл for) позволяют выполнять повторяющиеся операции для элементов последовательности.
- Функция range() используется для создания последовательностей чисел и может принимать один, два или три аргумента, позволяя задавать начало, конец и шаг. 
- Вложенные циклы, такие как while, позволяют выполнять повторяющиеся операции, зависящие от нескольких переменных. Однако использование вложенных циклов имеет свои недостатки: 
  1. Временная сложность: Увеличивает общее время выполнения программы.
  2. Ресурсоемкость: Требует больше памяти и процессорного времени.
  3. Читаемость кода: Усложняет понимание и поддержку кода.
  4. Вероятность ошибок: Увеличивает риск возникновения логических ошибок.
  5. Альтернативные решения: В некоторых случаях возможно использование более эффективных алгоритмов без вложенных циклов.

