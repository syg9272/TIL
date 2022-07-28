상속

-   자식 is a 부모
-   자바는 단일상속만 가능 : 어떤 메서드를 쓸지 관계가 복잡해짐
-   단일상속만 가능하지만 포함관계를 통해 극복 -> 멤버 변수로 포함시켜서 활용

오버로딩 & 오버라이딩

-   오버로딩 : 추가 적재
-   오버라이딩 : 덮어쓰기(똑같은 메서드를 수정한 것이기 때문에 자식클래스꺼 사용)

Annotation

-   @Deprecated : 앞으로 사용 안 할 수도 있음
-   @Override

super

-   this() 처럼 super() 는 조상 클래스 생성자 호출
-   생성자의 맨 첫 줄에서만 호출 가능
-   this(), super() 없으면 명시적으로 super() 삽입

객체의 비교(Object)

-   객체의 주소 비교 : == 활용
-   객체의 내용 비교 : Object클래스의 equals 오버라이드 해서 비교

Singleton 디자인 패턴

-   객체의 생성을 제한
-   외부에서 생성자에 접근할 수 없도록 생성자의 접근 제한자를 private
-   내부에서 직접 객체 생성 private
-   외부에서는 내부에서 생성한 객체를 가져다 쓸 수 있도록 public static getter 생성 -> 내부에서 생성한 객체에도 static
-   외부에서는 getter 메서드를 불러와 사용

접근 제한자

-   public : 누구나 사용 가능
-   protected : 같은 패키지 + 다른 패키지의 자손 클래스(상속받은 자손)
-   package(default) : 같은 패키지
-   private : 같은 클래스

다형성

-   상속 관계에서 조상 클래스의 타입으로 자식 클래스 객체를 참조할 수 있다.
-   쓰는 이유 ? : 다른 타입의 객체 배열을 다루기 쉬움 ex) person\[0\] = new Person(); / person\[1\] = new SpiderMan();
-   Object\[\] 는 뭐든 다 담을 수 있음 (모든 클래스의 조상)

참조형 객체의 형 변환

-   묵시적 케스팅 : 자식에서 부모로 ex) Phone phone = new Phone(); -> Object obj = phone;
-   명시적 케스팅 : 부모에서 자식으로 ex) Phone phone = new SmartPhone(); -> SmartPhone smartphone = (SmartPhone)phone;
-   형 변환 아무거나 막 하면 안됨 . ! 컴파일은 되지만 런타임 에러 발생
-   조건문을 통해 instanceof 로 타입 확인 후 변환

참조관계에서 변수 타입

-   멤버 변수가 중복일 때는 참조 변수에 따라 변수 정해짐
-   메서드가 중복 될 때는 오버라이드 된 걸로 호출(무조건 !! 자식 메서드 호출)

객체출력과정

-   객체를 출력하면 Object의 toString 덕분에 출력됨
-   오버라이드 되어 있다면 그걸로 출력
