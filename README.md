# Тема 3. Операторы, условия, циклы.
Отчет по теме 3 выполнила:
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

  ## Лабораторная работа №3
### 1) Создайте две переменные, значение которых будете вводить через консоль. Также составьте условие, в котором созданные ранее переменные будут сравниваться, если условие выполняется, то выведете в консоль «Выполняется», если нет, то «Не выполняется».
```python
one = int(input('Введите значение первой переменной: '))
two = int(input('Введите значиение второй переменной: '))
if one >= two:
    print('Выполняется')
else:
    print('Не выполняется')
```

### Результат
![Меню](https://github.com/tplxv/hh/blob/%D1%84%D0%BE%D1%82%D0%BE3/1.jpg)

### 2) Напишите программу, которая будет определять значения переменной меньше 0, больше 0 и меньше 10 или больше 10. Это нужно реализовать при помощи одной переменной, значение которой будет вводится через консоль, а также при помощи конструкций if, elif, else.
```python
one = int(input('Введите значение переменной: '))
if one < 0:
    print('Переменная меньше 0')
elif 0 < one < 10:
    print('Переменная больше 0 и меньше 10')
else:
    print('Переменная больше 10')
```

### Результат
![Меню](https://github.com/tplxv/hh/blob/%D1%84%D0%BE%D1%82%D0%BE3/2.jpg)

### 3) Напишите программу, в которой будет проверяться есть ли переменная в указанном массиве используя логический оператор in. Самостоятельно посмотрите, как работает программа со значениями которых нет в массиве numbers.
```python
num = [1, 3, 4, 6, 8 ,9]
value = int(input('Введите значение переменной: '))
if value in num:
     print('Переменная есть в данном массиве')
else:
     print('Переменной нет в этом массиве')
```

### Результат
![Меню](https://github.com/tplxv/hh/blob/%D1%84%D0%BE%D1%82%D0%BE3/3.jpg)

### 4) Напишите программу, которая будет определять находится ли переменная в указанном массиве и если да, то проверьте четная она или нет. Самостоятельно протестируйте данную программу с разными значениями переменной value.

```python
num = [1, 3, 4, 6, 8 ,9, 15, 16, 73, 321, 322]
value = int(input('Введите значение переменной: '))
if value in num:
     if value%2==0:
         print('Переменная четная и есть в данном массиве')
     else:
         print('Переменная нечетная и есть в данном массиве')
else:
     print(f"Переменной нет в массиве num и она равна{value}")
```

### Результат
![Меню](https://github.com/tplxv/hh/blob/%D1%84%D0%BE%D1%82%D0%BE3/4.jpg)

### 5) Напишите программу, в которой циклом for значения переменной i будут меняться от 0 до 10 и посмотрите, как разные виды сравнений и операций работают в цикле.
```python
for i in range(10):
      print('i= ', i)
      if i==0:
          i+=2
      if i==1:
          continue
      if i==2 or i==3:
          print('Переменная равна 2 или 3')
      elif i in [4, 5, 6]:
          print('Переменная равна 4, 5 или 6')
      else:
          break
```

### Результат
![Меню](https://github.com/tplxv/hh/blob/%D1%84%D0%BE%D1%82%D0%BE3/5.jpg)

### 6) Напишите программу, в которой при помощи цикла for определяется есть ли переменная value в строке string и посмотрите, как работает оператор else для циклов. Самостоятельно посмотрите, что выведет программа, если значение переменной value оказалось в строке string.
```python
s='Привет всем изучающим Python!'
value= input()
for i in s:
     if i==value:
           index = s.find(value)
           print(f"Буква '{value}' есть в строке под {index} индексом")
           break
else:
     print(f"Буквы '{value}' нет в указанной строке")
```

### Результат
![Меню](https://github.com/tplxv/hh/blob/%D1%84%D0%BE%D1%82%D0%BE3/6.jpg)

### 7) Напишите программу, в которой вы наглядно посмотрите, как работает цикл for проходя в обратном порядке, то есть, к примеру не от 0 до 10, а от 10 до 0. В уже готовой программе показано вычитание из 100, а вам во время реализации программы будет необходимо придумать свой вариант применения обратного цикла
```python
value = 100
for i in range(10, -1, -1):
      value -=i
      print(i, value)
```

### Результат
![Меню](https://github.com/tplxv/hh/blob/%D1%84%D0%BE%D1%82%D0%BE3/7.jpg)

### 8) Напишите программу используя цикл while, внутри которого есть какие-либо проверки, но быть осторожным, поскольку циклы while при неправильно написанных условиях могут становится бесконечными, как указано в примере далее.
```python
value = 0
while value < 100:
      if value ==0:
           value+=10
      elif value//5>1:
           value*=5
      else:
           value-=5
      print(value)
```

### Результат
![Меню](https://github.com/tplxv/hh/blob/%D1%84%D0%BE%D1%82%D0%BE3/8.jpg)

### 9) Напишите программу с использованием вложенных циклов и одной проверкой внутри них. Самое главное, не забудьте, что нельзя использовать одинаковые имена итерируемых переменных, когда вы используете вложенные циклы.
```python
value = 0
for i in range(10):
      for j in range(10:
           if i!=j:
                value+=j
           else:
                pass
print(value)
```

### Результат
![Меню](https://github.com/tplxv/hh/blob/%D1%84%D0%BE%D1%82%D0%BE3/9.jpg)

### 10) Напишите программу с использованием flag, которое будет определять есть ли нечетное число в массиве. В данной задаче flag выступает в роли индикатора встречи нечетного числа в исходном массиве, четных чисел.
```python
e_a=[2, 4, 6, 8, 9]
flag =false
for value in e_a:
      if value %2==1:
           flag=true
if flag is true:
      print('В массиве есть нечетное число')
else:
      print('В массиве все четные числа')
```

### Результат
![Меню](https://github.com/tplxv/hh/blob/%D1%84%D0%BE%D1%82%D0%BE3/10.jpg)

  ## Самостоятельная работа №3. 
### 1) Напишите программу, которая преобразует 1 в 31. Для выполнения поставленной задачи необходимо обязательно и только один раз использовать: Цикл for; *= 5; += 1. Никаких других действий или циклов использовать нельзя
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

### 2) Напишите программу, которая фразу «Hello World» выводит в обратном порядке, и каждая буква находится в одной строке консоли.
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

### 3) Напишите программу, на вход которой поступает значение из консоли, оно должно быть числовым и в диапазоне от 0 до 10 включительно (это необходимо учесть в программе). Если вводимое число не подходит по требованиям, то необходимо вывести оповещение об этом в консоль и остановить программу. Код должен вычислять в каком диапазоне находится полученное число. Нужно учитывать три диапазона: от 0 до 3 включительно; от 3 до 6; от 6 до 10 включительно. Результатом работы программы будет выведенный в консоль диапазон. Программа должна занимать не более 10 строчек в редакторе кода.
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

### 4) Манипулирование строками. Напишите программу на Python, которая принимает предложение (на английском) в качестве входных данных от пользователя. Выполните следующие операции и отобразите результаты: Выведите длину предложения; Переведите предложение в нижний регистр; Подсчитайте количество гласных (a, e, i, o, u) в предложении; Замените все слова "ugly" на "beauty"; Проверьте, начинается ли предложение с "The" и заканчивается ли на "end". Проверьте работу программы минимум на 3 предложениях, чтобы охватить проверку всех поставленных условий.

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

### 5) Составьте программу, результатом которой будет данный вывод в консоль: Программу нужно составить из данных фрагментов кода:
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

