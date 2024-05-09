# 5일차 (2024-05-09)

## CSS

### CSS 적용 순위
1. 브라우저 css
2. 인라인 css
3. 내부 css
4. 외부 css
    - `<link rel="stylesheet" href="style.css">`
     - link를 style위에 써야함

> 웬만하면 외부 css 방식을 사용할 것!

### CSS 상속

- width, height, margin, padding, border 등
- 요소의 크기와 위치에 영향을 주는 css는 상속이 되지 않는다.
- input, button과 같은 form 관련 태그들 또한 상속이 되지 않는다. (브라우저 스타일 때문에)

> inherit, initial은 거의 쓰지 않는다!

### CSS 선택자

#### 타입 선택자
```html
h1 {
	font-weight:bold;
}
p{
	font-size: 24px;
}
```

#### 아이디 선택자(#) - 중복 x
```html
#header {
padding: 10px;
}
```
```html
<header id="header">
...
</header>
```

#### 클래스 선택자(.) - 중복 o
```html
.fc-red {
	color: red;
}
```
```html
<h1 class="fc-red">hello wolrd</h1>
<p>Lorem ipsum dolor sit amt</p>
<p class="fc-red">Lorem ipsum dolor sit amt</p>
```

#### 그룹 선택자(,)
```html
h1, h2, h3, h4, h5, h6{ 
    font-weight:bold;
}
```

#### 가상 클래스
| `:link` | 방문하지 않은 링크 |
| --- | --- |
| `:visited` | 방문한 링크 |
| `:hover` | 마우스 커서를 올려 놓았을 때 |
| `:active` | 마우스로 클릭했을 때 |
| `:focus` | 포커스 되었을때 |

#### 선택자 연습 사이트

https://css-speedrun.netlify.app/

### CSS 선택자 우선순위

#### 1.후자우선의 원칙
- 동일 선택자일 경우 뒤에 적힌 속성을 따름

#### 2.구체성의 원칙
1. inline 스타일 속성
2. id `#`
3. class `.`, 가상 클래스, 속성 선택자
4. type(tag), 가상 요소 선택자

> 아무리 구체적으로 작성하였다 하더라도,
가중치의 점수가 클래스선택자 > 유형 선택자 가중치 법칙을 이길 수 없다!

#### 3.중요성의 원칙
- `important` - 최우선
> important 는 최대한 사용하지 않기!

### CSS Box Model


#### box-sizing
- `content-box`: 기본값. width,height
- `border-box`: width,height + border + padding

### 생소, 어려웠던 내용

- CSS 선택자 우선순위 퀴즈 2번
  - 클래스 + 타입 선택자 11점 > 타입 선택자 12점
  - 점수보다 클래스 > 타입 가중치 법칙이 중요하다는 것을 알게되었다.

- 💡 [주의] CSS 속성으로 시각적인 부분이 바뀌었을 뿐 태그 자체의 요소가 블록 레벨로 바뀐 것은 아닙니다!
    - 태그 자체의 요소가 바뀌지 않는 이유는..?

- weniv 로그인 화면 과제에서 테두리 안쪽 공백(19px, 16px, 16px, 18px) 
  - padding vs margin

### 앞으로의 계획, 목표
- weniv 로그인 화면 과제에서 평소 자주 쓰던 flex를 사용하여 구현했는데
아직 경험이 부족한 block, inline, inline-block만을 활용해서 다시 구현해볼 것이다.
