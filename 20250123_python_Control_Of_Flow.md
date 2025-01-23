> 제어문(Control Statement)
> 

→ 코드의 실행 흐름을 제어하는 데 사용되는 구문, 조건에 따라 코드 블록을 실행하거나 반복적으로 코드를 실행

> 제어문
> 
- 조건문
    - if, elif, else
- 반복문
    - for, while
- 반복문 제어
    - break, continue, pass

> 조건문(conditional statement)
> 

→ 주어진 조건식을 평가하여 해당 조건이 참(True)인 경우에만 코드 블록을 실행하거나 건너뜀

> if statement의 기본 구조
> 

```python
if 표현식:
		코드 블록
elif 표현식:
		코드 블록
else:
		코드 블록
```

> 조건문 예시
> 

```python
a = 5

if a > 3:
    print('3 초과')
else:
    print('3 이하')

print(a)
```

> 복수 조건문
> 

→ 조건식을 동시에 검사하는 것이 아니라 “순차적”으로 비교

```python
dust = 35

if dust > 150:
    print('매우 나쁨')
elif dust > 80:
    print('나쁨')
elif dust > 30:
    print('보통')
else:
    print('좋음')
```

> 중첩 조건문
> 

```python
dust = 480

if dust > 150:
    print('매우 나쁨')
    if dust > 300:
        print('위험해요!')
elif dust > 80:
    print('나쁨')
elif dust > 30:
    print('보통')
else:
    print('좋음')
```

> __pycache__
> 

파이선 프로젝트를 효율적으로 관리하기 위해 생성된 인터프리터 파

> 반복문(Loop Statement)
> 

→ 주어진 코드 블록을 여러 번 반복해서 실행하는 구문

> for vs while( 주어진 조건이 참인 동안 반복해서 실행)
> 
- for :(특정 작업을 반복적으로 수행, 작업량 정해 놓음)
- while: ( 주어진 조건이 참인 동안 반복해서 실행)

> for
> 

→ 임의의 시퀀스의 항목들을 그 시퀀스에 들어있는 순서대로 반복

- for statement의 기본 구조

```python
for 변수 in 반복 가능한 객체:
		코드 블록
```

- 반복이 가능한 객체(iterable)
    - 반복문에서 순회할 수 있는 객체
    - 시퀀스 객체 뿐만 아니라 dict, set 등도 포함

> for 문 작동원리
> 
- 리스트 내 첫 항목이 반복 변수에 할당되고 코드블록이 실행
- 다음으로 반복 변수에 리스트 의 2번째 항목이 할당되고 코드블록이 다시 실행
- … 마지막으로 반복 변수에 리스트의 마지막 요소가 할당되고 코드블록 실행

```python
items = ['apple', 'banana', 'coconut']

for item in items:
    print(items)
"""
apple
banana
coconut
"""
```

> 문자열 순회
> 

```python
country = 'Korea'

for char in country:
    print(char)

"""
K
o
r
e
a
"""
```

> range 순회
> 

```python
for i in range(5):
		print(i)
		
"""
0
1
2
3
4
"""
```

> 딕셔너리 순회
> 

```python
my_dict = {
    'x': 10,
    'y': 20,
    'z': 30,
}

for key in my_dict:
    print(key)
    print(my_dict(key)) # value

```

> 인덱스로 리스트 순회
> 
- 리스트의 요소가 아닌 인덱스로 접근하여 해당 요소들을 변경하기
- 인덱스는 알고리즘에서 나중에 사용

```python
numbers = [4, 6, 10, -8, 5]

for idx in range(len(numbers)):
    numbers[idx] = numbers[idx] * 2

print(numbers)  # [8, 12, 20, -16, 10]
```

> 중첩된 반복문
> 

```python
outers = ['A', 'B']
inners = ['c', 'd']

for outer in outers:
    for inner in inners:
        print(outer, inner)
"""
A c
A d
B c
B d
"""
```

> while
> 

→ 주어진 조건식이 참(True)인 동안 코드를 반복해서 실행

→ ==조건식이 거짓(False)가 될 때까지 반복

- while statement의 기본 구조

```python
while 조건식:
		코드 블록
```

> 사용자 입력에 따른 반복
> 
- while 문을 사용한 특정 입력값에 대한 종료 조건 활용하기

```python
number = int(input('양의 정수를 입력해주세요.: '))
while number <= 0:
    if number < 0:
        print('음수를 입력했습니다.')
    else:
        print('0은 양의 정수가 아닙니다.')
    number = int(input('양의 정수를 입력해주세요.: '))
print('잘했습니다!')
```

- while 문은 반드시 ***종료 조건***이 필요

