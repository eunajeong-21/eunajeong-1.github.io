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

###1. 한 번만 하면 되는 초기 설정

사용할 jekyll테마를 내 github으로 복사하면서 저장소가 만들어진 상태였기 때문에, 컴퓨터에 작업할 디렉토리를 생성하는 것부터 시작했습니다.

D:\gitblog 폴더를 만들고, '여기에서 파일을 올리고 내려받고 이것저것 할거야' 라고 지정해 주었어요.

<img src="assets/img/post_img/git-bash_initial_commands.png">



### 1. name, email 입력하기
$ git config --global user.name "깃허브 닉네임"

$ git config --global user.email "깃허브 이메일계정"

### 2. 원격 저장소 내 컴터로 복사하기
$ git clone "내 git repository 주소"

ex) $ git clone "https://github.com/png93/png93.gihub.io.git"
