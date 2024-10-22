# Тема 7.
Отчет по теме 6 выполнила:
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

  ## Лабораторная работа №7.
### 1) Составьте текстовый файл и положите его в одну директорию с
программой на Python. Текстовый файл должен состоять минимум из
двух строк.

### Результат
![Меню]()

### 2) Напишите программу, которая выведет только первую строку из вашего файла, при этом используйте конструкцию open()/close().
```python
f = open('input.txt', 'r')
print(f.readline())
f.close()
```

### Результат
![Меню]()

### 3) Напишите программу, которая выведет все строки из вашего файла в массиве, при этом используйте конструкцию open()/close().
```python
f = open('input.txt', 'r')
print(f.readlines())
f.close()
```

### Результат
![Меню]()

### 4) Напишите программу, которая выведет все строки из вашего файла в массиве, при этом используйте конструкцию with open().

```python
with open('input.txt') as f:
    print(f.readlines())
```

### Результат
![Меню]()

### 5) Напишите программу, которая выведет каждую строку из вашего файла отдельно, при этом используйте конструкцию with open().
```python
with open('input.txt') as f:
    for line in f:
        print(line)
```

### Результат
![Меню]()

### 6) Напишите программу, которая будет добавлять новую строку в ваш файл, а потом выведет полученный файл в консоль. Вывод можно осуществлять любым способом. Обязательно проверьте сам файл, чтобы изменения в нем тоже отображались.
```python
with open('input.txt', 'a+') as f:
    f.write('\nIm additional line')

with open('input.txt', 'r') as f:
    result = f.readlines()
    print(result)
```

### Результат
![Меню]()

### 7) Напишите программу, которая перепишет всю информацию, которая была у вас в файле до этого, например напишет любые данные из произвольно вами составленного списка. Также не забудьте проверить что измененная вами информация сохранилась в файле.
```python
lines = ['one', 'two', 'three']
with open('input.txt', 'w') as f:
    for line in lines:
        f.write('\nCycle run ' + line)
    print('Done!')
```


### Результат
![Меню]()

### 8) Выберите любую папку на своем компьютере, имеющую вложенные директории. Выведите на печать в терминал ее содержимое, как и всех подкаталогов при помощи функции print_docs(directory).
```python
import os

def print_docs(directory):
    all_files = os.walk(directory)
    for catalog in all_files:
        print(f'Папка {catalog[0]} содержит:')
        print(f'Директории: {", ".join([folder for folder in catalog[1]])}')
        print(f'Файлы: {", ".join([file for file in catalog[2]])}')
    print('-' * 48)


print_docs('C:/Users\dna5c\Загрузки')
```

### Результат
![Меню]()

### 9) Документ «input.txt» содержит следующий текст: 
### Приветствие
### Спасибо
### Извините
### Пожалуйста
### До свидания
### Ты готов?
### Как дела?
### С днем рождения!
### Удача!
### Я тебя люблю.
### Требуется реализовать функцию, которая выводит слово, имеющее максимальную длину (или список слов, если таковых несколько). Проверьте работоспособность программы на своем наборе данных
```python
def longest_words(file):
    with open(file, encoding='utf-8') as f:
        words = f.read().split()
        max_length = len(max(words, key=len))
        for word in words:
            if len(word) == max_length:
                sought_words = word

        if len(sought_words) == 1:
            return sought_words[0]
        return sought_words

print(longest_words('input.txt'))
```

### Результат
![Меню]()

### 10) Требуется создать csv-файл «rows_300.csv» со следующими столбцами:
### • № - номер по порядку (от 1 до 300);
### • Секунда – текущая секунда на вашем ПК;
### • Микросекунда – текущая миллисекунда на часах.
### Для наглядности на каждой итерации цикла искусственно приостанавливайте скрипт на 0,01 секунды.
```python
import csv
import datetime
import time

with open('rows_300.csv', 'w', encoding='utf-8', newline='') as f:
    writer = csv.writer(f)
    writer.writerow(['№', 'Секунда', 'Микросекунда'])
    for line in range(1, 301):
        writer.writerow([line, datetime.datetime.now().second,
                         datetime.datetime.now().microsecond])
        time.sleep(0.01)
```

