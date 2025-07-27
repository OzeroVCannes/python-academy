# Решения заданий тренажёра от [PYTHON ACADEMY](https://python-academy.org)




<h3><br>1. Произведение элементов массива</br></h3>

```python
num = input().split()
print(eval("*".join(num)))
```




<h3><br>2. Количество уникальных значений</br></h3>

```python
num = list(map(int, input().split()))
print(len(set(num)))
```




<h3><br>3. Поиск второго максимума</br></h3>

```python
n = int(input())
sc = list(map(int, input().split()))

print(sorted(list(set(sc)))[-2])
```




<h3><br>4. Средний балл студента</br></h3>

```python
n = int(input())
students = {}
for _ in range(n):
    line = input().split()
    name = line[0]  
    marks = list(map(float, line[1:]))
    students[name] = marks
    
std_nm = input()

z = sum(students[std_nm])/3
print(f"{z:.2f}")
```




<h3><br>5. Сжатие последовательностей</br></h3>

```python
s = [int(k) for k in input()]

ans = []
tv = []
ln = len(s)
k = 0
ci = s[0]
for ii, i in enumerate(s):
    if ci == i:
        k += 1
        if ii == ln-1:
            ans = (k, ci)
            tv.append(ans)
    else:
        ans = (k, ci)
        ci = i
        k = 1
        tv.append(ans)
        if ii == ln-1:
            ans = (k, ci)
            tv.append(ans)
print(*tv)
```




<h3><br>6. Инверсия регистра</br></h3>

```python
s = input()
ans = ""

for i in s:
    if i.isalpha():
        if i.isupper():
            ans += i.lower()
        else:
            ans += i.upper()
    else:
        ans += i

print(ans)
```




<h3><br>10. День недели</br></h3>

```python
import calendar

date_input = input().split()
m = int(date_input[0])
d = int(date_input[1])
y = int(date_input[2])
z = calendar.weekday(y, m, d)
print(calendar.day_name[z].upper())
```




<h3><br>12. Проверка Email-адреса</br></h3>

```python
def is_valid_email(s):
    
    if not "@" in s:
        return False
    e = s.split("@")
    if not "." in e[1]:
        return False
    us = e[0]
    if not us.replace("_", "").replace("-", "").isalnum():
        return False
    p2 = e[1].split(".")
    st = p2[0]
    if not st.isalnum():
        return False
    rs = p2[1]
    if len(rs) > 3 or not rs.isalpha():
        return False
    return True

email = input().strip()
result = is_valid_email(email)
print(result)
```




<h3><br>13. Извлечение CSS цветов</br></h3>

```python

from re import findall, I

def css_extractor(c):
    z = findall(r'(#[0-9A-Z]{3}|#[0-9A-Z]{6})[,|\)|;]', c, I)
    for a in z:
        print(a)
    
n = int(input())
css_code = ""
for _ in range(n):
    css_code += input() + "\n"

css_extractor(css_code)
```




<h3><br>15. Нахождение Медианы</br></h3>

```python
def find_median(inp):
    inp = sorted(inp)
    ln = len(inp)
    if ln % 2 == 0:
        n1 = ln // 2
        res = (inp[n1] + inp[(n1 - 1)]) / 2
        if res % 2 == 0:
            return int(res)
        else:
            return round(res, 1)
    else:
        return int(inp[(ln // 2)])

go = list(map(int, input().strip().split()))
result = find_median(go)
print(result)
```




<h3><br>17. Проверка на палиндром</br></h3>

```python
def is_palindrome(t):
    if t == t[::-1]:
        return True
    else:
        return False


input_text = input().strip().lower()
result = is_palindrome(input_text)
print(result)
```




<h3><br>18. Транспонирование матрицы</br></h3>

```python
def transpose_matrix(mr):
    z = [[0 for k in range(n)] for i in range(m)]
    for i, a in enumerate(mr):
        for j, b in enumerate(a):
            z[j][i] = b
    return z

n, m = map(int, input().strip().split())
matrix = []
for _ in range(n):
    row = list(map(int, input().strip().split()))
    matrix.append(row)
result = transpose_matrix(matrix)

for row in result:
    print(' '.join(map(str, row)))
```




<h3><br>19. FizzBuzz</br></h3>

```python
def fizzbuzz(n):
    ans = []
    for i in range(1, n + 1):
        if i % 3 == 0 and i % 5 == 0:
            ans.append("FizzBuzz")
        elif i % 3 == 0:
            ans.append("Fizz")
        elif i % 5 == 0:
            ans.append("Buzz")
        else:
            ans.append(i)
    return "\n".join(map(str, ans))
            
            
n = int(input().strip())
print(fizzbuzz(n))
```




