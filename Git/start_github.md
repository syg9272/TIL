**Git을 활용한 버전 관리**

---

우선 git --version 명령어를 통해

git이 설치되어 있는지 파악해 준다

![설치되어 있다면 요롷게 버전이 뜬다](https://blog.kakaocdn.net/dn/cG4qHY/btryP0UvZAO/XxmV03EEtMDWEBJjdXNDWk/img.png)

설치되어 있다면 요롷게 버전이 뜬다

설치는 요기서

[https://www.git-scm.com/](https://www.git-scm.com/)

다음 단계는 **github 가입**하기

[https://github.com/](https://github.com/)

---

OS가 달라도 문제가 발생되지 않도록

**개행문자(Newline) 설정**

```jsx
git config --global core.autocrlf true
```

Windows

```jsx
git config --global core.autocrlf input
```

Linux, macOS

커밋(버전 생성)을 위한

**사용자 정보 입력**

```jsx
git config --global user.name 'syg9272'
```

```jsx
git config --global user.email 'syg9272@naver.com'
```

구성 확인

![https://blog.kakaocdn.net/dn/bJrUZH/btryV2XHiZI/9CvjYNWasnSPgqcEUK5yK1/img.png](https://blog.kakaocdn.net/dn/bJrUZH/btryV2XHiZI/9CvjYNWasnSPgqcEUK5yK1/img.png)

현재 프로젝트에서 변경사항 추적을 시작하기 위해

git init 명령어 입력