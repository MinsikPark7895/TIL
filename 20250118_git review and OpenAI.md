# 2025/01/17(금)

# Git

## Remote Repository

1. 원격 저장소(ex. gitlab, github, bitbucket)

---

- $ git remote add origin remote_repo_url : 로컬 저장소에 원격 저장소 추가
- $ git remote set -a origin remote_repo_url : 로컬 저장소 잘못 입력 시 수정
- $ git push origin master : git아, push해줘 origin이라는 이름의 원격 저장소에 master라는 이름의 브랜치를
- $ git clone remote_repo_url : 원격 저장소 전체를 복제(다운로드), clone으로 받은 프로젝트는 이미 git init이 되어 있음, 주로 처음에만 사용, 내 컴퓨터에서 프로젝트 시작(init), 다른 사람 컴퓨터 시작(clone)
- $git pull origin master : 원격 저장소의 변경사항만을 받아옴(업데이트), clone은 최초로 참여할 때만 사용, 그 후에는 pull 사용

### .gitignore

- git에서 특정 파일이나 디렉토리를 추적하지 않도록 설정하는데 사용되는 텍스트 파일
    
    주의 사항 : 이미 git의 관리를 받은 이력이 있는 파일이나 디렉토리는 나중에 gitignore 에 작성해도 적용되지 않음
    
    (git rm —cached 명령어를 통해 git 캐시에서 삭제 필요)
    
- [README.md](http://README.md) 파일이란?
    - 프로젝트에 대한 설명, 사용 방법, 문서화된 정보 등을 포함하는 역할
    - Markdown 형식으로 작성되며, 프로젝트의 사용자, 개발자, 혹은 기여자들에게 프로젝트에 대한 전반적인 이해와 활용 방법을 제공하는데 사용
    - 주로 프로젝트의 소개, 설치 및 설정 방법, 사용 예시, 라이선스 정보, 기여 방법 등을 포함
    - 반드시 저장소 최상단에 위채해야 원격 저장소에서 올바르게 출력됨

### revert

git revert : 특정 commit을 없었던 일로 만드는 작업, 없던 일로 하자

- git revert 작동 원리
    - 재설정
    - 단일 commit을 실행 취소하는 것
    - 프로젝트 기록에서 commit을 없었던일로처리 후 그 결과를  새로운 commit으로 추가함
        
        ![스크린샷 2025-01-17 105615.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/627c6497-5cea-4142-af10-027d34c57265/855632f5-c847-4afb-9935-e925581e9e31/cd09cd39-19dd-4134-9cdf-d3ac85c75e51.png)
        

revert 추가 명령어

- Git reset
    - 특정 commit을 되돌아가는 작업
    - git reset [옵션(reset 명령어임)] <commit id>

reset의 3가지 옵선

- — soft, —mixed, —hard
- reset은 과거 commit으로 되돌아간 후 되돌아간 commit 이후 commit들이 삭제됨
- 그런데 삭제되는 commit들의 기록을 어떤 영역에 남겨둘 것이지 옵션을 활용해 조정할 수 있음

- —soft
    - 삭제된 commi의기록을  staging area에 남긴
- —mixed
    - 삭제된 commit의 기록을 working directory에 남김 (기본 옵션 값)
- —hard
    - 삭제된 commit의 기록을 남기지 않음

git restore

→ Modified 상태의 파일 되돌리기

→ working Directory에서 파일을 수정한 뒤, 파일의 수정 사항을 취소하고, 원래대로 되돌리는 작업

### Unstage 하는 명령어

1. git rm —cached
- staging Area에서 Working Directory로 되돌리기 (git 저장소에 “commit이 없는 경우”)
- - ex) $ git rm —cached 파일명
- to unstage and remove paths only from the staging area
1. git restore —staged
- staging Area에서 working Directory로 되돌리기 ( git 저장소에 “commit이 존재하는 경우”)
- ex) $ git restore —staged 파일명
- contents are restored from HEAD

