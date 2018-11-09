---
layout: post
title: "[취준] 기술 면접 대비 Spring 정리"
date: 2018-11-09
excerpt: "Spring Framework 요약 정리"
tag:
- 취준
comments: true
---

Spring의 주요 기능 / 특징
[1. MVC](#spring-mvc)
2. DI
3. AOP

- - -

# Spring MVC
- MVC는 __Model / View / Controller__ 의 약자
- 세 가지의 컴포넌트(?) 들이 유기적으로 동작
- <hlr>개발자가 직접 컴포넌트를 호출하지 않아도 자동으로 불러주며, 반복적인 작업을 줄여줌</hlr>
- 따라서 개발자는 핵심 로직에 집중할 수 있음

__[Spring MVC의 처리 과정]__  

![](https://png93.github.io/assets/img/post/spring_mvc_flow.PNG)  

1. DispatcherServlet이 클라이언트로 부터 요청을 받음
2. HandlerMapping을 통해 요청에 해당하는 Controller를 찾고
3. 해당 Controller로 요청을 보냄
4. Contoller에서 작업을 수행한 후 ModelAndView를 반환
5. ViewResolver에서 사용자에게 보여줄 View를 결정
6. DispatcherServlet이 View를 호출
7. 클라이언트에 해당 View가 보여짐

- - -
