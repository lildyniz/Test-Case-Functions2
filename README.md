#### Задача 1. Разработайте функцию, которая принимает целое число в качестве аргумента и возвращает строку, содержащую это число и слово "компьютер" в нужном склонении по падежам в зависимости от числа. Например, при вводе числа 25 функция должна возвращать "25 компьютеров", для числа 41 — "41 компьютер", а для числа 1048 — "1048 компьютеров".
```
def declension(num):
   if num % 10 == 1 and num % 100 != 11:
       return f"{num} компьютер"
   elif num % 10 in [2, 3, 4] and num % 100 not in [12, 13, 14]:
       return f"{num} компьютера"
   else:
       return f"{num} компьютеров"
```

#### Задача 2. Написать функцию/метод, которая на вход получает массив положительных целых чисел произвольной длины. 
Например `[42, 12, 18]`. На выходе возвращает массив чисел, которые являются общими делителями для всех указанных числе. В примере это будет `[2, 3, 6]`.
```
def find_divisors(nums):
    if not nums:
      return []

    def gcd(a, b):
        while b:
            a, b = b, a % b
        return a

    divisor = nums[0]
    for num in nums[1:]:
        divisor = gcd(divisor, num)

    divisors = []
    for i in range(2, divisor + 1):
        if divisor % i == 0:
            divisors.append(i)

    return divisors
```

#### Задача 3. Написать функцию/метод, которая возвращает массив простых чисел в диапазоне (2 числа - минимальное и максимальное) заданных чисел.
Например, на вход переданы 2 числа: от 11 до 20  (диапазон считается включая граничные значения).
```
def prime_numbers(minimum, maximum):
    prime_numbers = []
    for number in range(minimum, maximum + 1):
        if number > 1:
            prime = True
            for divisor in range(2, int(number ** 0.5) + 1):
                if number % divisor == 0:
                    prime = False
                    break
            if prime:
                prime_numbers.append(number)
    return prime_numbers
```

#### Задача 4. Написать метод, который в консоль выводит таблицу умножения. На вход метод получает число, до которого выводит таблицу умножения. В консоли должна появиться таблица. 
```
def multiplication_table(number):
    print(" ", end=" ")
    for i in range(1, number + 1):
        print(f"{i:2}", end=" ")
    print()
    
    # Печать таблицы умножения
    for i in range(1, number + 1):
        print(f"{i:2}", end=" ")
        for j in range(1, number + 1):
            print(f"{i * j:2}", end=" ")
        print()
```
