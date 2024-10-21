# Тема 8. Введение в ООП.
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


знак "+" - задание выполнено; знак "-" - задание не выполнено;

Работу проверили:
- к.э.н., доцент Панов М.А.

  ## Лабораторная работа №8.
### 1) Создайте класс “Car” с атрибутами производитель и модель. Создайте объект этого класса. Напишите комментарии для кода, объясняющие его работу. Результатом выполнения задания будет листинг кода с комментариями.
```python
class Car:  # Определение класса Car, который моделирует автомобиль.
    def __init__(self, make, model):  # Метод инициализации, который вызывается при создании нового объекта класса Car.
        self.make = make  # Присваивание значения марки автомобиля атрибуту экземпляра
        self.model = model  # Присваивание значения модели автомобиля атрибуту экземпляра

# Создание экземпляра класса Car с маркой "Toyota" и моделью "Corolla".
my_car = Car("Toyota", "Corolla")
```

### Результат
![Меню]()

### 2) Дополните код из первого задания, добавив в него атрибуты и методы класса, заставьте машину “поехать”. Напишите комментарии для кода, объясняющие его работу. Результатом выполнения задания будет листинг кода с комментариями и получившийся вывод в консоль.
```python
class Car:  # Определение класса Car, который моделирует автомобиль.
    def __init__(self, make, model):  # Метод инициализации, который вызывается при создании нового объекта класса Car.
        self.make = make  # Присваивание значения марки автомобиля атрибуту экземпляра.
        self.model = model  # Присваивание значения модели автомобиля атрибуту экземпляра.

    def drive(self):  # Метод, который описывает действие вождения автомобиля.
        print(f"Driving the {self.make} {self.model}")  # Выводит информацию о том, что автомобиль марки make и модели model движется.

# Создание экземпляра класса Car с маркой "Toyota" и моделью "Corolla".
my_car = Car("Toyota", "Corolla")
# Вызов метода drive() для объекта my_car, который печатает информацию о вождении автомобиля.
my_car.drive()

```

### Результат
![Меню]()

### 3) Создайте новый класс “ElectricCar” с методом “charge” и атрибутом емкость батареи. Реализуйте его наследование от класса, созданного в первом задании. Заставьте машину поехать, а потом заряжаться. Напишите комментарии для кода, объясняющие его работу. Результатом выполнения задания будет листинг кода с комментариями и получившийся вывод в консоль.
```python
class Car:  # Определение класса Car, который моделирует обычный автомобиль.
    def __init__(self, make, model):  # Метод инициализации, вызываемый при создании нового объекта класса Car.
        self.make = make  # Присваивание значения марки автомобиля атрибуту экземпляра.
        self.model = model  # Присваивание значения модели автомобиля атрибуту экземпляра.

    def drive(self):  # Метод, который описывает действие вождения автомобиля.
        print(f"Driving the {self.make} {self.model}")  # Выводит информацию о том, что автомобиль марки make и модели model движется.

# Создание экземпляра класса Car с маркой "Toyota" и моделью "Corolla".
my_car = Car("Toyota", "Corolla")

# Вызов метода drive() для объекта my_car, который печатает информацию о вождении автомобиля.
my_car.drive()

class ElectricCar(Car):  # Определение класса ElectricCar, который наследует от класса Car.
    def __init__(self, make, model, battery_capacity):  # Метод инициализации для электрического автомобиля.
        super().__init__(make, model)  # Вызов метода инициализации родительского класса (Car) для установки марки и модели.
        self.battery_capacity = battery_capacity  # Присваивание значения ёмкости батареи атрибуту экземпляра.

    def charge(self):  # Метод, который описывает процесс зарядки электрического автомобиля.
        print(f"Charging the {self.make} {self.model} with {self.battery_capacity} kWh")  # Выводит информацию о зарядке автомобиля с его маркой, моделью и ёмкостью батареи.

# Создание экземпляра класса ElectricCar с маркой "Tesla", моделью "Model S" и ёмкостью батареи 75 кВтч.
my_electric_car = ElectricCar("Tesla", "Model S", 75)

# Вызов метода drive() для объекта my_electric_car, который печатает информацию о вождении электрического автомобиля.
my_electric_car.drive()

# Вызов метода charge() для объекта my_electric_car, который печатает информацию о зарядке электрического автомобиля.
my_electric_car.charge()
```

### Результат
![Меню]()

