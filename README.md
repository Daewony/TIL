# TIL
### 주말 외 매일 업로드 할 것!
### 시작은 미미하나 끝은 창대하리라!

20211221{
### flask로 프론트엔드와 백엔드 둘다 지원하기: jinja2 template

+jinja2 템플릿: 

+html 코드에 변수, 조건문, 반복문 넣을 수 있는 엔진

+정적 웹페이지에 반복문이나 조건문을 설정할 수 있도록 도와주는 템플릿?

+여태까지 render_template() 함수를 활용해서 정적인 html 페이지 리턴

+리턴할 페이지에 변수를 넣어서 변수에 값에 따라 조건문 반복문을 활용해 html 코드를 변경 가능

+⇒ 사용자에게 변경된 페이지 보여줌

```python
{{ 변수명 }}
```

+html 코드 안에 jinja2 템플릿 문법을 쓴 코드를 넣으면 하나의 템플릿이 됨,

+변수나 조건들을 바꿔넣으면 최종 html 코드 완성 → 사용자에게 정적으로 리턴

+이 기능 알면 프론트엔드 페이지를 자유자재로 할 수 있음

+ex) 로그인창 아이디 로그인 기입후 비밀번호 기입할때 그 장면 

+~~~~@~~~~.com → 변환되서 보여줌

+password: ????

+정적인 페이지를 변환해서 기본적인 페이지 제작 가능

---

+  jinja2 템플릿 반복문

```html
{% for i in range(10) %} 
{{ 변수명 }}
{% endfor %}
```

+ jinja2 템플릿 조건문

```html
**{% if %}**
{% elif %}
{% else %}
**{% endif %}**
```

+ jinja2 템플릿 주석

```html
{# #}
```

+여태 배운것

+(REST API)라우팅 경로 지정 → 데코레이터 실행되는 함수 안에서 html 코드를 리턴 → 사용자 웹브라우저에서 보여줌

+만약 html 코드를 다른 사이트에서 가져온다면? 구글 사이트 가져와보기

+거의 비슷한 형태로 보여줌(약간 이상한데 css 파일 없으니)

+html 코드, 페이지 리턴 = 경로 라고 표현

+계산된 결과, 조건에 맞는 결과 JSON 포맷으로 리턴 = REST API

}


20211219{
+VSCode:터미널 powershell 오류

+vscode: 계속 OUTPUT에서 출력됨, Extenstion > Run Code Configuration >Run In Terminal 설정, 항상 터미널로 실행되도록 변경

### 프론트엔드와 백엔드 flask로 한번에 구현

 

+request.args.get(파라미터 변수)

+HTTP 요청 → 여러개 파라미터 보냄 → (파라미터 이름 알음) = request.args.get 함수로 해당 값을 가져올 수 있음

+주소에서 ?~~~~~ 이 부분

+리턴 jsonify(data) → 프론트엔드에서 받음

+주소의 ? 이후는 파라미터이다

+아나콘다 프롬트 에서 REST API 잘 작동하는지 확인하기(GET방식)

http GET http://localhost:8081/login?user_name=dave&pw=111&email_address=korea@gmail.com

---

**form** method, action 버튼 누룬 후 반응(ex. 페이지 요청), input type,

+go live 하면 편하지만 임시 주소를 줘서 기존 8081과 만들어진 5050으로 달라질 수 있으니 action에서 자세히 주소를 설정해서 성공해라

---

### flask 로 정적 웹페이지 로드하기 (프론트엔드 페이지도 flask로 보여줄 수 있음)

+flask render_template(HTML파일명):HTML파일전송 + HTML파일은 flask 가 실행되는 하위폴더인 templates폴더 안에 위치 해야함

+Bootstrap 활용

+app 객체에 static의 path 추가하기

}


