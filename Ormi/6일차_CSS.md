# 6일차 (2024-05-09)

## CSS

### CSS Box Model

---

- 자식의 마진은 부모에 포함되지 않음
- `display: flow-root;`: 자식의 마진 영역까지 부모에 포함
> 여러 요소들의 간격을 둘 때 마진병합을 이용하자 ex) `margin: 10px 0 10px 0;`

#### overflow
- `hidden`: 초과 범위를 잘라낸다
- `scroll`: 잘라내고, 스크롤 제공
- `auto` : 초과할 경우 자동으로 스크롤 노출
> `overflow-y: scroll`을 적용했는데 x축도 스크롤 생길 경우 `overflow-x: hidden`

#### opacity
- 0-1 사이의 숫자 (0: 투명, 1: 불투명)

### position

---

#### static
- 기본값, 노멀 플로우

#### relative
- 원래 자신이 있어야 하는 위치(static)에 상대적
    - top, bottom, right, left로 이동

#### absolute
- 노멀 플로우에서 벗어나게 한다.

#### fixed
- 뷰포트를 기준으로! (현재 보이는 화면)

#### sticky
- 조상에 스크롤이 있다면 가장 가까운 부모 요소의 컨텐츠 영역에 붙는다.

![image](https://github.com/terranking1/TIL/assets/92567159/7c625c8c-76c3-4cb5-abdb-9ee56f567962)

#### z-index
- static은 적용 불가
- z-index 값이 같을 경우 나중에 렌더링 된 요소가 위에 위치함
- 부모 z-index가 없을 경우 자식 z-index는 독립적으로 적용됨
- 부모 z-index 값이 존재하지만 부모 레벨의 다른 요소 z-index 값보다 부모 z-index 값이 낮을 경우
자식 z-index 값이 아무리 높아도 다른 요소의 위에 위치할 수 없다!
- z-index 의 음수는 -1까지만 지원!
> 실무에서는 1,2,3,4 단위보다는 10,20,30,40 단위로 사용함!

### flex

---

#### `display: flex`
- 부모 입장에서 자식들의 위치를 설정할 수 있게 해주는 속성
- 반드시 부모가 되는 요소가 있어야 되고, 자식이 되는 요소가 있어야 된다.
- 부모 요소 : flex-container
- 자식 요소 : flex-item

#### flex-container
- `justify-content`: 주축, `align-items` : 교차축
  - `flex-start` `flex-end` `center` `space-between` `space-around` `space-evenly`
- `flex-direction`: 주축의 방향
  - `row` `column` `row-reverse` `column-reverse`

#### flex-item
- `gap`: 간격

### 생소, 어려웠던 내용

---

- `position: sticky` 의 원리에 이해가 어려워 따로 실습을 해보았다.

### 앞으로의 계획, 목표

---

- 5일차 과제에서 자식이 부모를 삐져나가는 현상
  - => 높이를 부모가 아닌 자식에게 주자
- 강사님 과제 코드 분석하기

### flex 연습

---

- 유진 멘토님의 진으로 연습해봤습니다!


![image](https://github.com/terranking1/TIL/assets/92567159/9b7e61bc-ae0e-48db-8eab-759636cf2523)


