# servlet 

#### 프로젝트 경로 자동 추가
`@WebServlet("/servlet/test01")`


#### input 
name 필수
`<input type="text" name="msg" />`


#### post 한글깨짐
`request.setCharacterEncoding("utf-8");`


#### 체크박스
value사용 필수
`<label><input type="checkbox" name="Lang" value="1" />자바</label>`

null 체크 필수(체크 안하면 null)

내가 만드는 것 : `response`
받는 것 : `request`



# jsp

`<%!   선언문(변수/메서드)   %>`

`<%=  표현식(출력)  %>`

`<%@  지시문(page(import, contentType)/include/taglib)  %>`

`<%  실행문 자바  %>`

`<%--  jsp주석(.jsp -> .java 변경할 때 주석 처리된다.)   --%>`

### 기본객체 9개
- pageContext
- request
- session : HttpSession
- application : ServletContext
- page
- response
- config
- out
- exception

#### 공유영역(4가지) - mvc
- session
- application
- request
- pageContext


#### 페이지 이동방식
- forward (프로젝트 경로 생략)
- sendRedirect (프로젝트 경로 써줘야함)


