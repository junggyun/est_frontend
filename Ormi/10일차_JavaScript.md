# 10일차 (2024-05-17)

## JavaScript

### JavaScript 타입 보충

---

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

- 객체 값에 접근하는 방법
  1. 객체['키']
  2. 객체.키


- 객체 프로퍼티
  - 생성
    - 객체['키'] = 값
    - 객체.키 = 값
  - 삭제
    - delete 객체['키']
    - delete 객체.키


- 객체 메소드
  - `hasOwnProperty()` - 프로퍼티 존재 여부
  - `for ... in` - 프로퍼티 순환 ex)`for(const num in nums)`
    > 프로퍼티의 순서는 보장되지 않음!
> '123num' 과 같이 객체의 키 변수명이 지켜지지 않았을 경우,   
키를 문자열로 선언하고 대괄호로 접근해야한다.
```javascript
//잘못된 예시
const obj = {
    123num : 123 // 키 이름이 문자열이 아님
}
console.log(obj.123num) // 대괄호로 접근하지 않음

//올바른 예시
const obj = {
    '123num' : 123
}
console.log(obj['123num'])
```

### this

---
> this가 호출된 위치에 따라 참조 대상이 달라진다!

```javascript
// 전역에서 console.log(this); 가 호출됐으므로 this는 window를 참조
let myObj = {
    val1: 100,
    func1: function () {
        console.log(this);
    }
}

let test = myObj.func1;
test()

// my.Obj.func1()의 반환값은 undefined이므로, test()는 함수가 아니다.
let myObj = {
    val1: 100,
    func1: function () {
        console.log(this);
    }
}

let test = myObj.func1();
test()
```
```javascript
function sayName(){
  console.log(this.name);
}
var name = 'Hero';

let peter = {
  name : 'Peter Parker',
  sayName : sayName
};

let bruce = {
  name : 'Bruce Wayne',
  sayName : peter.sayName
};

bruce.sayName();

// 출력 결과 
// Bruce Wayne
```

### 객체지향 프로그래밍

---

#### 객체 = 추상화한 것
- 행동과 상태를 가진다.
  - 행동: 메소드
  - 상태: 프로퍼티
  
#### 생성자
- 내장 생성자(이미 알고있는 것들)
  - ex) `Array`, `let myArr = new Array(1,2,3);`
- 생성자를 사용하는 이유
  - 생성자를 통해 생성된 객체는 같은 프로퍼티와 메소드를 공유할 수 있음
- 인스턴스
  - 생성자로 생성된 객체
  - `객체 instanceof 생성자`: 생성자와 객체 관계 확인
> :boom: 화살표 함수를 통한 객체의 메소드 정의 xx 화살표함수의 this는 window를 참조!!

#### 프로토타입
- 생성자 함수로 생성된 객체들의 메소드는 자원 낭비
> :bulb: 프로토타입은 공간을 참조하고, 그 공간은 인스턴스들이 공유한다.

```javascript
function Program(name) { //생성자 함수
  this.name = name;
  this.progress = 0;
}

Program.prototype.proceed = function () { //프로토타입
  this.progress += 5;
}

function Me(name, address, team) { //생성자 함수
  this.name = name;
  this.address = address;
  this.team = team;
}

Me.prototype.study = function (program) { //프로토타입
  program.proceed()
}
```
> 객체의 메소드는 배열이 쓸 수 있으나, 배열의 메소드는 객체가 쓸 수 없다.   
배열의 __proto__가 Array __proto__를 참조,   
Array __proto__가 Object __proto__를 참조 => :star: **프로토타입 체이닝**   
=> 배열이 Object의 프로퍼티와 메소드 사용 가능   

#### 클래스
- 하나의 생성자만 정의 가능
- new 키워드 호출과 동시에 생성자 함수 실행

```javascript
class Program {
  constructor(name) { //생성자
    this.name = name;
    this.progress = 0;
  }

  proceed() { //메소드
    this.progress += 5;
  }
}

class Member {
  constructor(name, address, team) { //생성자
    this.name = name;
    this.address = address;
    this.team = team;
  }

  study(program) { //메소드
    program.proceed();
  }
}

const program = new Program("오르미 백엔드");
const member = new Member("박정균", "경기도 안양", "오르미 5기");
```

#### 상속 클래스 (extends)
- 파생 클래스의 super() => 자식 클래스의 constructor()
- 파생 클래스의 constructor() 생략 가능, 생략 안할 시 super() 필수
- 파생 클래스의 constructor()에서 this 사용시 super() 뒤에 와야함

```javascript
class Program {
  constructor(name) {
    this.name = name;
    this.progress = 0;
  }

  proceed() {
    this.progress += 5;
  }
}

class Member {
  constructor(name, address, team) {
    this.name = name;
    this.address = address;
    this.team = team;
  }

  study(program) {
    program.proceed();
  }
}

class Special extends Member {
  constructor(name, address, team, title) {
    super(name, address, team); // 부모 클래스의 name, team만 생성하고 싶다면?
    this.title = title // 새로운 변수
  }
}

const program = new Program("오르미 백엔드");
const member = new Member("박정균", "경기도 안양", "오르미 5기");
const special = new Special("박정균", "경기도 안양", "오르미", "에이스");
```

### 생소, 어려웠던 내용

---

- this를 유의하며 화살표 함수를 사용해야 한다는 것
- 여러 객체들 사이에서 this가 정확히 무엇을 참조하는지

### 앞으로의 계획, 목표

---

- 강사님의 airbnb 코드 분석하고 프로젝트 준비
