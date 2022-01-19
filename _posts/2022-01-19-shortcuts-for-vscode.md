---
layout: single
title:  "단축키 모음집 1 (윈도우와 크롬 환경에서)"
author_profile: false
---

오늘은 Visual Studio Code 를 사용하면서 유용하게 쓰고 있는 단축키들을 정리했다. 

지금까지 배우면서 거의 모든 활동을 이 프로그램으로 했기 때문에 더 잘 사용해 보고자 국내외 다수의 유투브를 참고하여 모은 리스트다.

오늘 수업에서 PLC 통신에 대해서 배우면서 Visual Studio라는 프로그램도 사용해 봤는데 거기서는 적용이 안되는 단축키들도 있었다. 앞으로 며칠간 사용하면서 알게되는 내용이 있으면 공유하겠다. 

(난생 처음보는 C#에 치여 기력을 다해 오늘은 못하겠다는 말🐣)

----

# VS code에서

| Ctrl + `  | cmd 열기 |
| --- | --- |
| Ctrl + p | 파일 검색 |
| Ctrl + p + ‘> new’ 입력 | 새 파일 만들기 가능 |
| Ctrl + p + ‘> format’ 입력 → document 선택 | 작업중인 문서 포맷팅 가능!  |
| 단어 선택 후 Ctrl + shift + L  | 해당 단어 한꺼번에 수정 |
| 줄에 커서놓고 Ctrl + l | 줄 전체 선택 |
| 줄에 커서놓고 Ctrl + x | 줄 지우기 |
| 줄에 커서 놓고 Alt + 방향키 | 줄 이동 |
| Alt + Shift + 방향키 | 아래로 코딩 복붙 |
| Alt + 숫자키  | 해당 번째에 있는 탭으로 이동  |
| Ctrl 누르고 있으면 열린 탭 목록 + 방향키 | 탭 전환 |
| Ctrl + 숫자키 | 누른 숫자 만큼 창 분할 |
| Ctrl + b | 사이드바 닫기/열기 |
| Alt + 마우스 클릭 | 여러 곳에 커서놓기 가능, esc 로 나올 수 있음 |
| 타겟 단어 선택 후 Ctrl + d | 같은 단어 차례로 선택 |
| Ctrl + Shift + O  | 파일 내부 함수 목록 나옴 |
| 함수 이름에 커서놓고 + F2, F12 | 파일에 있는 해당 함수 이름 전체 변경 가능  |

- 내부 검색기능 잘 알아두기 : Ctrl + F + [검색어].+/(
    - 뒤에 붙은 . , + , / , ( ← 들이 각각 의미가 있다.
    - 추후 추가하겠다 ㅎㅎ
    
- Tab 버튼 : 자동완성 기능 다양하게 사용하자!
    
    ex) <>굳이 입력하지 않아도 태그 이름만 쓰고 tab 누르면 앞뒤로 다 완성해준다.
    
- [파일명].md  ← markdown file 만들기 가능하고 미리보기도 가능
    
    : 내가 여기 블로그에 글 작성할 때 사용하는 방법! 편리하다.
    

- jetbrains mono 글씨체 유용하니 적용해보기
    
    [JetBrains Mono: A free and open source typeface for developers](https://www.jetbrains.com/ko-kr/lp/mono/)
    
    1. 글꼴 파일 받아서 .tff 파일까지 접근해 선택 > 마우스 우클릭 > 설치 
    2. VS code 다시 시작 
    3. File > preference > settings > Font > 직접 editing 들어가기 (setting.jeson 파일 접속)
    4. 아래 내용 첨부하고 저장 > 바로 적용되는 것 확인 가능 
        
        ```python
        "editor.fontFamily": "Jetbrains Mono",
        "editor.fontLigatures": true,
        ```
        
    5. 글꼴 권장 설정 - 크기: 13  줄 간격: 1.2
    
    ----
    
    여기까지 내가 정확히 아는 내용의 공유! 
    
    오늘도 나의 코린이 동지들에게 도움이 되기를 바라며! 끝!