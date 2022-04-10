**화살표 함수**

```jsx
x => x * 2
```

기본적인 로직을 축약형으로 줄일 수 있음

```jsx
const double = x => x * 2;

console.log(double(7));
```

**즉시실행함수**

**IIFE, Immediately-Invoked Function Expression**

```jsx
const a = 7;

(function () {

	console.log(a * 2)

}());
```

**호이스팅(Hoisting)**

**함수 선언부가 유효범위 최상단으로 끌어올려지는 현상**

```jsx
const b = 7;

double2();

function double2 () {

	console.log(b * 2)

};
```

**타이머 함수**

setTimeout(함수, 시간) : 일정 시간 후 함수 실행

setInterval(함수, 시간) : 시간 간격마다 함수 실행

clearTimeout() : 설정된 Timeout 함수를 종료

clearInterval() : 설정된 Interval 함수를 종료

```jsx
const timer = setTimeout(() => {

	console.log('Daisy!')

}, 3000);

const h1EL = document.querySelector('h1')

h1EL.addEventListener('click', () => {

	clearTimeout(timer)

});
```

**콜백(Callback)**

실행위치 보장

함수의 인수로 사용되는 함수

```jsx
setTimeout(함수, 시간)

function timeout(cb) {

	setTimeout(() => {

		console.log('Daisy!')

		cb()

	}, 3000)

};

timeout(() => {

	console.log('Done!')

});
```

---

**Math**

abs : 절댓값

min : 최소값

max : 최대값

ceil : 올림

floor : 내림

round : 반올림

random : 랜덤 (0.xxxxxx) 로 나오기 때문에 Math.floor(Math.random() * 10)

메서드의 인수로 사용되는 함수 : 콜백 함수

**배열**

length : 배열이 비어있는 지 확인할 때 자주 사용

concat() : 배열 합치기 (원본은 그대로)

forEach(function(배열 아이템(element), 횟수(index), 원본의 배열 데이터(array)){}) : 배열의 index만큼 함수 실행

map(function(){return}) : 배열데이터의 아이템 개수만큼 콜백함수 반복실행, 반환된 값이 배열 형태로 저장됨

filter(콜백) : 콜백에 정의된 특정 기준에 의해 필터링됨

find(콜백) : 특정 조건에 맞는 아이템 찾기

test() : 주어진 문자열이 정규 표현식을 만족하는지 판별, 불린 값으로 반환

includes() : 포함여부

push() : 뒤에 추가 , unshift() : 앞에 추가

reverse() : 순서 뒤집기, splice(index, num, new_item) : index에서 num개의 아이템 삭제 후 new_item 삽입

**객체**

Object.assign(대상 객체, 출처 객체) : 출처 객체에서 속성을 복사해 대상 객체에 덮어쓰기

새로운 객체에 복붙하고 싶다면({}, 출처 객체1, 출처 객체2 , ...)

Object.keys(객체) : key들이 배열 데이터로 저장됨

구조 분해 할당 : 객체, 배열 속성을 가져와서 변수로 활용

객체: 이름으로 가져오기, 배열: 순서대로 가져오기

const {} = 객체, const [] = 배열

[객체]다른 변수로 활용 -> {key: 변수이름}

[배열]특정 변수만 사용 -> [, , b]

전개 연산자 : 하나의 배열 데이터를 쉼표로 구분하는 각각의 아이템으로 전개해서 출력

...{obj}

배열 데이터를 매개변수로 주고 받을 때 좋음

---

**가져오기, 내보내기**

```jsx
import _ from 'lodash' // From `node_modules`!

import getType from './getType' // getType.js

import {random} from './getRandom' // getRandom.js

console.log(_.camelCase('the hello world'))

console.log(getType([1, 2, 3]))

console.log(random(), random())
```

- default export는 아무렇게나 가져와도 됨
- named export는 {}로 이름 지정

**Lodash의 documentation**

_.uniq() : 하나의 배열 데이터, 중복제거 -> _.uniqBy(array, '속성')

_.unionBy(a, b, '속성') 여러 개의 배열 데이터

_.find(array, {name: 'yeji'})

_.findIndex(array, {name: 'yeji'})

_.remove(array, {name: 'yeji'})

**JSON**

- 큰따옴표만 사용, 속성의 key와 value는 모두 ""로 묶기
- 하나의 json파일은 하나의 데이터(문자 데이터인데 포맷 규칙에 의해 자동 변환되어서 객체 데이터처럼 출력됨)
- 하나의 메모리만 참조할 수 있는 큰 덩어리의 문자 데이터로 관리됨
- undefined는 사용불가
- 최대한 경량화 시켜야 하는 구조

```jsx
import myData from './myData.json'

console.log(myData)

const user = {

	name: 'Daisy',

	age: 24,

	emails: [

		'syg9272@gmail.com',

		'daisy@naver.com'

	]

}

const str = JSON.stringify(user)

console.log('str', str)

console.log(typeof str)

const obj =JSON.parse(str)

console.log('obj', obj)
```

- JSON.stringify() : 문자 데이터화 시키기
- 실제 javascript 데이터처럼 변경이 되려면 JSON.parse() 사용

---

**Storage**

- setItem : JSON.stringify()
- getItem: JSON.parse()

```jsx
const user = {

	name: 'yeji',

	age: 24,

	emails: [

		'syg9272@gmail.com',

		'syg9272@naver.com'

	]

}

localStorage.setItem('user', JSON.stringify(user))

console.log(JSON.parse(localStorage.getItem('user')))

~~localStorage.removeItem('user')~~ // 삭제

const str = localStorage.getItem('user')

const obj = JSON.parse(str)

obj.age = 26

console.log(obj)

localStorage.setItem('user', JSON.stringify(obj))
```