> 적절한 반복문 활용하기
> 
- for
    - ***반복 횟수가 명확***하게 정해져 있는 경우에 유용
    - 예를 들어 리스트, 튜플, 문자열 등과 같은 시퀀스 형식의 데이터를 처리할 때
- while
    - ***반복 횟수가 불명확***하거나 ***조건***에 따라 반복을 종료해야 할 때 유용
    - 예를 들어 사용자의 입력을 받아서 특정 조건이 충족될 때까지 반복하는 경우

> 반복문 제어 키워드
> 
- break
    - 반복을 즉시 중지
    
    ```python
    # break
    for i in range(10):
        if i == 5:
            break
        print(i)
    ```
    
- continue
    - 다음 반복으로 건너뜀
    
    ```python
    # continue
    for i in range(10):
        if i % 2 == 0:
            continue
        print(i)
    ```
    
- pass
    - 아무런 동작도 수행하지 않고 넘어감
    
    ```python
    # pass
    for i in range(10):
        pass
    ```
    

> break 예시
> 

```python
# break 예시 2 - "리스트에서 첫번째 짝수만 찾은 후 반복 종료하기"
numbers = [1, 3, 5, 6, 7, 9, 10, 11]

# 첫 번째 짝수를 찾았는지 여부를 저장하는 플래그 변수
# 초기값은 찾지 못했다(False)로 설정
found_even = False

for number in numbers:
    if number % 2 == 0:
        print(f'첫번째 짝수 {number}를 찾았습니다.')
        # 짝수를 찾은 상태이므로 True로 변경
        found_even = True
        break

# 반복문이 끝날 때까지 짝수를 찾지 못한 경우
if found_even == False:
    print('짝수를 찾지 못함')
```

> continue 예시
> 
- 리스트에서 홀수만 출력하기
- 현재 반복문의 남은 코드를 건너뛰고 다음 반복으로 넘어감

```python
# continue 예시 - "리스트에서 홀수만 출력하기"
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

for num in numbers:
    if num % 2 == 0:
        continue
    print(num)
```

> pass 예시
> 
1. 코드 작성 중 미완성 부분
    1. 구현해야할 부분이 나중에 추가될 수 있고, 코드를 컴파일하는 동안 오류가 발생하지 않음
2. 조건문에서 아무런 동작을 수행하지 않아야 할 때
3. 무한 루프에서 조건이 충족되지 않을 때 pass를 사용하여 루프를 계속 진행하는 방법

> List Comprehension
> 

→ 간결하고 효율적인 리스트 생성 방법

> List comprehension 구조
> 

```python
# 기존 방식
numbers = [1, 2, 3, 4, 5]
squared_numbers = []

for num in numbers:
    squared_numbers.append(num**2)  # 리스트.append는 리스트에 값 추가

print(squared_numbers)

# 리스트 컴프리헨션
squared_numbers2 = [num ** 2 for num in numbers]
# squared_numbers2 = list(num ** 2 for num in numbers) # 위와 같은 결과
print(squared_numbers2)
```

- 2차원 배열 생성 시 (인접행렬 생성 시)

```python
# List Comprehension 활용 예시 - "2차원 배열 생성 시 (인접행렬 생성 시)"
data1 = [[0] * (5) for _ in range(5)]
print(data1)
# 또는
data2 = [[0 for _ in range(5)] for _ in range(5)]
print(data2)

"""
[[0, 0, 0, 0, 0],
 [0, 0, 0, 0, 0],
 [0, 0, 0, 0, 0],
 [0, 0, 0, 0, 0],
 [0, 0, 0, 0, 0]]
"""
```

- 리스트 컴프리헨션 with 조건문

```python
# 리스트 컴프리헨션 with 조건문
# 기존 방식
evens = []
for x in range(10):
    if x % 2 == 0:
        evens.append(x)

print(evens)  # [0, 2, 4, 6, 8]

# 리스트 컴프리헨션
evens = [x for x in range(10) if x % 2 == 0]
print(evens)  # [0, 2, 4, 6, 8]

```

---

## 참고자료

> 모듈 내부 살펴보기
> 
- 내장 함수 help를 사용해 모듈에 무엇이 들어있는지 확인

> enumerate(iterable, start = 0)
> 

→ iterable 객체의 각 요소에 대해 인덱스와 함께 반환하는 내장함수
```python
fruits = ['apple', 'banana', 'cherry']

for index, fruit in enumerate(fruits):
    print(index, fruit)

"""
0 apple
1 banana
2 cherry
"""

for index, fruit in enumerate(fruits, 3):
    print(index, fruit)

"""
3 apple
4 banana
5 cherry
"""
```
