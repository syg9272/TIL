Interface

인터페이스의 특징

-   interface 로 선언 : class 정의시 class, interface 정의시 interface, annotation(@) 정의시 @interface
-   class A
-   interface A
-   @interface A
-   추상클래스와의 차이점 : 다중상속 가능
    -   클래스 extends 클래스 (단일) // extends : 확장, implements : 구현
    -   클래스 implements 인터페이스, ,,, 인터페이스(다중상속 가능)
    -   인터페이스 extends 인터페이스, ,,, 인터페이스
    -   인터페이스 -> 클래스 (x)
-   추상클래스와의 공통점
    -   : 객체생성이 안됨
    -   : 자식클래스를 이용해서 처리
    -   : 자식클래스는 인터페이스에 있는 추상메서드를 재정의 해야함
-   선언되는 모든 변수는 자동으로 "public static final" 추가됨
-   선언되는 모든 메서드는 자동으로 "public abstract" 추가됨
-   8버전 부터 "default" 와 "static" 메서드가 추가됨
