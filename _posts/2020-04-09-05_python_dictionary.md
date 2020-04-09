---
title : "python - 딕셔너리"
excerpt : "딕셔너리(Dictionary) 사용법"
toc : true
toc_sticky : true
categories :
    - Python
tags :
    - python
---

## 딕셔너리(Dictionary(dict))
- '키'값의 형태를 갖는다.
- '키'로 '값'을 찾아내는 해시테이블(Hash Table) 구조를 갖는다.
- 'dict' 클래스로 구현되어 있다.
- '키'는 변경할 수 없는 Immutable 타입이고, '값'은 Immutable과 Mutable 모두 가능하다.
- `{ }`로 표현하고, 특정 값을 찾아 읽고 쓰기 위해서 '키'를 인덱스처럼 사용한다.
```python
dict1 = {1 : 'apple', 2: 'banana', 3: 'orange'}
dict2 = {'name':'pey', 'phone':'0119993323', 'birth': '1118'}
```

## 딕셔너리 쌍 추가, 삭제
```python
dict = {1: 'a'}
dict[2] = 'b' # 쌍 추가
dict['name'] = 'apple' # 쌍 추가
dict[3] = [1,2,3] # 쌍 추가
del dict[3] # 쌍 삭제
```

## '키' 사용하여 '값' 얻기
- `딕셔너리변수이름[key]`를 사용하여 값을 구할 수 있다.
```python
dict = {1 : 'apple', 2: 'banana', 3: 'orange'}
print(dict[1]) # apple
print(dict[2]) # banana
```

## 딕셔너리 만들 때 주의사항
- '키'는 고유한 값으로 중복되는 키가 존재하면, 마지막 값으로 덮어씌워진다.
```python
dict = {1:'a', 1:'b'}
print(dict) # {1: 'b'}
```
- '키'에 리스트를 사용할 수 없다.(튜플은 사용 가능)
```python
dict = {(1, 2) : 'a', (3, 4) : 'b'}
```

## 딕셔너리 관련 함수
### keys()
딕셔너리의 '키'만을 모아서 dict_keys 객체를 리턴한다.  
리스트로 변환하기 위해서는 `list()` 함수 사용
```python
dict = {1 : 'apple', 2: 'banana', 3: 'orange'}
print(dict.keys()) # dict_keys([1, 2, 3])
print(list(dict.keys())) # [1, 2, 3]

for k in dict.keys():
    print(k) # 반복문을 사용하여 '키'를 출력 가능
```

### values()
딕셔너리의 '값'만을 모아서 dict_values 객체를 리턴한다.  
`keys()`함수와 마찬가지로 리스트, 반복문 사용 가능
```python
dict = {1 : 'apple', 2: 'banana', 3: 'orange'}
print(dict.values()) # dict_values(['apple', 'banana', 'orange'])
print(list(dict.values())) # ['apple', 'banana', 'orange']

for v in dict.values():
    print(v)
```

### items()
'키'와 '값'의 쌍을 튜플로 묶은 값으로 dict_items 객체로 리턴한다.  
`keys()`함수와 마찬가지로 리스트, 반복문 사용 가능
```python
dict = {1 : 'apple', 2: 'banana', 3: 'orange'}
print(dict.items()) # dict_items([(1, 'apple'), (2, 'banana'), (3, 'orange')])
print(list(dict.items())) # [(1, 'apple'), (2, 'banana'), (3, 'orange')]

for i in dict.items():
    print(i)
```

### clear()
딕셔너리 안의 모든 요소를 삭제한다.  
`{}`로 표현
```python
dict = {1 : 'apple', 2: 'banana', 3: 'orange'}
dict.clear()
print(dict) # {}
```

### get(키, 디폴트값)
'키'에 대응하는 '값'을 리턴한다. dict[key]와 동일한 결과를 갖지만, 존재하지 않는 '키'일 경우 dict[key]는 오류를 발생시키고, get() 함수는 None를 리턴한다. '디폴트값'을 설정하면, 딕셔너리 안에 찾으려는 '키'가 없을 경우 사용할 수 있다.
```python
dict = {1 : 'apple', 2: 'banana', 3: 'orange'}
print(dict.get(1)) # apple
print(dict.get(4)) # None
print(dict.get(4, 'cat')) # cat
```

### '키' in 딕셔너리변수이름
딕셔너리 안에 해당 '키'가 존재하는지 확인할 수 있다. 존재하면 'True', 존재하지 않는 다면 'False'를 리턴한다.
```python
dict = {1 : 'apple', 2: 'banana', 3: 'orange'}
print(1 in dict) # True
print(4 in dict) # False
```

### '키' not in 딕셔너리변수이름
딕셔너리 안에 해당 '키'가 존재하지 않는지 확인할 수 있다. 존재하지 않으면 'True', 존재하면 'False'를 리턴한다.
```python
dict = {1 : 'apple', 2: 'banana', 3: 'orange'}
print(1 not in dict) # False
print(4 not in dict) # True
```

### pop(키)
특정 '키'값을 리턴하고, 삭제한다.  
'키'값이 없으면 오류 발생
```python
dict = {1 : 'apple', 2: 'banana', 3: 'orange'}
print(dict.pop(1)) # apple
print(dict) # {2: 'banana', 3: 'orange'}
```

### popitem()
마지막 키-값을 튜플로 리턴하고, 삭제한다.
```python
dict = {1 : 'apple', 2: 'banana', 3: 'orange'}
print(dict.popitem()) # (3, 'orange')
print(dict) # {1: 'apple', 2: 'banana'}
```