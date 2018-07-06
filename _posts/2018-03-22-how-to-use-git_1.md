---
layout: post
title: "git 사용법, how to use git"
date: 2018-03-22
excerpt: "git-bash를 사용하기 위한 기초적인 명령어, github과 연동하는 방법"
tag:
- Git
feature: https://cdn.pixabay.com/photo/2016/02/19/11/19/computer-1209641_1280.jpg
comments: true
---

github에 repository가 먼저 만들어져 있고,
로컬이랑 연결할 때


초기 설정
--
- - -

### 1. name, email 입력하기
$ git config --global user.name "깃허브 닉네임"

$ git config --global user.email "깃허브 이메일계정"

### 2. 원격 저장소 내 컴터로 복사하기
$ git clone "내 git repository 주소"

ex) $ git clone "https://github.com/png93/png93.gihub.io.git"
