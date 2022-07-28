**byte**

-   InputStream : byte 한 개씩 읽음 (utf-8은 한글 한 글자가 3byte여서 깨질 수도 있음) -> char는 Reader로 읽기
-   OutputStream

**char**

-   Reader : buffr 크기 만큼 씩 읽음
-   Writer

**File**

-   "." 경로는 프로젝트 경로가 아니라 java를 실행시킨 곳이다
-   separator : os환경에 맞게 / \\ 를 결정함

**Serialization**

-   객체를 파일에 저장하거나 네트워크로 전송하기 위해 연속적인 데이터로 변환하는 것
-   역 직렬화(deserialization)
-   조건

1.  Serialization 인터페이스 구현
2.  클래스 모든 멤버가 구현해야 함
3.  직렬화 하지 않을 멤버는 transient 선언 (ex) password 같은 민감한 데이터)

**<도구의 도움없이 해석 가능 - 문자 단위처리 가능>**  
pdf 파일 - 바이트  
mp3 파일 - 바이트  
a.doc 파일 - 바이트  
사진.jpg 파일 - 바이트  
Test01.java - 문자, 바이트

               **입력                  출력**

**바이트**     InputStream     OutputStream  
**문자**        Reader             Writer

File InputStream

File OutputStream

File Writer

File Reader

-   **속도의 개선**  
    Buffered InputStream  
    Buffered OutputStream  
    Buffered Writer  
    Buffered Reader
-   **메모리**(문자 단위가 없음 !! 바이트임)**에 있는 객체를 저장하고 싶다** (밖으로 내보내는 것 - 출력)  
    Object OutputStream (문자 단위가 없음 !! 바이트임) 따라서 Writer 는 없음  
    Object InputStream

InputStreamReader - 문자 (InputStream을 Reader로 변환해서 사용해야 할 때)

화면에서 c:/test 폴더 밑에 있는 자바파일의 이름을 입력받아서 c:/copy 디렉토리 밑에 사용자가 입력한 파일을 복사하려고 한다. c:/test/A.java, B.java, C.java

-   **일반적인 상황**  
    이름을 입력받아서 -> InputStreamReader([system.in](http://system.in/)) || Scanner  
    해당 이름의 파일 읽어들일 때 - FileInputStream  
    해당 이름의 파일 복사해서 만들 때 -> FileOutputStream
-   **만약 속도개선이 필요하다면**  
    이름을 입력받아서 -> InputStreamReader([system.in](http://system.in/)) || Scanner  
    해당 이름의 파일 읽어들일 때 - BufferedInputStream  
    해당 이름의 파일 복사해서 만들 때 -> BufferedOutputStream

입력 메서드 - **read** 출력 메서드 - **write**

읽을 때 더 이상 없다는 건 **\-1**임 -> 따라서 파일 읽어들이는 조건에 == -1 넣어주면 됨