### 4) Реализуйте инкапсуляцию для класса, созданного в первом задании. Создайте защищенный атрибут производителя и приватный атрибут модели. Вызовите защищенный атрибут и заставьте машину поехать. Напишите комментарии для кода, объясняющие его работу. Результатом выполнения задания будет листинг кода с комментариями и получившийся вывод в консоль.

```python
class Car:  # Определение класса Car, который моделирует обычный автомобиль.
    def __init__(self, make, model):  # Метод инициализации, вызываемый при создании нового объекта класса Car.
        self._make = make  # Присваивание значения марки автомобиля (make) защищённому атрибуту экземпляра self._make.
        self.__model = model  # Присваивание значения модели автомобиля (model) приватному атрибуту экземпляра self.__model.

    def drive(self):  # Метод, который описывает действие вождения автомобиля.
        print(f"Driving the {self._make} {self.__model}")  # Выводит информацию о том, что автомобиль марки _make и модели __model движется.

# Создание экземпляра класса Car с маркой "Toyota" и моделью "Corolla".
my_car = Car("Toyota", "Corolla")

# Вывод защищённого атрибута _make. 
print(my_car._make)  # Печатает марку автомобиля, которая доступна через защищённый атрибут.

# Вызов метода drive() для объекта my_car, который печатает информацию о вождении автомобиля.
my_car.drive()
```

### Результат
![Меню]()

### 5) Реализуйте полиморфизм создав основной (общий) класс “Shape”, а также еще два класса “Rectangle” и “Circle”. Внутри последних двух классов реализуйте методы для подсчета площади фигуры. После этого создайте массив с фигурами, поместите туда круг и прямоугольник, затем при помощи цикла выведите их площади. Напишите комментарии для кода, объясняющие его работу. Результатом выполнения задания будет листинг кода с комментариями и получившийся вывод в консоль.
```python
class Share:  # Определение абстрактного класса Share, который будет использоваться в качестве базового класса для других фигур.
    def area(self):  # Абстрактный метод, который должен быть переопределён в подклассах для вычисления площади.
        pass  # Метод не реализован в базовом классе; его необходимо реализовать в классах-наследниках.

class Rectangle(Share):  # Класс Rectangle, наследуемый от класса Share, моделирует прямоугольник.
    def __init__(self, width, height):  # Метод инициализации, принимающий ширину и высоту прямоугольника.
        self.width = width  # Присваивание значения ширины атрибуту width экземпляра.
        self.height = height  # Присваивание значения высоты атрибуту height экземпляра.

    def area(self):  # Переопределение метода area для вычисления площади прямоугольника.
        return self.width * self.height  # Возвращает площадь, умножая ширину на высоту.

class Circle(Share):  # Класс Circle, наследуемый от класса Share, моделирует круг.
    def __init__(self, radius):  # Метод инициализации, принимающий радиус круга.
        self.radius = radius  # Присваивание значения радиуса атрибуту radius экземпляра.

    def area(self):  # Переопределение метода area для вычисления площади круга.
        return 3.14 * self.radius * self.radius  # Возвращает площадь, используя формулу πr², где π приближено как 3.14.
shapes= [Rectangle(4,5), Circle(3)]
for shape in shapes:
    print(shape.area())
```

### Результат
![Меню]()


  ## Самостоятельная работа №8. 
### 1) Самостоятельно создайте класс и его объект. Они должны отличаться, от тех, что указаны в теоретическом материале (методичке) и лабораторных заданиях. Результатом выполнения задания будет листинг кода и получившийся вывод консоли
```python
class Book:
    def __init__(self, title, author, year):
        self.title = title
        self.author = author
        self.year = year

    def get_info(self):
        return f'"{self.title}" by {self.author}, published in {self.year}'

my_book = Book("1984", "George Orwell", 1949)
print(my_book.get_info())
```

### Результат
![Меню]()
### Вывод

### 2) Самостоятельно создайте атрибуты и методы для ранее созданного класса. Они должны отличаться, от тех, что указаны в теоретическом материале (методичке) и лабораторных заданиях. Результатом выполнения задания будет листинг кода и получившийся вывод консоли.
```python
class Book:
    def __init__(self, title, author, year, genre, pages):
        self.title = title
        self.author = author
        self.year = year
        self.genre = genre
        self.pages = pages
        self.rating = None

    def get_info(self):
        return f'"{self.title}" by {self.author}, published in {self.year}, Genre: {self.genre}, Pages: {self.pages}'

    def rate_book(self, rating):
        if 0 <= rating <= 5:
            self.rating = rating
            return f'Book rated with {self.rating}/5 stars.'
        else:
            return 'Rating must be between 0 and 5.'

    def get_rating(self):
        return self.rating if self.rating is not None else 'No rating yet'

my_book = Book("1984", "George Orwell", 1949, "Dystopian", 328)
print(my_book.get_info())
print(my_book.rate_book(5))
print(f'Rating: {my_book.get_rating()}')
```

