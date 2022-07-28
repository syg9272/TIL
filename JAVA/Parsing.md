공공데이터

## **종류**

-   **CSV**  
    용량이 작지만 구조적이지 못함
-   **XML**  
    구조적, 정확한 문법을 지켜야 동작(well formed), 큰 용량  
    태그를 사용 (key- value) -> 시작태그와 종료태그가 일치해야 함, 대소문자 구분  
    무조건 로 시작  
    무조건 root element 존재해야 함 나머지는 tree 형태로 구성  
    DTD & Schema 를 잘 따른 문서를 valid 하다고 함
-   **JSON**  
    구조를 가지며 객체로 다른 언어와 호환  
    간결한 문법, 단순한 텍스트, 적은 용량으로 호환성이 높음  
    이 기종 간의 데이터 교환에 광범위하게 사용됨  
    key - value 쌍으로 관리 (java의 map 처럼 !)

## **파싱**

-   **XML 파싱**  
    내용 추출 과정  
    SAX parser : 내용을 읽으면서 처리 (빠르고 한번에 처리해서 다양한 탐색 어려움)  
    DOM parser : 다 읽고 나서 탐색 (다양한 탐색 가능하지만 무겁고 느림)
-   **SAX parser**  
    동작 방식 : 문서를 읽다가 발생하는 이벤트를 기반으로 문서 처리  
    SAX Parser Factory (생성) -> SAX Parser  
    XML 문서 (파싱) -> SAX Parser (이벤트 발생 시 호출) -> MyHandler (필요한 메서드 재정의) -> DefaultHandler (참조) -> SAX Parser
-   **DOM Parser**  
    동작 방식 : 문서를 완전히 메모리에 로딩 후 필요한 내용 찾기  
    Document Builder Factory (생성) -> Document Builder  
    XML 문서 (파싱) -> Document Builder -> DOM Tree
-   **JSON 파싱**  
    ObjectMapper 사용
