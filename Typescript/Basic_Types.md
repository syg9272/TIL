**boolean**

```jsx
let isDone: boolean = false;

isDone = true;
console.log(typeof isDone);

//let isOk: Boolean = true;
//let isNotOk : boolean = new Boolean(true);
```

**number**

```jsx
let decimal: number = 6;

let hex: number = 0xf00d;

let binary: number = 0b1010;

let octal: number = 0o744;

let notANumber: number = NaN;

let underscoreNum: number = 1_000_000;
```

**string**

```jsx
let fullName: string = 'Yeji Seo'
let age: number = 24;

let sentence: string = `Hello, My name is ${fullName}.

I'll be ${age + 1} years old next month.`;

console.log(sentence);
```

**symbol**

```jsx
console.log(Symbol('foo') === Symbol('foo'));

const sym = Symbol();

const obj = {
  [sym]: 'value'
};

obj[sym]
```

**null & undefined**

```jsx
// let myName: string = null; // 안됨

// let u: undefined = null; // 안됨

let v: void = undefined; // null은 안됨

let union: string | null = null; // 합집합으로 작성하면 null 할당 가능

union = 'Yeji'
```

**object**

```jsx
const person1 = {name: 'Yeji', age: 24}; // object type 아님
const person2 = Object.create({name: 'Yeji', age: 24});
```

**Array**

```jsx
// let list: number[] = [1, 2, 3];  // 보통 이걸 사용
// let list: Array<number> = [1, 2, 3];

let list: (number | string)[] = [1, 2, 3, '4'];
```

**Tuple**

```jsx
let x: [string, number];

x = ['hello', 39]; // 순서도 맞고 타입도 맞고 길이도 맞아야됨

// x = [10, 'Yeji']; // error
// x[3] = 'world'; // 정해진 타입 이후 index에는 값 할당 못함

const person: [string, number] = ['Yeji', 24];

// const [first, second, third] = person;
```

**any**

```jsx
// 어떤 타입이어도 상관없는 타입
// 최대한 쓰지 않기
function returnAny(message: any): any {
  console.log(message);
}

const any1 = returnAny("리턴은 아무거나");

any1.toString();

let looselyTyped: any = {};

const d = looselyTyped.a.b.c.d; // any가 이런 식으로 전파됨

function leakingAny(obj: any) {
  const a = obj.num;
  const b = a + 1;
  return b;
}

const c = leakingAny({ num: 0 }); // c가 number여야 하지만 any
c.indexOf("0");
```

**unknown**

```jsx
// type을 모를 때 사용
// any를 보완 ..?
declare const maybe: unknown;

// const aNumber: number = maybe;

if (maybe === true) {
  const aBoolean: boolean = maybe; // 만약 maybe가 boolean이라면 조건문 통과하니까 boolean에 할당 가능 !

  // const aString: string = maybe; // string은 당연히 안됨 !
}

if (typeof maybe === 'string') {
  const aString: string = maybe; // 여기서는 가능
}
```

**never**

```jsx
// return에 사용됨 (아무것도 반환하지 않음)
function error(message: string): never {
  throw new Error(message);
}

function fail() {
  return error('failed');
}

function infiniteLoop(): never {
  while(true) {}
}

let a: string = 'hello';

if (typeof a != 'string') {
  a; // a는 string 인데 조건문에 해당하는 건 없으니까 할당할 수 없는 상태 ! 그래서 여기서 a는 never가 된다
//만약 string | number 였다면 여기서 a는  number
}

type Indexable<T> = T extends string ? T & { [index: string]: any } : never;
// T가 string이면 앞에꺼, 아니면 never

type ObjectIndexable = Indexable<{}>; // T = {}, ObjectIndexable = never
```

**void**

```jsx
// 함수의 return을 가지고 아무것도 하지 않겠다 !
function returnVoid(message: string): void {
  console.log(message);

  return undefined; // return 에는 undefined 만 들어갈 수 있음
}

const r = returnVoid('리턴이 없다.');
```