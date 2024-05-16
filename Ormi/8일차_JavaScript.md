# 8일차 (2024-05-14)

## JavaScript

### 함수

---

- 필요 이상의 아규먼트를 넣었을 때 - 필요 아규먼트까지 적용되어 return
- 필요 이하의 아규먼트를 넣었을 때 - NaN return
- NaN - Not a Number

#### 선언문 (권장)
```javascript
function sum(x, y) {
    return x + y;
}
```
#### 표현식
```javascript
let sumXY = function(x, y) {
    return x + y;
};
```

#### 화살표함수
```javascript
let sum = (x, y) => {
    return x + y;
}

// 표현식이 한 줄이라면 중괄호, return 생략 가능
let sum = (x, y) => x + y

// 인자가 한 개라면 소괄호 생략 가능
let sum = x = x + 10
```

### 조건문

---

#### if 문
```javascript
let test = 5
if (text < 10) {
    // code 실행
}
```
```javascript
let x = 3;
let y = 7;

if (x == y) {
    console.log('if문으로 실행되었습니다.');
} else {
    console.log('else문으로 실행되었습니다.');
}
```
```javascript
let score = 69;
let money = 1000;

if (score > 90){
    console.log('참 잘했습니다!<br>');
  money += 100000
} else if (score > 80){
  console.log('잘했습니다!<br>');
  money += 10000
} else if (score > 70){
  console.log('했습니다!<br>');
  money += 1000
} else {
  money = 0
}

console.log(money);
```

#### 퀴즈
```javascript
// 두 가지 수를 전달하면 두 수의 합을 반환하는 함수를 만들어 주세요.
// 이때 두 가지 수를 전달하지 못했을 경우 “두 가지 수를 전달해야 합니다” 라는 메시지를 띄어야 합니다.
function add(val1, val2){
    if(String(val1 + val2) == 'NaN'){
        console.log('두 가지 수를 전달해야 합니다.');
    }
    return val1 + val2;
}

console.log(add(10, 30));
```

#### 삼항연산자
```javascript
let item = true ? 100 : 200;
console.log(item); // 100
```

- 활용 `hello${true ? 1 : 2}` -> `hello1`
> 조건문을 통해 결과물을 반환하고 싶다 -> 삼항연산자

#### 퀴즈
```javascript
// 두 수 a와 b를 입력받고, a와 b 중 더 큰 수를 출력하는 코드를 만들어보세요.
// 이때, a와 b가 같은 경우 "같은 숫자입니다"라는 문장을 출력하세요.
let a = Number(prompt('a를 입력하세요.'));
let b = Number(prompt('b를 입력하세요.'));
console.log(a > b ? a : a == b ? '같은 숫자입니다.' : b)
```
> `prompt()` 는 반환값이 문자열이다.

#### switch 문
```javascript
switch (표현식) {
  case 값1:
    // 값1에 대한 실행 코드
    break;
  case 값2:
    // 값2에 대한 실행 코드
    break;
  ...
  default:
    // 모든 case에 해당하지 않을 때 실행될 코드
    break;
}
```
- `break` 작성!

### 반복문

---

#### for 문

```javascript
let nums = [1, 3, 5, 7, 9]
for (let i = 0; i < nums.length; i++) {
    console.log(nums[i]);
}
// 출력결과
1
3
5
7
9
```

### 생소, 어려웠던 내용

---

- 숫자 타입 형변환을 `parseInt`만 알고 있었는데 `Number`을 새로 알게되었다.
- if vs 삼항연산자 - 반대 경우의 수가 없을 때
    - `if(true) console.log("같은 숫자입니다.");`
    - `true ? console.log("같은 숫자입니다.") : undefined`

### 앞으로의 계획, 목표

---

- 효율적인 코드도 좋지만 코드롤 효율적으로 쪼개는 연습하기
- 단순한 조건문은 삼항연산자 사용해보기