### 정리

- 파일 내용을 수정 전으로 되돌리기
    - git restore
- staging Area에 올라간 파일을  Unstage 하기
    - git rm —cached
    - git restore —staged

---

# ChatGPT

- AI(chatGPT 등장 이전에 분야)
    
    ML(Machine Learning)
    
    - 모델을 만들어 인간을 모방하는 분야
    - 모델의 구성요소
        - 알고리즘
        - 데이터
    - 알고리즘에 기반한 방정식에 매개변수를 정할 수 있는 방식으로 데이터 제공(ax^2 + bx + c)
    - 알고리즘을 통해 생성된 결과를 돌려주는 것이 ML의 기본
    - 세부 분야
        - Neural Network : 인간의 신경을 모방한 네트워크
        - Deep Learning : Neural Network의 한 분야
    - 모듈의 기능에 따른 분류
        
        

### Generative AI

→ 오디오, 비디오, 이미지, 텍스트, 코드, 시뮬레이션 등의 새로운 컨텐츠를 생성하는 인공지능 모델

generative/ pre-trained/ transformer

생성 모델/ 사전 훈련/ 트랜스포머 AI 모델

### ChatGPT 주요 개념

- Generative AI
    - 기존 패텅을 기반을 오디오, 비디오, 이미지, 텍스트, 코드, 시뮬레이션 등의 새로운 콘뎉츠를 생성하는 인공지능 모델
- pre-trained
    - 거대 언어 모델 + 추가 학습 데이터 + 추가 강화 학습
- transformer
    - 문장 속의 단어 간 관계를 추적해 맥락과 의미를 학습
    - 이간처럼 일관되고 연관성이 높은 언어를 구사하여 대화형 작업에 강점

LLM(Large Language Model)

텍스트를 이해하고 생성하는 AI 프로그램, 대규모 언어 모델

### 트랜스포머 (Neural Network Architecture)

문장의 맥락을 효과적으로 이해하고 처리 → Attention 메커니즘

### Transformer 주요 개념

- Self-Attention 메커니즘
    - 입력 데이터 간의 관계와 중요도를 계산
- 병렬 처리 가능
    - RNN과 달리 순차 처리가 필요 없어 속도가 빠름
- 스케일링 가능
    - 대규모 데이터및 파라미터로 확정 가능
- GPT 모델은 특히 Transformer의 디코더 부분만을 사용
    
    
    ### Attention 메커니즘
    
    - AI가 데이터의 맥락과 중요도를 이해하도록 돕는 필수 기술
    - 입력 데이터의 각 요소가 출력에 얼마나 중요한지 중요도(weight)를 계산하는 기법
    - “중요한 것에 집중한다”는 아이디어를 바탕으로 설계됨
    - 종류
        - self-attention : 입력 데이터 내부에서 각 요소 간 중요도를 계산
        - Multi-Head Attention : 다양한 관심사(관점)를 병렬로 계산하여 성능 향상
    

---

## API(Application Programming Interface)

두 소프트웨어(또는 시스템)가 서로 통신할 수 있게 하는 메커니즘

- Interface
    - 서로 다른 두 개의 시스템(기기, 소프트웨어 등)이 정보를 교환할 때, 그 사이에 존재하는 접점
    - 사용자가 기기를 쉽게 동작 시키거나, 기계와 기계가 통신할 때 필요한 ‘약속된 방식’
- Interface 예시
    - 키보드, 마우스, 모니터
    
    → 컴퓨터와 사람 사이의 물리적 인터페이스
    
    - TV 리모컨
    
    → TV와 사람 사이의 인터페이스
    
    - 자동차 운전대, 페달
    
    → 자동차의 내부 장치와 운전자 사이를 연결
    
    - 스마트폰 터치 스크린
    
    → 디지털 인터페이스
    

### UI(User Interface)

