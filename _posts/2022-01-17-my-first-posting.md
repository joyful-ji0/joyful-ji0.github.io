---
layout: single
title:  "Github Blog 첫 글 올리기, 그 험난함 (github-blog posting error TroubleShooting)"
author_profile: false
---

왜 하란대로도 하지 못하는 것이냐 😰

첫 글 올리는 것부터 난관이 많았다. 

변명일 수 있지만 하루종일 수업 듣다보면 집중력이 점점 바닥나서 점점 놓치는 것 천국이 되는 현실. 

### 오늘은 블로그 첫 글로 github blog에 글 포스팅 할 때 주의할 점에 대해 다룬다.

---

다음은 포스팅 할 때, 혹은 포스팅 실패하거나 원하는 포맷으로 올라가지 않았을 때 (나처럼) 해결을 위해 수정하는 화면이다.

<img src="..\images\220117\first-1.png" width="100%" title="수정화면" />


## 다음에 표시된 내용들을 주의하면 실패할 확률이 줄어든다.
(나는 무려 2, 3, 4, 5, 6번 항목에서 하나씩 문제가 있었다. 🤣🤣🤣)

<img src="..\images\220117\first-2.png" width="100%" title="수정화면 표시" />

1. 주소 생성할 때 내 아이디와 주소에 적인 아이디에 차이가 없는가
2. 경로 작성시에 _posts (언더바 + 포스트스!! S!!!) 로 작성했는가
3. 포스트 포멧을 잘 맞췄는가 (.md, 날짜와 제목? 사이에 언더바가 아닌 - 넣었는지)
4. Front matter 형식을 지켰는가 ( 위아래 - 3개씩! )
    
    ```markdown
    ---
    layout: post / single ... 
    title:  "오타는 나의 적"
    ---
    ```
    
5. title:  “제목” 큰 따옴표로 감쌌는가
6. 내용 Markdown 언어 형식에 문제는 없는가


---

## 추가로 posting 안될 때,

어느 지점에서 문제가 생겼는지 파악해 보려면 Actions 탭에 들어가면 상세내용을 확인할 수 있다.

여기서 실시간으로 진행상황을 볼 수 있어서 로딩 끝나는 걸 확인하고 블로그 화면에서 새로고침하면 조바심이 덜 난다.

<img src="..\images\220117\first-3.png" width="100%" title="Actions" />

이렇게 실행 실패한 경우에는 딱 티가난다. 

클릭하면 자세한 내용을 확인할 수 있다.

<img src="..\images\220117\first-4.png" width="100%" title="Actions_detail" />

이 경우에는 Environment 문제라고 판단되어 [_config.yml](https://github.com/joyful-ji0/joyful-ji0.github.io/blob/master/_config.yml) 파일을 다시 수정했다.

---

아직 마크다운 형식도 제대로 모르면서 이걸 어떻게 하면 좋을지 고민하다가 아주 유용한 내용을 알게되었다. 지금 모든 수업 내용 필기, 정리를 Notion에서 하고있는데 이를 활용할 수 있다는 것! 

Notion에서 작성한 문서를 Notepad++, VS code과 같은 텍스트 편집기에 복붙(copy&paste)하면 마크다운문법으로 작성된 문장이 기입된다는 것! 

이를 다시 포스팅 내용에 복붙하면 되니 아주아주 편리하다. 

** 얼마 전 까지는 Typora 프로그램이 편하고 무료였는데 유료로 전환 된 모양이다. 어떻게 해도 결제를 해야 사용할 수 있다. 나는 그래서 대체로써 VS code 프로그램을 사용하였다. (설정하는 방법은 다음 글에서 다룰 예정이다.)

아직 git도 제대로 모르면서 블로그부터 하다니 우습지만.. 

하나하나 알아가면 되지. 계속 성장만 하면 된다!고 위안 삼고있다.

이 글이 또 어디서 헤메이고 있을 깃린이에게 도움이 되길 바란다.  

---

### 참고

- **깃헙 블로그 만들기 : 시즌 1의 EP01, 02 까지 보자!**
    
    [깃헙(GitHub) 블로그 10분안에 완성하기](https://www.youtube.com/watch?v=ACzFIAOsfpM&t=474s)
    
- Posting 형식 등에 대하여
    
    [Posts](https://jekyllrb.com/docs/posts/)
    
- About Jekyll build errors for GitHub Pages sites
    
    [About Jekyll build errors for GitHub Pages sites - GitHub Docs](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/about-jekyll-build-errors-for-github-pages-sites)
    
- MarkDown 형식 등에 대해
    
    [마크다운(Markdown) 사용법](https://gist.github.com/ihoneymon/652be052a0727ad59601)
