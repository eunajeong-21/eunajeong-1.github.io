---
layout: post
title: "Jekyll 테마에 카테고리 추가하기"
date: 2018-11-17
excerpt: "사용중인 지킬 테마에 'category'를 추가해 보았습니다."
tag:
- markdown
- jekyll
category: [ Jekyll 블로그 ]
feature: https://png93.github.io/assets/img/title/basic.jpg
comments: true
---


현재 사용중인 지킬 테마를 선택할 때, 태그 기능이 깔끔하게 구현되어 있었기 때문에 "오 이거 카테고리로 이용하면 되겠다!" 라는 생각에 Fork하여 사용하게 되었는데요.  

아직까진 tag만 사용하다가, 글이 더 많아지기 전에 카테고리를 만들어 놓는게 좋겠다 싶어서 여기저기 참고하며 만들어 보았습니다.  

[지킬 공식 페이지의 카테고리 설명](https://jekyllrb-ko.github.io/docs/posts/#%ED%8F%AC%EC%8A%A4%ED%8A%B8%EC%9D%98-%EC%B9%B4%ED%85%8C%EA%B3%A0%EB%A6%AC%EC%99%80-%ED%83%9C%EA%B7%B8-%ED%91%9C%EC%8B%9C%ED%95%98%EA%B8%B0)  
{: .notice}

[참고한 블로그](https://devyurim.github.io/development%20environment/github%20blog/2018/08/07/blog-6.html)  
{: .notice}


만들면서 느낀 점을 말하자면,  
코드 부분은 사용하는 지킬 테마에서 뽑아오거나, 간단하게 만들수 있기 때문에  
지킬의 __디렉토리 구조__ 를 이해하는게 제일 중요한 것 같아요!


# 카테고리 만든 과정

1. [categories 폴더와 index 페이지 만들기](#categories-폴더에-index-페이지-생성하기)
2. [category 레이아웃 만들기](#category-레이아웃-만들기)
  2-1. [layout이 category인 마크다운문서 만들기](#layout이-category인-마크다운문서-만들기)

## 미리 요약
1. categories/index.html 만들기
2. \_layouts 폴더에 category.html 만들기
3. categories 폴더에 카테고리 이름과 동일한 이름의 markdown문서 만들기
4. markdown 문서에는 layout: category, title: "카테고리" 작성하기

- - -

## categories 폴더에 index 페이지 생성하기

<hly> __categories/index.html__ 파일을 가장 먼저 만들어 주세요~ </hly>  
그리고 보여주고 싶은 내용을 index.html에 작성해줍니다.  

~~~html
{% capture site_categories %}{% for category in site.categories %}{{ category | first }}{% unless forloop.last %},{% endunless %}{% endfor %}{% endcapture %}
{% assign categories_list = site_categories | split:',' | sort %}
~~~

위 코드는 tags/index.html의 코드를 재사용한 categories/index.html의 일부 인데요, tags 부분을 categories로 바꿔주었습니다.  

처음엔 이게 당최 무슨 언어인가 했는데, 'Liquid' 라는 언어라고 합니다.. 액체 언어... 처음 들었어요..ㅎㅎ  

찾아보니 아래의 사이트에 사용법들이 잘 정리되어 있고, 막 엄청 어렵지는 않아요?  

[Liquid 사이트](http://shopify.github.io/liquid/)  
{: .notice}

아무튼 저 코드는 <hly>__site.categories__ 의 정보를 __site_categories__ 라는 변수에 담고,  
site_categories 에서 카테고리 이름들을 __categories_List__ 라는 변수에 담는 일을 하는구나~</hly> 정도로 이해했습니다.  

그래서 다음 코드를 보면,  
반복문을 이용해서 <hly>categories_list</hly> 안의 카테고리들을 꺼내 보여주는 작업을 하고 있습니다.

~~~html
<ul class="entry-meta inline-list">
  {% for item in (0..site.categories.size) %}{% unless forloop.last %}
    {% capture this_word %}{{ categories_list[item] | strip_newlines }}{% endcapture %}
  	<li><a href="#{{ this_word }}" class="tag"><span class="term">{{ this_word }}</span> <span class="count">{{ site.categories[this_word].size }}</span></a></li>
  {% endunless %}{% endfor %}
</ul>

{% for item in (0..site.categories.size) %}{% unless forloop.last %}
  {% capture this_word %}{{ categories_list[item] | strip_newlines }}{% endcapture %}
	<article>
	  <a href="{{site.url}}/categories/{{this_word}}">
     <h2 id="{{ this_word }}" class="tag-heading">{{ this_word }}</h2>
    </a>
	    <ul>
    {% for post in site.categories[this_word] %}{% if post.title != null %}
      <li class="entry-title"><a href="{{ site.url }}{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a></li>
    {% endif %}{% endfor %}
		</ul>
	</article><!-- /.hentry -->
{% endunless %}{% endfor %}
~~~


위와 같은 categories/index.html 을 만들어 준 후,  
_(블로그 주소)/categories/_ 에 접속하면 내가 만들어준 카테고리별로 정리된 페이지가 나옵니다.  

![](https://png93.github.io/assets/img/make-category-1/01.png)  


## category 레이아웃 만들기

다음으로 카테고리별로 포스트 목록을 보여주는 페이지를 만들기 위해서  

<hly>Jekyll 테마의 디렉토리 중 \_layouts 폴더에 category.html을 만들어 줍니다!</hly>  

이번엔 post-list.html 의 코드에서 수정이 필요한 부분만 바꿨어용  

~~~html
<div class="post-list">
      {% assign category = page.title %}
      {% for post in site.categories[category] %} <!-- 카테고리 조건 -->
            <ul>
              <!-- post 제목 나열 -->              
            </ul>
      {% endfor %}
</div>
~~~

{% assign category = page.title %}  
바로 다음에 설명하겠지만, category 레이아웃을 사용하는 page의 title은 카테고리와 동일하게 설정해야 합니다.  
위 코드는 현재 페이지의 title을 category 라는 변수에 할당하는 일을 합니다.  

{% for post in site.categories[category] %}  
여기선 위에서 얻어온 category와 동일한 category를 가지는 post 들만 뽑아오게 됩니다.  


## layout이 category인 마크다운문서 만들기  

레이아웃을 만들었으니 사용을 해야겠죠!:)  

맨 처음에 만들었던 categories 폴더에  
__카테고리 이름과 동일한 이름의 마크다운문서__ 를 추가해 줍니다.

![](https://png93.github.io/assets/img/make-category-1/03.JPG)  

각 파일은 'YAML 머리말' 의 layout과 title만 가지면 끄읕.
Algorithm 을 예로 들면 아래와 같이 작성하면 됩니다.
~~~
---

layout: category
title: Algorithm

---
~~~


이제 각각의 카테고리는 다음과 같은 페이지를 나타낼 수 있습니다.  

![](https://png93.github.io/assets/img/make-category-1/02.png)


- - -

이상으로 만들고 보니 뿌듯한 카테고리 만들기 설명이었습니다(ㅎㅎ)  
