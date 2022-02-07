---
layout: single
title:  "Git 처음 시작하기의 모든 것"
author_profile: false
---

git을 공부해야 하는데 정보가 너무 많아서 정신 못 차리던 중 관련 수업이 진행되었다. 
가려운 부분을 많이 긁어준 수업이었다. 
영상으로도 좋은 소스가 많지만 나 같은 text중독자는 글로 정리해 두고 한 번 찬찬히 보는게 나중에 편할 것 같다.

그럼 시작!

----

## 설치와 환경설정

1. Git 설치하기
    
    [Git](https://git-scm.com/)
    
    전부 기본값으로 설치 완료하기 > git bash 설치된 것 확인 > 열어서 다음 코드 입력해서 버전 확인
    
    ```basic
    $ git --version
    ```
    
    ** Vim Editor 사용 필요
    
2. SourceTree 설치하기 
    
    [Sourcetree | Free Git GUI for Mac and Windows](https://www.sourcetreeapp.com/)
    
    Bitbucket menu 선택 > 로그인 > 등록완료 > Mercurial 체크박스 해제 > github에 가입된 이름과 이메일 입력 > SSH키 아니오 
    
3. Git 환경설정
    
    Git Bash 프로그램 or CMD 프로그램 실행하여 다음과 같이 글로벌 사용자 등록, github 계정과는 별개지만 추후에 협업시에 누가 수정한건지 등의 기록을 남기기 위해 등록
    
    ```basic
    $ git config --global user.name "사용자 영문이름"
    $ git config --global user.email "사용자 이메일 주소"
    $ git config --list // q 버튼으로 원래 화면으로 돌아오기
    $ git config --global core.autocrlf true // 호환성을 위해 설정
    $ git config --global init.defaultBranch main // 기존의 master라는 기본 이름 셋팅값을 main으로 변경
    ```
    
    - 명령어 입력하고 엔터치는 동안 별 반응이 없을 것임
    - 다 작성한 뒤에는 마지막 코드와 같이 list 입력하여 입력한 내용이 등록되었는지 확인할 수 있음
    - 내용 확인하고 빠져 나올때는 q 버튼으로 원래 화면으로 돌아오기
    - core.autocrlf 코드는 Mac, linux 와 window OS 사이에 문자열바꿈 코드가 달라서 발생할 수 있는 오류 방지하기 위한 설정
    

---

## Repository (저장소) 생성

기록 원하는 폴더 최상위로 들어가서 마우스 우클릭 > git bash here

or 

VScode에서 해당 폴더로 접근, 하단에 Bash terminal 열기

<img src="..\images\220207\gitbash.png" width="100%" title="Actions" />



### 명령어 정리

- Reposiroty 초기화 (git init)
    
    ```basic
    $ git init  
    
    Initialized empty Git repository in C:/Users/user/sample-repo/.git/
    ```
    
    - 현재 경로 이하로 git local repository 생성 -> .git 숨김폴더 생성 확인
    
- 파일의 생성  ex) [README.md](http://README.md) 파일 생성
    
    ```basic
    user@LAPTOP-GE8TFFGF MINGW64 ~/sample-repo (main)
    $ echo 'Hello, Git!' > README.md
    
    user@LAPTOP-GE8TFFGF MINGW64 ~/sample-repo (main)
    $ cat README.md
    Hello, Git!
    ```
    
    - echo 명령어로 새 파일과 내용까지 한번에 작성
    - cat 명령어로 파일과 내용 확인
    
- Repository 상태 확인 (git status)
    
  <img src="..\images\220207\status.png" width="100%" title="Actions" />
    
    파일만 만들고 나면 이는 Working directory에 있는 상태 
    
    stage로 올려서 tracking 하도록 해야한다. 
    
    다음과 같이 확인할 수 있다. 
    
    ```basic
    $ git status
    On branch main
    
    No commits yet
    
    Untracked files:
      (use "git add <file>..." to include in what will be committed)
            README.md
    
    nothing added to commit but untracked files present (use "git add" to track)
    ```
    
    - 방금 만든 [README.md](http://README.md) 파일을 아직 올리지 않았기 떄문에 untracked 라고 나옴

- 파일 등록 (git add) - commit 직전에 필수적!
    
    ```basic
    $ git add .  OR  add [파일명]  
    
    warning: LF will be replaced by CRLF in README.md.
    The file will have its original line endings in your working directory
    ```
    
    - ‘.’  :  전체파일 추적(tracked) 상태로 하겠다. staging 위치로 옮기겠다.
    - [파일명] : 해당 파일만 staging 하겠다.
    - 등록 후 다시 상태 확인 해 보면 다음과 같이 changes 볼 수 있다.
        
        초록색은 add 된 것 빨간색은 add 안 된 것
        
        ```basic
        $ git status
        On branch main
        
        No commits yet
        
        Changes to be committed:
          (use "git rm --cached <file>..." to unstage)
                new file:   README.md
        ```
        
    - add 한 이후에 또 수정하고 나면 다시 staging해야 하므로 계속 add 해 줘야 함

- working/staging 변경내용 비교 (git diff)
    
    ```basic
    $ git diff 
    
    warning: LF will be replaced by CRLF in README.md.
    The file will have its original line endings in your working directory
    diff --git a/README.md b/README.md
    index 670a245..e8fe9e9 100644
    --- a/README.md
    +++ b/README.md
    @@ -1 +1,2 @@
     Hello, Git!
    +This is a change.
    \ No newline at end of file
    ```
    
    - staging되어 있는 내용과 현재 working 중인 내용 변경사항 자세히 확인 가능 (tracking 중인 파일에 한함)
    
- Commit, repository에 반영시킴 (git commit)
    
    ```basic
    $ git commit   
    OR 
    $ git commit -m "원하는 제목 like : FIRST COMMIT"  
    
    [main (root-commit) bef9415] first sample commit
     1 file changed, 1 insertion(+)
     create mode 100644 README.md
    ```
    
    - 옵션 없이 commit하게 되면 저장하는 모드 진입 -> Vim editor, 원하는 제목 작성하고 저장하고 빠져나오기 (:wq)
    - -m 옵션, “commit mesaage” 내용 작성하여 바로 커밋, 저장 가능
    - commit 할 때에는 다 완성한 상태로 커밋하는 것이 아니라 초기 모델부터 시작해서 모듈로 세분화하여 하나가 완성되거나 초기 빌드가 될 때마다 해 주는 것이 더 의미있다고 할 수 있다.
    - 오류 하나가 고쳐지면 그 내용에 대한 commit만 진행하는 것이 더 의미있음 + 알맞은 제목을 달아주는 것도 필수적
    - commit 한 이후에 status 확인하면 다음과 같은 메세지 확인 가능
        
        ```basic
        $ git status
        
        On branch main
        nothing to commit, working tree clean
        ```
        

- 커밋 이력 확인하기 (git log)
    
    ```basic
    $ git log
    
    commit 3df91849bb6869be61ee0650bc73d56f945b7da9 (HEAD -> main)
    Author: Jiyoung Yoo <joy_ji0@naver.com>
    Date:   Mon Feb 7 17:19:08 2022 +0900
    
        second sample commit
    
    commit bef9415a99c2a6a4928e8f6eedff23cec5d7ea5b
    Author: Jiyoung Yoo <joy_ji0@naver.com>
    Date:   Mon Feb 7 17:16:23 2022 +0900
    
        first sample commit
    ```
    
    - commit message, commit id 등 확인 가능
    - (HEAD -> main) 있는 걸로 내 지금 시점 확인 가능
    
- 변경 취소 (git reset)
    
    staging 취소, working 까지도 전체 변경 취소, 혹은 특정 commit 상태로 되돌리기
    
    ```basic
    $ git reset
    
    Unstaged changes after reset:
    M       README.md
    
    $ git reset --hard
    HEAD is now at 3df9184 second sample commit
    
    $ git reset --hard [commit id]
    ```
    
    - —hard 옵션을 통해 working 까지도 전체 취소하고 직전 commit 상태로 돌아감. 이 경우 변경내용이 모두 소멸되기 때문에 주의할 것
    - log에서 확인한 commit id를 통해 그 시점으로 전체 되돌리기 가능
    

---

## github (remote repository) 연결하기 (mapping)

commit한 내용을 다른 사람들과 공유하기 위해서는 github에 보내줘야하므로 연결이 필요하다.

- 우선 github에서 repository 생성
    
    <img src="..\images\220207\newrepo.png" width="100%" title="Actions" />    
    - 생성하면 맨 처음 나타나는 화면
    
- 연결하기
    
    ```basic
    $ git remote add origin https://github.com/joyful-ji0/sample-repo.git
    ```
    
    - 위 내용은 github에서 repository 만들면 나타나는 화면에서 복붙할 수 있음
    - 내 git 내용을 위의 repository로 보내겠다.
    - add origin 명령을 통해 해당 주소의 별명 origin 생성, 매번 전체 입력하기 불편하므로
    - 엔터 눌러도 아무일도 안생김

- 연결 확인하기
    
    ```basic
    $ git remote -v
    
    origin  https://github.com/joyful-ji0/sample-repo.git (fetch)
    origin  https://github.com/joyful-ji0/sample-repo.git (push)
    
    $ git remote show [타겟별칭]
    ```
    
    - -v 옵션 붙여별칭과 함께 연결된 주소 나타남, 연결된 repository 정보 확인 가능
    - show 옵션을 통해서는 좀 더 자세한 정보 확인 가능

- 원격 서버 관리
    
    ```basic
    $ git remote rename [변경전별칭] [변경후별칭]  // 이름 바꾸기
    $ git remote rm [타겟별칭] // 원격서버 연결 삭제
    ```
    

---

## Remote repository에 clone, push, pull

  <img src="..\images\220207\remote.png" width="100%" title="Actions" />    

- branch 확인 우선
    
    ```basic
    $ git branch -M main
    ```
    
- Push
    
    github에 업로드 하는 것 
    
    ```basic
    $ git add .  
    $ git status  
    $ git commit -m "commit message"  
    
    $ git push -u origin main  
    
    Enumerating objects: 15, done.
    Counting objects: 100% (15/15), done.
    Delta compression using up to 8 threads
    Compressing objects: 100% (7/7), done.
    Writing objects: 100% (15/15), 1.20 KiB | 408.00 KiB/s, done.   
    Total 15 (delta 1), reused 0 (delta 0), pack-reused 0
    remote: Resolving deltas: 100% (1/1), done.
    To https://github.com/joyful-ji0/sample-repo.git
     * [new branch]      main -> main
    Branch 'main' set up to track remote branch 'main' from 'origin'.
    
    ```
    
    - main branch에 push 성공

- Clone
    
    remote repository의 내용 ‘전부’를 local에 받기
    
    아래 코드는 앞서 업로드한 원격 저장소를 다른 이름의 로컬 저장소로 복제하는 용도
    
    ```basic
    $ cd [메인폴더]
    $ mkdir [복제할 새 폴더명]
    $ cd [방금 만든 폴더]     -- clone 복제할 폴더에 위치한 상태에서 
    
    $ git clone [복제하려는 repository URL]
    
    $ ls -all  -- 복제한 목록 전체 확인 가능
    ```
    

- Pull
    
    remote repository의 ‘변경을 local에 통합’시키기 (정보의 최신화, 갱신)
    
    이 과정에서 fetch - 정보 업데이트, merge - 정보통합 : 두가지 조작 수행
    
    ```basic
    $ git pull
    
    remote: Enumerating objects: 4, done.
    remote: Counting objects: 100% (4/4), done.
    remote: Compressing objects: 100% (2/2), done.
    remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
    Unpacking objects: 100% (3/3), 744 bytes | 148.00 KiB/s, done.
    From https://github.com/joyful-ji0/sample-repo
       bd313bf..e96e8fe  main       -> origin/main
    Updating bd313bf..e96e8fe
    Fast-forward
     README.md | 1 +
     1 file changed, 1 insertion(+)
     create mode 100644 README.md
    
    user@LAPTOP-GE8TFFGF MINGW64 ~/sample-repo (main)
    $ ls
    README.md  child-dir/  sample.txt
    
    $ git pull
    Already up to date.
    ```
    
    - pull 해온 내용 보여줌
    - ls로 확인 가능
    - 이미 최신이라면 ‘Already up to date.’라고 알려줌

---

## Branch

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/b095157f-ade0-43e6-8d6f-41da3b7c737a/Untitled.png)

- Branch 확인
    
    ```basic
    $ git branch
    
    * main
    ```
    
    - 처음에는 main branch 하나만 존재

- Branch 생성
    
    ```basic
    $ git branch [branch명 - dev]
    
    $ git branch
      dev
    * main
    ```
    
    - dev branch 생김
    
- Branch 전환
    
    ```basic
    $ git checkout [branch명 - dev]
    
    $ git checkout -b feature1
    Switched to a new branch 'feature1'
    
    user@LAPTOP-GE8TFFGF MINGW64 ~/sample-repo (feature1)
    ```
    
    - 이동하면 (feature1) 이런 식으로 현재 브랜치 위치 보여주기 떄문에 확인 용이
    - -b 옵션을 통해 branch 형성하면서 전환도 가능
    
- commit 후 반영하여 원격 repository에 보내기
    
    ```basic
    $ git push -u origin dev 
    ```
    

---

드디어 git을 공부했다!!!! 

git을 안정적으로 사용하려면 워킨디렉토리를 깨끗하게 치우면서 해야 한다는데 관련 내용은 천천히 공부해서 추가하겠다.

또한 추후 팀 프로젝트 진행을 위해서는 병합에 대해서도 공부할 필요가 있다. (아래 책 8장)
[Git 교과서 - YES24](http://www.yes24.com/Product/Goods/89522012)


드디어 git을 좀 제대로 이해한 기념으로 블로그에 남겼다. 
이 글이 git을 시작해야하는데 정보가 많아서 힘든 이들에게 도움이 되기를 바란다.

오늘의 글 끝!