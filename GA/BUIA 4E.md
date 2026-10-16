
>> 16.10.2026

#### Test:
- posunout prvky v seznamu o +2
aka:
- arr[ i ] = arr[ i - 2 ]

## Rekurze

Existuje:
- rekurzivní algoritmy
- rekurzivní funkce

**Příklad: factorial**
```python
# Loop
def factorial_loop(n):
    result = 1
    for i in range(1, n + 1):
        result *= i
    return result

# Recursive
def factorial_recursive(n):
    if n == 0 or n == 1:
        return 1
    return n * factorial_recursive(n - 1)

print(factorial_loop(5))       # 120
print(factorial_recursive(5))  # 120
```


**Příklad: palindrom**
```python
# Loop
def palindrome_loop(s):
    for i in range(len(s) // 2):
        if s[i] != s[len(s) - 1 - i]:
            return False
    return True

# Recursive
def palindrome_recursive(s):
    if len(s) <= 1:
        return True
    if s[0] != s[-1]:
        return False
    return palindrome_recursive(s[1:-1])

print(palindrome_loop("racecar"))       # True
print(palindrome_recursive("racecar"))  # True

print(palindrome_loop("hello"))         # False
print(palindrome_recursive("hello"))    # False
```

**Fibonacciho čísla**
```python
# Loop
def fibonacci_loop(n):
    a, b = 0, 1

    for i in range(n):
        a, b = b, a + b

    return a

# Recursive
def fibonacci_recursive(n):
    if n == 0 or n == 1:
        return n

    return fibonacci_recursive(n - 1) + fibonacci_recursive(n - 2)

print(fibonacci_loop(6))       # 8
print(fibonacci_recursive(6))  # 8
```
$\uparrow$ Rekurzivní vypočítá stejné hodnoty několikrát

**Potenciální rešení:** 
- cache (aka memoizace)
	- třeba array
	- pak zkontrolovat jestli už existuje
	- $O(2^n) \rightarrow O(n)$
	- potřebuje mnohém více paměti
