---
layout: post
title: "git 사용법, how to use git"
date: 2018-07-08
excerpt: "git-bash를 사용하기 위한 기초적인 명령어, github과 연동하는 방법 등"
tag:
- Git
- Git bash
- github
feature: https://cdn.pixabay.com/photo/2017/10/31/19/05/web-design-2906159__480.jpg
comments: true
---

개발자가 되고자 하기 때문에, 공부하는 내용이나 앞으로 하게 될 프로젝트들을 정리할 나만의 공간을 만들어 놓으면 여러모로 좋을 것 같다는 생각이 들었습니다.
기억력을 믿으면 안되요. 기록을 해 놓는 것이 가장 좋은 방법이죠.

이러한 이유로 저는 github pages를 이용해서 블로그를 만들어 보게 되었습니다.


이 글에서는 github 저장소를 관리하기 위한 아주아주 기초적인 git 사용법을 설명해 보도록 하겠습니다.

- - -


### 1. 한 번만 하면 되는 "초기 설정"

사용할 jekyll테마를 내 github으로 복사하면서 저장소가 만들어진 상태였기 때문에, 컴퓨터에 작업할 디렉토리를 생성하는 것부터 시작했습니다.

D:\gitblog 폴더를 만들고, '여기에서 파일을 올리고 내려받고 이것저것 할거야' 라고 지정해 주었어요. git-bash를 실행한 후 아래의 순서대로 명령어를 입력 해주면 됩니다.

![git-command](https://png93.github.io/assets/img/post_img/git-bash_initial_commands.PNG)

차례대로 명령어들을 살펴볼께요.

<kbd>cd</kbd>  : 디렉토리 변경.

<kbd>git init</kbd>  :  git 저장소 초기화.

<kbd>git config user.name "user name"</kbd>  : github의 username 입력

<kbd>git config user.email "user email"</kbd>  : github에서 사용하는 이메일 계정 입력

<kbd>git clone "Repository 주소"</kbd>  : 원격 저장소를 현재 로컬 디렉토리로 복사.

Repository 주소는 내 저장소 상단 오른쪽에 보면, 'Clone or download'라는 초록색 버튼이 있는데 여기서 복사 해올 수 있어요.

여기까지 완료했다면 기본적인 설정은 끝낸거라고 보면 됩니다.



### 2. github 저장소 변경 사항 가져오기 & 파일 github 저장소에 올리기

블로그를 만들고 git으로 원격 저장소와 로컬(내 컴퓨터)을 연결 해 주었으니 이제  글을 써서 올려볼거에요.


jekyll로 만든 블로그는 **markdown** 이라는 형식을 지원하는데
css나 html처럼 원하는 형식을 지정해주면서 글을 써내려 갈 수 있기 때문에 잘 사용하면 굉장히 편할 거 같습니다.

처음 접하는 형식이지만, 어려운 건 없어서 사용하다보면 금방 익숙해 질 것 같아요!

저는 markdown 문서를 편집하기 위해 Atom을 설치했는데, [Atom 홈페이지](https://atom.io/) 에 들어가면 무료로 다운 받을 수 있습니다.

새로운 글을 쓰고, 파일을 올릴 준비가 되었다면 다음과 같은 방법으로 원격 저장소에 반영할 수 있습니다.

**▼원격 저장소에 새로운 파일 올리기 ▼**