17일 실수로 못올림
20211217{
+라우팅 기법
+/<인자> 로 해서 새로운 주소 및 리턴값 생성 가능
+<인자>값의 데이터 타입 지정 가능

+flask로 REST API 만들기

+데코레이터로 만들기?

+마이크로 서비스

+데이터 ⇒ CRUD!

1. HTTP 프로토콜 
2. → 4가지 HTTP method 
3. → CRUD = **POST, GET,** PUT, DELETE
4. → REST API 구현(백엔드는 REST API 제공 기능)
5. 컴퓨터 간에 데이터 교환 및 컴퓨터 분산
6. 상용화된 서비스 제작

+JSON형식이 뭐지?

+JSON format : 파이썬에 있는 사전 데이터 타입과 동일함

+REST API로 데이터를 주고 받음 → 데이터를 주고 받음 = 포맷이 필요함, 그 포맷이 JSON 포맷 

+JSON 형태로 데이터를 보내고 받아 처리

+짝궁: REST API & JSON 포맷

+httpie 설치

+백엔드 서비스 구현 = 여러가지 REST API 만들기 + REST API 수시로 테스트 하기 

+테스트 할때마다 [ 웹서버 띄우기 + 웹브라우저 접속 + 데이터 보기 ] ⇒ 어휴 비효율적

+간단한 명령으로 REST API가 정상적으로 동작 및 응답 확인

+터미널 상태 익숙해져야함

+httpie 사용법
+http 명령 + http 메서드 + URL/URI (주소)

+예시)

```python
http GET http://localhost:8081/json_test
```

+flask jsonify() 함수: 리턴 데이터를 JSON 포맷으로 제공

```python
from flask import Flask, jsonify

def server_json():
	data = {'server_name':'0.0.0.0','server_port':'8080' }
	return jsonify(data)
```

+flask → REST API → return JSON
}


20211216
{
+ WWW 와 관련 있는 것: HTML(데이터), URL(주소), HTTP(통신)
+ 라우팅: 적절한 목적지를 찾아줌(URL)
+ flask로 웹서버 구동 (WAS 프레임워크이지만)
+ 데코레이터 문법
+ 숙제 git 기본 공부, github블로그 만들기!
}




20211215
{
+ 백엔드: 로직 + 데이터베이스 관리 + 웹서버 관리
+ 프론트엔드: 웹페이지 틀 & 구성 제작
1. Client - 웹서버에 HTTP 요청 
2. 웹서버 - 백엔드에게 요청
3. 백엔드 - 데이터가 저장된 데이터베이스와 통신
4. 백엔드: 로직 + 데이터 처리
5. 데이터 처리 결과 - 프론트 엔드에 전달
6. 프론트엔드 + 데이터 처리된 것 - 웹서버에 전달
7. 웹서버 - HTTP 반응 - Client

+ 1세대: 만들어진 것에 만족 = 유통기한 지난 빵이라도 먹을 순 있음
+ 2세대: 자동 구성(DB) = 매주마다 새로운 빵이 나옴 (이제 유통기한 지난 빵 안먹어도 돼!)
+ 3세대: 특정 부분만 바꿀 수 없을까? = MVC 패턴, 웹서비스 개발(+MVC패턴 프레임워크 탄생) = 빵(재료, 반죽, 굽기) 담당으로 구조화함
+ 4세대: 어떻게하면 빠르게 페이지를 보여줄까?(이용자가 많아도) = 서버 분산(통신을 통합, REST API 사용(데이터 요청&응답) ) = 빵 공장 설립(공장 크기에 따른 재료,반죽,굽기파트)

+ 풀스택 vs 마이너스?

+ from 라이브러리 import 클래스
+ ' !pip install ~~~ ' VS pip install ~~~ 차이
+ !를 안하면 아래와 같은 문장 발생하는 차이가 있다
+ Note: you may need to restart the kernel to use updated packages.


+ !!!숙제: 사진 업로드 및 노션 연결 내일 시도해봐야지! 깃허브 블로그도!
}