- 사람(사용자)이 소프트웨어에 접근하는 그래픽적, 화면적 요소
- 예시
    - ATM의 언어 선택 화면
    - 브라우저의 뒤로가기 버튼
    - 스마트폰 앱의 아이콘 등

- 눈에 보이지 않는 영역의 통신
    - 실제로는 기계와 기계, 시스템과 시스템 사이에서도 수많은 ‘인터페이스’를 통해 정보를 주고받고 있음
    - 여기서는 화면(UI)이 없을 뿐, 약속된 방식으로 데이터를 주고 받음
    

---

## 웹의 동작 방식

CLIENT → (requests) → SERVER

CLIENT ← (responses) ← SERVER

클라이언트(Client) : 서비스를 요청하는 쪽

서버(Server) : 요청을 받아서 처리하고, 결과를 응답해주는 쪽

- Application
    - 특정 기능을 수행하는 모든 소프트웨어
    - 웹 모바일 데스크톱 앱 등, 우리가 만든 서비스나 프로그램도 모두 앱의 일종

- API 예시
    - 소셜 로그인 (ex. google ID로  chatGPT 가입)
    - 날씨 앱 (스마트폰 ↔ 기상청)

- API Key
    - API에게 요청을 보내는 애플리케이션을 구별하기 위한 고유한 식별 문자열

- API Key가 필요한 이유
    - 보안 강화
        - 무단 접근을 막고, 승인된 사용자(또는 앱)만 요청할 수 있도록
    
    - 데이터 관리
        - API 호출 횟수, 사용량 모니터링
        - 일정량 이상의 사용 시 제한 또는 과금 정책 적용 가능

- API Key  사용 시 주의 사항
    - 공개된 곳에 노출하지 말 것
    - 키가 유출될 경우 무단 사용 위험 → 정기 갱신 필요
    - 서버-클라이언트 구조에서 키를 안전하게 저장하는 방법들 고려
    

## 챗봇 프로그램 with ChatGPT

## Prompt Engineering

- 응답 다양성 제어
    
    temperature :다음 토큰(단어) 예측의 다양성을 조정(0~2)
    
    - 응답의 창의성과 다양성 조정
    - 
    
    top_p: 선택할 토큰의 확률 범위를 제한(0~1)
    
    - 누적 확률 기반으로 응답의 범위 제한
    - 확률이 안되는 것은 컷하는 방식
    - ex) 확률이 큰 분야부터 제일 작은 분야까지 가는데 1에 가까울 수록 확률이 낮은 애들까지 포함

---

## OpenAI API

### 토큰

- GPT와 같은 인공지능 모델에세 텍스트 데이터를 처리하고 이해하는 기본 단위
- 토큰은 문장에서 단어로 생각할 수 있음
    - 각 토큰별로 고유한 숫자가 매겨져있음
    - 영어보다 한글 문장을 표현하는데 더 많은 토큰 소요됨
        - 한글은 다양한 조합형 문자로 인해 토큰이 필요
- 최대 입력 토큰 제한: 각 LLM 모델마다 최대로 입력할 수 있는 토큰 수가 제한
- 토큰 수 확인: opentAI Docs tokenizer 페이지 활용

### OpenAI API 주요 파라미터

- 필수 파라미터
    - model: GPT 모델 이름 (예: gpt-4o-mini)
    - messages : 대화 메시지 기록
- 응답 다양성 제어
    - temperature: 다음 토큰(단어) 예측의 다양성을 조정(0~2)
        - 응답의 창의성과 다양성 조정
    - top_p: 선택할 토큰의 확률 범위를 제한(0~1)
        - 누적 확률 기반으로 응답의 범위 제한

temperature(0~2)

