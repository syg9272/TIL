<java.util 패키지>

-   DB의 CRUD 기능처럼 다수의 데이터 쉽게 처리하는 방법 제공
-   collection framework의 핵심 interface

\-----------------람다식 사용 방법 -------------------

// num : 메서드의 매개변수 / num % 3 == 0 -> 메서드의 구현부

nums.removeIf(num -> num % 3 == 0);

// 리스트, 비교대상(타입은 앞에 리스트 보고 추론 가능해서 생략) -> 구현부가 하나라서 return필요없음

// 메서드가 하나여야만 람다식 사용 가능 (@FunctionalInterface)

Collections.sort(names, (o1, o2) -> Integer.compare(o1.length(), o2.length()));

\- 익명 클래스

-   특징 : 이름이 없다 (class 이름 - X)
-   하는 일 : 객체 생성 + 클래스 내용 정의
-   작성 법 : new 클래스(또는 인터페이스) () {내용 정의} -----> 여기 쓰인 클래스 or 인터페이스는 익 명 클래스의 부모
-   익명클래스는 한 번 밖에 안쓰려고 만들기 때문에 바로 변수처럼 집어넣어서 사용

# List

Collection Framework - List

1.  List

\- 순서가 있는 데이터 집합

\- 중복 허용 (순서로 구분)

ex) ArrayList, LinkedList

\- 메서드

-   add(E e) : 추가
-   contains(Objecto) : 포함여부
-   equals() : 같은지 판단
-   isEmpty() : 비었는지
-   iterator() :

```
//-----------------Iterator 사용 방법 ---------------
Iterator<Integer> ite = nums.iterator();
while(ite.hasNext()) {
	if(ite.next() % 3 == 0) {
		ite.remove();
	}
}
```

-   size() : 크기
-   clear() : 초기화
-   remove() : 삭제 (integer에서는 인덱스 우선순위)
-   toArray() : 배열로 변환

\- 선언

List<String> names = Arrays.asList("Hi Hello", "Java", "World", "Welcome");

List<String> friends = new ArrayList<>();

\- 관련 클래스 관계도

              stack --> Vector ---> List --> Collection

ArrayList -> List LinkedList-> List

                   LinkedList-> Deque --> Queue --> Collection

\- ArrayList 와 LinkedList 비교

순차 수정, 조회 위주 - ArrayList

추가, 수정, 삭제(비순차) - LinkedList

\- 고려해야 할 점

List 값 변경 : set(index, 내용)

for문을 이용해 요소 삭제할 때는 뒤에서부터 remove

List<String> 에서는 add, remove 지원 안함. -----> strs.set(0, "Hi!!!"); 이런 식으로 활용

for each : 읽기 전용 (되도록 수정 금지 ~!~!~!~!)

Sort Collections.sort(List) : 오름차순 정렬

Collections.reverse(List) : 내림차순 정렬

1.  내부 클래스 사용

```
class MyComp implements Comparator<String> {	// 내부 클래스
	@Override
	public int compare(String o1, String o2) {
		return Integer.compare(o1.length(), o2.length());
	}
}

Collections.sort(names, new MyComp());
```

2\. 익명 클래스 사용

```
Collections.sort(names, new Comparator<String>() {	// 익명클래스는 한 번 밖에 안쓰려고 만들기 때문에 바로 변수처럼 집어넣어서 사용
	public int compare(String o1, String o2) {
		return Integer.compare(o1.length(), o2.length());
	}
});
```

3\. 람다식 사용

```
// 리스트, 비교대상(타입은 앞에 리스트 보고 추론 가능해서 생략) -> 구현부가 하나라서 return필요없음
// 메서드가 하나여야만 람다식 사용 가능 (@FunctionalInterface)
Collections.sort(names, (o1, o2) -> Integer.compare(o1.length(), o2.length()));
```

# Set & Map

Collection Framework - Set

1.  Set

-   순서 없는 데이터 집합
-   중복 불가능 (구분 못함)
-   ex) HashSet, TreeSet
-   객체가 같음을 따질 때 : hash set, map
-   instance비교, null이 아닐 때 : hashCode
-   선언 Set<Object> hset = new HashSet<Object>();

Collection Framework - Map

1.  Map

-   key, value 쌍으로 데이터 관리
-   key는 중복 불가, value는 중복 가능 (key로 데이터 구분)
-   ex) HashMap, TreeMap
-   메서드 put(key, value) : 추가 및 수정 put할 때 null : 처음 추가, null이 아니면 value 수정 putIfAbsent(key, value) : 해당 키에 대한 값이 없을 때만 추가 entrySet() : entry : map이 key값들을 관리하는 것 keySet() : key값 모음 get(Objext key) : map이 가지고 있는 key에 연결된 value valuse() : value값 모음 clear() : 초기화 remove(key) : key의 자료 삭제
-   선언 Map<String, String> hMap = new HashMap<>();

Collections의 sort() 사용해서 정렬