<h3><br>20. Минимальная амплитуда</br></h3>

```python
def min_amplitude(a):
    ar = sorted(a)
    ampl = []
    if len(a) > 4:
        for i in [[0, 1, 2], [-1, 0, 1], [-2, -1, 0], [-3, -2, -1]]:
            r = [ar[j] for j in i]
            b = [k for k in ar if k not in r]
            if len(b) > 1:
                ampl.append(b[-1] - b[0])
            elif len(b) == 1:
                ampl.append(b[0])
            else:
                ampl.append(0)
    elif len(a) == 4:
        return abs(min(a))
    else:
        return 0
    return min(ampl)
    

arr = list(map(int, input().strip().split()))
result = min_amplitude(arr)
print(result)
```




<h3><br>22. Реализация класса Counter</br></h3>

```python
class Counter:
    def __init__(self):
        self.x = 0
    
    def increase(self, amount=1):
        self.x += amount
        
    def decrease(self, amount=1):
        self.x -= amount
        
    def getValue(self):
        return self.x
```




<h3><br>23. Реализация класса BankAccount</br></h3>

```python
class BankAccount:
    def __init__(self, x=0):
        if x < 0:
            raise ValueError("Initial balance cannot be negative")
        self.x = x
    
    def deposit(self, amount):
        if amount <= 0:
            raise ValueError("Deposit amount must be positive")
        self.x += amount
        return self.x
        
    def withdraw(self, amount):
        if amount <= 0:
            raise ValueError("Withdrawal amount must be positive")
        if amount > self.x:
            raise ValueError("Insufficient funds")
        self.x -= amount
        return self.x
        
    def get_balance(self):
        return self.x
        
    def transfer(self, target_account, amount):
        if not isinstance(target_account, BankAccount):
            raise TypeError("Target must be a BankAccount")
        try:
            self.withdraw(amount)
            target_account.deposit(amount)
            return self.get_balance()
        except ValueError as e:
            return e
        
account = BankAccount(100)
print(account.get_balance())
account.deposit(50)
print(account.get_balance())
account.withdraw(30)
print(account.get_balance())
```




<h3><br>24. Проверка анаграмм</br></h3>

```python
def is_anagram(a, b):
    a = a.replace(" ", "")
    b = b.replace(" ", "")
    return sorted(list(a.lower())) == sorted(list(b.lower()))

word1 = input().strip()
word2 = input().strip()
result = is_anagram(word1, word2)
print(str(result).lower())
```




<h3><br>25. Треугольник Паскаля</br></h3>

```python
def generate_pascal_triangle(n):
    ans = []
    p = []
    for i in range(n):
        c = [0 for z in range(i+1)]
        for j in range(i+1):
            if j == 0 or j == i:
                c[j] = 1
                continue
            c[j] = p[j] + p[j-1]
        p = c
        ans.append(c)
    return ans
            
num_rows = int(input().strip())
result = generate_pascal_triangle(num_rows)
for row in result:
    print(row)
```




<h3><br>26. Делимость на свои цифры</br></h3>

```python
def is_divisible_by_digits(n):
    s = str(n)
    for i in s:
        if i == "0":
            continue
        elif n % int(i) != 0:
            return False
    else:
        return True
        

number = int(input().strip())
result = is_divisible_by_digits(number)
print(str(result))
```




<h3><br>27. Размещение видеорекламы</br></h3>

```python
def can_place_video_ads(fi, n):
    ind = [i for i, k in enumerate(fi) if k == 0]
    ln = len(ind)
    if ln > 0:
        o = ind[0]
        z = 0
        for a in ind[1:]:
            if a == o + 1:
                z += 1
            o = a
        for b in [0, -1]:
            if fi[b] == 0:
                z += 1
        return True if z >= n else False
    else:
        return False

feed_items_input = input().strip()
n = int(input().strip())

feed_items = list(map(int, feed_items_input.strip('[]').split(',')))

result = can_place_video_ads(feed_items, n)
print(str(result))
```




<h3><br>28. Римские числа</br></h3>

