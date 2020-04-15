---
title : "python - 반복문"
excerpt : "while, for문 사용법"
toc : true
toc_sticky : true
categories :
    - Python
tags :
    - python
---

while 반복문
===========
## while문의 기본 구조
while문은 조건문이 참인 동안에 반복할 코드를 수행한다.
```python
while (조건문):
    (반복할 코드)
```
```python
mouseClick = 0
while mouseClick < 5:
    mouseClick += 1
    print("마우스를 %d번 클릭했습니다.")
    if mouseClick == 5:
        print("마우스가 고장났습니다.")
```

## break문
while문은 조건문이 참인 동안에 반복적으로 수행한다. 하지만 강제로 while문을 빠져나가고 싶을 경우에 break문을 사용할 수 있다.
```python
# 카운트 다운 중, 5에서 종료
i = 10
print("카운트다운을 시작합니다.")
while i >= 0:
    if i == 5:
        print("카운트가 %d로 종료합니다." % i)
        break
    print(i)
    i -= 1
```

## continue문
while문의 조건문으로 들어가게 만들고 싶은 경우 사용할 수 있다.
```python
# 10까지의 숫자 중, 홀수만 출력
i = 0
while i < 10:
    i += 1
    if i % 2 == 0:
        continue # 짝수일 경우 출력하지 않음
    print(i)
```

## 무한루프
- 무한히 루프를 반복한다.
- Ctrl + C 로 무한루프를 빠져나올 수 있다.

<br>
--------------------------------------------------
<br>

for 반복문
======
## for 문
리스트, 튜플, 딕셔너리와 같은 반복 가능한 자료형을 처리하기 위해서 편리하다.
```python
for (변수) in (반복가능한자료형):
    (반복할코드)
```
```python
# 리스트 반복
L = ['apple', 'banana', 'orange']
for i in L:
    print(i)

# 튜플 반복
T = ('apple', 'banana', 'orange')
for i in T:
    print(i)

# 튜플을 포함한 리스트 반복
List_tuple = [(1,2), (3,4), (5,6)]
for (first, last) in List_tuple:
    print(first, last)

# 응용
L_students = [90, 25, 67, 45, 80]
number = 0
for student in L_students:
    number += 1
    if student >= 60:
        print("%d번 학생은 합격~" % number)
    else:
        print("%d번 학생은 불합격...." % number)
```

## continue 문
```python
L_students = [90, 25, 67, 45, 80]
number = 0
for student in L_students:
    number += 1
    if student < 60:
        continue
    print("%d번 학생 축하합니다~ 합격입니다~" % number)
```

## range 함수
- 숫자 리스트를 자동으로 만들어준다.
- ragne(10)은 0부터 10미만(0~9)의 숫자를 포함하는 range 객체를 만들어 준다.
- range(시작 숫자, 끝 숫자)를 통해 지정할 수도 있다.(끝 숫자는 포함되지 않음)
```python
# for문과 range함수를 이용한 구구단
for i in range(2, 10):
    for j in range(1, 10):
        print(i * j, end = " ")
    print(' ')
# 매겨변수 end는 결과값이 다음줄로 넘어가지 않고 계속해서 출력하기 위함
# print(' ')는 단을 구분하기 위해 다음줄부터 출력되게 하기 위함
```