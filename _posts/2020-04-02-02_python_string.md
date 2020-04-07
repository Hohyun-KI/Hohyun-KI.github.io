---
title : "python - 문자형"
excerpt : "문자형 자료형 사용법"
toc : true
toc_sticky : true
categories :
    - Python
tags :
    - python
---

## 문자열 포맷 코드

| 포맷 코드 | 설명 |
| ----- | ----- |
| %s | 문자열(String) |
| %c | 문자 1개(Character) |
| %d | 정수(Integer) |
| %f | 부동소수(Floating-point) |
| %o | 8진수 |
| %x | 16진수|
| %% | 문자 '%' |

## 문자열 내장 함수
### count()
특정 문자의 개수 세기
```python
a = "Hello"
b = a.count('l') # 'l'문자의 개수
print(b) # 2
```
### find()
찾는 문자열이 처음으로 나온 위치를 반환
```python
a = "Do your best"
b = a.find('y')
c = a.find('a')
print(b, c) # 3 -1
# 'a'는 해당 문자열에 포함되어 있지 않아 -1 반환
# 찾는 문자열이 없을 경우 -1 반환
```
### index()
find() 함수와 동일하게 찾는 문자열이 처음으로 나온 위치를 반환
```python
a = "Do your best"
b = a.index('y')
print(b) # 3
c = a.index('a') # Error 발생
# find 함수와는 다르게 찾는 문자열이 없을 경우 오류 발생
```

### join()
문자열, 리스트, 튜플 사이에 iterable 인자를 전달하여 문자열로 연결
```python
a = ','.join('abcd')
print(a) # a,b,c,d
```

### upper()
대문자로 변경
```python
a = 'hello'
b = a.upper()
print(b) # HELLO
```

### lower()
소문자로 변경
```python
a = 'HELLO'
b = a.lower()
print(b) # hello
```

### lstrip()
왼쪽 공백 지우기
```python
a = '  hello'
b = a.lstrip()
print(a, b, sep='\n')
#   hello
# hello
```

### rstrip()
오른쪽 공백 지우기
```python
a = 'hello  '
b = a.rstrip()
print(a, b, sep='\n')
# hello  
# hello
```

### strip()
양쪽 공백 지우기
```python
a = '  hello  '
b = a.strip()
print(a, b, sep='\n')
#   hello  
# hello
```

### replace()
특정 문자열 바꾸기
```python
a = 'do your best'
b = a.replace('best', 'bit')
print(b) # do your bit
```

### split()
문자열 나누어 리스트로 반환
```python
a = 'do your best'
b = a.split()
print(b) # ['do', 'your', 'best']

c = "a=b=c=d"
d = c.split('=')
print(d) # ['a', 'b', 'c', 'd']
```