```python
def roman_to_int(s):
    s = list(s)
    ans = []
    d = {
        "I": 1,
        "V": 5,
        "X": 10,
        "L": 50,
        "C": 100,
        "D": 500,
        "M": 1000
    }
    for i, j in enumerate(s):
        ln = len(s)
        if i >= ln - 1:
            ans.append(d[j])
            break
        if d[j] < d[s[i+1]]:
            ans.append(d[s[i+1]] - d[j])
            del s[i]
        else:
            ans.append(d[j])
            
    return sum(ans)

roman_numeral = input().strip()
result = roman_to_int(roman_numeral)
print(result)
```




<h3><br>29. Самая длинная последовательность</br></h3>

```python
from itertools import groupby

def longest_consecutive(n):
    nn = [(i, j) for i, j in enumerate(sorted(set(n)))]
    z = groupby(nn, key=lambda x: x[1] - x[0])
    p = [[k[1] for k in list(i[1])] for i in z]
    ln = [len(i) for i in p]
    return max(ln)

nums = list(map(int, input().strip().split()))
result = longest_consecutive(nums)
print(result)
```




<h3><br>30. Подарочные карты</br></h3>

```python
def max_satisfied_teammates(n, m):
    ans = []
    nn = sorted(n)[::-1]
    mm = sorted(m)[::-1]
    for i in nn:
        for j in mm:
            if j >= i:
                ans.append(j)
                del mm[mm.index(j)]
    return len(ans)
    
expectations = list(map(int, input().strip().split()))
cards = list(map(int, input().strip().split()))
result = max_satisfied_teammates(expectations, cards)
print(result)
```




<h3><br>31. Преобразование в систему счисления с основанием 13</br></h3>

```python
def to_base13(n):
    d = {10: "A", 11: "B", 12: "C"}
    z = n % 13
    c = n // 13
    y = str(z) if z < 10 or z > 13 else d[z]
    if c > 9:
        return to_base13(c) + y
    return (str(c) if c > 0 else "") + y

num = int(input().strip())
result = to_base13(num)
print(result)
```




<h3><br>32. Плоский список</br></h3>

```python
def flat(r):
    ans = []
    for i in r:
        if len(i) > 1:
        
            for ii in i:
                ans.append(ii)
        else:
            ans.extend(i)
    return ans

import ast
input_str = input().strip()
arr = ast.literal_eval(input_str)
result = flat(arr)
print(result)
```




<h3><br>33. Подсчет частоты слов</br></h3>

```python
def word_frequency(t, n):
    t = t.replace(".", "").replace(",", "").replace("!", "").lower().split()
    unic = list(set(t))
    z = []
    for i in unic:
        if i not in z:
            tp = t.count(i)
            z.append((i, tp))
    zz = sorted(z, key=lambda x: (-x[1], x[0]))
    return zz[:n]
text = input().strip()
n = int(input().strip())
result = word_frequency(text, n)
print(result)
```




<h3><br>34. Самые частые элементы</br></h3>

```python
def top_k_frequent(nm, k):
    vs = [(i, nm.count(i)) for i in set(nm)]
    sr = sorted(vs, key=lambda x: -x[1])
    return sorted([i[0] for i in sr[:k]])
    
nums = list(map(int, input().strip().split()))
k = int(input().strip())
result = top_k_frequent(nums, k)
print(result)
```




<h3><br>35. Группировка анаграмм</br></h3>

```python
from itertools import groupby

def group_anagrams(w):
    z = [sorted(list(k)) for i, k in groupby(w, key=lambda x: set(x))]
    return z

import ast
input_str = input().strip()
words = ast.literal_eval(input_str)
result = group_anagrams(words)
print(result)
```




<h3><br>
36. Самый популярный город</br></h3>

```python
def most_popular_city(v):
    
    vv = ", ".join(v)        
    twn = vv.split(", ")[::2]
    d = {}
    top = twn[0]
    mx = 0
    for i in twn:
        if i not in d:
            cnt = vv.count(i)
            d[i] = cnt
            if d[i] > mx:
                top = i
                mx = cnt
            elif d[i] == mx and top[:1] > i[:1]:
                top = i
                mx = cnt
    return top

in_str = input().strip().replace("\"", "")
result = most_popular_city(in_str[1:-1].split(", "))
print(result)
```




<h3><br>38. Символы на четных позициях</br></h3>

```python
def even_chars(s):
    ans = ""
    for i, j in enumerate(s):
        if i % 2 == 0:
            ans += j
    return ans
        

s = input().strip()
result = even_chars(s)
print(result)
```




<h3><br>39. Максимальная сумма подмассива</br></h3>

