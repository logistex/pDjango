# 파이썬 웹 프로그래밍 실습

## 2. 장고 기초

### 2.1 개발 환경 세팅

- 가상환경 생성
  - 파이썬 버전 3.7.1
  - 장고 버전 2.1.3
  - 아나콘다에서 해당 버전의 가상환경 설치
    - [아나콘다 설치](./anaconda.md)
    - 콘다 홈 디렉토리를 작업 폴더로 변경
    - 아나콘다 파워쉘 프롬프트 작업
```
(base) $ python --version                             # Python 3.7.6 확인
(base) $ conda env list                               # 기존 가상환경 목록 확인
(base) $ conda create -n vnv_dj python=3.7.1          # 가상환경 생성
(base) $ conda env list                               # 가상환경 생성 확인
(base) $ conda activate vnv_dj                        # 가상환경 활성화
(vnv_dj) $ python --version                           # 파이썬 버전 확인
(vnv_dj) $ conda install -c conda-forge django=2.1.3  # 장고 설치
(vnv_dj) $ python -m django --version                 # 장고 버전 확인
(vnv_dj) $ conda list                                 # 현 가상환경에 설치된 패키지 확인
(vnv_dj) $ conda env export > vnv_dj.yml              # 가상환경 설치 내역 출력 (!!! utf8(BOM 없음) 변환 필요함 !!!)
(vnv_dj) $ conda deactivate                           # 가상환경 비활성화
```

- 가상환경 (삭제 및) 복원 연습
```
# 아나콘다 파워쉘 프롬프트 새로 열고 작업
(base) $ conda env list                               # 가상환경 목록 확인
(base) $ conda remove -n vnv_dj --all                 # 가상환경 삭제
(base) $ conda env list                               # 삭제 여부 확인
(base) $ conda env create -f ./vnv_dj.yml             # 가상환경 복제
(base) $ conda env list                               # 가상환경 생성 여부 확인
(base) $ conda activate vnv_dj                        # 가상환경 활성화
(vnv_dj) $ conda list                                 # 패키지 버전 확인
```

- 파이참 설치
  - 다운로드 https://www.jetbrains.com/ko-kr/pycharm/download/#section=windows
  - Professional 버전을 다운로드 받아 설치 (교재 참조)

### 2.2 기본 프로젝트 생성
1. 프로젝트 생성
    - 교재 Step 02까지는 동일
    - 교재 Step 03 ~ 08
     - `Project Interpreter`에서 `Existing Interpreter` 선택하고, `...` 단추 클릭
     - `Add Python Interpreter`에서 `Conda Environment` 선택하고,
       - `Interpreter` 항목에서 `▼` 클릭하여 `C:\anaconda3\envs\vnv_dj\pytnon.exe` 선택
       - `Make available to all projects` 항목 체크
       - `OK`
     - `Create`
    - 교재 Step 09 ~ 10
     - `Terminal` 열면, `(vnv_dj) C:\somewhere\to\working_folder>` 프롬프트가 보임
     - `django-admin startproject config .`   # 장고 프로젝트 생성
     - `python manage.py migrate`             # DB 초기화

2. 프로젝트 구조 이해
3. settings.py 이해
4. wsgi.py 이해

### 2.3 장고 기본 명령

### 2.4 디자인 패턴과 MTV
  - `python manage.py startapp app_default`   # 앱 생성

### 2.5 관리자 계정 생성
  - `python manage.py createsuperuser`        # 관리자 계정 생성

### 2.6 사이트 확인
  - `python manage.py runserver`              # 개발용 웹 서버 기동
  - http://127.0.0.1:8000
  - http://127.0.0.1:8000/admin

### 다음 공부
- 교재 3장 설문조사
- [장고 공식 문서](https://docs.djangoproject.com/ko/3.0/)의
  첫 번째 장고 앱 작성하기 (7부작) 중에서
  [part 1](https://docs.djangoproject.com/ko/3.0/intro/tutorial01/)
