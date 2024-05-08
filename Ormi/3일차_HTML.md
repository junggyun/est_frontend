# 3일차 (2024-05-07)

## HTML

### HTML 기본

---

#### `<>` 시작 태그 `</>` 종료 태그의 쌍으로 구성

    <p>Hello</p>

#### 빈 요소

    <br > <input type="text"> <img src="" alt="">

#### 주석

- 최소한으로 남기기

```html
<!-- 폼 시작 -->
<form>...</form>
<!-- 폼 끝 -->
```

#### 부모, 형제, 자식, 자손

![image](https://github.com/terranking1/TIL/assets/92567159/7b66979e-13b1-4cfa-9fed-de99fd9c8e5d)

```html
<html>
  <head></head>

  <body>
    <section>
      <h1>
        <strong></strong>
      </h1>
      <img />
      <div>
        <p><strong></strong></p>
        <p><strong></strong></p>
        <p><strong></strong></p>
      </div>
    </section>
  </body>
</html>
```

<br>
<br>
<br>

### HTML 문서해부

---

#### \<!DOCTYPE html>

- '이 문서는 html Living Standard 문서!' 라는 의미

#### \<html lang="">

- 주 언어 설정
- 주 언어는 검색엔진, 스크린리더, 번역 기능 제공 등에 영향

#### head

- 문자 코드의 종류 설정
  - `<meta charset="utf-8">`
- 뷰포트의 너비

  - `<meta name="viewport" content="width=device-width, initial-scale=1.0" />`

- title

  - 브라우저의 제목 표시줄, 페이지 탭에 노출
  - 검색엔진이 탐색할 페이지 제목
  - 약 60자 제한

- body
  - 사용자에게 보이는 영역

<br>
<br>
<br>

### 블록 레벨 요소 vs 인라인 요소

---

![image](https://github.com/terranking1/TIL/assets/92567159/32a45167-29da-4c72-9088-0089fbd6496e)


#### block

- 부모 너비 전체를 차지
- 줄바꿈
- 구조적 요소 표현에 사용
- ex) div, p, form

#### inline

- 항상 블록 요소 내에 포함 (독립 불가)
- 문장, 단어 같은 작은 부분 표현에 사용
- 줄바꿈 x
- ex) a, label, input

#### block / inline / inline-block

![image](https://github.com/terranking1/TIL/assets/92567159/a129cca9-27b8-4e5c-a026-66f89a826d7f)

<br>
<br>
<br>

### 다양한 태그들

---

#### div & span

- div
  - 컨텐츠 분할
  - 블록 요소

```
💡 div 보다는 최대한 시맨틱 태그 사용
```

- span
  - 인라인 요소

#### Sections

- header
  - 소개 및 탐색
- nav
  - 탐색
- footer
  - 페이지의 작성자, 저작권정보, 관련 문서 등
- main
  - 주요 컨텐츠
  - 한 번만 사용 가능
  - 여러 페이지에 반복되는 컨텐츠 포함 불가
    - 검색 폼이 주요 기능이라면 예외
- article
  - **독립적**으로 재사용 가능한 구획
  - 게시판, 블로그 글, 매거진, 뉴스 기사, 위젯, 실시간 채팅 창 등
  - 제목 요소 필수!
- section
  - 제목 요소 필수!
  ```
  💡 article vs section
  일단 article 사용을 우선 고민해보세요. 독립적으로 사용한다면 article 사용하시고,
  웹페이지의 앞뒤 문맥이 연결성이 필요하거나, 더 적합한 의미를 가진 요소가 없을 때 section을 사용하세요!
  단순 스타일링이 목적이라면 div 요소를 사용합니다!
  ```
- aside
  - 광고, 배너 등

#### Contents

- h1~h6
  - 레벨 순서에 맞게 작성
  ```html
  <h1>위니브</h1>
  <h2>위니브 캐릭터</h2>
  <h3>라이캣</h3>
  <h3>칠리</h3>
  <h3>개리</h3>
  <h2>위니브 소개</h2>
  <h3>위니브는...</h3>
  <h3>위니브 커리큘럼</h3>
  ```
  ```html
  <h1>위니브</h1>
  <h3>라이캣</h3>
  <!-- X -->
  <h2>위니브 캐릭터</h2>
  <h3>칠리</h3>
  <h3>개리</h3>
  <h2>위니브 소개</h2>
  <h4>위니브는...</h4>
  <!-- X -->
  <h3>위니브 커리큘럼</h3>
  ```
- a

  - href
    - `tel:` : 전화번호
    - `mailto:` : 이메일주소
  - target
    - `_self` : 현재 페이지(기본값)
    - `_blank` : 새 탭
  - `download`

  ```
  💡 인라인 요소이지만, 예외적으로 블록 요소들을 감쌀 수 있습니다!
  ```

  ```html
  <a href="b.html">b.html으로 이동</a>
  <a href="b.html" target="_blank">b.html 새탭으로 이동</a>
  <a href="b.html" download>b.html 파일 다운로드</a>
  <a href="mailto:google@gmail.com">mailto:google@gmail.com</a>
  <a href="tel:010-0000-0000">010-1234-1234</a>
  ```

  - 해시 링크

  ```html
  <a href="#main-text">본문으로 이동</a>
  ... ... ...
  <main id="main-text"></main>
  ```

- p
  - 하나의 문단
  - 블록 요소
- strong
  - 긴급 콘텐츠
- br
  - 줄바꿈
- hr
  - 단락 구분
  - `<p>` 태그 내 사용 x
- code
  - 짧은 코드
  ```html
  <code>push()<code></code></code>
  ```
- pre
  - HTML에 작성한 내용 그대로 표현 (줄바꿈, 공백)

#### 목록 태그

- ol
  - 순서가 중요할 때
- ul
  - 순서가 중요하지 않을 때
- li
  - 목록(ol, ul)의 항목
  - 단독으로 사용 불가

```
💡 ol,ul의 자식요소로는 li만 사용할 수 있습니다!
```

#### Media

- img
  - `src`: 경로
  - `alt`: 대체 텍스트, 이미지에 대한 설명
    - `alt=""`: 생략이 아닌 빈 값!

![image](https://github.com/terranking1/TIL/assets/92567159/692e9fc4-24ad-4bb7-bb50-e72d3ddd3cca)

## 기타

- TIL 작성 요령 다지기
- 최대한 시맨틱한 태그 사용하기
- HTML emmet 암기
