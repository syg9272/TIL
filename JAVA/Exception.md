예외 : Exception \*

-   개발자가 처리하기 힘든 예외(Error)와 처리할 수 있는 예외(Exception)
-   예외관련 키워드
-   try catch : 직접 처리
-   finally : 직접 처리
-   throws : 간접 처리
-   throw : 예외를 인위적으로 생성

예외 처리

-   프로그램의 정상처리 여부와 관련 예외의 직접 처리

```
try {
// 예외와 관련있는 코드를 감싼다.
}
```

-   try 블럭에서 예외가 발생했을 때 어떤 예외를 처리할지 예외타입을 선언하고
-   블럭안에 예외의 처리 구문을 작성한다.
-   여러 개의 예외처리 시 자식예외가 먼저 나와야 문제없이 사용 가능

```
catch (예외타입 변수명) {
// 예외처리 구문...
}
```

-   finally {}
-   try{} catch {}
-   try{} finally {}
-   try{} catch {} finally {}

```
// 간소화된 에러 메세지 확인
String errMsg = e.getMessage();
System.out.println("errMsg : " + errMsg);
// 에러의 디버깅을 위한 ...
e.printStackTrace();

// 1.7 버전부터 multi catch 가능해짐
catch (ArithmeticException | FileNotFoundException e) {
System.out.println("예외가 발생하였음");
}
```

호출 순서 이해 //finally : 무조건 실행 -> 예외 발생 여부와 상관없이 수행한다. (앞에서 return 해서 메서드를 종료해도 실행) (exit를 통해 프로그램 종료 시에는 실행 안함)

보통은 상황이 있어야 예외 발생 but, 간접 처리는 원하는 상황에 예외 발생시킴 \*

-   예외의 간접 처리 : throws

```
import java.io.FileNotFoundException;
import java.io.FileReader;

public class Test07 {
	static void callFour() {
		System.out.println(1 / 0);
	}
	static void callThree() throws ArithmeticException {
		System.out.println(1 / 0);
	}
	static void callOne() {
		try {
			FileReader fr = new FileReader("a.txt");
		} catch (FileNotFoundException e) {
			e.printStackTrace();
		}
		
	}
	static void callTwo() throws FileNotFoundException {	// 상위에러로 던져도 됨
		FileReader fr = new FileReader("a.txt");
	}
	public static void main(String[] args) {
//		callOne();	// 예외가 발생하지 않은 걸로 생각함
		callThree();	// 런타임에러 즉, 언체크드 에러이므로 에러 캐치는 필수가 아니다. (본인 선택)
		try {
//			callTwo();	
			callFour(); 	// 런타임에서는 throws 선택적
		} catch (Exception e) {
			e.printStackTrace();
		}
	}
}

```

사용자 정의 예외 \*

-   class UserException extends Exception -> 컴파일 발생, checkedException ----> 예외처리 필수
-   class UserException extends RuntimeException -> 실행시 발생, UncheckedException ----> 이후 예외처리는 선택적
-   조건문이 아닌 예외처리를 하면 가독성이 좋아지고 심각한 문제임을 한 눈에 파악할 수 있음
