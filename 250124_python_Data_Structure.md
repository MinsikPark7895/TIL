# Data Structure(데이터 구조)

→ 여러 데이터를 효과적으로 사용, 관리하기 위한 구조(str, list, dict 등)

> 자료 구조
> 
- 컴퓨터 공학에서는 ‘자료 구조’라고 함
- 각 데이터의 효율적인 저장, 관리를 위한 구조를 나눠 놓은 것

> 데이터 구조 활용
> 
- 문자열, 리스트, 딕셔너리 등 각 데이터 구조의 메서드를 호출하여 다양한 기능을 활용하기

### 메서드(method)

→ 객체에 속한 함수

→ 객체의 상태를 조작하거나 동작을 수행

> 메서드 특징
> 
- 메서드는 클래스(class) 내부에서 정의되는 함수
- 클래스는 파이썬에서 ‘타입을 표현하는 방법’이며 이미 은연중에 사용해왔음
- 예를 들어 help 함수를 통해 str을 호출해보면 class였다는 것을 확인 가능
- ***메서드는 어딘가(클래스)에 속해 있는 함수이며, 각 데이터 타입별로 다양한 기능을 가진 메서드가 존재***

> 메서드 호출 방법
> 

```python
# 데이터 타입 객체.메서드()
'hello'.capitalize()
```

→ 

- 예시

```python
print('hello'.capitalize()) # Hello

# 리스트 메서드 예시
numbers = [1, 2, 3]
numbers.append(4)

print(numbers) # [1, 2, 3, 4]
```

### 시퀀스 데이터 구조

> 문자열 조회/탐색 및 검증 메서드(pg 18)
> 

| 메서드 | 설명 |
| --- | --- |
| s.find(x) | x의 첫 번째 위치를 반환. 없으면, -1 반환 |
| s.index(x) | x의 첫 번째 위치를 반환. 없으면, 오류 발생 |
| s.isupper() | 문자열 내의 모든 문자가 대문자인지 확인 |
| s.islower() | 문자열 내의 모든 문자가 소문자인지 확인 |
| s.isalpha() | 문자열 내의 모든 문자가 알파벳인지 확인
* 단순 알파벳이 아닌 유니코드 상 Letter (한국어도 포함) |

> 문자열 조회/탐색 및 검증 메서드
> 
1. .find(x)

→ x의 첫 번째 위치를 반환, 없으면, -1을 반환

```python
# find
text = 'banana'
print(text.find('a'))  # 1
print(text.find('z'))  # -1
```

1. .index(x)

→ x

```python
# index
print(text.index('a'))  # 1
print(text.index('z'))  # ValueError
```

1. .isupper() / .islower()

→ 문자열이 모두 대문자/소문자로 이루어져 있는지 확인

```python
# isupper
string1 = 'HELLO'
string2 = 'Hello'
print(string1.isupper())  # True
print(string2.isupper())  # False

# islower
print(string1.islower())  # False
print(string2.islower())  # False
```

1. .isalpha()

→ 문자열이 알파벳으로만 이루어져 있는지 확인

```python
# isalpha
string1 = 'Hello'
string2 = '123heis98576ssh'
print(string1.isalpha())  # True
print(string2.isalpha())  # False

```

> 문자열 조작 메서드 (새 문자열 반환)
> 