### Результат
![Меню]()

  ## Самостоятельная работа №7. 
### 1) Найдите в интернете любую статью (объем статьи не менее 200 слов), скопируйте ее содержимое в файл и напишите программу, которая считает количество слов в текстовом файле и определит самое часто встречающееся слово. Результатом выполнения задачи будет: скриншот файла со статьей, листинг кода, и вывод в консоль, в котором будет указана вся необходимая информация.
```python
from collections import Counter
import re

def count_words_in_file(filename):
    with open(filename, 'r', encoding='utf-8') as file:
        text = file.read().lower()
        words = re.findall(r'\b\w+\b', text)
        word_count = Counter(words)
        most_common_word = word_count.most_common(1)[0]
    return len(words), most_common_word

total_words, most_common_word = count_words_in_file("input.txt")
print(f"Общее количество слов: {total_words}")
print(f"Самое частое слово: '{most_common_word[0]}', количество вхождений: {most_common_word[1]}")

```

### Результат
![Меню]()
### Вывод
- text = file.read().lower() Читаем файл и приводим текст к нижнему регистру
- words = re.findall(r'\b\w+\b', text) Используем регулярное выражение для поиска слов
- word_count = Counter(words) Подсчитываем количество вхождений каждого слова
- most_common_word = word_count.most_common(1)[0] Находим самое частое слово

### 2) У вас появилась потребность в ведении книги расходов, посмотрев все существующие варианты вы пришли к выводу что вас ничего не устраивает и нужно все делать самому. Напишите программу для учета расходов. Программа должна позволять вводить информацию о расходах, сохранять ее в файл и выводить существующие данные в консоль. Ввод информации происходит через консоль. Результатом выполнения задачи будет: скриншот файла с учетом расходов, листинг кода, и вывод в консоль, с демонстрацией работоспособности программы.
```python
def add_expense(filename):
    with open(filename, 'a', encoding='utf-8') as file:
        expense = input("Введите описание расхода и сумму: ")
        file.write(expense + "\n")

def show_expenses(filename):
    with open(filename, 'r', encoding='utf-8') as file:
        expenses = file.readlines()
        if expenses:
            print("Ваши расходы:")
            for expense in expenses:
                print(expense.strip())
        else:
            print("Расходов нет.")

add_expense("expenses.txt")
add_expense("expenses.txt")
add_expense("expenses.txt")
show_expenses("expenses.txt")
```

### Результат
![Меню]()
### Вывод
- file.write(expense + "\n") Записываем строку в файл
- print(expense.strip()) Выводим каждую строку

### 3) Имеется файл input.txt с текстом на латинице. Напишите программу, которая выводит следующую статистику по тексту: количество букв латинского алфавита; число слов; число строк.
### • Текст в файле:
### Beautiful is better than ugly.
### Explicit is better than implicit.
### Simple is better than complex.
### Complex is better than complicated.
### • Ожидаемый результат:
### Input file contains:
### 108 letters
### 20 words
### 4 lines
```python
import re

def text_statistics(filename):
    with open(filename, 'r', encoding='utf-8') as file:
        lines = file.readlines()
        num_lines = len(lines)
        num_words = 0
        num_letters = 0

        for line in lines:
            words = line.split()
            num_words += len(words)
            num_letters += len(re.findall(r'[a-zA-Z]', line))

        print(f"Количество букв латинского алфавита: {num_letters}")
        print(f"Количество слов: {num_words}")
        print(f"Количество строк: {num_lines}")

text_statistics("input.txt")
```

### Результат
![Меню]()

### Вывод
- lines = file.readlines() Читаем все строки файла
- words = line.split() Разбиваем строку на слова
- num_words += len(words) Считаем слова
- num_letters += len(re.findall(r'[a-zA-Z]', line)) Используем регулярное выражение для поиска латинских букв

