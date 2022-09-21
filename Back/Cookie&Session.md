# cookie & session

- HTTP protocol의 약점 보완 : 응답 후 연결 해제하는데 상태 정보를 유지해야 하는 경우가 있음 ..
- 상태 관리를 위해 사용 ( ex ) 로그인 ...)


## cookie
- 특징

  - `java.servlet.http.Cookie`
  - 사용자의 컴퓨터(client)에 정보 저장
  - 요청 시 헤더에 쿠키정보를 넣어 서버에 전송
  - `key와 value`  --> String 형태로 이루어짐
  - 브라우저 별로 관리
  - 개수 제한 : client에 총 300개 cookie 저장 가능(가장 오래된 쿠키 자동 삭제)
  - 도메인 당 20개 cookie 가질 수 있음
  - 용량 제한 : 4KB

- 사용

  - 사이트 팝업 : 오늘 하루동안 열지 않기 버튼
  - 자동로그인, 장바구니
  - 세션관리(정보 저장), 개인화(사용자 페이지), 트레킹(사용자 행동 패턴 기록)

- 구성요소

  - 이름(key)
  - 값(value)
  - _유효기간_
  - 도메인(default : 쿠키를 설정한 도메인)
  - _경로(쿠키를 설정한 path경로 아래만 전송 가능... 사이트 전체로 보낼거면 `/` )_

- 동작 순서
```
1. client가 페이지 요청
2. cookie생성
3. 헤더에 cookie 넣어 응답
4. 받은 cookie PC에 저장
5. 브라우저가 종료되어도 유효기간동안 client는 cookie 보관
6. 동일 사이트 재방문 --> 남아있는 cookie 전송
```
- 쿠키 설정

![image](https://user-images.githubusercontent.com/55950992/191391238-d9d98d2f-a989-4bff-b4d2-f04f1fff386c.png)

  1. 생성 `Cookie cookie = new Cookie(String name, String value);`
  2. 값 변경/얻기 `cookie.setValue(String value);`  `String value = cookie.getValue();`
  3. 사용 도메인지정/얻기 `cookie.setDomain(String domain);`  `String domain = cookie.getDomain();`
  4. 값 범위지정/얻기 `cookie.setPath(String path);`  `String path = cookie.getPath();`
  5. cookie 유효기간 지정/얻기 `cookie.setMaxAge(int expiry);`  `int expiry = cookie.getMaxAge();`  (0을 넣으면 쿠키 삭제)
  6. client에 저장된 cookie얻기 `Cookie cookies[] = request.getCookies();`




## session
- server에 정보 저장
- 서버에 부담되기 때문에 유지시간을 최소화해야함



