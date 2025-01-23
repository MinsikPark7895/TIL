## 모듈

→ 한 파일로 묶인 변수와 함수의 모음

→ 특정한 기능을 하는 코드가 작성된 파이썬 파일(.py)

→ 다른 프로그래머가 이미 작성해 놓은 수천, 수백만 줄의 코드를 활용하는 것은 생산성에서 매우 중요한 일

> 모듈 예시
> 
- math 내장 모듈
    - 파이썬이 미리 작성해 둔 수학 관련 변수와 함수가 작성된 모듈
    
    ```python
    import math
    import random
    import datetime
    
    print(math.pi)
    print(math.sqrt(4))
    
    print(random.randint(1,10))
    
    now = datetime.datetime.now()
    print(now)
    
    ```
    

> 모듈을 가져오는 방법
> 
- import 문 사용(이걸 파이썬은 더 선호)
    
    ```python
    import math
    print(math.sqrt(4))
    ```
    
- from 절 사용
    
    ```python
    from math import sqrt # math의 pi는 못씀
    print(sqrt(4))
    ```
    

> 모듈 사용하기
> 
- ‘. (dot)’ 연산자
    - “점의 왼쪽 객체에서 점의 오른쪽 이름을 찾아라” 라는 의미

> 모듈 주의사항
> 
- 서로 다른 모듈이 같은 이름의 함수를 제공할 경우 문제 발생
- 마지막에 import된 이름으로 대체됨

```python
from math import pi, sqrt
from my_math import sqrt

from math import *
```

> ‘as’ 키워드
> 
- as 키워드를 사용하여 별칭(alias)을 부여
    - 두 개 이상의 모듈에서 동일한 이름의 변수, 함수 클래스 등을 가져올 때 발생하는 이름 충돌 해결
    
    ```python
    from math import sqrt
    from my_math import sqrt as my_sqrt
    
    sqrt(4)
    my_sqrt(4)
    ```
    

> 사용자 정의 모듈
> 

→ 직접 정의한 모듈 사용하기

1. 모듈 my_math.py 작성
2. 두 수의 합을 구하는 add 함수 작성
3. my_math 모듈 import 후 add 함수 호출

> 파이썬 표준 라이브러리(Python Standard Library, PSL)
> 

→ 파이썬 언어와 함께 제공되는 다양한 모듈과 패키지의 모음

> 패키지(Package)
> 

→ 연관된 모듈들을 하나의 디렉토리에 모아 놓은 것

> PSL 내부 패키지 vs 외부 패키지
> 
- PSL : 설치 없이 바로 import하여 사용
- 외부 : pip를 사용하여 설치 후 import

> pip
> 

→ 외부 패키지들을 설치하도록 도와주는 파이썬의 패키지 관리 시스템

- PyPI(Python Package Index)에 저장된 외부 패키지들을 설치

> 패키지 설치
> 
- 최신 버전 / 특정 버전 / 최소  버전을 명시하여 설치할 수 있음

```python
$ pip install SomePackage==1.0.5 # package 설치, 숫자는 버젼
$ pip uninstall SomePackage # package 삭제
```

> requests 외부 패키지 설치 및 사용 예시
> 
- requests 외부 API 서버로 요청하는 패키지(파이썬 개발자는 필수로 알아야 함)

```python
# HTTP 요청을 보낼 수 있도록 도와주는 requests 라이브러리 import
import requests

# 무작위 사용자 정보를 제공해주는 API의 URL
url = 'https://random-data-api.com/api/v2/users'

# requests.get(url)을 통해 API에 요청을 보냄
# 서버로부터 응답(Response)을 JSON 형태로 받아 Python 객체(딕셔너리/리스트 등)로 변환
response = requests.get(url).json()

# 받은 응답 데이터(딕셔너리 형태)를 출력
print(response)
print(type(response))

```

> 패키지 사용 목적
> 

→ 모듈들의 이름 공간을 구분하여 충돌을 방지 모듈들을 효율적으로 관리하고 재사용할 수 있도록 돕는 역할