### 4) Напишите программу, которая получает на вход предложение, выводит его в терминал, заменяя все запрещенные слова звездочками * (количество звездочек равно количеству букв в слове). Запрещенные слова, разделенные символом пробела, хранятся в текстовом файле input.txt. Все слова в этом файле записаны в нижнем регистре. Программа должна заменить запрещенные слова, где бы они ни встречались, даже в середине другого слова. Замена производится независимо от регистра: если файл input.txt содержит запрещенное слово exam, то слова exam, Exam, ExaM, EXAM и exAm должны быть заменены на ****.
### • Запрещенные слова:
### hello email python the exam wor is
### • Предложение для проверки:
### Hello, world! Python IS the programming language of thE future. My EMAIL is.... PYTHON is awesome!!!!
### • Ожидаемый результат:
### *****, ***ld! ****** ** *** programming language of *** future. My ***** **.... ****** ** awesome!!!!
```python
import re

def load_forbidden_words(filename):
    with open(filename, 'r', encoding='utf-8') as file:
        forbidden_words = file.read().split()
    return forbidden_words

def censor_sentence(sentence, forbidden_words):
    for word in forbidden_words:
        pattern = re.compile(re.escape(word), re.IGNORECASE)
        sentence = pattern.sub('*' * len(word), sentence)
    return sentence

forbidden_words = load_forbidden_words("input.txt")

sentence = input("Введите предложение для проверки: ")

censored_sentence = censor_sentence(sentence, forbidden_words)

print("Результат:", censored_sentence)
```

### Результат
![Меню]()

### Вывод
- forbidden_words = file.read().split() Чтение и разбиение строки на слова
- pattern = re.compile(re.escape(word), re.IGNORECASE) Создаем регулярное выражение для поиска запрещенных слов независимо от регистра
- sentence = pattern.sub('*' * len(word), sentence) Замена на звездочки
- forbidden_words = load_forbidden_words("input.txt") Чтение списка запрещённых слов из файла
### 5) Напишите программу, которая позволяет пользователю сохранять текстовые заметки в файл и выводить их содержимое. Программа должна поддерживать следующие функции:
### 1. Добавление новой заметки.
### 2. Вывод всех заметок.
### 3. Поиск заметок по ключевым словам.
```python
def add_note(file_name):
    note = input("Введите вашу заметку: ")
    with open(file_name, 'a', encoding='utf-8') as file:
        file.write(note + '\n')
    print("Заметка добавлена!")

def show_notes(file_name):
    try:
        with open(file_name, 'r', encoding='utf-8') as file:
            notes = file.readlines()
            if notes:
                print("\nСписок всех заметок:")
                for i, note in enumerate(notes, start=1):
                    print(f"{i}. {note.strip()}")
            else:
                print("Заметок нет.")
    except FileNotFoundError:
        print("Файл с заметками не найден.")

def search_notes(file_name):
    keyword = input("Введите ключевое слово для поиска: ")
    try:
        with open(file_name, 'r', encoding='utf-8') as file:
            notes = file.readlines()
            found_notes = [note for note in notes if keyword.lower() in note.lower()]
            if found_notes:
                print("\nНайденные заметки:")
                for i, note in enumerate(found_notes, start=1):
                    print(f"{i}. {note.strip()}")
            else:
                print("Заметки не найдены.")
    except FileNotFoundError:
        print("Файл с заметками не найден.")

def main():
    file_name = 'notes.txt'

    while True:
        print("\nВыберите опцию:")
        print("1. Добавить заметку")
        print("2. Показать все заметки")
        print("3. Искать заметки по ключевым словам")
        print("4. Выйти")

        choice = input("Ваш выбор: ")

        if choice == '1':
            add_note(file_name)
        elif choice == '2':
            show_notes(file_name)
        elif choice == '3':
            search_notes(file_name)
        elif choice == '4':
            print("Выход из программы.")
            break
        else:
            print("Неверный выбор. Попробуйте снова.")

# Запуск программы
if __name__ == "__main__":
    main()

```

### Результат
![Меню]()
### Вывод
1. Добавление заметок: Пользователь может ввести текст заметки, и она будет добавлена в файл notes.txt.
2. Вывод всех заметок: Программа считывает все заметки из файла и отображает их.
3. Поиск заметок по ключевым словам: Пользователь вводит ключевое слово, и программа находит все заметки, которые содержат это слово.
4. Программа будет работать в цикле до тех пор, пока пользователь не решит выйти.

  ## Вывод

