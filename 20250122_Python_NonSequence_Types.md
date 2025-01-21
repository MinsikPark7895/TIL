## Non-sequence Types

1. dict(딕셔너리)
    - key - value 쌍으로 이루어진 순서와 중복이 없는 변경 가능한 자료형
    
    딕셔너리 표현
    
    - key는 변경 불가능한 자료형만 사용 가능(str, int, float, tuple, range, …)
    - value는 모든 자료형 사용 가능
    - 중괄호({})로 표기
    
    딕셔너리 사용
    
    - key를 통해 value에 접근
    - key는 중복 불가능
    
    ```python
    # 딕셔너리 표현
    my_dict_1 = {}
    my_dict_2 = {'key': 'value'}
    my_dict_3 = {'apple': 12, 'list':[1, 2, 3]}
    print(my_dict_1)  # 
    print(my_dict_2)  # 
    print(my_dict_3)  # 
    
    # 딕셔너리는 키에 접근해 값을 얻어냄
    my_dict = {'apple': 12, 'list': [1, 2, 3]}
    print(my_dict['apple']) # 12
    print(my_dict['list']) # [1, 2, 3]
    print(my_dict['list'][1]) # 2
    
    # 추가
    my_dict['banana'] = 50
    print(my_dict)  # {'apple': 12, 'list': [1, 2, 3], 'banana': 50}
    
    # 변경
    my_dict['apple'] = 100
    print(my_dict)  # {'apple': 100, 'list': [1, 2, 3], 'banana': 50}
    
    ```
    
2. set(세트)
    - 순서와 중복이 없는 변경 가능한 자료형
    
    세트 표현
    
    - 수학에서의 집합과 동일한 연산 처리 가능
    - 중괄호({})로 표기
    
    ```python
    # 세트 표현
    my_set_1 = set()
    my_set_2 = {1, 2, 3}
    my_set_3 = {1, 1, 1}
    print(my_set_1)  # set()
    print(my_set_2)  # {1, 2, 3}
    print(my_set_3)  # {1}
    
    # 세트의 집합 연산산
    my_set_1 = {1, 2, 3}
    my_set_2 = {3, 6, 9}
    
    # 합집합
    print(my_set_1 | my_set_2)  # {1, 2, 3, 6, 9}, 중복 X, index 접근 X, 순서 X
    
    # 차집합
    print(my_set_1 - my_set_2)  # {1, 2}
    
    # 교집합
    print(my_set_1 & my_set_2)  # {3}
    
    ```
    
    - 
3. Other Types
    1. None
        - 파이썬에서 ‘값이 없음’을 표현하는 자료형
    
    ```python
    variable = None
    print(variable)  # None
    ```
    
    b.  boolean
    
    - 참과 거짓을 표현하는 자료형
    
    불리언 표현
    
    - 비교 / 논리 연산의 평가 결과로 사용됨
    - 주로 조건 / 반복문과 함께 사용

1. Collection
    - 여러 개의 항목 또는 요소를 담는 자료 구조
    - str, list, tuple, set, dict
    - collection 정리
    
    | 컬렉션 | 변경 가능 여부 | 순서 여부 |
    | --- | --- | --- |
    | str | X | O |
    | list | O | O |
    | tuple | X | O |
    | dict | O | X |
    | set | O | X |
    - ‘list / dict를 얼마나 잘 활용하느냐’가 중요
