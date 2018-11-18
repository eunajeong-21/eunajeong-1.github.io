---
layout: post
title: "git 사용법, how to use git"
date: 2018-07-08
excerpt: "git-bash를 사용하기 위한 기초적인 명령어, github과 연동하는 방법 등"
tag:
- Git
- Git bash
- github
category: [ Git ]
feature: https://png93.github.io/assets/img/title/git.png
comments: true
---

많은 기술 블로그들을 보면서,
공부하는 내용과 프로젝트들을 정리할 수 있는 공간을 만들어 놓으면 여러모로 좋겠다는 생각이 들었습니다.
아직은 신입 개발자에 지원하고 있는 햇병아리 취준생이라 아주 전문적인 글을 쓰지는 못하겠지만,
우선 지금 하고 있는 알고리즘 공부에 대한 정리부터 시작해 보려고 합니다.  


글을 쓰면서 머리 속에 다시 한번 정리 되는 효과도 있고, 나만의 자료가 남는다는 장점도 있기에 자주는 못 쓰더라도 "꾸준히" 쓰는 것을 목표로 삼았습니다. &#128588;

<br/>
이러한 이유로 github pages를 이용한 블로그를 만들게 되었습니다.  
많은 블로그 중에서도 github pages와 Jekyll의 조합에 흥미가 생겨서 직접 해보니 손이 많이 가긴 해도 내 마음대로 만들어 갈 수 있다는 게 짱짱!  


아무튼, 이 글에서는 github 블로그를 관리할 때 필요한 아주아주 기초적인 git 사용법을 정리해 보겠습니다 :)


---
## contents
1. [초기설정](#초기설정-init-config-clone)
2. [변경사항 반영하기](#pull-add-commit-push)
3. [파일 삭제하기](#삭제-명령어-rm)
4. [기타 명령어](#그-외-명령어)
---

## 초기설정 init config clone

사용할 jekyll테마를 내 github으로 복사하면서 저장소가 만들어진 상태였기 때문에, 컴퓨터에 작업할 디렉토리를 생성하는 것부터 시작했습니다.

저는 `D:\gitblog` 폴더를 만들고, '여기에서 파일을 올리고 내려받고 이것저것 할거야' 라고 지정해 주었어요.  
git-bash를 실행한 후 아래의 순서대로 명령어를 입력 해주면 됩니다.

<figure>
  <img src = "https://png93.github.io/assets/img/post/git-bash_initial_commands.jpg">
</figure>

차례대로 명령어들을 살펴볼께요.

<kbd>cd</kbd>  : 디렉토리 변경.

<kbd>git init</kbd>  :  git 저장소 초기화.

<kbd>git config user.name "user name"</kbd>  : github의 username 입력

<kbd>git config user.email "user email"</kbd>  : github에서 사용하는 이메일 계정 입력

<kbd>git clone "Repository 주소"</kbd>  : 원격 저장소를 현재 로컬 디렉토리로 복사.

Repository 주소는 내 저장소 상단 오른쪽에 보면, 'Clone or download'라는 초록색 버튼이 있는데 여기서 복사 해올 수 있습니다.

여기까지 완료했다면 기본적인 설정은 끝낸거라고 보면 됩니다.     

- - -

## pull add commit push

블로그를 만들고 git으로 원격 저장소와 로컬(내 컴퓨터)을 연결 해 주었으니 이제  글을 써서 올려보겠습니다.


jekyll로 만든 블로그는 **markdown** 이라는 형식을 지원하는데,
css나 html처럼 원하는 형식을 지정해주면서 글을 써내려 갈 수 있습니다.

처음 접하는 형식이지만, 어려운 건 없어서 사용하다보면 금방 익숙해 질 것 같네요ㅎㅎ

참고로 저는 markdown 편집기로 Atom을 설치했습니다.
[Atom 홈페이지](https://atom.io/) 에 들어가면 무료로 다운 받을 수 있어용

_markdown 문서의 파일 이름은 `YYYY-MM-DD-제목.md` 의 형식을 지켜 주어야 합니다._  
{: .notice}


**▼원격 저장소에 새로운 파일 올리기 ▼**
<figure>
  <img src = "https://png93.github.io/assets/img/post/git_upload_commands.PNG">
</figure>

참고로 git add와 git commit이 명령을 수행하는 단계가 있는데, 아래 그림처럼 동작합니다.

<center><img src = "https://png93.github.io/assets/img/post/git layer.png" width="60%"/></center>

<br/>

이제 명령어들을 차례대로 볼께요.

<kbd>git pull origin master</kbd>  :  원격 저장소의 변경 사항을 가져옴.

나중에 push 하면서 문제가 생길 수도 있기 때문에
파일을 올리기 전에 혹시 있을 변경 사항을 먼저 처리해 주는 게 좋습니다.

<kbd>git add 파일이름</kbd>  :  staging area에 파일 올리기.

( <kbd>git add .</kbd>  : working directory 내의 모든 파일을 staging area에 올리기. )

<kbd>git commit -m "커밋 메세지"</kbd>  : 인라인 메세지를 입력하는 커밋.

( <kbd>git commit</kbd> 명령어도 있는데, 인라인 메세지를 사용하는 게 간편해요. )


<kbd>git push -u origin master</kbd>  :  원격 저장소에 저장.

---

## 삭제 명령어 rm

삭제는 `$git rm` 명령어를 사용합니다.

알아둘 점이 있다면, `$git rm`은 원격 저장소와 로컬의 폴더 또는 파일을 모두 삭제하고,  
`$git rm --cached` 속성을 사용하면 __원격 저장소에서만__ 삭제 됩니다.

예를 들어 github 저장소에 \_posts/test 라는 폴더를 삭제하려면 다음 명령어들을 입력하면 됩니다.

<figure>
  <img src = "../assets/img/post/git_remove_commands.PNG"/>
</figure>

파일 삭제는 원격 저장소에서만 삭제 하려면 `$git rm --cached <파일이름>`
원격 저장소와 로컬 두 곳 모두 삭제하려면  `$git rm <파일이름>`
{: .notice}


---

## 그 외 명령어

<kbd>git remote add origin `https://github.com/png93/png93.github.io` </kbd>  :  github 저장소와 연결하기 (초기설정)  

<kbd>git remote -v</kbd>  : 연결된 원격 저장소 확인  

<kbd>git status</kbd>  :  현재 상태 확인  

<kbd>:wq</kbd>  : Vim 편집기 화면에서 EXIT
