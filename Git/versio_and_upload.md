가장 먼저 GitHub에서 **Repositorie 생성**하기

![새로운 레파지토리](https://blog.kakaocdn.net/dn/b4VjA1/btryXb7NjJ2/NvUWt8QSFjQU67obqLNfg1/img.png)

새로운 레파지토리

![이름을 입력하고 되도록이면 Public으로 설정 나머지는 건들지 않고 레파지토리 생성](https://blog.kakaocdn.net/dn/ndohy/btryQ0N1NrF/H8d7m9fLp3bP7KkZSXFsc1/img.png)

이름을 입력하고 되도록이면 Public으로 설정 나머지는 건들지 않고 레파지토리 생성

![https://blog.kakaocdn.net/dn/JE4FB/btryTrDS87X/KXzoEudpcw8tPx5sMIMEA0/img.png](https://blog.kakaocdn.net/dn/JE4FB/btryTrDS87X/KXzoEudpcw8tPx5sMIMEA0/img.png)

생성 후 뜨는 페이지에 저 부분을 클릭해 링크를 복사한다

---

여기까지 완료했다면

다시 VS code로 이동해서 복사했던 링크 입력

![https://blog.kakaocdn.net/dn/lyq6o/btryV4gTX6C/uGKc7s8UzTfs8BvEScg511/img.png](https://blog.kakaocdn.net/dn/lyq6o/btryV4gTX6C/uGKc7s8UzTfs8BvEScg511/img.png)

</br>git status 명령어를 통해 변경사항이

있는 파일 목록을 확인한다

![빨간색으로 나타난 파일들은 추적하지 않는 상태 !](https://blog.kakaocdn.net/dn/cWc0u5/btryXbNu2aj/VF4bLxf5qpCDLwdRJI0lLK/img.png)

빨간색으로 나타난 파일들은 추적하지 않는 상태 !

</br>빨간색으로 나온 파일들을 추적이 가능한 형태로

수정하기 위해 git add .

![다시 확인해 보면 초록색으로 바뀌어있다!](https://blog.kakaocdn.net/dn/Ol5P7/btryPBUZ3WL/XBwF0QUAGpFKWK31bzasRK/img.png)

다시 확인해 보면 초록색으로 바뀌어있다!

</br>
**버전 생성하기**

</br>git commit -m ' 메시지 '

git log를 통해 확인

![버전 확인을 위해 되도록이면 직관적인 메시지 작성](https://blog.kakaocdn.net/dn/8LuNc/btryU15McqO/dOuHC0QRlqACzYD9glZhJ0/img.png)

버전 확인을 위해 되도록이면 직관적인 메시지 작성

</br>
**업로드**

</br>git push origin (branch 이름)

![https://blog.kakaocdn.net/dn/vQAoS/btryV2i6lFd/rlHcUjUL5gVtqwbaSEg9xK/img.png](https://blog.kakaocdn.net/dn/vQAoS/btryV2i6lFd/rlHcUjUL5gVtqwbaSEg9xK/img.png)

우선은 master branch로 업로드

</br>다시 GitHub로 돌아가서 확인해 보면

![https://blog.kakaocdn.net/dn/NvR8f/btryQRJwgHd/M96drJejhgsH0vBNozblAK/img.png](https://blog.kakaocdn.net/dn/NvR8f/btryQRJwgHd/M96drJejhgsH0vBNozblAK/img.png)

업로드 성공!