| 메서드 | 설명 |
| --- | --- |
| s.replace(old, new[, count]) | 바꿀 대상 글자를 새로운 글자로 바꿔서 반환 |
| s.strip([chars]) | 공백이나 특정 문자를 제거 |
| s.split(sep=None, maxsplit=-1 | sep를 구분자 문자열로 사용하여 문자열에 있는 단어들의 리스트 반환 |
| ‘seperator’.join(iterable) | 구분자로 iterable의 문자열을 연결한 문자열을 반환 |
| s.capitalize() | 가장 첫 번째 글자를 대문자로 변경 |
| s.title() | 문자열 내 띄어쓰기 기준으로 각 단어의 첫 글자는 대문자로, 나머지는 소문자로 변환 |
| s.upper() | 모두 대문자로 변경 |
| s.lower() | 모두 소문자로 변경 |
| s.swapcase() | 대 ↔ 소문자 서로 변경 |
1. .replace(old, new[,count(바꿀 개수)])

→ 바꿀 대상 글자를 새로운 글자로 바꿔서 반환

→ 여기서 [], 대괄호는 선택적 인자

```python
# replace
text = 'Hello, world! world world'
new_text1 = text.replace('world', 'Python')
new_text2 = text.replace('world', 'Python', 1)
print(new_text1)  # Hello, Python! Python Python
print(new_text2)  # Hello, Python! world world
```

1. .strip([chars])
- 문자열의 시작과 끝에 있는 공백 혹은 지정한 문자를 제거

```python
# strip
text = '  Hello, world!  '
new_text = text.strip()
print(new_text)    # Hello, world!
```

1. .split(sep=None, maxsplit=-1)

→ sep를 구분자 문자열로 사용하여 문자열에 있는 단어들의 리스트를 반환

```python
# split
text = 'Hello, world!'
words1 = text.split(',')
words2 = text.split()
print(words1)  # ['Hello', ' world!']
print(words2)  # ['Hello,', 'world!']
```

1. ‘seperator’.join(iterable)

→ iterable의 문자열을 연결한 문자열을 반환

```python
# strip
text = '  Hello, world!  '
new_text = text.strip()
print(new_text)    # Hello, world!
```

1. 나머지

```python
# capitalize
text = 'heLLo, woRld!'
new_text1 = text.capitalize()
print(new_text1)  # Hello, world!

# title
new_text2 = text.title()
print(new_text2)  # Hello, World!

# upper
new_text3 = text.upper()
print(new_text3)  # HELLO, WORLD!

# lower
new_text4 = text.lower()
print(new_text4)  # hello, world!

# swapcase
new_text5 = text.swapcase()
print(new_text5)  # HEllO, WOrLD!
```

> 리스트 값 추가 및 삭제 메서드
> 
1. .append(x)

→ 리스트 마지막에 항목 x를 추가

```python
# append
my_list = [1, 2, 3]
my_list.append(4)
print(my_list)  # [1, 2, 3, 4]
print(my_list.append(4))  # None, append는 리턴 값이 없다
```

- append는 return 값이 없다

1. extend(iterable)

→ 리스트에 다른 반복 가능한 객체의 모든 항목을 추가

```python
# extend
my_list = [1, 2, 3]
my_list.extend([4, 5, 6])
print(my_list)  # [1, 2, 3, 4, 5, 6]
```

- expend 주의사항
- append()와의 비교

```python
# append와의 비교
my_list.append([4, 5, 6])
print(my_list)  # [1, 2, 3, 4, 5, 6, [4, 5, 6]]
```

- 반복 가능한 객체가 아니면 추가 불가

```python
my_list.extend(100)
# TypeError: 'int' object is not iterable
```

1. .insert(i, x)

→ 리스트의 지정한 인덱스 i 위치에 항목 x를 삽입

```python
# insert
my_list = [1, 2, 3]
my_list.insert(1, 5)
print(my_list)  # [1, 5, 2, 3]
```

1. .remove(x)

→ 리스트에서 첫 번째로 일치하는 항목을 삭제

```python
# remove
my_list = [1, 2, 3, 2, 2, 2]
my_list.remove(2)
print(my_list)  # [1, 3, 2, 2, 2]
```

1. .pop(i)

→ 리스트에서 지정한 인덱스의 항목을 제거하고 반환 작성하지 않을 경우 마지막 항목을 제거

```python
# pop
my_list = [1, 2, 3, 4, 5]
item1 = my_list.pop()
item2 = my_list.pop(0)

print(item1)  # 5
print(item2)  # 1
print(my_list)  # [2, 3, 4]
```

1. .clear()

→ 리스트의 모든 항목을 삭제

```python
# clear
my_list = [1, 2, 3]
my_list.clear()
print(my_list)  # []
```

> 리스트 탐색 및 정렬 메서드
> 
1. .index(x)

→ 리스트에서 첫 번째로 일치하는 항목 x의 인덱스를 반

```python
# index
my_list = [1, 2, 3]
index = my_list.index(2)
print(index)  # 1
```

1. .count(x)

→ 리스트에서 항목 x의 개수를 반환

```python
# count
my_list = [1, 2, 2, 3, 3, 3]
counting_number = my_list.count(3)
print(counting_number)  # 3
```

1. .reverse()

→ 리스트의 순서를 역순으로 변경(정렬 x)

```python
# reverse
my_list = [1, 3, 2, 8, 1, 9]
my_list.reverse()
# print()  
print(my_list)  # [9, 1, 8, 2, 3, 1]
```

1. .sort()

→ 원본 리스트를 오름차순으로 정렬

```python
# sort
my_list = [3, 2, 100, 1]
my_list.sort()
print(my_list)  # [1, 2, 3, 100]

# sort(내림차순 정렬)
my_list.sort(reverse=True)
print(my_list)  # [100, 3, 2, 1]
```

---

## 복사

### 객체와 참조

> 가변/불변 객체 개념
> 
1. Mutable(가변) 객체: 생성 후 내용을 변경할 수 있는 객체
    - 예: 리스트(list), 딕셔너리(dict), 집합(set)
2. Immutable(불변) 객체: 생성 후 내용을 변경할 수 없는 객체
    - 예: 정수(int), 실수(float), 문자열(str), 튜플(tuple)

> 변수 할당의 의미, pg 48
> 
- 파이썬에서 변수 할당은 객체에 대한 참조
    - 변수는 객체의 메모리 주소를 가리키는 Label 역할을 함
    - ‘=’ 연산자를 사용하여 변수에 값을 할당
    - 할당 시 새로운 객체가 생성되거나 기존 객체에 대한 참조가 생성됨

> 메모리 참조 방식
> 
- 변수는 객체의 ‘메모리 주소’를 저장
- 여러 변수가 동일한 객체를 참조할 수 있음
- 가변 객체의 예시
    
    ```python
    # ================================================
    # 가변(mutable) 객체 예시
    # ================================================
    print('가변(mutable) 객체 예시')
    a = [1, 2, 3, 4]
    b = a
    b[0] = 100
    
    print(f'a의 값: {a}')  # [100, 2, 3, 4]
    print(f'b의 값: {b}')  # [100, 2, 3, 4]
    print(f'a와 b가 같은 객체를 참조하는가? {a is b}')  # True
    ```
    
- 불변 객체의 예시
    
    ```python
    # ================================================
    # 불변(immutable) 객체 예시
    # ================================================
    print('\n불변(immutable) 객체 예시')
    a = 20
    b = a
    b = 10
    
    print(f'a의 값: {a}')  # 20
    print(f'b의 값: {b}')  # 10
    print(a is b)  # False
    ```
    

> id() 함수를 사용한 메모리 주소 확인
> 
- id() 함수를 사용하여 객체의 메모리 주소를 확인 가능
- is 연산자를 통해 두 변수가 같은 객체를 참조하는 지 확인

```python
print('\n메모리 주소 확인')
x = [1, 2, 3]
y = x
z = [1, 2, 3]

print(f'x의 id: {id(x)}')   # 1840895268224
print(f'y의 id: {id(y)}')   # 1840895268224
print(f'z의 id: {id(z)}')   # 1840895294720
print(f'x와 y는 같은 객체인가? {x is y}')  # True
print(f'x와 z는 같은 객체인가? {x is z}')  # False
```

> 가변/불변 메모리 관리 방식
> 
- 가변 객체
    - 생성 후에도 그 내용을 수정할 수 있음
    - 객체의 내용이 변경되어도 같은 메모리 주소를 유지
- 불변 객체
    - 생성 후 그 값을 변경할 수 없음
    - 새로운 값을 할당하면 새로운 객체가 생성되고, 변수는 새 객체를 참조하게 됨

> 이러한 동작 방식의 이유
> 
1. 성능 최적화
    - 불변 객체는 변경은 불가능하므로, 여러 변수가 같은 객체를 안전하게 공유할 수 있음
    - 가변 객체는 내용 수정이 빈번한 경우 새 객체를 생성하지 않고 직접 수정하여 성능을 향상시킴
2. 메모리 효율성
    - 불변 객체는 동일한 값을 가진 여러 객체가 메모리를 공유할 수 있어 효율적
    - 가변 객체는 크기가 큰 데이터를 효율적으로 수정할 수 있음

### 얕은 복사

→ 객채의 최상위 요소만 새로운 메모리에 복사하는 방법

→ 내부에 중첩된 객체가 있다면 그 객체의 참조만 복사됨

> 얕은 복사 구현 방법
> 
1. 리스트 슬라이싱
2. copy() 메서드
3. list() 함수

```python
# ================================================
# 얕은 복사
# ================================================
print('\n얕은 복사 예시')

# 1차원 리스트
a = [1, 2, 3]
b = a[:]  # 슬라이싱
c = a.copy()  # copy() 메서드
d = list(a)  # list() 함수

b[0] = 100
c[0] = 999
d[0] = 8080
print(a)  # [1, 2, 3]
print(b)  # [100, 2, 3]
print(c)  # [999, 2, 3]
print(d)  # [8080, 2, 3]

# 다차원 리스트
print('\n다차원 리스트 얕은 복사의 한계')
a = [1, 2, [3, 4, 5]]
b = a[:]

b[0] = 999
print(a)  # [1, 2, [3, 4, 5]]
print(b)  # [999, 2, [3, 4, 5]]

b[2][1] = 100
print(a)  # [1, 2, [3, 100, 5]]
print(b)  # [999, 2, [3, 100, 5]]
print(f'a[2]와 b[2]가 같은 객체인가? {a[2] is b[2]}')  # True
```

> 얕은 복사의 한계
> 
- 2차원 리스트와 같이 변경 가능한 객체 안에 변경 가능한 객체가 있는 경우
- a와 b의 주소는 다르지만 내부 객체의 주소는 같기 때문에 함께 변경됨

> 1차원 리스트와 다차원 리스트의 차이점
> 
- 1 차원 리스트
    - 얕은 복사로 충분히 독립적인 복사본을 만들 수 있음
- 다차원 리스트
    - 최상위 리스트만 복사되고, 내부 리스트는 여전히 원본과 같은 객체를 참조

### 깊은 복사

→ 모든 수준의 요소를 새로운 메모리에 복사하는 방법

→ 중첩된 객체까지 모두 새로운 객체로 생성됨

- copy 모듈에서 제공하는 deepcopy() 함수를 사용

```python
# ================================================
# 깊은 복사
# ================================================
import copy

print('\n깊은 복사 예시')
a = [1, 2, [3, 4, 5]]
b = copy.deepcopy(a)

b[2][1] = 100
print(a)  # [1, 2, [3, 4, 5]]
print(b)  # [1, 2, [3, 100, 5]]
print(f'a[2]와 b[2]가 같은 객체인가? {a[2] is b[2]}')  # False

# 복잡한 중첩 객체 예시
print('\n복잡한 중첩 객체 깊은 복사')
original = {
    'a': [1, 2, 3],
    'b': {
        'c': 4,
        'd': [5, 6],
    },
}
copied = copy.deepcopy(original)

copied['a'][1] = 100
copied['b']['d'][0] = 500

print(f'원본: {original}')  # {'a': [1, 2, 3], 'b': {'c': 4, 'd': [5, 6]}}
print(f'복사본: {copied}')  # 복사본: {'a': [1, 100, 3], 'b': {'c': 4, 'd': [500, 6]}}
print(
    f'original["b"]와 copied["b"]가 같은 객체인가? {original["b"] is copied["b"]}'
)  # False

```

> 메서드 체이닝(Method chaining)
> 

→ 여러 메서드를 연속해서 호출하는 방식

- 문자열에서의 메서드 체이닝 예시

```python
# 문자열 메서드 체이닝
text = 'heLLo, woRld!'
new_text = text.swapcase().replace('l', 'z')
print(new_text)  # HEzzO, WOrLD!

# 1. 단계별로 실행하기
text = 'heLLo, woRld!'
step1 = text.swapcase()
print('1단계 결과:', step1)  # HEllO, WOrLD!

step2 = step1.replace('l', 'z')
print('2단계 결과:', step2)  # HEzzO, WOrLD!

# 2. 한 줄로 실행하기 (위와 동일한 결과)
new_text = text.swapcase().replace('l', 'z')
print('최종 결과:', new_text)  # HEzzO, WOrLD!
```

- 리스트에서의 메서드 체이닝 예시

```python
# 리스트 메서드 체이닝 예시

# 잘못된 체이닝 방식 1
numbers = [3, 1, 4, 1, 5, 9, 2]
result = numbers.copy().sort()
print(result)  # None (sort()는 None을 반환하므로 체이닝이 중단됨)
print(numbers)  # [3, 1, 4, 1, 5, 9, 2] (원본은 변경되지 않음)

# 잘못된 체이닝 방식 2
result = numbers.append(7).extend([8, 9])  # AttributeError, numbers.append(7)의 반환 값은 None.extend([8, 9])

# 개선된 방식
# 리스트 조작에서 메서드 체이닝을 사용할 때는 각 메서드가 적절한 값을 반환하는지 확인하고,
# 필요한 경우 새로운 리스트 객체를 반환하는 함수를 사용하는 것이 좋음
sorted_numbers = sorted(numbers.copy())
print(sorted_numbers)  # [1, 1, 2, 3, 4, 5, 9]

```

> 메서드 체이닝 주의사항
> 
- 모든 메서드가 체이닝을 지원하는 것은 아님
    - 메서드가 객체를 반환할 때만 체이닝이 가능
- None을 반환하는 메서드는 메서드 체이닝이 불가능
    - ex) 리스트의 append(), sort()
- 메서드 체이닝을 사용할 때는 각 메서드의 반환 값을 잘 이해하고 있어야 함

> 문자열에 포함된 문자들의 유형을 판별하는 메서드
> 
- isdecimal()
    - 문자열이 모두 숫자 문자(0~9)로만 이루어져 있어야 True
- isdigit()
    - isdecimal()과 비슷하지만, 유니코드 숫자도 인식(’(1)’도 숫자로 인식)
- isnumeric()
    - isdigit()과 유사하지만, 몇 가지 추가적인 유니코드 문자들을 인식
    - 분수, 지수, 루트 기호도 숫자로 인식