- 확률 분포를 날카롭거나 평탄하게 만드는 역할
- 높은 확률을 더 높게, 낮은 확률은 더 낮게 조정
- 모든 후보 단어의 확률을 조정하여 다양한 응답을 가능하게 함
- 낮은 temperature (ex. 0.5): 높은 확률 단어가 더 강화되어 일관성 있는 응답 생성
- 높은 temperature(ex. 1.5): 확률 분포가 평탄해져 다양한 단어가 선택될 가능성 증가

| 단어 | 확률 | 누적 확률 |
| --- | --- | --- |
| 김치찌개 | 0.4 | 0.4 |
| 된장찌개 | 0.3 | 0.7 |
| 라면 | 0.2 | 0.9 |
| 초밥 | 0.1 | 1.0 |

top_p(0~1)

- 확률 분포의 범위 (상위 확률의 단어들만) 제한
- 누적 확률 기준으로 단어 후보의 수를 제한
- 응답의 신뢰성과 예측 가능성을 조정
- 낮은 top_p(0.5) : “김치찌개”와 “된장찌개”만 후보로 남음
- 높은 top_p (1.0): 모든 단어를 후보로 포함

temperature와 top_p 함께 사용하기

- 낮은 temperature + 높은 top_p
    - temperature가 낮아 확률 분포의 차이가 더 강조됨 → 높은 확률의 단어에 집중
    - top_p가 높아 누적 확률 범위가 넓음 → 상위 확률 단어들을 다양하게 고려
        - 응답이 안정적이고 예측 가능
    - 활용 사례: 기술 문서 작성, 고객 지원
- 높은 temperature + 낮은 top_p
    - temperature가 높아 확률 분포가 평탄해짐 → 다양한 단어가 선택될 가능성 증가
    - top_p가 낮아 누적 확률 범위가 좁음 → 선택 후보가 제한적
        - 창의적이고 독창적인 응답
    - 활용 사례: 아이디어 도출, 소설 생성

### OpenAI API 실습

1. 필수 라이브러리 설치 및 설정

```python
!pip install openai

OPEN_API_KEY = "OPENAI_API_KEY"
```

1. 라이브러리 및 객체 초기화

```python
from openai import OpenAI
client = OpenAI(api_key=OPENAI_API_KEY)
```

- Client
    - OpenAI API를 호출하는 클라이언트 객체 생성
- api_key
    - OpenAI API 호출을 위한 인증 키
1. 대화 설정

```python
conversation_history = [
	{"role": "system", "content" : "당신은 사용자 질문에 답변하는 챗봇입니다."},
	{"role": "system", "content": "추가 설정"},
	]
```

- 대화 이력 저장
    - conversation_history에 대화 내용을 기록
- role=”system”
    - 역할: 기본 지침을 설정하고 대화의 전체적인 방향을 설정
    - 특징: 대화의 톤, 스타일, 특정 규칙 등을 정의
1. 사용자 질문 추가

```python
conversation_history.append({
	"role": "user",
	"content": "오늘 달달하고 매콤한 것을 먹고 싶은데, 점심 메뉴 추천해줄래?",
}]
```

- role=”user”
    - 역할: 사용자의 입력
    - 특징: 질문이나 명령 등 사용자가 챗봇에게 전달하는 메시지를 포함
1. OpenAI API 호출

```python
response = client.chat.completions.create(
	model="gpt-4o-mini",
	messages=conversation_history,
	max_tokens=500,
	temperature=1.0,
	top_p=1.0
	n=1,
	seed=1000;
)
```

- max_tokens: 생성할 응답의 최대 길이 설정 (최대 16,385 토큰까지 가능)
- n: 생성할 응답의 개수 (1로 설정 시 하나의 응답만 생성)
- seed: 랜덤 씨드 값을 고정하여 응답의 일관성을 유지
1. 응답 출력

```python
for response in response.choices:
	print(f"Assistant: {response.message.content}")
```

- response.choices
    - OpenAI API에서 생성된 응답 목록
    - n=1로 설정했기 때문에 응답 하나만 포함
- response.message.content
    - 생성된 응답 텍스트를 출력
