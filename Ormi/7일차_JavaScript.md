# 7일차 (2024-05-13)

## JavaScript

### JavaScript를 사용하는 방법들

---

1. 인라인 태그 - 사용 x
2. 바디 내 script 태그 - 편리
3. 외부 파일 - 사용 권장

### 변수

---

1. var - 사용 x
2. let - 재정의 불가능
3. const - 상수, 재정의,재할당 불가능, 초기화 필수
- let, const는 코드 블록 밖에서 접근 불가능
- **가리키는 값**이 반드시 변경되어야 할 경우는 let 아닐 시 const
> const 배열에 값이 추가되어도 Error가 나지 않음!

### 함수

---

#### 매개변수(파라미터)
- 함수 선언

#### 인자(아규먼트)
- 함수 실행(실제 값)

```javascript
function 라면레시피() {
    let 라면그릇;

    물 550ml를 끓인다;
    면과 분말 스프, 후레이크를 같이 넣는다;
    4분 40초간 더 끓인다;

    라면그릇 = 맛있는라면;

    return 라면그릇; // return에 도달하면 함수가 종료된다.
    라면을 먹는다; // 함수가 종료되었으므로 실행 x
}
```

### CSS flex 보충

---

#### flex-item 많이쓰는 속성
- flex-basis - flex-item의 크기를 설정하는 것으로, 브라우저가 극도로 작아지지 않는 경우에 크기를 유지한다.
- flex-grow - 여백 공간을 분할. `flex-basis:0`일 경우 전체 공간 분할
- flex-shrink - 0을 줄 경우 줄어들지 않는다.
> width, height의 %는 부모 요소 기준, vw vh는 뷰포트 기준

#### flex 연습
![image](https://github.com/terranking1/TIL/assets/92567159/518074b2-ef42-47b2-8685-2125e16d45f7)


```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            display: flex;
            flex-direction: column;
            height: 100vh;
        }
        header, footer {
            background-color: #323232;
            height: 30px;
            color: white;
            padding: 5px;
        }
        .cont-wrapper {
            display: flex;
            flex-grow: 1;
        }
        .cont-wrapper main {
            flex-grow: 1;
            background-color: whitesmoke;
        }
        .cont-wrapper aside {
            /*flex-grow: 1;*/
            flex-basis: 100px;
            flex-shrink: 0;
            background-color: #DBDBDB;
        }
    </style>
</head>
<body>
<header>
    <b>Header</b>
</header>
<div class="cont-wrapper">
    <main>
        <b>Main Content</b>
    </main>
    <aside>
        <b>Sidebar</b>
    </aside>
</div>
<footer>
    <b>Footer</b>
</footer>
</body>
</html>
```


### 생소, 어려웠던 내용

---

- `flex-basis` 는 처음 알게 되었고, `flex-shrink`는 익숙하지 않았는데 연습을 통해 이해하였다.
- let, const를 정확히 어떤 상황에 따라 어떻게 다르게 쓰이는지 감이 안잡힌다.
- flex 연습에서 나머지를 컨텐츠 부분으로 채우는 법
  - 전체 높이를 `height:100vh`로 설정하고, 컨텐츠 부분을 `flex-grow:1`을 주면 된다.

### 앞으로의 계획, 목표

---

- HTML/CSS 과정이 끝났으므로 복습차원으로 지금까지 배운 내용을 골고루 사용하여 간단한 화면 만들어보기