### Результат
![Меню]()
### Вывод


### 3) Самостоятельно реализуйте наследование, продолжая работать с ранее созданным классом. Оно должно отличаться, от того, что указано в теоретическом материале (методичке) и лабораторных заданиях. Результатом выполнения задания будет листинг кода и получившийся вывод консоли.
```python
class Book:
    def __init__(self, title, author, year, genre, pages):
        self.title = title
        self.author = author
        self.year = year
        self.genre = genre
        self.pages = pages
        self.rating = None

    def get_info(self):
        return f'"{self.title}" by {self.author}, published in {self.year}, Genre: {self.genre}, Pages: {self.pages}'

    def rate_book(self, rating):
        if 0 <= rating <= 5:
            self.rating = rating
            return f'Book rated with {self.rating}/5 stars.'
        else:
            return 'Rating must be between 0 and 5.'

    def get_rating(self):
        return self.rating if self.rating is not None else 'No rating yet'


class EBook(Book):
    def __init__(self, title, author, year, genre, pages, file_size):
        super().__init__(title, author, year, genre, pages)
        self.file_size = file_size

    def get_info(self):
        return super().get_info() + f', File size: {self.file_size} MB'

my_ebook = EBook("Sapiens: A Brief History of Humankind", "Yuval Noah Harari", 2011, "Non-fiction", 443, 1.2)

print(my_ebook.get_info())
print(my_ebook.rate_book(5))
print(f'Rating: {my_ebook.get_rating()}')
```

### Результат
![Меню]()

### Вывод


### 4) Самостоятельно реализуйте инкапсуляцию, продолжая работать с ранее созданным классом. Она должна отличаться, от того, что указана в теоретическом материале (методичке) и лабораторных заданиях. Результатом выполнения задания будет листинг кода и получившийся вывод консоли

```python
class Book:
    def __init__(self, title, author, year, genre, pages):
        self.__title = title  # Приватный атрибут
        self.__author = author  # Приватный атрибут
        self.__year = year  # Приватный атрибут
        self.__genre = genre  # Приватный атрибут
        self.__pages = pages  # Приватный атрибут
        self.__rating = None  # Приватный атрибут

    # Геттер для названия книги
    @property
    def title(self):
        return self.__title

    # Геттер для автора книги
    @property
    def author(self):
        return self.__author

    def get_info(self):
        return f'"{self.__title}" by {self.__author}, published in {self.__year}, Genre: {self.__genre}, Pages: {self.__pages}'

    def rate_book(self, rating):
        if 0 <= rating <= 5:
            self.__rating = rating
            return f'Book rated with {self.__rating}/5 stars.'
        else:
            return 'Rating must be between 0 and 5.'

    # Геттер для рейтинга книги
    @property
    def rating(self):
        return self.__rating if self.__rating is not None else 'No rating yet'


class EBook(Book):
    def __init__(self, title, author, year, genre, pages, file_size):
        super().__init__(title, author, year, genre, pages)
        self.__file_size = file_size 

    def get_info(self):
        return super().get_info() + f', File size: {self.__file_size} MB'

my_ebook = EBook("Sapiens: A Brief History of Humankind", "Yuval Noah Harari", 2011, "Non-fiction", 443, 1.2)

print(my_ebook.get_info())
print(my_ebook.rate_book(5))
print(f'Rating: {my_ebook.rating}')
```

### Результат
![Меню]()

### Вывод

### 5) Самостоятельно реализуйте полиморфизм. Он должен отличаться, от того, что указан в теоретическом материале (методичке) и лабораторных заданиях. Результатом выполнения задания будет листинг кода и получившийся вывод консоли.
```python
class Animal:
    def speak(self):
        raise NotImplementedError("Subclasses must implement this method")

class Dog(Animal):
    def speak(self):
        return "Гав!"

class Cat(Animal):
    def speak(self):
        return "Мяу!"

class Cow(Animal):
    def speak(self):
        return "Муу!"

def animal_sound(animal):
    print(animal.speak())

if __name__ == "__main__":
    animals = [Dog(), Cat(), Cow()]
    for animal in animals:
        animal_sound(animal)
```

### Результат
![Меню]()
### Вывод


  ## Вывод

