# 9일차 (2024-05-16)

### 반복문 보충

---

#### do-while문
- 조건이 거짓이더라도 최소한 한 번은 실행되어야 할 때!

```javascript
let input;

do { // 한 번은 무조건 실행
  input = prompt("숫자를 입력하세요.");
} while (isNaN(input)); // 참일 경우 do 문 실행

console.log("입력한 숫자는 " + input + "입니다.");
```

#### break&continue

```javascript
// while문의 break
let num = 0;
while (num < 11) {
    num++;
    document.write(num, '<br>');
    if (num > 5) {
        break;
    }
}

// for문의 continue
for (let i = 0; i < 20; i++) {
    if (i < 13) continue;
    console.log(i + '살은 청소년입니다.');
}
```


## 타입

### 원시타입

---

- `string`, `number`, `bigint`, `boolean`, `undefined`, `symbol`, `null`
- 값의 참조가 아닌, 값 자체가 저장됨
- `undefined` - 초기화가 안되어 있는 경우
- `null` - 데이터가 없는 상태

### 객체타입

---

- 값과 메서드를 가진다.
    - ex) `const myArr = [1,2]` `myArr.push(10)`
- 값 자체가 아닌, 값의 위치가 저장됨
```javascript
const arr1 = [1,2]
const arr2 = [3,4]

const arr3 = arr1 // arr3 => [1,2]
arr3 = arr2 // const 라서 에러
arr1.push(5) // arr3 => [1,2,5]
arr3.push(6) // arr1 => [1,2,5,6]
```

#### 배열(Array)
```javascript
const arr = [];
const arr = [1, 2, 3];
const arr2 = new Array(4, 5, 6); // 권장 x
const arr2 = new Array(3); // 권장 x
```
- `length` -> 배열의 길이
    - `arr.length`


- `push()` -> 맨 끝에 배열의 요소 추가
    - `arr.push(4)`
    - `arr.length` 반환


- `pop()` -> 배열의 마지막 요소 삭제
    - `arr.pop()`
    - 삭제된 요소 반환


- `shift()` -> 맨 앞에 배열의 요소 추가
    - `arr.shift(0)`
    - `arr.length` 반환


- `unshift()` -> 배열의 맨 앞 요소 삭제
    - `arr.unshift()`
    - 삭제된 요소 반환


- `splice()` -> 배열의 요소 추가, 삭제
    - `arr.splice(시작 인덱스, 삭제 개수, 추가할 요소)`
    - 삭제된 요소의 배열 반환


- `slice()` -> 배열의 요소 추출
    - `arr.slice(시작 인덱스, 끝낼 인덱스)`
    - 추출된 배열 반환
> `slice` 를 사용한다고 해서 추출된 배열로 저장되는 것은 아님!


- `sort()` -> 사전식 정렬. 숫자가 아닌 문자로 인식
    - `arr.sort((a, b) => a - b);` 오름차순
    - `arr.sort((a, b) => b - a);` 내림차순


- `forEach()` - 배열의 요소를 순환 (자주 사용됨)
```javascript
arr.forEach((item) => {
    console.log(item)
})

arr.forEach((item, index) => {
  console.log(item)
  console.log(index)
})

arr.forEach((item, index, arr) => {
  console.log(item)
  console.log(index)
  console.log(arr)
})
```

- `map()` - 새로운 배열 반환 (중요)
```javascript
const data = [
    {
        "_id": "642ba3980785cecff3f39a8d",
        "index": 0,
        "age": 28,
        "eyeColor": "green",
        "name": "Annette Middleton",
        "gender": "female",
        "company": "KINETICA"
    },
    {
        "_id": "642ba398d0fed6e17f2f50c9",
        "index": 1,
        "age": 37,
        "eyeColor": "green",
        "name": "Kidd Roman",
        "gender": "male",
        "company": "AUSTECH"
    },
    {
        "_id": "642ba39827d809511d00dd8d",
        "index": 2,
        "age": 39,
        "eyeColor": "brown",
        "name": "Best Ratliff",
        "gender": "male",
        "company": "PRISMATIC"
    }
];

const ages = data.map((item) => item.age);
// ages => [28, 37, 39]
```

- `filter()` - 특정 조건을 만족하는 요소들을 배열로 추출
```javascript
const nums = [1,2,3,4,5]
const result = nums.filter((num) => {
  return num % 2 === 0
})
// result => [2, 4]
```

- `includes()` - 요소가 포함되어 있으면 true 아니면 false 를 반환
```javascript
const nums = [1,2,3,4,5]
nums.includes(4) // true
nums.includes(6) // false
```

#### 객체
```javascript
const obj = {
    'name': 'park', // 프로퍼티
    'age': 26, // 프로퍼티
    testfunction: function () { // 메소드
        console.log("hello");
    },
}
```

### 생소, 어려웠던 내용

---
- 비슷해보이지만 다른 Map과 Object
- push로 넣었으면 pop으로 빼야지 스택이 유지된다
  - 스택을 유지해야 되는 이유? 이점?

### 앞으로의 계획, 목표

---
- 배열의 메소드 익히기
- 화살표 함수 익히기
- 가볍게라도 알아놓기
  - 깊스너큐(깊이우선탐색 스택 너비우선탐색 큐)
  - 물데네전세표응(OSI7계층)

#### 기타 자료
![image](https://github.com/terranking1/TIL/assets/92567159/52a59fb3-5469-4e7f-8f39-e3269e3e4e55)

