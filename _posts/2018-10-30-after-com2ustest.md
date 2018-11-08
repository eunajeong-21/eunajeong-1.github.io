---
layout: post
title: "[취준] 필기테스트 정리"
date: 2018-10-30
excerpt: "제대로 못푼 문제 위주"
tag:
- 취준
comments: true
---

## 목차

* [세션과 쿠키의 차이](#session과-cookie)
* [__encryption과 hashing의 차이__](#encryption과-hashing)
* [__clustered index와 Non clustered index__](#clusteredindex와-nonclusteredindex)
* [스택, 큐, 덱의 차이](#stack)
* outer join
* GROUP BY
* JavaScript
  - [__undefined와 null의 비교__](#undefined와-null)
  - [=== 연산](#일치-연산자)
  - 전위증가, 후위증가 연산
* 정렬 알고리즘

- - -

## session과 cookie

### 1. session ?


### 2. cookie ?

### 3. 차이점 정리

- - -

## encryption과 hashing

### 1. encryption ?
[암호화]  
- '키'를 사용하여 암호화와 복호화를 수행(양방향)
- 대칭형 암호화와 비대칭형 암호화가 있음

대칭형 암호화  
- 암호화와 복호화에서 동일한 키(=대칭키)를 공유하는 방법
- 안전하지 않다는 단점이 있음

비대칭형 암호화  
- 공개키와 비밀키 두개를 사용하는 방법
- 대칭형에 비해 안전하지만, 속도가 느림


### 2. hashing ?
- 데이터를 '고정된'길이의 데이터로 매핑하는 방법
- 해시 알고리즘마다 매핑하는 데이터의 길이, 매핑하는 방법이 다양
- 단방향성 -  암호화만 가능하며 한번 암호화 되면 복호화 불가
- 복호화가 필요없는 비밀번호 등에 사용되며, 입력 값에 대해 '해시 값'이 일치하는지에 대한 확인을 수행
- 해싱의 문제점 - 충돌(Collision): 서로 다른 입력 값에 대해 같은 해시 값이 나오는 경우


### 3. 차이점 정리
Encryption은 '키'를 사용하며 '양방향'암호화 방식이고,  
Hashing은 '키'를 사용하지 않으며 '단방향'암호화 방식이다.

- - -

## ClusteredIndex와 NonClusteredIndex

### 1. clustered index

### 2. non clustered index
- - -

## Stack

- - -
## undefined와 null
### 1. undefined
자바 스크립트의 자료형 중 하나로 <hly>선언하지 않은 변수</hly> 또는 <hly>선언 했지만 초기화 하지 않은 변수</hly>를 undifined 자료형 이라고 함  
~~~
  alert(typeof (variable));
~~~
위와 같은 코드가 실행되면, undefined 라고 출력
* typeof(): 숫자, 문자열, bool 과 같은 자료형을 확인하는 함수  

- 자바스크립트에서 __Boolean(undefined) 는 false__

### 2. undefined와 null의 차이
- - -
## 일치 연산자
<자바스크립트의 일치 연산자>  
자료형을 확실하게 구분하고자 할 때 사용.  
<hlr>자료형과 값이 모두 일치</hlr>하는지 확인.
~~~
=== : 양쪽 자료형과 값이 일치하는지 확인
!== : 양쪽 자료형과 값이 불일치하는지 확인
~~~

~~~
  alert(0 == false);  //true 출력
  alert(0 === false); //false 출력 (좌변은 숫자 자료형, 우변은 bool 자료형)
~~~
