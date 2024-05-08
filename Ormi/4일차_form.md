# 4일차 (2024-05-08)

## 멘토님 피드백

- 다음 학습 계획, 학습 내용 등 간단한 회고
- 앞으로의 계획과 목표
- 실습 캡쳐 화면, 어려웠던 점, 해결 방법

## form

---

### Post
- `multipart/form-data`: `<input type="file">`이 존재하는 경우 사용

### Get
- `<input type="text" name="">` 에서 `name=""`은 ?{키}={값} 에서 {키}를 의미

### autocomplete

- `<input type="email" autocomplete="on" />`
- 보안적인 측면에서 사용하지 않는 것이 좋음

### input

#### 속성
![image](https://github.com/terranking1/TIL/assets/92567159/ce43e284-25a2-479b-b55b-c5f28ccc80b0)

#### 유형
![image](https://github.com/terranking1/TIL/assets/92567159/2f305094-65c9-4878-86f7-954e472d0a41)

### form 실습
```html
    <!--
    form: 사용자가 입력한 데이터를 서버로 보내기 위한 양식
    input: 사용자가 입력하는 부분
    label: input과 연결되어 있는 텍스트
    button: 사용자가 입력한 데이터를 서버로 보내는 버튼

    action: 내 요청을 처리할 주소, 비어있으면 나 자신
    method: 요청을 어떤 방식으로 보낼지에 대한 것
        get: 보통 데이터를 읽는 요청을 할 때 사용(검색어, 게시물 조회, 항공권 조회 등)
        post: 보통 데이터를 생성하는 요청을 할 때 사용(게시물, 회원가입, 댓글 등)

    데이터는 url로 보낸다
    url은 action에 의해 결정
    -->
    <!-- 보통 로그인은 POST로 처리-->
    <form action="" method="get">
        <input type="text" name="id">
        <input type="password" name="pw">
        <button>로그인</button>
    </form>
    <!-- 이렇게 많이 사용합니다.-->
    <form action="" method="get">
        <input type="text" name="q">
        <button>검색</button>
    </form>
    <!--
    로그인 버튼을 누르니 아래와 같이 주소창에 나타남
    htmlDay1/001.html?id=aaa&pw=bbb
    key1=value1&key2=value2&key3=value3의 양식으로 들어갑니다.

    #GET 처리 절차
    1. 로그인 버튼을 누르게 되면 브라우저에서 각각에 input의 name값과 value값을 가져와서 아래 패킷 데이터를 만듭니다.

    GET /001.html?id=aaa&pw=bbb HTTP/1.1              # 요청라인
    # ... 여러 정보 생략 ...
    host: 나 자신

    2. 이 패킷을 host로 보내서 처리합니다.

    3. 그런데 처리해야 할 사람이 나 자신입니다. 그래서 나 자신에게
    'htmlDay1/001.html?id=aaa&pw=bbb'이 뜨게 됩니다.
    
    #POST 처리 절차
    1. 로그인 버튼을 누르게 되면 브라우저에서 각각에 input의 name값과 value값을 가져와서 아래 패킷 데이터를 만듭니다.

    POST / HTTP/1.1
    Host: 나 자신

    {
        "id": aaa,
        "pw": "bbb",
        ... 생략 ...
    }

    2. 이 패킷을 host로 보내서 처리합니다.

    3. 그런데 처리해야 할 사람이 나 자신입니다.
    그런데 나 자신은 POST를 처리할 코드와 SW가 없습니다.
    그래서 아무것도 처리되지 않는 것처럼 보입니다.

    #GET 방식의 장점과 단점
    1. URL에 데이터가 노출되어 보안에 취약합니다. 예를 들어서 카페 같은 곳에 잠시 자리 비웠는데 누군가
    훔쳐보면 어떡해요? URL은 기본적으로 도청이 됩니다.

    2. 그래서 노출이 되어도 되는 데이터들은 GET으로 하고 보통은 검색창들이 이 GET으로 처리됩니다.

    3. 그러면 노출되어도 좋은 데이터는 무엇일까요? 그냥 다 post로 하면 안될까요?
    'https://search.naver.com/search.naver?where=nexearch&sm=top_hty&fbm=0&ie=utf8&query=weniv' 처럼 공유했을 때
    다른 사람도 이 URL로 바로 접속해서 같은 결과를 볼 수 있습니다.

    4. 그러나 검색 키워드를 GET으로 만드는 것이 절대적이진 않습니다. 예를 들어 정부의 부동산 서비스의
    경우에는 검색 키워드도 POST로 처리합니다. 보안상 정보를 감춰야 할 때에는 POST를 사용합니다.
    -->
    <a href="">안녕</a>
    <!--
        href 링크로 이동하게 합니다.
    -->
    <input type="button" value="안녕">
    <input type="submit" value="안녕">
    <!--
        인풋의 버튼은 동작을 하지 않습니다.
    -->
    <button>안녕</button>
    <!--
        button은 기본 타입이 submit이기 때문에 동작을 합니다.
        그래서 form안에 버튼이 있을 경우 form의 액션으로 이동합니다.
        안에 입력된 데이터들을 액션으로 보내는 역할을 합니다.
    -->
    <!-- 자주 쓰이는 input type -->
    <input type="text"><br>
    <input type="date"><br>
    <input type="email"><br>
    <input type="tel"><br>
    <input type="password"><br>
    <input type="checkbox"><br>
    <input type="radio"><br>
    <input type="file"><br>
    <input type="range"><br>
    <input type="color"><br>
    
    <input type="text" placeholder="검색어를 입력하세요.">

    <!--
        신뢰할 수 있는 데이터인지 항상 검증해야합니다.
        사용자가 입력한 데이터는 믿을 수 없습니다.
        프론트엔드에서도 검증하고
        백엔드에서도 검증해야합니다.
        required 속성이 적용되어도 개발자 도구에서
        조작이 가능하기에 백엔드에서도 검증해야합니다.
    -->
    <form action="" method="get">
        아이디
        <input type="text" name="id" required>
        패스워드
        <input type="password" name="pw" required>
        <button>로그인</button>
    </form>

    <!--
        데이터를 URL로 보내고 싶다면 GET방식을 사용
        데이터를 숨겨서 보내고 싶다면 POST방식을 사용
        email=hello%40gmail.com&password=1234&gender=male&html=on&css=on
        %40는 골뱅이 => URL인코딩
        hello@gmail.com => hello%40gmail.com
        hello world => hello%20world
        https://www.urlencoder.org/ko/
    
        인코딩: 우리가 원하는 방식으로 문자열을 변경
        디코딩: 원본으로 복구
    -->
    <h1>서비스이름</h1>
    <section>
        <h2>로그인</h2>
        <form action="" method="get">
            <label for="user-email">이메일</label>
            <input type="email" name="email" id="user-email">
    
            <label for="user-password">비밀번호</label>
            <input type="password" name="password" id="user-password">
    
            <fieldset>
                <legend>성별</legend>
                <label for="user-male">남</label>
                <input type="radio" name="gender" id="user-male" value="male">
                <label for="user-female">여</label>
                <input type="radio" name="gender" id="user-female" value="female">
                <label for="user-nothing">선택안함</label>
                <input type="radio" name="gender" id="user-nothing" value="nothing">
            </fieldset>
    
            <!-- checkbox에서 name을 다르게 하는 경우, ?html=on&css=on -->
            <fieldset>
                <legend>사용 기술</legend>
                <label for="html">html</label>
                <input type="checkbox" name="html" id="html">
                <label for="css">css</label>
                <input type="checkbox" name="css" id="css">
                <label for="javascript">javascript</label>
                <input type="checkbox" name="javascript" id="javascript">
            </fieldset>
            <!-- name은 같게 하되, value를 추가한 경우, ?skill=html&skill=css -->
            <fieldset>
                <legend>사용 기술</legend>
                <label for="html">html</label>
                <input type="checkbox" name="skill" id="html" value="html">
                <label for="css">css</label>
                <input type="checkbox" name="skill" id="css" value="css">
                <label for="javascript">javascript</label>
                <input type="checkbox" name="skill" id="javascript" value="javascript">
            </fieldset>
    
            <button>로그인</button>
        </form>
    </section>
```

### 기타
- 대부분 페이지의 이름(로고)가 h1
- 회원가입 <- 이런 것들은 보통 h2
- 프론트, 백엔드 둘 다 검증 중요!

### 생소, 어려웠던 내용

- fieldset, legend (014.html) - 처음 접해본 내용
- input checkbox 에서 name, value에 대한 고민
```html
<!--1-->
<label for="html">html</label>
<input type="checkbox" name="html" id="html">
<!--2-->
<label for="html">html</label>
<input type="checkbox" name="skill" id="html" value="html">
```
- 현재 생각으로는 `?html=on`의 결과를 띄는 1번 코드가 편하다고 생각하지만
- 백엔드를 설계하는 상황이 되어야 정확하게 알 수 있을 것 같다.

### 앞으로의 계획, 목표

- html 커스텀 단축키 만들기 (lang="ko" 세팅 등)
- 자주 사용하는 input type 숙지하기

