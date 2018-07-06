---
layout: post
title: "git bash 명령어(1)-연결하기"
categories: [git사용법]
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
