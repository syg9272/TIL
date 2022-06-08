**compileOnSave**

- true/false

**extends**
-파일경로명

**files, include, exclude**

- 셋 다 설정이 없으면, 전부 다 컴파일
- include < exclude < files
- include, exclude : .gitignore 같이 glod 패턴
- exclude 설정 안하면 4가지 default로 제외 (node_modules, bower_components, jspm_packages, <outDir>)

**compileOptions**

- typeRoots, types 같이 사용하지 않음
- typeRoots : 배열 안에 들어있는 경로들 아래서만 가져옴
- types : 배열 안의 모듈 혹은 ./node_modules/@types/ 안의 모듈에서 찾아옴, [] 빈 배열을 넣는다는 건 이용하지 않겠다는 뜻
- target : 결과물 버전
- lib : 기본 라이브러리 버전
- outDir, outFile, rootDir
- rootDir : 이 dir 아래 파일들 복제 ..?
- outDir : 설정한 폴더에 복제 ..?
- strict
- -nolmplicitAny : 선언하지 않은 any를 사용하면 에러
- suppressImplicitAnyIndexErrors : obj에 없는 key에 값을 할당해도 에러 발생 x
- -nolmplicitThis : 선언하지 않은 any를 this 표현식에 사용하면 에러
- -strictNullChecks : null, undefined 는 any이거나 자신을 타입으로 가질 때만 사용 가능
- -strictFunctionTypes : 반환 타입은 공변적, 인자 타입은 반공변적 (에러 발생)
- -strictPropertyInitialization : 정의되지 않은 클래스의 속성이 생성자에서 초기화 되었는 지