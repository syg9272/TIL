String Method
- s.equalsIgnoreCase("hello Java") -> 대소문자 구분없이 비교
- s.toUpperCase(); -> 대문자로 변경
- s.toLowerCase(); -> 소문자로 변경
- s.startsWith(""); -> 해당 문자열로 시작하는 여부
- s.endsWith(""); -> 해당 문자열로 끝나는 여부
- s.substring(2, 4) -> 2인덱스부터 4-1인덱스까지 자름
- s.index("a") -> a가 있는 인덱스
- s.lastIndexOf("a") -> a가 있는 인덱스를 뒤에서부터 앞으로 찾는 거
- s = "12Hea83ca9038ddfjg";
	System.out.println(Arrays.toString(s.split("[0-9]"))); ->  문자만 뽑아내기
	System.out.println(Arrays.toString(s.split("[A-Za-z]"))); -> 숫자만 뽑아내기
- s = s.trim(); -> 양쪽 끝 공백 제거


싱글톤 디자인 패턴
1. 생성자를 private로 선언 
2. 미리 객체 생성해놓기(private) -> 객체를 넘겨주는 getInstance가 접근할 수 있도록 static으로 선언 (선언만 해놓기)
3. 생성해놓은 객체를 넘겨주는 getInstance 메서드 선언 -> 외부에서 접근할 수 있도록 public static 선언
4. 매번 객체를 생성하는 건 비효율적 -> 조건문으로 instance 가 null 일 때만 생성하도록 객체 넘겨주는 getInstance에서 객체 생성

DAO  - 데이터 관리
