**데이터 불변성**

- 원시 데이터: String, Number, Boolean, undefined, null

쉽게 말하면 얘네는 생긴 게 같으면 같은 데이터

- 참조형 데이터: Object, Array, Function

값이 같아도 복사하지 않으면 다른 데이터(다른 메모리 주소 가리킴)

---

**얕은 복사(shallow copy)**

```jsx
const user = {

	name: 'yeji',

	age: 24,

	emails: [

		'syg9272@gmail.com'

	]

}

const copyUser = user

console.log(copyUser === user) // true
```

객체를 직접 대입하면 참조에 의한 할당이 이루어져 같은 메모리 주소 가리킴

즉, 원본 객체를 참조하는 것

여기서 user의 속성을 수정한 뒤 출력하면 copyUser의 데이터도 변경된다

Object.assign(), 전개연산자{...obj} 사용

**깊은 복사(deep copy)**

```jsx
import _ from 'lodash'

const copyUser2 = _.cloneDeep(user)

console.log(copyUser2 === user) // false

user.age = 26

console.log('user', user)

console.log('copyUser', copyUser2)
```

![user객체의 age속성의 값을 변경해도 copyUser2의 age는 그대로](https://blog.kakaocdn.net/dn/cBaH5z/btrySNNXo8Y/947tqaGSx9sC3UVuPk03yK/img.png)

user객체의 age속성의 값을 변경해도 copyUser2의 age는 그대로

원본과 참조관계가 없는 복사

lodash의 cloneDeep 함수 사용

1. VS code 터미널에서 npm i lodash
2. import _ from 'lodash'
3. _.cloneDeep(객체)