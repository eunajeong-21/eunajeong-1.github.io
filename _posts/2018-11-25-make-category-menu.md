---
layout: post
title: "포스트 목록 페이지에 메뉴영역 추가하기"
date: 2018-11-25
excerpt: "지킬 테마에 category menu 영역을 추가해 보았습니다."
tag:
- markdown
- jekyll
category: [ Jekyll 블로그 ]
feature: ../assets/img/title/basic.jpg
comments: true
---

<figure class="half">
  <img src = "../assets/img/make-category-menu/01.png">
  <img src = "../assets/img/make-category-menu/02.png">
</figure>

첫 번째 사진은 제가 다운받은 테마의 원래 모습이고, 두 번째 사진은 category 메뉴 영역을 추가한 뒤의 모습입니다!  

어떻게 만들었는지 그 과정들을 작성해 볼게요. 레고! &#128540;  


## 순서  
1. [css로 위치 및 모양 설정하기](#css로-위치-및-모양-설정하기)
2. [post-list.html 파일 수정하기](#html-파일-수정하기)

## css로 위치 및 모양 설정하기

Jekyll 블로그 디렉토리를 보면 css 파일을 모아둔 곳이 있는데요.  
저는 `_sass/site.scss`에 사이트와 관련된 css가 설정되어 있어서 이곳에서 작업을 진행했습니다!  

아래와 같은 코드를 추가해 주었어요.
~~~css
.post_wrapper{
  float: right;
  width: 70%;
  margin: 2rem 1rem;
  position: relative;
	background: $white;
	color: $color_tuatara;
	padding: 2em;
	border-radius: 3px;
	box-shadow: 0 0 10px 0 rgba($color_shark,0.3);
	@include transition(.5s);
	@media #{$small} {
		width: 90%;
		padding: 2em 0;
	    box-shadow: none;
	}
}

.category_box {
  position: fixed;
  top: 8rem;
  left: 1rem;
  width: 25%;
	background: $white;
	color: $color_tuatara;
	padding: 2em;
	border-radius: 3px;
	box-shadow: 0 0 10px 0 rgba($color_shark,0.3);

    @media #{$small} {
		visibility: hidden;
	}
}
~~~

요렇게 만들어준 post_wrapper와 category_box css클래스는  
아래와 같은 html구조에서 사용하게 될거에요.  

~~~html
<header>
  <div class = "post_wrapper">
  </div>
  <div class = "category_box">
  </div>
</header>
~~~



## html 파일 수정하기
