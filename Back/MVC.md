# MVC


### M - model (DTO, DAO, Service)
### V - view (jsp)
### C -controller (Servlet)

<br/>

- controller --> service --> dao --> db


### controller 역할

파라미터 추출, 정제
서비스 호출
결과 받고 데이터 공유
데이터 처리할 페이지 호출
오후 5:47


### 코드 작성 tip
#### DAO
- `try-finally`

- 객체 만들기

- `close`작성

- `con = db.getConnection();`

- sql짜기

- 실행객체 얻기 :
`pstmt = con.prepareStatement(sql.toString());`

- ? 채우기 :
`setType`

- insert : `return pstmt.executeUpdate();`
- select(list) : `rs = pstmt.executeQuery();` --> `rs.next` -> 객체 데이터 변경해주기



#### service

- dao 받아와서 controller에서 받은 정보 넘겨주기

#### controller

- 메서드 만들기
- post엔 `request.setCharacterEncoding("utf-8");` 작성
- process만들기 --> pocess호출
.
.
.

#### jsp 파일 만들기(화면에 보여지는 부분)

#### 공유, url 변경 여부에 따라 
- foward 
- redirect(프로젝트 경로 써줘야함 !!! ---> request.getContextPath()   아니면 맨 뒤에 바뀌는 부분만 적기 ... 슬래시 제외)

`<input type="hidden" name="act" value="insert" />` 외우기 ..
