# 12일차 (2024-05-21)

## JavaScript

### DOM

---

#### DOM 접근
- `document.querySelector(target)`

#### DOM 제어
1. 이벤트 삽입
    - `target.addEventListener(type, listener)`

2. 클래스 제어
    - `target.classList.add("hidden")` - 추가
    - `target.classList.remove("hidden")` - 삭제
    - `target.classList.toggle("hidden")` - 토글
    - `target.classList.contains("hidden")` - 포함 여부

3. 요소 제어
    - `document.createElement(target)`
    - `document.createTextNode(target)`
    - `element.appendChild(target)`
    - `element.removeChild(target)`
    - `element.append(target)`
    - `target.remove()`

4. element, text 노드 생성 추가
    - `textContent`
    - `innerHTML` - 태그도 처리 가능
   > 요소만 생성할 경우는 `innerHTML`을 사용하지만,   
   > 이벤트까지 필요한 경우는 `createElement`, `append` 등을 사용한다.

5. 속성 제어
    - `target.style.?` - 인라인 스타일로 적용되므로 사용 xx
   > 단! 연산을 통한 수치를 변경해야될 경우는 사용