```python
def max_subarray_sum(n):
    ln = len(n)
    vse = []
    for k in range(ln):
        for m in range(k, ln):
            vse.append(n[k:m+1])
    ans = [(sum(i), i) for i in vse]
    return sorted(ans, key=lambda x: x[0])[-1][0]
    
import ast

input_str = input().strip()
nums = ast.literal_eval(input_str)
result = max_subarray_sum(nums)
print(result)
```




<h3><br>40. Слияние интервалов</br></h3>

```python
def merge(iv):
    ans = []
    x = iv[0]
    ln = len(iv)
    for n, i in enumerate(iv[1:]):
        if x[1] >= i[0]:
            x[0] = min(x[0], i[0])
            x[1] = max(x[1], i[1])
        else:
            ans.append(x)
            x = [i[0], i[1]]
        if n == ln - 2:
            ans.append(x)
    return ans

import ast

input_str = input().strip()
intervals = ast.literal_eval(input_str)
result = merge(intervals)
print(result)
```




<h3><br>41. Плюс один</br></h3>

```python
def plus_one(d):
    d = int("".join(d))
    return [int(i) for i in str(d + 1)]

d = input().strip()[1:-1].split(", ")
print(plus_one(d)
```




<h3><br>43. Минимальное количество монет</br></h3>

```python
def coin_change(c, t):
    cc = sorted(set(c))[::-1]
    for a in cc:
        x = t // a
        y = t % a
        if y == 0:
            return x
        elif y in c:
            return x + 1
    return -1

import ast
full_input = input().strip()
bracket_pos = full_input.rindex(']')
coins_str = full_input[:bracket_pos+1]
target_str = full_input[bracket_pos+1:].strip()

coins = ast.literal_eval(coins_str)
target_amount = int(target_str)
result = coin_change(coins, target_amount)
print(result)
```




<h3><br>44. Обратный порядок слов</br></h3>

```python
def reverse_words(s):
    return " ".join(s[::-1])
sentence = input().strip().split()
r = reverse_words(sentence)
print(r)
```




<h3><br>45. Подсчёт гласных букв</br></h3>

```python
def count_vowels(s):
    s = s.lower()
    d = ["a", "e", "i", "o", "u"]
    ans = 0
    for i in d:
        ans += s.count(i)
    return ans
    
s = input().strip()
result = count_vowels(s)
print(result)
```




<h3><br>46. Счастливое число</br></h3>

```python
def is_happy_number(n):
    s = str(n)
    if len(s) % 2 != 0:
        return False
    b = int(len(s) / 2)
    p1 = 1
    p2 = 1
    for i1 in s[b:]:
        p1 *= int(i1)
    for i2 in s[:b]:
        p2 *= int(i2)
    if p1 == p2:
        return True
    else:
        return False
        

number = int(input().strip())
result = is_happy_number(number)
print(result)
```




<h3><br>47. RLE-декодирование</br></h3>

```python
def rle_decode(e):
    if len(e) == 1:
        return e
    ln = len(e)
    chi = []
    cc = ""
    for jj, j in enumerate(e, 1):
        if jj == ln:
            chi.append(bk * int(cc))
        elif j.isalpha():
            bk = j
            for kk, k in enumerate(e[jj:]):
                if k.isdigit():
                    cc += k
                else:
                    chi.append(j * int(cc))
                    cc = ""
                    break
    return "".join(chi)

encoded_string = input().strip()
result = rle_decode(encoded_string)
print(result)
```




<h3><br>48. Угол между стрелками часов</br></h3>

```python
def angle_between_hands(h, m):
    xh = (h * 30) + (m * 0.5)
    xm = m * 6
    rzn = abs(xh - xm)
    return min(rzn, 360 - rzn)
    
hour = int(input())
minutes = int(input())
result = angle_between_hands(hour, minutes)
print(result)
```




<h3><br>50. Изоморфные строки</br></h3>

```python
def is_isomorphic(s, t):
    if len(s) == len(t) and len(set(s)) == len(set(t)):
        ss = [s.count(x) for x in set(s)]
        tt = [t.count(y) for y in set(t)]
        return sorted(ss) == sorted(tt)
    else:
        return False

s = input().strip()
t = input().strip()
result = is_isomorphic(s, t)
print(result)
```




<h3><br>53. Счёт строки</br></h3>

```python
def score_of_string(s):
    q = 0
    stp = len(s)
    for i, ii in enumerate(s, 1):
        if i < stp:
            q += abs(ord(ii) - ord(s[i]))
    return q

s = input().strip()
result = score_of_string(s)
print(result)
```







