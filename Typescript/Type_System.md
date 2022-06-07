**structural type system**

- 구조가 같으면 같은 타입 !

**서브타입**

- 범위가 작은 게 서브타입
ex)

```jsx
let sub2: number[] = [1];
let sup2: object = sub2;

//일 경우 sub2 = sup2 가 불가능 !
//이럴 때 sub2는 서브타입, sup2는 슈퍼타입
```

ex)

```jsx
let sub3: [number, number] = [1, 2];
let sup3: number[] = sub3;
//일 경우 sub3 = sup3 가 불가능 !
//sub3는 튜플, sup3는 array 인데 튜플이 한 가지 type으로만 이루어져 있을 경우
//해당 type array가 더 큰 범위 !!!
```

- any는 예외 ! !
- 같거나 서브 타입인 경우, 할당 가능 => 공변
- 함수의 매개변수 타입만 같거나 슈퍼타입(상속.. 부모)인 경우, 할당 가능 => 반병

**Type Alias 타입 별칭**

- union, tuple, function 처럼 길게 쓰는 걸 짧게 쓰기 위해 사용 !
- type 변수에 타입을 할당 !